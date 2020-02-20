---
title: Lync Server 2013：禁用或启用聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="3bac9-102">在 Lync Server 2013 中禁用或启用聊天室</span><span class="sxs-lookup"><span data-stu-id="3bac9-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bac9-103">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="3bac9-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="3bac9-104">如果持久聊天室的主题不再相关，可以通过禁用聊天室使用户无法使用该聊天室。</span><span class="sxs-lookup"><span data-stu-id="3bac9-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="3bac9-105">禁用聊天室后，所有成员都将立即从聊天室断开连接。</span><span class="sxs-lookup"><span data-stu-id="3bac9-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="3bac9-106">禁用聊天室后，用户将无法重新加入聊天室或在聊天室搜索中找到它。</span><span class="sxs-lookup"><span data-stu-id="3bac9-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="3bac9-107">已禁用的聊天室可在稍后由持久聊天管理员启用。</span><span class="sxs-lookup"><span data-stu-id="3bac9-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="3bac9-108">禁用某聊天室时，将保留其成员身份列表和其他设置。</span><span class="sxs-lookup"><span data-stu-id="3bac9-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="3bac9-109">如果再次启用会议室，则无需手动重新创建这些设置。</span><span class="sxs-lookup"><span data-stu-id="3bac9-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="3bac9-110">如果聊天室的历史记录持续存在（聊天室历史记录持续性是适用于类别中所有聊天室的类别的可选设置; 默认值为 "已保留"，但可以通过将类别的 "**启用聊天历史记录**" 设置为 "false" 来将其关闭，在禁用聊天室时保留内容。</span><span class="sxs-lookup"><span data-stu-id="3bac9-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="3bac9-111">但是，在聊天室仍处于禁用状态时，搜索中不会显示该内容。</span><span class="sxs-lookup"><span data-stu-id="3bac9-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="3bac9-112">如果后来启用了聊天室，用户可以搜索在禁用聊天室之前已发布的邮件。</span><span class="sxs-lookup"><span data-stu-id="3bac9-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="3bac9-113">有关通过使用 Windows PowerShell 命令行界面禁用和启用聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。</span><span class="sxs-lookup"><span data-stu-id="3bac9-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="3bac9-114">若要禁用聊天室，请使用与以下类似的命令：</span><span class="sxs-lookup"><span data-stu-id="3bac9-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="3bac9-115">若要启用聊天室，请将 Disabled 属性设置为 False：</span><span class="sxs-lookup"><span data-stu-id="3bac9-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="3bac9-116">请注意，聊天室无法使用 Lync Server 控制面板启用或禁用。</span><span class="sxs-lookup"><span data-stu-id="3bac9-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="3bac9-117">有关配置聊天室的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置会议室](lync-server-2013-configure-rooms.md)。</span><span class="sxs-lookup"><span data-stu-id="3bac9-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

