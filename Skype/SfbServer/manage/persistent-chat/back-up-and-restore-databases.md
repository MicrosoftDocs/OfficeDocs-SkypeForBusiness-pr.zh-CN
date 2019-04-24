---
title: 在 Skype for Business Server 2015 中备份和还原持久聊天数据库
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要： 了解如何备份和还原业务服务器 2015 Skype 中的持久聊天服务器数据库。
ms.openlocfilehash: a07321c7e9167e830a7af472e9022b669a45c3e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222085"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="8cd71-103">在 Skype for Business Server 2015 中备份和还原持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="8cd71-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8cd71-104">**摘要：** 了解如何备份和还原业务服务器 2015 Skype 中的持久聊天服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="8cd71-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8cd71-105">持久聊天服务器需要 SQL Server 数据库软件存储聊天室数据，如历史记录和内容、 配置、 用户设置和其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="8cd71-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="8cd71-106">此外，如果您的组织需要的持久聊天活动要存档的法规且启用可选的合规性服务，SQL Server 数据库软件用于存储合规性数据，包括聊天内容和事件，如加入和离开聊天室。</span><span class="sxs-lookup"><span data-stu-id="8cd71-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="8cd71-107">持久聊天数据库 (mgc) 中存储聊天室内容。</span><span class="sxs-lookup"><span data-stu-id="8cd71-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="8cd71-108">合规性数据存储在合规性数据库 (mgccomp) 中。</span><span class="sxs-lookup"><span data-stu-id="8cd71-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="8cd71-109">这是应定期备份的业务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="8cd71-109">This is business-critical data that should be backed up regularly.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8cd71-110">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="8cd71-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="8cd71-111">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8cd71-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="8cd71-112">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="8cd71-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="8cd71-113">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="8cd71-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="back-up-the-databases"></a><span data-ttu-id="8cd71-114">备份数据库</span><span class="sxs-lookup"><span data-stu-id="8cd71-114">Back up the databases</span></span>

<span data-ttu-id="8cd71-115">有两种备份持久聊天数据。</span><span class="sxs-lookup"><span data-stu-id="8cd71-115">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="8cd71-116">SQL Server 备份</span><span class="sxs-lookup"><span data-stu-id="8cd71-116">SQL Server Backup</span></span>
    
- <span data-ttu-id="8cd71-117">**Export-cspersistentchatdata** cmdlet，将持久聊天数据导出为文件</span><span class="sxs-lookup"><span data-stu-id="8cd71-117">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="8cd71-118">使用 SQL Server 备份创建的数据明显需要更多磁盘空间，所需磁盘空间量可能是使用 **Export-CsPersistentChatData** cmdlet 创建的数据所需空间量的 20 倍以上，但您可能更熟悉 SQL Server 备份过程。</span><span class="sxs-lookup"><span data-stu-id="8cd71-118">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="8cd71-119">如果您希望使用 SQL Server 备份过程，请参阅 SQL 文档以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="8cd71-119">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="8cd71-120">如果您希望使用 **Export-CsPersistentChatData** cmdlet，您可以如下所示指定命令：</span><span class="sxs-lookup"><span data-stu-id="8cd71-120">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="8cd71-121">或者</span><span class="sxs-lookup"><span data-stu-id="8cd71-121">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="8cd71-p103">例如，以下命令可将持久聊天数据从位于服务器 atl-sql-001.contoso.com 上的持久聊天数据库中导出；导出的数据将存储在文件 C:\Logs\PersistentChatData.zip 中。因为没有指定 Level 参数，该命令将完全导出持久聊天信息：</span><span class="sxs-lookup"><span data-stu-id="8cd71-p103">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="8cd71-124">还原数据库</span><span class="sxs-lookup"><span data-stu-id="8cd71-124">Restore the databases</span></span>

<span data-ttu-id="8cd71-125">还原持久聊天数据的方式取决于您用来备份它的方法。</span><span class="sxs-lookup"><span data-stu-id="8cd71-125">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="8cd71-126">如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。</span><span class="sxs-lookup"><span data-stu-id="8cd71-126">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="8cd71-127">如果**Export-cspersistentchatdata** cmdlet 用于备份持久聊天数据，则必须使用**Import-cspersistentchatdata** cmdlet 还原数据：</span><span class="sxs-lookup"><span data-stu-id="8cd71-127">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="8cd71-128">或者</span><span class="sxs-lookup"><span data-stu-id="8cd71-128">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
