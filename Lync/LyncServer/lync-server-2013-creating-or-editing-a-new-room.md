---
title: Lync Server 2013：创建或编辑新聊天室
TOCTitle: 创建或编辑新聊天室
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215880(v=OCS.15)
ms:contentKeyID: 49313885
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或编辑新聊天室

 

_**上一次修改主题：** 2015-03-19_

配置 持久聊天聊天室通常是由用户进行处理的； 持久聊天管理员通常不会配置或管理聊天室。用于管理聊天室的 Windows PowerShell cmdlet 仅可供 **CsPersistentChatAdministrator** 管理员使用。

在任何给定的类别中为 **创建者**的用户可以使用 Lync 客户端创建和管理聊天室。已被指定为特定聊天室的管理员的用户也可以对聊天室执行持续的管理，如编辑聊天室属性或成员身份。

> [!TIP]
> 持久聊天管理员也可以是创建者，并且他们不受对创建者规定的限制的约束。


（可选）如果您是 持久聊天管理员，则可以使用用户界面来创建和管理聊天室，而不是使用 Windows PowerShell cmdlet。为此，用户需要为 持久聊天服务器管理员启用 SIP，然后使用 Lync 客户端创建和管理聊天室。

如果您想要为用户创建自定义聊天室管理工作流，则可以设置您的 持久聊天服务器配置上的 **RoomManagementUrl** 属性，以将用户从 Lync 客户端重定向到您的自定义解决方案。

有关使用 Windows PowerShell 命令行接口 配置聊天室的详细信息，请参阅[使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的“聊天室管理”。

有关配置聊天室的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置聊天室](lync-server-2013-configure-rooms.md)。

