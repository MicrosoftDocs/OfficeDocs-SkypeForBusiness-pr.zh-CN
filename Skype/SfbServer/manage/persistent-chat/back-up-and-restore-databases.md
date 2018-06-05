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
description: 摘要： 了解如何备份和还原业务服务器 2015 Skype 中的持久聊天服务器数据库。
ms.openlocfilehash: 37a2a1bb2cab33a05468f27e04eda10b927b4bbe
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568736"
---
# <a name="back-up-and-restore-persistent-chat-databases-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中备份和还原持久聊天数据库
 
**摘要：** 了解如何备份和还原业务服务器 2015 Skype 中的持久聊天服务器数据库。
  
持久聊天服务器需要 SQL Server 数据库软件存储聊天室数据，如历史记录和内容、 配置、 用户设置和其他相关的元数据。 此外，如果您的组织需要的持久聊天活动要存档的法规且启用可选的合规性服务，SQL Server 数据库软件用于存储合规性数据，包括聊天内容和事件，如加入和离开聊天室。 持久聊天数据库 (mgc) 中存储聊天室内容。 合规性数据存储在合规性数据库 (mgccomp) 中。 这是应定期备份的业务关键型数据。 
  
## <a name="back-up-the-databases"></a>备份数据库

有两种备份持久聊天数据。 
  
- SQL Server 备份
    
- **Export-cspersistentchatdata** cmdlet，将持久聊天数据导出为文件
    
使用 SQL Server 备份创建的数据明显需要更多磁盘空间，所需磁盘空间量可能是使用 **Export-CsPersistentChatData** cmdlet 创建的数据所需空间量的 20 倍以上，但您可能更熟悉 SQL Server 备份过程。
  
如果您希望使用 SQL Server 备份过程，请参阅 SQL 文档以了解更多信息。 
  
如果您希望使用 **Export-CsPersistentChatData** cmdlet，您可以如下所示指定命令：
  
```
Export-CsPersistentChatData [-FileName <String>] <COMMON PARAMETERS>
```

或者
  
```
Export-CsPersistentChatData [-AsBytes <SwitchParameter>] <COMMON PARAMETERS>
```

例如，以下命令可将持久聊天数据从位于服务器 atl-sql-001.contoso.com 上的持久聊天数据库中导出；导出的数据将存储在文件 C:\Logs\PersistentChatData.zip 中。因为没有指定 Level 参数，该命令将完全导出持久聊天信息：
  
```
Export-CsPersistentChatData -DBInstance "atl-sql-001.contoso.com\rtc" -FileName "C:\Logs\PersistentChatData.zip"
```

## <a name="restore-the-databases"></a>还原数据库

还原持久聊天数据的方式取决于您用来备份它的方法。 如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。 如果**Export-cspersistentchatdata** cmdlet 用于备份持久聊天数据，则必须使用**Import-cspersistentchatdata** cmdlet 还原数据：
  
```
Import-CsPersistentChatData -FileName <String> <COMMON PARAMETERS>
```

或者
  
```
Import-CsPersistentChatData -ByteInput <Byte > <COMMON PARAMETERS>
```