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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4f2b689b-7f15-48dc-a069-da7bc8527def
description: 摘要：了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。
ms.openlocfilehash: 9da64a3ba6f6ad8053faebf0d536a610e02cce8f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817338"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中备份和还原持久聊天数据库
 
**摘要：** 了解如何在 Skype for Business Server 2015 中备份和还原持久聊天服务器数据库。
  
持久聊天服务器要求 SQL Server 数据库软件存储聊天室数据，如历史记录和内容、配置、用户预配和其他相关元数据。 此外，如果你的组织具有要求存档持久聊天活动的法规，并且启用了可选合规性服务，则 SQL Server 数据库软件用于存储合规性数据，包括聊天内容和事件，例如加入和离开聊天室。 聊天室内容存储在持久聊天数据库（mgc）中。 合规性数据存储在合规性数据库 (mgccomp) 中。 这是应定期备份的业务关键型数据。 
  
> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。 

## <a name="back-up-the-databases"></a>备份数据库

备份持久聊天数据有两种方法。 
  
- SQL Server 备份
    
- **导出 CsPersistentChatData** cmdlet，该 Cmdlet 将永久聊天数据导出为文件
    
使用 SQL Server 备份创建的数据明显需要更多磁盘空间，所需磁盘空间量可能是使用 **Export-CsPersistentChatData** cmdlet 创建的数据所需空间量的 20 倍以上，但您可能更熟悉 SQL Server 备份过程。
  
如果您希望使用 SQL Server 备份过程，请参阅 SQL 文档以了解更多信息。 
  
如果您希望使用 **Export-CsPersistentChatData** cmdlet，您可以如下所示指定命令：
  
```PowerShell
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

或者
  
```PowerShell
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

例如，以下命令可将持久聊天数据从位于服务器 atl-sql-001.contoso.com 上的持久聊天数据库中导出；导出的数据将存储在文件 C:\Logs\PersistentChatData.zip 中。因为没有指定 Level 参数，该命令将完全导出持久聊天信息：
  
```PowerShell
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>还原数据库

还原持久聊天数据的方式取决于用于备份的方法。 如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。 如果你使用**Export CsPersistentChatData** Cmdlet 备份持久聊天数据，则必须使用**CsPersistentChatData** cmdlet 还原数据：
  
```PowerShell
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

或者
  
```PowerShell
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```
