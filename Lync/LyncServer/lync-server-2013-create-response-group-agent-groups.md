---
title: Lync Server 2013：创建响应组代理组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be70adae85256178defca0269e6663bad76dabfc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="07afe-102">创建响应组代理组 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07afe-102">Create Response Group agent groups Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07afe-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="07afe-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="07afe-104">创建代理组时要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。</span><span class="sxs-lookup"><span data-stu-id="07afe-104">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="07afe-105">必须登录和注销组（不同于登录或注销 Lync Server）的代理称为*正式代理*。</span><span class="sxs-lookup"><span data-stu-id="07afe-105">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="07afe-106">正式代理必须登录到组，然后才能接收路由至该组的呼叫。</span><span class="sxs-lookup"><span data-stu-id="07afe-106">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="07afe-107">这对于以兼职形式应答组中的呼叫的代理很有用。</span><span class="sxs-lookup"><span data-stu-id="07afe-107">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="07afe-108">正式代理通过单击 Lync 2013 中的菜单项来打开 Windows Internet Explorer Internet 浏览器并显示网页控制台，以登录和注销其组。</span><span class="sxs-lookup"><span data-stu-id="07afe-108">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="07afe-109">不登录到组或从组注销的代理称为*非正式代理*。</span><span class="sxs-lookup"><span data-stu-id="07afe-109">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="07afe-110">非正式代理在登录 Lync Server 时自动登录到组，并且无法注销组。</span><span class="sxs-lookup"><span data-stu-id="07afe-110">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="07afe-p103">只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。</span><span class="sxs-lookup"><span data-stu-id="07afe-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07afe-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="07afe-113">In This Section</span></span>

[<span data-ttu-id="07afe-114">在 Lync Server 2013 中创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="07afe-114">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

