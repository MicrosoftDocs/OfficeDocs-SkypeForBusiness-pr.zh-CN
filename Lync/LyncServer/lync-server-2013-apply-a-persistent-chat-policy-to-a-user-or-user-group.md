---
title: Lync Server 2013：将持久聊天策略应用于用户或用户组
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
ms.openlocfilehash: 726fe9a5fa20a52f770cd5bab475de5731562989
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="1a442-102">在 Lync Server 2013 中将持久聊天策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="1a442-102">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a442-103">_**主题上次修改时间：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="1a442-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="1a442-104">如果已启用 Lync Server 2013 的用户，则可以将适当的策略应用于特定用户，以便为永久聊天服务器启用或禁用它们。</span><span class="sxs-lookup"><span data-stu-id="1a442-104">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a442-105">若要配置和使用持久聊天服务器，必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="1a442-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="1a442-106">有关详细信息，请参阅在部署文档中<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="1a442-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="1a442-107">若要配置持久聊天服务器配置设置，请参阅在部署文档中<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">为 Lync server 2013 中的永久聊天服务器池配置持久聊天服务器选项</A>。</span><span class="sxs-lookup"><span data-stu-id="1a442-107">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="1a442-108">使用本主题中的过程将以前创建的持久聊天用户策略应用于一个或多个用户帐户或用户组。</span><span class="sxs-lookup"><span data-stu-id="1a442-108">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="1a442-109">将持久聊天用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="1a442-109">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="1a442-110">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1a442-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a442-111">从 "**开始**" 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="1a442-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="1a442-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1a442-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a442-113">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1a442-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="1a442-114">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="1a442-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1a442-115">在 "**永久聊天策略**" 下的 "**编辑 Lync Server 用户**" 中，选择要应用的持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="1a442-115">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1a442-116">" <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认有效策略。</span><span class="sxs-lookup"><span data-stu-id="1a442-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="1a442-117">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="1a442-117">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="1a442-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1a442-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

