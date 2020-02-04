---
title: 配置联合路由和媒体流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd9cf1c7c61261e4e1a6974498f9f9dff980169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="478ba-102">配置联合路由和媒体流量</span><span class="sxs-lookup"><span data-stu-id="478ba-102">Configure federation routes and media traffic</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="478ba-103">_**主题上次修改时间：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="478ba-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="478ba-104">联盟是两个或多个 SIP 域之间的信任关系，这些 SIP 域允许单独组织中的用户通过网络边界进行通信。</span><span class="sxs-lookup"><span data-stu-id="478ba-104">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="478ba-105">在迁移到 Lync Server 2013 试验池后，需要从 Lync Server 2010 Edge 服务器的联盟路径切换到 Lync Server 2013 Edge 服务器的联合路由。</span><span class="sxs-lookup"><span data-stu-id="478ba-105">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="478ba-106">使用以下过程可将 Lync Server 2010 Edge 服务器和控制器中的联盟路由和媒体流量路由切换到 Lync Server 2013 Edge 服务器，以便用于单个网站部署。</span><span class="sxs-lookup"><span data-stu-id="478ba-106">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="478ba-107">更改联盟路由和媒体流量路由需要你为 Lync Server 2013 和 Lync Server 2010 Edge 服务器安排维护停机时间。</span><span class="sxs-lookup"><span data-stu-id="478ba-107">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="478ba-108">此整个过渡过程还意味着，在中断期间，联盟访问将不可用。</span><span class="sxs-lookup"><span data-stu-id="478ba-108">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="478ba-109">你应该将停机时间安排为预计最少的用户活动。</span><span class="sxs-lookup"><span data-stu-id="478ba-109">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="478ba-110">你还应向最终用户提供足够的通知。</span><span class="sxs-lookup"><span data-stu-id="478ba-110">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="478ba-111">为此停机安排相应的计划，并在你的组织内设置适当的期望值。</span><span class="sxs-lookup"><span data-stu-id="478ba-111">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="478ba-112">如果旧版 Lync Server 2010 Edge 服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN，则不支持本部分中的过程。</span><span class="sxs-lookup"><span data-stu-id="478ba-112">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="478ba-113">如果将旧边缘服务配置为使用相同的 FQDN，则必须首先将所有用户从 Lync Server 2010 迁移到 Lync Server 2013，然后在 Lync Server 2013 Edge 服务器上启用联盟之前解除 Lync Server 2010 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="478ba-113">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="478ba-114">如果你的 XMPP 联盟通过 Lync Server 2013 Edge 服务器路由，则旧版 Lync Server 2010 用户将无法与 XMPP 联盟伙伴通信，直到所有用户都已移动到 Lync Server 2013、XMPP 策略和证书已已配置，已在 Lync Server 2013 上配置了 XMPP 联盟合作伙伴，最后更新了 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="478ba-114">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="478ba-115">删除 Lync Server 2013 网站中的旧联合身份验证关联</span><span class="sxs-lookup"><span data-stu-id="478ba-115">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="478ba-116">在 Lync Server 2013 前端服务器上，在拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="478ba-116">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="478ba-117">在左窗格中，导航到位于 " **Lync 服务器**" 正下方的 "网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="478ba-117">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="478ba-118">右键单击网站，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-118">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="478ba-119">在左窗格中，选择 "**联盟路由**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-119">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="478ba-120">在 "**网站联合路由分配**" 下，清除 "**启用 SIP 联盟**" 复选框以通过旧版 Lync Server 2010 环境禁用联盟路由。</span><span class="sxs-lookup"><span data-stu-id="478ba-120">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="478ba-121">!["编辑属性" 对话框，"联盟路由" 页面](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg ""编辑属性" 对话框，"联盟路由" 页面")</span><span class="sxs-lookup"><span data-stu-id="478ba-121">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="478ba-122">单击 **"确定"** 以关闭 "编辑属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-122">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="478ba-123">从**拓扑生成器**中，选择顶级节点**Lync 服务器**。</span><span class="sxs-lookup"><span data-stu-id="478ba-123">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="478ba-124">从 "**操作**" 菜单中，单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-124">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="478ba-125">单击 "**下一步**" 完成发布过程，然后在发布过程完成时单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-125">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="478ba-126">将旧式边缘服务器配置为非联合边缘服务器</span><span class="sxs-lookup"><span data-stu-id="478ba-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="478ba-127">在左窗格中，导航到**Lync Server 2010**节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="478ba-127">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="478ba-128">右键单击边缘服务器，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="478ba-129">在左窗格中选择 "**常规**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-129">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="478ba-130">清除 "**为此 Edge 池启用联盟（端口5061）** " 复选框条目，然后选择 **"确定"** 关闭页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-130">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="478ba-131">![编辑属性，常规，清除启用联盟](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "编辑属性，常规，清除启用联盟")</span><span class="sxs-lookup"><span data-stu-id="478ba-131">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="478ba-132">从 "**操作**" 菜单中，选择 "**发布拓扑**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-132">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="478ba-133">**发布向导**完成后，单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="478ba-133">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="478ba-134">验证旧版 Edge 服务器的联盟是否已禁用。</span><span class="sxs-lookup"><span data-stu-id="478ba-134">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="478ba-135">![拓扑生成器，Edge 池，已禁用联合身份验证](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "拓扑生成器，Edge 池，已禁用联合身份验证")</span><span class="sxs-lookup"><span data-stu-id="478ba-135">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="478ba-136">在 Lync Server 2010 Edge 服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="478ba-136">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="478ba-137">从旧版 Lync Server 2010 Edge 服务器导出外部访问代理服务器证书以及私钥。</span><span class="sxs-lookup"><span data-stu-id="478ba-137">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="478ba-138">在 Lync Server 2013 Edge 服务器上，导入上一步中的 "访问代理服务器外部证书"。</span><span class="sxs-lookup"><span data-stu-id="478ba-138">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="478ba-139">将访问代理服务器外部证书分配给边缘服务器的 Lync Server 2013 外部接口。</span><span class="sxs-lookup"><span data-stu-id="478ba-139">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="478ba-140">Lync Server 2013 Edge 服务器的内部界面证书应由受信任的 CA 请求并被分配。</span><span class="sxs-lookup"><span data-stu-id="478ba-140">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="478ba-141">将 Lync Server 2010 联盟路由更改为使用 Lync Server 2013 Edge 服务器</span><span class="sxs-lookup"><span data-stu-id="478ba-141">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="478ba-142">从拓扑生成器的左窗格中，导航到**Lync Server 2013**节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="478ba-142">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="478ba-143">右键单击边缘服务器，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-143">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="478ba-144">在左窗格中选择 "**常规**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-144">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="478ba-145">选中 "为**此 Edge 池启用联盟（端口5061）** " 复选框条目，然后单击 **"确定"** 关闭页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-145">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="478ba-146">!["编辑属性" 对话框，"常规" 页面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg ""编辑属性" 对话框，"常规" 页面")</span><span class="sxs-lookup"><span data-stu-id="478ba-146">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="478ba-147">从 "**操作**" 菜单中，选择 "**发布拓扑**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-147">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="478ba-148">**发布向导**完成后，单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="478ba-148">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="478ba-149">验证**联盟（端口5061）** 是否设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-149">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="478ba-150">![拓扑生成器、Edge 池、已启用联盟](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "拓扑生成器、Edge 池、已启用联盟")</span><span class="sxs-lookup"><span data-stu-id="478ba-150">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="478ba-151">更新 Lync Server 2013 Edge 服务器联合身份验证下一跃点</span><span class="sxs-lookup"><span data-stu-id="478ba-151">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="478ba-152">从拓扑生成器的左窗格中，导航到**Lync Server 2013**节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="478ba-152">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="478ba-153">展开节点，右键单击列出的边缘服务器，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-153">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="478ba-154">在 "**常规**" 页面上的 "**下一跃点选择**" 下，从下拉列表中选择 "Lync Server 2013 池"。</span><span class="sxs-lookup"><span data-stu-id="478ba-154">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="478ba-155">!["编辑属性" 对话框，"下一跃点" 页面](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg ""编辑属性" 对话框，"下一跃点" 页面")</span><span class="sxs-lookup"><span data-stu-id="478ba-155">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="478ba-156">单击 **"确定"** 以关闭 "编辑属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-156">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="478ba-157">从**拓扑生成器**中，选择顶级节点**Lync 服务器**。</span><span class="sxs-lookup"><span data-stu-id="478ba-157">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="478ba-158">从 "**操作**" 菜单中，单击 "**发布拓扑**" 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="478ba-158">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="478ba-159">配置 Lync Server 2013 Edge 服务器出站媒体路径</span><span class="sxs-lookup"><span data-stu-id="478ba-159">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="478ba-160">从拓扑生成器的左窗格中，导航到**Lync Server 2013**节点，然后导航到**标准版前端服务器**或**企业版前端池**下的池。</span><span class="sxs-lookup"><span data-stu-id="478ba-160">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="478ba-161">右键单击该池，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-161">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="478ba-162">在 "**关联**" 部分中，选择 "**关联边缘池（适用于媒体组件）** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="478ba-162">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="478ba-163">![编辑属性，常规，关联边缘池](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "编辑属性，常规，关联边缘池")</span><span class="sxs-lookup"><span data-stu-id="478ba-163">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="478ba-164">从下拉框中，选择 Lync Server 2013 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="478ba-164">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="478ba-165">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-165">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="478ba-166">打开 Lync Server 2013 Edge 服务器联合身份验证</span><span class="sxs-lookup"><span data-stu-id="478ba-166">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="478ba-167">从拓扑生成器的左窗格中，导航到**Lync Server 2013**节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="478ba-167">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="478ba-168">展开节点，右键单击列出的边缘服务器，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-168">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="478ba-169">仅可对单个边缘池启用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="478ba-169">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="478ba-170">如果你有多个边缘池，请选择一个以用作联盟边缘池。</span><span class="sxs-lookup"><span data-stu-id="478ba-170">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="478ba-171">在 "**常规**" 页面上，验证 "为**此 Edge 池启用联盟（端口5061）** " 设置是否已选中。</span><span class="sxs-lookup"><span data-stu-id="478ba-171">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="478ba-172">!["编辑属性" 对话框，"常规" 页面](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg ""编辑属性" 对话框，"常规" 页面")</span><span class="sxs-lookup"><span data-stu-id="478ba-172">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="478ba-173">单击 **"确定"** 以关闭 "编辑属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-173">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="478ba-174">接下来，导航到 "网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="478ba-174">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="478ba-175">右键单击网站，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-175">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="478ba-176">在左窗格中，单击 "**联盟路由**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-176">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="478ba-177">在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后从列表中选择列出的 Lync server 2013 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="478ba-177">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="478ba-178">!["编辑属性"、"联盟路由" 页面](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg ""编辑属性"、"联盟路由" 页面")</span><span class="sxs-lookup"><span data-stu-id="478ba-178">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="478ba-179">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="478ba-179">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="478ba-180">对于多站点部署，请在每个网站上完成此过程。</span><span class="sxs-lookup"><span data-stu-id="478ba-180">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="478ba-181">发布边缘服务器配置更改</span><span class="sxs-lookup"><span data-stu-id="478ba-181">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="478ba-182">从**拓扑生成器**中，选择顶级节点**Lync 服务器**。</span><span class="sxs-lookup"><span data-stu-id="478ba-182">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="478ba-183">从 "**操作**" 菜单中，选择 "**发布拓扑**" 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="478ba-183">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="478ba-184">等待对部署中的所有池执行 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="478ba-184">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="478ba-185">您可能会看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="478ba-185">You may see the following message:</span></span><BR><span data-ttu-id="478ba-186"><STRONG>警告：该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中可能会发生这种情况。在这种情况下，仅有一台边缘服务器将主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要将多个联合边缘服务器部署为同时活动（即不是迁移方案），请验证所有联盟伙伴是否都在使用 Lync Server。验证外部 DNS SRV 记录是否列出所有启用联盟的边缘服务器。</STRONG></span><span class="sxs-lookup"><span data-stu-id="478ba-186"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="478ba-187">此警告是预期的，可以安全忽略。</span><span class="sxs-lookup"><span data-stu-id="478ba-187">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="478ba-188">配置 Lync Server 2013 Edge 服务器</span><span class="sxs-lookup"><span data-stu-id="478ba-188">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="478ba-189">使所有 Lync Server 2013 边缘服务器联机。</span><span class="sxs-lookup"><span data-stu-id="478ba-189">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="478ba-190">更新外部防火墙路由规则或硬件负载平衡器设置，以将外部访问（通常是端口443）和联盟（通常为端口5061）的 SIP 流量发送到 Lync Server 2013 Edge 服务器，而不是旧版边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="478ba-190">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="478ba-191">如果你没有硬件负载平衡器，你需要更新联合身份验证的 DNS A 记录，以解析到新的 Lync 服务器访问边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="478ba-191">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server.</span></span> <span data-ttu-id="478ba-192">若要通过最小的中断完成此操作，请减小外部 Lync Server 访问边缘 FQDN 的 TLL 值，以便在更新 DNS 以指向新的 Lync 服务器访问边缘时，将快速更新联合身份验证和远程访问。</span><span class="sxs-lookup"><span data-stu-id="478ba-192">To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="478ba-193">接下来，从每台边缘服务器计算机停止**Lync 服务器访问边缘**。</span><span class="sxs-lookup"><span data-stu-id="478ba-193">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="478ba-194">从每个旧式边缘服务器计算机上，从 "**管理工具**" 中打开 "**服务**" 小程序。</span><span class="sxs-lookup"><span data-stu-id="478ba-194">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="478ba-195">在 "服务" 列表中，找到 " **Lync Server Access Edge**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-195">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="478ba-196">右键单击服务名称，然后选择 "**停止**" 以停止该服务。</span><span class="sxs-lookup"><span data-stu-id="478ba-196">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="478ba-197">将 "启动类型" 设置为 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="478ba-197">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="478ba-198">单击 **"确定"** 以关闭 "**属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="478ba-198">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

