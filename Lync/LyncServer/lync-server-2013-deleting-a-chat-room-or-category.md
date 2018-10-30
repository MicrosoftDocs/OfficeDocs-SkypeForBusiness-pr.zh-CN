---
title: Lync Server 2013：删除聊天室或类别
TOCTitle: 删除聊天室或类别
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215881(v=OCS.15)
ms:contentKeyID: 49313913
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中删除聊天室或类别

 

_**上一次修改主题：** 2012-11-01_

可以删除 持久聊天聊天室。如果您不打算继续使用某聊天室，可以禁用该聊天室。有关详细信息，请参阅 [在 Lync Server 2013 中禁用或启用聊天室](lync-server-2013-disabling-or-enabling-a-chat-room.md)。

持久聊天管理员可以查询已禁用的聊天室，并且可以使用 Windows PowerShell cmdlet（即 **Remove-CsPersistentChatRoom**）定期清除并永久删除聊天室。

可以删除类别。但是，要删除某个类别，您必须先删除该类别下的所有聊天室，或将聊天室移动到新类别，从而留下空类别以进行删除。 持久聊天服务器不允许您删除包含聊天室的类别。有关详细信息，请参阅 [在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。

有关使用 Windows PowerShell 命令行接口 删除空类别的详细信息，请参阅[使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的“聊天室管理”。

有关聊天室和类别的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置聊天室](lync-server-2013-configure-rooms.md)和 [在 Lync Server 2013 中配置类别](lync-server-2013-configure-categories.md)。

