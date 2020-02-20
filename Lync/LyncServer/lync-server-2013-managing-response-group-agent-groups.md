---
title: Lync Server 2013：管理响应组代理组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34fab5d046aa11435aff5be416e281e5848fe4d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="a031b-102">在 Lync Server 2013 中管理响应组代理组</span><span class="sxs-lookup"><span data-stu-id="a031b-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a031b-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a031b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a031b-p101">代理组由指定应答响应组呼叫的一组人员组成。创建代理组时，要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。</span><span class="sxs-lookup"><span data-stu-id="a031b-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a031b-106">必须先为用户启用企业语音，然后才能将其添加到代理组。</span><span class="sxs-lookup"><span data-stu-id="a031b-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="a031b-107">有关如何为用户启用企业语音的详细信息，请参阅<A href="lync-server-2013-enable-users-for-enterprise-voice.md">enable users For Enterprise voice In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="a031b-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a031b-p103">只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。</span><span class="sxs-lookup"><span data-stu-id="a031b-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="a031b-110">必须登录和注销组（不同于登录或注销 Lync Server）的代理称为*正式代理*。</span><span class="sxs-lookup"><span data-stu-id="a031b-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="a031b-111">正式代理必须登录到组，然后才能接收路由至该组的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a031b-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="a031b-112">这对于以兼职形式应答组中的呼叫的代理很有用。</span><span class="sxs-lookup"><span data-stu-id="a031b-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="a031b-113">正式代理通过单击 Lync 2013 中的菜单项来打开 Windows Internet Explorer Internet 浏览器并显示网页控制台，以登录和注销其组。</span><span class="sxs-lookup"><span data-stu-id="a031b-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="a031b-114">不登录到组或从组注销的代理称为*非正式代理*。</span><span class="sxs-lookup"><span data-stu-id="a031b-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="a031b-115">非正式代理在登录 Lync Server 时自动登录到组，并且无法注销组。</span><span class="sxs-lookup"><span data-stu-id="a031b-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a031b-p106">如果将用户分配为响应组代理，需告知用户，如果他们已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。</span><span class="sxs-lookup"><span data-stu-id="a031b-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a031b-119">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a031b-119">In This Section</span></span>

  - [<span data-ttu-id="a031b-120">在 Lync Server 2013 中创建或修改代理组</span><span class="sxs-lookup"><span data-stu-id="a031b-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="a031b-121">在 Lync Server 2013 中删除代理组</span><span class="sxs-lookup"><span data-stu-id="a031b-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

