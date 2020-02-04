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

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="3ddcb-102">在 Lync Server 2013 中删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="3ddcb-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ddcb-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3ddcb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3ddcb-104">可以删除持久的聊天室。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="3ddcb-105">如果您有一个不再使用的聊天室，则可以将其禁用。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="3ddcb-106">有关详细信息，请参阅[在 Lync Server 2013 中禁用或启用聊天室](lync-server-2013-disabling-or-enabling-a-chat-room.md)。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="3ddcb-107">永久性聊天管理员可以查询禁用的聊天室，并且可以使用 Windows PowerShell cmdlet 定期清除和永久删除聊天室。 **CsPersistentChatRoom**。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="3ddcb-108">可以删除类别。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-108">Categories can be deleted.</span></span> <span data-ttu-id="3ddcb-109">但是，若要删除某个类别，您必须先删除其下方的所有聊天室，或者将聊天室移动到新的类别中，而保留空类别以将其删除。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="3ddcb-110">持久聊天服务器不允许您删除包含聊天室的类别。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="3ddcb-111">有关详细信息，请参阅[Lync Server 2013 中将聊天室从一个类别移动到另一个类别](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="3ddcb-112">有关使用 Windows PowerShell 命令行界面删除空类别的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "房间管理"。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="3ddcb-113">有关聊天室和类别的详细信息，请参阅在[Lync server 2013 中配置会议室](lync-server-2013-configure-rooms.md)和在部署文档中的[Lync Server 2013 中配置类别](lync-server-2013-configure-categories.md)。</span><span class="sxs-lookup"><span data-stu-id="3ddcb-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

