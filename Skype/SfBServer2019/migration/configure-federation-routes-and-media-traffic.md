---
title: 配置联合路由和媒体流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 联盟是两个或多个 SIP 域，它允许不同组织跨网络边界进行通信中的用户之间的信任关系。 迁移到试点池后，您需要转换您 Skype 的联盟路由到您旧版边缘服务器的联盟路由从业务 Server 2019 边缘服务器。
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880226"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="7a3be-104">配置联合路由和媒体流量</span><span class="sxs-lookup"><span data-stu-id="7a3be-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="7a3be-105">联盟是两个或多个 SIP 域，它允许不同组织跨网络边界进行通信中的用户之间的信任关系。</span><span class="sxs-lookup"><span data-stu-id="7a3be-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="7a3be-106">迁移到试点池后，您在需要转换到您的 Skype 的联盟路由的早期版本的边缘服务器联盟路由从业务 Server 2019 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7a3be-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="7a3be-107">使用以下过程的联盟路由和媒体流量路由从早期版本的边缘服务器和控制器到您的 Skype 业务 Server 2019 边缘服务器，转换为单站点部署。</span><span class="sxs-lookup"><span data-stu-id="7a3be-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a3be-108">更改联盟路由和媒体流量路由需要业务服务器 2019年和早期版本边缘服务器的 Skype 安排维护停机时间。</span><span class="sxs-lookup"><span data-stu-id="7a3be-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="7a3be-109">此整个转换过程还意味着联盟的访问将不可用中断的持续时间内。</span><span class="sxs-lookup"><span data-stu-id="7a3be-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="7a3be-110">当您预期最少的用户活动的时间，应安排停机时间。</span><span class="sxs-lookup"><span data-stu-id="7a3be-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="7a3be-111">您还应向最终用户提供足够的通知。</span><span class="sxs-lookup"><span data-stu-id="7a3be-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="7a3be-112">此中断并设置适当的相应规划组织内的预期。</span><span class="sxs-lookup"><span data-stu-id="7a3be-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7a3be-113">如果旧版边缘服务器配置为使用相同的 FQDN 为访问边缘服务、 Web 会议边缘服务和 A / V 边缘服务，本节中的过程不受支持。</span><span class="sxs-lookup"><span data-stu-id="7a3be-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="7a3be-114">如果旧的边缘服务配置为使用相同的 FQDN，您必须首先迁移所有用户，然后在启用 Business Server 2019 边缘服务器上的 Skype 联合身份验证之前停用旧版边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7a3be-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7a3be-115">如果 XMPP 联盟路由通过 Skype 业务 Server 2019 边缘服务器，在早期版本的用户将不能与 XMPP 联盟伙伴进行通信，直到所有用户都移动到 Skype 的业务服务器 2019，XMPP 策略和已配置证书、 已进行了业务服务器 2019 Skype 上配置 XMPP 联盟的伙伴和最后，已更新 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="7a3be-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="7a3be-116">若要从 Skype 业务服务器 2019年网站中删除旧联盟关联</span><span class="sxs-lookup"><span data-stu-id="7a3be-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="7a3be-117">业务服务器 2019年前端服务器的 Skype，在拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="7a3be-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="7a3be-118">在左窗格中，导航到网站节点，位于**Skype 业务服务器**的正下方。</span><span class="sxs-lookup"><span data-stu-id="7a3be-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="7a3be-119">右键单击站点，，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="7a3be-120">在左窗格中，选择**联盟路由**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="7a3be-121">在**站点联盟路由分配**下，请清除**启用 SIP 联盟**复选框，若要禁用联盟路由通过旧环境。</span><span class="sxs-lookup"><span data-stu-id="7a3be-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="7a3be-122">单击**确定**以关闭编辑属性页。</span><span class="sxs-lookup"><span data-stu-id="7a3be-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="7a3be-123">从**拓扑生成器**中，选择顶层节点**Skype 业务服务器**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="7a3be-124">从**操作**菜单中，单击**发布拓扑**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="7a3be-125">**下一步**完成发布过程中，单击，然后单击**完成**完成发布过程后。</span><span class="sxs-lookup"><span data-stu-id="7a3be-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="7a3be-126">若要配置为非联盟边缘服务器的旧的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="7a3be-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="7a3be-127">在左窗格中，依次导航到旧安装节点和**边缘池**节点。</span><span class="sxs-lookup"><span data-stu-id="7a3be-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="7a3be-128">右键单击边缘服务器，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="7a3be-129">在左窗格中，选择**常规**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="7a3be-130">清除**为此边缘池 （端口 5061） 启用联盟**复选框，然后选择**确定**关闭页面。</span><span class="sxs-lookup"><span data-stu-id="7a3be-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="7a3be-131">从**操作**菜单中，选择**发布拓扑**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7a3be-132">**发布向导**完成后，单击**完成**以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="7a3be-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="7a3be-133">验证在拓扑生成器中已禁用旧边缘服务器的联盟。</span><span class="sxs-lookup"><span data-stu-id="7a3be-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="7a3be-134">在旧边缘服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="7a3be-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="7a3be-135">导出外部访问代理证书及私钥，从旧的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7a3be-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="7a3be-136">在业务 2019年边缘服务器和导入的 Skype 的访问代理外部证书上一步。</span><span class="sxs-lookup"><span data-stu-id="7a3be-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="7a3be-137">将访问代理外部证书分配给边缘服务器外部接口业务服务器 2019 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a3be-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="7a3be-138">应从受信任的 CA 请求和分配 Skype 业务 Server 2019 边缘服务器的内部接口证书。</span><span class="sxs-lookup"><span data-stu-id="7a3be-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="7a3be-139">早期版本的联盟路由更改为 Skype 用于业务 Server 2019 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="7a3be-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="7a3be-140">从拓扑生成器的左窗格中导航到**业务服务器 2019年的 Skype**节点和**边缘池**节点。</span><span class="sxs-lookup"><span data-stu-id="7a3be-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="7a3be-141">右键单击边缘服务器，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="7a3be-142">在左窗格中，选择**常规**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="7a3be-143">对于**为此边缘池 （端口 5061） 启用联盟**，请选中复选框，然后单击**确定**以关闭页。</span><span class="sxs-lookup"><span data-stu-id="7a3be-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="7a3be-144">从**操作**菜单中，选择**发布拓扑**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7a3be-145">**发布向导**完成后，单击**完成**以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="7a3be-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="7a3be-146">确认**联盟 （端口 5061）** 设置为**已启用**在拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="7a3be-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="7a3be-147">若要更新 Skype 业务 Server 2019 边缘服务器联盟下一个跃点</span><span class="sxs-lookup"><span data-stu-id="7a3be-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="7a3be-148">从拓扑生成器的左窗格中导航到**业务服务器 2019年的 Skype**节点和**边缘池**节点。</span><span class="sxs-lookup"><span data-stu-id="7a3be-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="7a3be-149">展开节点，右键单击列出，边缘服务器，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="7a3be-150">在**常规**页面，**下一个跃点选择**下，从列表中选择下拉业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a3be-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="7a3be-151">单击**确定**以关闭编辑属性页。</span><span class="sxs-lookup"><span data-stu-id="7a3be-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="7a3be-152">从**拓扑生成器**中，选择顶层节点**Skype 业务服务器**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="7a3be-153">从**操作**菜单中，单击**发布拓扑**并完成向导。</span><span class="sxs-lookup"><span data-stu-id="7a3be-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="7a3be-154">若要配置 Skype 业务 Server 2019 边缘服务器出站媒体路径</span><span class="sxs-lookup"><span data-stu-id="7a3be-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="7a3be-155">从拓扑生成器的左窗格中导航到**业务服务器 2019年的 Skype**节点和**Standard Edition 前端服务器**或**Enterprise Edition 前端池**下方的池。</span><span class="sxs-lookup"><span data-stu-id="7a3be-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="7a3be-156">右键单击池，，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="7a3be-157">在**关联**部分中，选择**关联边缘池 （用于媒体组件）** 复选框。</span><span class="sxs-lookup"><span data-stu-id="7a3be-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="7a3be-158">从下拉列表框中，选择 Skype 业务 Server 2019 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="7a3be-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="7a3be-159">单击**确定**以关闭**编辑属性**页。</span><span class="sxs-lookup"><span data-stu-id="7a3be-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="7a3be-160">打开 Skype 业务 Server 2019 边缘服务器联盟</span><span class="sxs-lookup"><span data-stu-id="7a3be-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="7a3be-161">从拓扑生成器的左窗格中导航到**业务服务器 2019年的 Skype**节点和**边缘池**节点。</span><span class="sxs-lookup"><span data-stu-id="7a3be-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="7a3be-162">展开节点，右键单击列出，边缘服务器，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="7a3be-163">仅可以为单个边缘池启用联盟。</span><span class="sxs-lookup"><span data-stu-id="7a3be-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="7a3be-164">如果您有多个边缘池，请选择一个要用作联盟的边缘池。</span><span class="sxs-lookup"><span data-stu-id="7a3be-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="7a3be-165">在**常规**页上，验证已选中**为此边缘池 (端口 5061) 启用联盟**复选框。</span><span class="sxs-lookup"><span data-stu-id="7a3be-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="7a3be-166">单击**确定**以关闭编辑属性页。</span><span class="sxs-lookup"><span data-stu-id="7a3be-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="7a3be-167">导航到站点节点。</span><span class="sxs-lookup"><span data-stu-id="7a3be-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="7a3be-168">右键单击站点，，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="7a3be-169">在左窗格中，单击**联盟路由**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="7a3be-170">在**站点联盟路由分配**下选择**启用 SIP 联盟**，，然后从列表选择列出的业务服务器 2019年边缘服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a3be-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="7a3be-171">单击**确定**以关闭**编辑属性**页。</span><span class="sxs-lookup"><span data-stu-id="7a3be-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="7a3be-172">对于多站点部署，完成此过程在每个站点。</span><span class="sxs-lookup"><span data-stu-id="7a3be-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="7a3be-173">发布边缘服务器配置更改</span><span class="sxs-lookup"><span data-stu-id="7a3be-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="7a3be-174">从**拓扑生成器**中，选择顶层节点**Skype 业务服务器**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="7a3be-175">从**操作**菜单中，选择**发布拓扑**并完成向导。</span><span class="sxs-lookup"><span data-stu-id="7a3be-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="7a3be-176">等待在部署中的所有池间都执行 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="7a3be-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7a3be-177">您可能会看到以下消息：**警告： 拓扑包含多个联盟的边缘服务器。这可以对该产品的较新版本的迁移过程中出现。在这种情况下，只有一台边缘服务器将主动使用实现联合身份验证。验证外部 DNS SRV 记录指向正确的边缘服务器。如果您想要部署多个联合身份验证边缘服务器可同时活动 （即，不迁移方案中），验证所有联盟的伙伴的业务服务器使用 Skype。验证外部 DNS SRV 记录列出所有启用联盟的边缘服务器。**</span><span class="sxs-lookup"><span data-stu-id="7a3be-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="7a3be-178">该警告预期警告，可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="7a3be-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="7a3be-179">为业务 Server 2019 边缘服务器配置 Skype</span><span class="sxs-lookup"><span data-stu-id="7a3be-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="7a3be-180">将所有 Skype 业务 Server 2019 边缘服务器联机。</span><span class="sxs-lookup"><span data-stu-id="7a3be-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="7a3be-181">更新外部防火墙的路由规则或硬件负载平衡器设置发送外部访问的 SIP 流量 （通常为端口 443） 和联合 （通常为端口 5061） 到业务服务器 2019年边缘服务器，而不是旧边缘服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7a3be-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7a3be-182">如果您没有硬件负载平衡器，您需要更新联合身份验证将解析为业务服务器访问边缘服务器的新 Skype 的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="7a3be-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="7a3be-183">实现这一点中断降至最低，减少 TLL 值的外部 Skype 业务服务器访问边缘 fqdn，以便在 DNS 更新为指向新的 Skype 业务访问边缘服务器的联盟和远程访问将更新快速。</span><span class="sxs-lookup"><span data-stu-id="7a3be-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="7a3be-184">停止从每台边缘服务器计算机**的业务 Server 访问边缘的 Skype** 。</span><span class="sxs-lookup"><span data-stu-id="7a3be-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="7a3be-185">从每台旧的边缘服务器计算机，打开**管理工具**中的**服务**小程序。</span><span class="sxs-lookup"><span data-stu-id="7a3be-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="7a3be-186">在服务列表中，找到**Skype 的业务 Server 访问边缘**。</span><span class="sxs-lookup"><span data-stu-id="7a3be-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="7a3be-187">右键单击服务名称，并选择**停止**以停止该服务。</span><span class="sxs-lookup"><span data-stu-id="7a3be-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="7a3be-188">设置为**已禁用**的启动类型。</span><span class="sxs-lookup"><span data-stu-id="7a3be-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="7a3be-189">单击**确定**以关闭**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="7a3be-189">Click **OK** to close the **Properties** window.</span></span> 
    

