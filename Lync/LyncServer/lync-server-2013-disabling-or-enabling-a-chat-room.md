---
title: Lync Server 2013：禁用或启用聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>在 Lync Server 2013 中禁用或启用聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-05_

如果永久聊天室的主题不再相关, 您可以通过禁用该聊天室使用户无法使用该聊天室。 禁用聊天室时，所有成员将立即从聊天室断开。 禁用聊天室后，用户无法重新加入或在聊天室搜索中找到该聊天室。

已禁用的聊天室可在稍后由持久聊天管理员启用。 如果聊天室被禁用，其成员关系列表和其他设置将被保留。 如果再次启用聊天室, 则无需手动重新创建设置。

如果聊天室的历史记录仍然存在 (聊天室历史记录持久性是一个适用于类别内所有聊天室的类别的可选设置; 默认值是保留, 但可以通过将类别的 "**启用聊天历史记录**" 设置为 "关闭"false) 时, 将在禁用聊天室时保留内容。 但是，在该聊天室处于禁用状态时，该内容不会显示在搜索中。 如果随后启用该聊天室，则用户可以搜索禁用该聊天室之前发布的消息。

有关通过使用 Windows PowerShell 命令行界面禁用和启用聊天室的详细信息, 请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。 若要禁用聊天室, 请使用类似下面的命令:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

若要启用聊天室, 请将 Disabled 属性设置为 False:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

请注意, 聊天室无法通过使用 Lync Server 控制面板启用或禁用。

有关配置聊天室的详细信息, 请参阅部署文档中[Lync Server 2013](lync-server-2013-configure-rooms.md)中的 "配置聊天室"。

</div>

<span> </span>

</div>

</div>

</div>

