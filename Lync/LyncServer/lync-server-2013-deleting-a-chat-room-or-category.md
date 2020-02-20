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
ms.openlocfilehash: 3c4e346d33e44a9365d9cf4924374c2a28b8b908
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="d5918-102">在 Lync Server 2013 中删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="d5918-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5918-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5918-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5918-104">可以删除持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="d5918-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="d5918-105">如果您不打算继续使用某聊天室，可以禁用该聊天室。</span><span class="sxs-lookup"><span data-stu-id="d5918-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="d5918-106">有关详细信息，请参阅[在 Lync Server 2013 中禁用或启用聊天室](lync-server-2013-disabling-or-enabling-a-chat-room.md)。</span><span class="sxs-lookup"><span data-stu-id="d5918-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="d5918-107">持久聊天管理员可以查询已禁用的聊天室，并可以定期清除并永久删除聊天室，方法是使用 Windows PowerShell cmdlet **set-cspersistentchatroom**。</span><span class="sxs-lookup"><span data-stu-id="d5918-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="d5918-108">可以删除类别。</span><span class="sxs-lookup"><span data-stu-id="d5918-108">Categories can be deleted.</span></span> <span data-ttu-id="d5918-109">但是，要删除某个类别，您必须先删除该类别下的所有聊天室，或将聊天室移动到新类别，从而留下空类别以进行删除。</span><span class="sxs-lookup"><span data-stu-id="d5918-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="d5918-110">持久聊天服务器不允许您删除包含聊天室的类别。</span><span class="sxs-lookup"><span data-stu-id="d5918-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="d5918-111">有关详细信息，请参阅[Lync Server 2013 中的将聊天室从一个类别移动到另一个类别](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。</span><span class="sxs-lookup"><span data-stu-id="d5918-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="d5918-112">有关使用 Windows PowerShell 命令行界面删除空类别的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。</span><span class="sxs-lookup"><span data-stu-id="d5918-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="d5918-113">有关聊天室和类别的详细信息，请参阅部署文档中的在[Lync server 2013 中配置聊天室](lync-server-2013-configure-rooms.md)和[配置 lync server 2013](lync-server-2013-configure-categories.md)中的类别。</span><span class="sxs-lookup"><span data-stu-id="d5918-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

