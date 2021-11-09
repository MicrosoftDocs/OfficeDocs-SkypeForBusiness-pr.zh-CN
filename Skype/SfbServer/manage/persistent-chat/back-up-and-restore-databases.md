---
title: 备份和还原 Skype for Business Server 2015 中的持久聊天数据库
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。
ms.openlocfilehash: 3c294a33a82a9279e05e1d69e48b531f8b85e3c0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841164"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>备份和还原 Skype for Business Server 2015 中的持久聊天数据库
 
**摘要：** 了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。
  
持久聊天服务器SQL Server软件来存储聊天室数据，如历史记录和内容、配置、用户设置和其他相关元数据。 此外，如果组织规定需要存档持久聊天活动，并且启用了可选的合规性服务，SQL Server 数据库软件将用于存储合规性数据，包括聊天内容和事件，如加入和离开聊天室。 聊天室内容存储在持久聊天数据库中 (mgc) 。 合规性数据存储在合规性数据库 (mgccomp) 。 这是应定期备份的业务关键数据。 
  
> [!NOTE]
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 

## <a name="back-up-the-databases"></a>备份数据库

有两种方法可以备份持久聊天数据。 
  
- SQL Server备份
    
- **Export-CsPersistentChatData** cmdlet，用于将持久聊天数据导出为文件
    
使用 SQL Server 备份创建的数据所需的磁盘空间明显多于 **Export-CsPersistentChatData** cmdlet 创建的磁盘空间（可能多于 20 倍），但 SQL Server 备份可能是您熟悉的过程。
  
如果要使用备份SQL Server，请参阅SQL文档了解详细信息。 
  
如果要使用 **Export-CsPersistentChatData** cmdlet，您可以按如下方式指定命令：
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

或
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

例如，以下命令从位于服务器数据库的持久聊天数据库中导出持久聊天 atl-sql-001.contoso.com;导出的数据将存储在文件C:\Logs\PersistentChatData.zip。 由于未指定 Level 参数，因此该命令将完全导出持久聊天信息：
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>还原数据库

如何还原持久聊天数据取决于用于备份数据的方法。 如果您使用了SQL Server备份过程，则必须使用SQL Server过程。 如果您使用 **Export-CsPersistentChatData** cmdlet 备份持久聊天数据，则必须使用 **Import-CsPersistentChatData** cmdlet 还原数据：
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

或
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
