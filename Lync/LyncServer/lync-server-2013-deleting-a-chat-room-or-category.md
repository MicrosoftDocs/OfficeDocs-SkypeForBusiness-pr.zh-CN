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
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>在 Lync Server 2013 中删除聊天室或类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

可以删除持久聊天室。 如果您不打算继续使用某聊天室，可以禁用该聊天室。 有关详细信息，请参阅[在 Lync Server 2013 中禁用或启用聊天室](lync-server-2013-disabling-or-enabling-a-chat-room.md)。

持久聊天管理员可以查询已禁用的聊天室，并可以定期清除并永久删除聊天室，方法是使用 Windows PowerShell cmdlet **set-cspersistentchatroom**。

可以删除类别。 但是，要删除某个类别，您必须先删除该类别下的所有聊天室，或将聊天室移动到新类别，从而留下空类别以进行删除。 持久聊天服务器不允许您删除包含聊天室的类别。 有关详细信息，请参阅[Lync Server 2013 中的将聊天室从一个类别移动到另一个类别](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。

有关使用 Windows PowerShell 命令行界面删除空类别的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

有关聊天室和类别的详细信息，请参阅部署文档中的在[Lync server 2013 中配置聊天室](lync-server-2013-configure-rooms.md)和[配置 lync server 2013](lync-server-2013-configure-categories.md)中的类别。

</div>

<span> </span>

</div>

</div>

</div>

