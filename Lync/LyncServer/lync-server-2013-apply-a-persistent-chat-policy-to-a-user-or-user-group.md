---
title: Lync Server 2013：将持久聊天策略应用于用户或用户组
description: Lync Server 2013：将持久聊天策略应用于用户或用户组。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 168fa795303bbcf3f3eef4bfc817aa98d763d1ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573478"
---
# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="fd22b-103">在 Lync Server 2013 中将持久聊天策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="fd22b-103">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd22b-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fd22b-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fd22b-105">如果已为用户启用 Lync Server 2013，则可以将适当的策略应用于特定用户，以便为持久聊天服务器启用或禁用它们。</span><span class="sxs-lookup"><span data-stu-id="fd22b-105">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd22b-106">若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="fd22b-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="fd22b-107">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A> 。</span><span class="sxs-lookup"><span data-stu-id="fd22b-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="fd22b-108">若要配置持久聊天服务器配置设置，请参阅部署文档中的 " <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全局或在 Lync server 2013 中为持久聊天服务器池配置持久聊天服务器选项</A> "。</span><span class="sxs-lookup"><span data-stu-id="fd22b-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="fd22b-109">使用本主题中的过程可将以前创建的持久聊天用户策略应用于一个或多个用户帐户或用户组。</span><span class="sxs-lookup"><span data-stu-id="fd22b-109">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="fd22b-110">将持久聊天用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="fd22b-110">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="fd22b-111">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fd22b-111">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fd22b-112">从 " **开始** " 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="fd22b-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="fd22b-113">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="fd22b-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fd22b-114">在左侧导航栏中，单击“用户”\*\*\*\*，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fd22b-114">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="fd22b-115">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd22b-115">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="fd22b-116">在 " **编辑 Lync Server 用户** " 中的 " **持久聊天策略**" 下，选择要应用的持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="fd22b-116">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fd22b-117">" <STRONG> &lt; 自动 &gt; </STRONG>设置" 应用默认有效策略。</span><span class="sxs-lookup"><span data-stu-id="fd22b-117">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="fd22b-118">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="fd22b-118">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="fd22b-119">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd22b-119">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

