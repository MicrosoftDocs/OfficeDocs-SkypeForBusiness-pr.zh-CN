---
title: Lync Server 2013：删除聊天室或类别
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>在 Lync Server 2013 中删除聊天室或类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

可以删除持久的聊天室。 如果您有一个不再使用的聊天室，则可以将其禁用。 有关详细信息，请参阅[在 Lync Server 2013 中禁用或启用聊天室](lync-server-2013-disabling-or-enabling-a-chat-room.md)。

永久性聊天管理员可以查询禁用的聊天室，并且可以使用 Windows PowerShell cmdlet 定期清除和永久删除聊天室。 **CsPersistentChatRoom**。

可以删除类别。 但是，若要删除某个类别，您必须先删除其下方的所有聊天室，或者将聊天室移动到新的类别中，而保留空类别以将其删除。 持久聊天服务器不允许您删除包含聊天室的类别。 有关详细信息，请参阅[Lync Server 2013 中将聊天室从一个类别移动到另一个类别](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。

有关使用 Windows PowerShell 命令行界面删除空类别的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "房间管理"。

有关聊天室和类别的详细信息，请参阅在[Lync server 2013 中配置会议室](lync-server-2013-configure-rooms.md)和在部署文档中的[Lync Server 2013 中配置类别](lync-server-2013-configure-categories.md)。

</div>

<span> </span>

</div>

</div>

</div>

