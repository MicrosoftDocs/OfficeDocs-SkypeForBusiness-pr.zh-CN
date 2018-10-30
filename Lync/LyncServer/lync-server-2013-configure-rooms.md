---
title: Lync Server 2013：配置聊天室
TOCTitle: 配置聊天室
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205067(v=OCS.15)
ms:contentKeyID: 49313502
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置聊天室

 

_**上一次修改主题：** 2012-10-06_

配置 持久聊天聊天室通常是由用户或其他使用 Windows PowerShell 命令行接口的中心团队处理的；管理员一般不会管理聊天室。但是，如果您必须创建并管理聊天室，则可使用 Windows PowerShell 命令行接口，或将自己作为聊天室的成员添加，然后使用 Lync 2013 客户端。

有关使用 Windows PowerShell 命令行接口 配置聊天室的详细信息，请参阅[使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的“聊天室管理”。

## 管理聊天室中的数据

持久聊天服务器使用户可通过将消息发布到 持久聊天聊天室来进行协作。数据是保存在服务器上的，聊天室的成员有权访问数据（包括历史记录数据）。但是，不同角色的用户对所保留的数据具有不同的访问权限，如下面的列表中概述。

  - 管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。他们也可以删除或替换认为对特定聊天室不合适的消息。

  - 最终用户（包括消息作者）无法删除任何聊天室的内容。

  - 聊天室管理员可禁用聊天室，但无法删除聊天室。聊天室创建后，仅管理员可删除它。

消息删除后，便无法撤销该操作。但是，如果备份了已删除消息，则可还原这些消息。如果启用 持久聊天合规性服务器，则将在合规性数据库中保留旧消息。

> [!NOTE]  
> 此聊天室数据使用情况适用于 Lync Server 2013持久聊天服务器 API 应用程序，调用管理员角色的情况除外。 持久聊天服务器 API 无法用于执行任何管理员操作。您必须在 Lync Server 命令行管理程序中执行这些操作。


