---
title: 还原持久聊天数据
TOCTitle: 还原持久聊天数据
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945649(v=OCS.15)
ms:contentKeyID: 52061112
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原持久聊天数据

 

_**上一次修改主题：** 2013-02-18_

持久聊天聊天室内容存储在持久聊天数据库 (Mgc.mdf) 中。这些内容是通常应备份的重要业务数据。除了聊天室内容外，主体（例如用户和用户组）及这些主体访问聊天室和聊天室内容所需具有的角色和访问权限也存储在持久聊天数据库中。

您还原持久聊天数据的方式取决于您备份这些数据的方式。

  - 如果您使用 SQL Server 备份过程，则必须使用 SQL Server 还原过程。

  - 如果使用 **Export-CsPersistentChatData** cmdlet 备份持久聊天数据，则必须使用 **Import-CsPersistentChatData** cmdlet 还原这些数据。

