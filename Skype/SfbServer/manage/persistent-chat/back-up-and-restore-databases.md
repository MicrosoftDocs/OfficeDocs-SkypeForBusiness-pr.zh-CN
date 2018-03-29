---
title: 在 Skype for Business Server 2015 中备份和还原持久聊天数据库
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要： 了解如何备份和恢复对于业务服务器 2015年在 Skype 的持久聊天服务器数据库。
ms.openlocfilehash: 419085219ea995c680fe31fcca3597a884ceba5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a><span data-ttu-id="ed7d1-103">在 Skype for Business Server 2015 中备份和还原持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="ed7d1-103">Back up and restore Persistent Chat databases in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ed7d1-104">**摘要：**了解如何备份和恢复对于业务服务器 2015年在 Skype 的持久聊天服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-104">**Summary:** Learn how to back up and restore Persistent Chat Server databases in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ed7d1-105">持久的聊天服务器需要 SQL Server 数据库软件存储聊天室数据，如历史和内容、 配置、 用户供应，以及其他相关的元数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-105">Persistent Chat Server requires SQL Server database software to store chat room data, such as history and content, configuration, user provisioning, and other relevant metadata.</span></span> <span data-ttu-id="ed7d1-106">此外，如果您的组织有需要进行存档的持久交谈活动的法规，并且启用了可选的法规遵从性服务，SQL Server 数据库软件用来存储法规遵从性数据，包括聊天内容和事件，如加入和离开房间。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-106">In addition, if your organization has regulations that require Persistent Chat activity to be archived, and the optional Compliance service is enabled, SQL Server database software is used to store compliance data, including chat content and events, such as joining and leaving rooms.</span></span> <span data-ttu-id="ed7d1-107">聊天室内容存储在持久聊天数据库 (mgc)。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-107">Chat room content is stored in the Persistent Chat database (mgc).</span></span> <span data-ttu-id="ed7d1-108">合规性数据存储在合规性数据库 (mgccomp) 中。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-108">Compliance data is stored in the Compliance database (mgccomp).</span></span> <span data-ttu-id="ed7d1-109">这是应定期备份的业务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-109">This is business-critical data that should be backed up regularly.</span></span> 
  
## <a name="back-up-the-databases"></a><span data-ttu-id="ed7d1-110">备份数据库</span><span class="sxs-lookup"><span data-stu-id="ed7d1-110">Back up the databases</span></span>

<span data-ttu-id="ed7d1-111">有两种方法备份数据持久聊天。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-111">There are two ways of backing up Persistent Chat data.</span></span> 
  
- <span data-ttu-id="ed7d1-112">SQL Server 备份</span><span class="sxs-lookup"><span data-stu-id="ed7d1-112">SQL Server Backup</span></span>
    
- <span data-ttu-id="ed7d1-113">**导出 CsPersistentChatData** cmdlet，持久聊天数据导出为一个文件</span><span class="sxs-lookup"><span data-stu-id="ed7d1-113">The **Export-CsPersistentChatData** cmdlet, which exports Persistent Chat data as a file</span></span>
    
<span data-ttu-id="ed7d1-114">使用 SQL Server 备份创建的数据明显需要更多磁盘空间，所需磁盘空间量可能是使用 **Export-CsPersistentChatData** cmdlet 创建的数据所需空间量的 20 倍以上，但您可能更熟悉 SQL Server 备份过程。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-114">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by the **Export-CsPersistentChatData** cmdlet, but SQL Server backup is likely to be a procedure with which you are familiar.</span></span>
  
<span data-ttu-id="ed7d1-115">如果您希望使用 SQL Server 备份过程，请参阅 SQL 文档以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-115">If you want to use SQL Server backup procedures, see your SQL documentation for more information.</span></span> 
  
<span data-ttu-id="ed7d1-116">如果您希望使用 **Export-CsPersistentChatData** cmdlet，您可以如下所示指定命令：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-116">If you want to use the **Export-CsPersistentChatData** cmdlet, you can specify the command as follows:</span></span>
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

<span data-ttu-id="ed7d1-117">或者</span><span class="sxs-lookup"><span data-stu-id="ed7d1-117">or</span></span>
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

<span data-ttu-id="ed7d1-p102">例如，以下命令可将持久聊天数据从位于服务器 atl-sql-001.contoso.com 上的持久聊天数据库中导出；导出的数据将存储在文件 C:\Logs\PersistentChatData.zip 中。因为没有指定 Level 参数，该命令将完全导出持久聊天信息：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-p102">For example, the following command exports Persistent Chat data from the Persistent Chat database located on the server atl-sql-001.contoso.com; the exported data will be stored in the file C:\Logs\PersistentChatData.zip. Because the Level parameter was not specified, the command will do a full export of the Persistent Chat information:</span></span>
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a><span data-ttu-id="ed7d1-120">还原数据库</span><span class="sxs-lookup"><span data-stu-id="ed7d1-120">Restore the databases</span></span>

<span data-ttu-id="ed7d1-121">您应该如何恢复持久聊天数据取决于用来备份的方法。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-121">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span> <span data-ttu-id="ed7d1-122">如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。</span><span class="sxs-lookup"><span data-stu-id="ed7d1-122">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span> <span data-ttu-id="ed7d1-123">如果您使用**导出 CsPersistentChatData** cmdlet 持久聊天数据进行备份，则必须使用**导入 CsPersistentChatData** cmdlet 来还原数据：</span><span class="sxs-lookup"><span data-stu-id="ed7d1-123">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data:</span></span>
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

<span data-ttu-id="ed7d1-124">或者</span><span class="sxs-lookup"><span data-stu-id="ed7d1-124">or</span></span>
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```


