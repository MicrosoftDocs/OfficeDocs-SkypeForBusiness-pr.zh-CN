---
title: Lync Server 2013：禁用或启用聊天室
TOCTitle: 禁用或启用聊天室
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215883(v=OCS.15)
ms:contentKeyID: 49314438
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中禁用或启用聊天室

 

_**上一次修改主题：** 2014-02-05_

如果某个 持久聊天聊天室的主题不再相关，则可以禁用该聊天室，以使用户不能使用该聊天室。禁用聊天室时，所有成员将立即从聊天室断开。禁用聊天室后，用户无法重新加入或在聊天室搜索中找到该聊天室。

持久聊天管理员可以在以后启用禁用的聊天室。如果禁用某聊天室，其成员身份列表和其他设置将保留。如果再次启用该聊天室，则不必手动重新创建这些设置。

如果该聊天室的历史记录仍然存在（聊天室历史记录暂留是类别的可选设置，应用于该类别内的所有聊天室；默认设置为暂留，但可通过将该类别的“启用聊天历史记录”设置为 false 来关闭），则可在禁用该聊天室后保留内容。但是，在该聊天室处于禁用状态时，该内容不会显示在搜索中。如果随后启用该聊天室，则用户可以搜索禁用该聊天室之前发布的消息。

有关使用 Windows PowerShell 命令行接口禁用和启用聊天室的详细信息，请参阅[使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的“聊天室管理”。要禁用聊天室，请使用类似于此的命令：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

要启用聊天室，请将 Disabled 属性设置为 False：

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

注意，无法使用 Lync Server 控制面板启用或禁用聊天室。

有关配置聊天室的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置聊天室](lync-server-2013-configure-rooms.md)。

