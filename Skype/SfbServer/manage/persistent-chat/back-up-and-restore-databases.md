---
title: 在 Skype for Business Server 2015 中备份和还原持久聊天数据库
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。
ms.openlocfilehash: 2c99f5e955756020f68b51ea214858c23fee0a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826372"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="43644-103">在 Skype for Business Server 2015 中备份和还原持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="43644-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="43644-104">**摘要：** 了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="43644-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="43644-105">持久聊天服务器SQL Server数据库软件来存储聊天室数据，如历史记录和内容、配置、用户设置和其他相关元数据。</span><span class="sxs-lookup"><span data-stu-id="43644-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="43644-106">此外，如果您的组织规定需要存档持久聊天活动，并且启用了可选的合规性服务，则 SQL Server 数据库软件用于存储合规性数据，包括聊天内容和事件（如加入和离开聊天室）。</span><span class="sxs-lookup"><span data-stu-id="43644-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="43644-107">聊天室内容存储在持久聊天数据库 (mgc) 。</span><span class="sxs-lookup"><span data-stu-id="43644-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="43644-108">合规性数据存储在合规性数据库 (mgccomp) 。</span><span class="sxs-lookup"><span data-stu-id="43644-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="43644-109">这是应定期备份的业务关键数据。</span><span class="sxs-lookup"><span data-stu-id="43644-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="43644-110">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="43644-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="43644-111">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="43644-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="43644-112">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="43644-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="43644-113">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="43644-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="43644-114">备份数据库</span><span class="sxs-lookup"><span data-stu-id="43644-114">Back up the databases</span></span>

<span data-ttu-id="43644-115">有两种方法可以备份持久聊天数据。</span><span class="sxs-lookup"><span data-stu-id="43644-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="43644-116">SQL Server备份</span><span class="sxs-lookup"><span data-stu-id="43644-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="43644-117">**Export-CsPersistentChatData** cmdlet，用于将持久聊天数据导出为文件</span><span class="sxs-lookup"><span data-stu-id="43644-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="43644-118">使用 SQL Server 备份创建的数据需要的磁盘空间明显多于 **Export-CsPersistentChatData** cmdlet 创建的磁盘空间（可能多于 20 倍），但 SQL Server 备份可能是您熟悉的过程。</span><span class="sxs-lookup"><span data-stu-id="43644-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="43644-119">如果要使用备份SQL Server，请参阅SQL文档了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="43644-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="43644-120">如果要使用 **Export-CsPersistentChatData** cmdlet，您可以按如下方式指定命令：</span><span class="sxs-lookup"><span data-stu-id="43644-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="43644-121">或者</span><span class="sxs-lookup"><span data-stu-id="43644-121">or</span></span>
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="43644-122">例如，以下命令从位于服务器的持久聊天数据库中导出持久聊天atl-sql-001.contoso.com;导出的数据将存储在文件C:\Logs\PersistentChatData.zip。</span><span class="sxs-lookup"><span data-stu-id="43644-122">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip.</span></span> <span data-ttu-id="43644-123">由于未指定 Level 参数，因此该命令将完全导出持久聊天信息：</span><span class="sxs-lookup"><span data-stu-id="43644-123">Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="43644-124">还原数据库</span><span class="sxs-lookup"><span data-stu-id="43644-124">Restore the databases</span></span>

<span data-ttu-id="43644-125">如何还原持久聊天数据取决于用于备份数据的方法。</span><span class="sxs-lookup"><span data-stu-id="43644-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="43644-126">如果使用了SQL Server过程，则必须使用SQL Server过程。</span><span class="sxs-lookup"><span data-stu-id="43644-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="43644-127">如果使用 **Export-CsPersistentChatData** cmdlet 备份持久聊天数据，则必须使用 **Import-CsPersistentChatData** cmdlet 还原数据：</span><span class="sxs-lookup"><span data-stu-id="43644-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="43644-128">或者</span><span class="sxs-lookup"><span data-stu-id="43644-128">or</span></span>
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
