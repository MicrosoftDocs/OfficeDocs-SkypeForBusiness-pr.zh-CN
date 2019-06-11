---
title: Lync Server 2013：为持久聊天创建站点策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be98028bf06c20c82dca98fc3bc20d25e97a94c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="5ba33-102">在 Lync Server 2013 中为持久聊天创建站点策略</span><span class="sxs-lookup"><span data-stu-id="5ba33-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ba33-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5ba33-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5ba33-104">对于已部署的每个网站, 你可以创建特定于站点的持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="5ba33-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="5ba33-105">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="5ba33-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ba33-106">若要配置和使用持久聊天服务器, 必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持, 然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="5ba33-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="5ba33-107">有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">将持久聊天服务器添加到 Lync Server 2013</A>中的部署。</span><span class="sxs-lookup"><span data-stu-id="5ba33-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="5ba33-108">若要配置持久聊天服务器配置设置, 请参阅在部署文档中<A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">为 Lync server 2013 中的永久聊天服务器池配置持久聊天服务器选项</A>。</span><span class="sxs-lookup"><span data-stu-id="5ba33-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="5ba33-109">为网站创建持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="5ba33-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="5ba33-110">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5ba33-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="5ba33-111">从 "**开始**" 菜单中, 选择 "Lync Server 控制面板" 或打开一个浏览器窗口, 然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="5ba33-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="5ba33-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5ba33-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5ba33-113">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="5ba33-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5ba33-114">你还可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ba33-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5ba33-115">有关详细信息, 请参阅在部署文档中<A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A>。</span><span class="sxs-lookup"><span data-stu-id="5ba33-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="5ba33-116">单击“**新建**”，然后单击“**站点策略**”。</span><span class="sxs-lookup"><span data-stu-id="5ba33-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="5ba33-117">在“**选择站点**”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="5ba33-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="5ba33-118">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="5ba33-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="5ba33-119">在“**名称**”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="5ba33-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="5ba33-120">在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="5ba33-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="5ba33-121">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。</span><span class="sxs-lookup"><span data-stu-id="5ba33-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="5ba33-122">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="5ba33-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

