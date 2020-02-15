---
title: Lync Server 2013：启用持久聊天服务器策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f98275ee911d1abecbc60907653ad8de0a4222
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="88b87-102">在 Lync Server 2013 中启用持久聊天服务器策略</span><span class="sxs-lookup"><span data-stu-id="88b87-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88b87-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="88b87-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="88b87-104">在 "Lync Server 2013 控制面板" 中，可以使用**持久**聊天组的 "**持久聊天策略**" 页来管理全局、池、站点或用户级别的策略，包括配置默认全局策略和为部署创建一个或多个其他用户策略和站点策略。</span><span class="sxs-lookup"><span data-stu-id="88b87-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="88b87-105">如果用户按策略启用了持久聊天服务器，则持久聊天服务器环境将显示在其 Lync 2013 客户端中。</span><span class="sxs-lookup"><span data-stu-id="88b87-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88b87-106">在拓扑中，持久聊天服务器网站策略适用于全局、每个用户的池、或每个用户的网站或每个用户。</span><span class="sxs-lookup"><span data-stu-id="88b87-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="88b87-107">全局策略是在部署持久聊天服务器时自动创建的，并且可以配置，但不能删除。</span><span class="sxs-lookup"><span data-stu-id="88b87-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="88b87-108">因为全局策略适用于所有用户，所以不必对每用户进行设置。</span><span class="sxs-lookup"><span data-stu-id="88b87-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="88b87-109">您可以创建和配置多个站点和用户策略，这些策略与全局策略一起为用户启用持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="88b87-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="88b87-110">池和站点持久聊天服务器策略替代全局持久聊天服务器策略，但仅适用于该网站的用户。</span><span class="sxs-lookup"><span data-stu-id="88b87-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="88b87-111">用户策略将覆盖分配有用户策略的用户的全局、池和网站策略。</span><span class="sxs-lookup"><span data-stu-id="88b87-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88b87-112">若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="88b87-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="88b87-113">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A>。</span><span class="sxs-lookup"><span data-stu-id="88b87-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88b87-114">本部分内容</span><span class="sxs-lookup"><span data-stu-id="88b87-114">In This Section</span></span>

  - [<span data-ttu-id="88b87-115">在 Lync Server 2013 中配置持久聊天的全局策略</span><span class="sxs-lookup"><span data-stu-id="88b87-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="88b87-116">在 Lync Server 2013 中为持久聊天创建站点策略</span><span class="sxs-lookup"><span data-stu-id="88b87-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="88b87-117">在 Lync Server 2013 中为持久聊天创建用户策略</span><span class="sxs-lookup"><span data-stu-id="88b87-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="88b87-118">在 Lync Server 2013 中将持久聊天策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="88b87-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

