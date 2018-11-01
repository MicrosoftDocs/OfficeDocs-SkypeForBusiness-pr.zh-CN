---
title: 备份持久聊天数据库
TOCTitle: 备份持久聊天数据库
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945646(v=OCS.15)
ms:contentKeyID: 52061125
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份持久聊天数据库

 

_**上一次修改主题：** 2013-02-17_

持久聊天聊天室内容存储在持久聊天数据库 (Mgc.mdf) 中。这些内容是通常应备份的重要业务数据。除了聊天室内容外，持久聊天数据库还存储有关主体（例如用户和用户组）及这些主体访问聊天室所需具有的角色和访问权限的信息。

可采用两种方法备份持久聊天数据。

  - SQL Server 备份

  - `Export-CsPersistentChatData` cmdlet，可将持久聊天数据作为文件导出

使用 SQL Server 备份创建的数据明显需要更多磁盘空间，所需磁盘空间量可能是使用 `Export-CsPersistentChatData` 创建的数据所需空间量的 20 倍以上，但管理员可能更熟悉 SQL Server 备份过程。

