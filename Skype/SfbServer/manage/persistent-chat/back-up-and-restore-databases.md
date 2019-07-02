---
title: 在 Skype for Business Server 2015 中备份和还原持久聊天数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: '摘要: 了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。'
ms.openlocfilehash: 0bb4895ef85ac9f38f2f9ef414769efcac6894b4
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417958"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="7e715-103">在 Skype for Business Server 2015 中备份和还原持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="7e715-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7e715-104">**摘要:** 了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="7e715-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7e715-105">持久聊天服务器要求 SQL Server 数据库软件存储聊天室数据, 如历史记录和内容、配置、用户预配和其他相关元数据。</span><span class="sxs-lookup"><span data-stu-id="7e715-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="7e715-106">此外, 如果你的组织具有要求存档持久聊天活动的法规, 并且启用了可选合规性服务, 则 SQL Server 数据库软件用于存储合规性数据, 包括聊天内容和事件, 例如加入和离开聊天室。</span><span class="sxs-lookup"><span data-stu-id="7e715-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="7e715-107">聊天室内容存储在持久聊天数据库 (mgc) 中。</span><span class="sxs-lookup"><span data-stu-id="7e715-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="7e715-108">合规性数据存储在合规性数据库 (mgccomp) 中。</span><span class="sxs-lookup"><span data-stu-id="7e715-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="7e715-109">这是应定期备份的业务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="7e715-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7e715-110">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="7e715-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="7e715-111">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="7e715-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="7e715-112">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="7e715-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="7e715-113">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="7e715-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="7e715-114">备份数据库</span><span class="sxs-lookup"><span data-stu-id="7e715-114">Back up the databases</span></span>

<span data-ttu-id="7e715-115">备份持久聊天数据有两种方法。</span><span class="sxs-lookup"><span data-stu-id="7e715-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="7e715-116">SQL Server 备份</span><span class="sxs-lookup"><span data-stu-id="7e715-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="7e715-117">**导出 CsPersistentChatData** cmdlet, 该 Cmdlet 将永久聊天数据导出为文件</span><span class="sxs-lookup"><span data-stu-id="7e715-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="7e715-118">使用 SQL Server 备份创建的数据明显需要更多磁盘空间，所需磁盘空间量可能是使用 **Export-CsPersistentChatData** cmdlet 创建的数据所需空间量的 20 倍以上，但您可能更熟悉 SQL Server 备份过程。</span><span class="sxs-lookup"><span data-stu-id="7e715-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="7e715-119">如果您希望使用 SQL Server 备份过程，请参阅 SQL 文档以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="7e715-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="7e715-120">如果您希望使用 **Export-CsPersistentChatData** cmdlet，您可以如下所示指定命令：</span><span class="sxs-lookup"><span data-stu-id="7e715-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="7e715-121">或者</span><span class="sxs-lookup"><span data-stu-id="7e715-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="7e715-p103">例如，以下命令可将持久聊天数据从位于服务器 atl-sql-001.contoso.com 上的持久聊天数据库中导出；导出的数据将存储在文件 C:\Logs\PersistentChatData.zip 中。因为没有指定 Level 参数，该命令将完全导出持久聊天信息：</span><span class="sxs-lookup"><span data-stu-id="7e715-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="7e715-124">还原数据库</span><span class="sxs-lookup"><span data-stu-id="7e715-124">Restore the databases</span></span>

<span data-ttu-id="7e715-125">还原持久聊天数据的方式取决于用于备份的方法。</span><span class="sxs-lookup"><span data-stu-id="7e715-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="7e715-126">如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。</span><span class="sxs-lookup"><span data-stu-id="7e715-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="7e715-127">如果你使用**Export CsPersistentChatData** Cmdlet 备份持久聊天数据, 则必须使用**CsPersistentChatData** cmdlet 还原数据:</span><span class="sxs-lookup"><span data-stu-id="7e715-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="7e715-128">或者</span><span class="sxs-lookup"><span data-stu-id="7e715-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
