---
title: 配置联合路由和媒体流量
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 联盟是两个或多个 SIP 域之间的信任关系, 这些 SIP 域允许单独组织中的用户通过网络边界进行通信。 迁移到你的试点池后, 你需要从你以前的版本 Edge 服务器的联盟路径切换到 Skype for business Server 2019 Edge 服务器的联合路线。
ms.openlocfilehash: 50c10a4dced237e59c8dad12b5bdee1ef7d970fe
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239360"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="15a19-104">配置联合路由和媒体流量</span><span class="sxs-lookup"><span data-stu-id="15a19-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="15a19-105">联盟是两个或多个 SIP 域之间的信任关系, 这些 SIP 域允许单独组织中的用户通过网络边界进行通信。</span><span class="sxs-lookup"><span data-stu-id="15a19-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="15a19-106">迁移到试验池后, 您需要从您以前版本的边缘服务器的联盟路径切换到 Skype for business Server 2019 Edge 服务器的联盟路线。</span><span class="sxs-lookup"><span data-stu-id="15a19-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="15a19-107">使用以下过程可将你以前版本的 Edge 服务器和控制器中的联盟路由和媒体流量路由转换到 Skype for business Server 2019 Edge 服务器 (对于单站点部署)。</span><span class="sxs-lookup"><span data-stu-id="15a19-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="15a19-108">更改联盟路由和媒体流量路由需要你为 Skype for Business Server 2019 和早期版本 Edge 服务器安排维护停机时间。</span><span class="sxs-lookup"><span data-stu-id="15a19-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="15a19-109">此整个过渡过程还意味着, 在中断期间, 联盟访问将不可用。</span><span class="sxs-lookup"><span data-stu-id="15a19-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="15a19-110">你应该将停机时间安排为预计最少的用户活动。</span><span class="sxs-lookup"><span data-stu-id="15a19-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="15a19-111">你还应向最终用户提供足够的通知。</span><span class="sxs-lookup"><span data-stu-id="15a19-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="15a19-112">为此停机安排相应的计划, 并在你的组织内设置适当的期望值。</span><span class="sxs-lookup"><span data-stu-id="15a19-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="15a19-113">如果你的旧版 Edge 服务器配置为对访问边缘服务使用相同的 FQDN、Web 会议边缘服务和 A/V 边缘服务, 则不支持本部分中的过程。</span><span class="sxs-lookup"><span data-stu-id="15a19-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="15a19-114">如果将旧边缘服务配置为使用相同的 FQDN, 则必须首先迁移所有用户, 然后在 Skype for business Server 2019 Edge 服务器上启用联盟之前, 取消以前版本的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="15a19-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="15a19-115">如果你的 XMPP 联盟通过 Skype for Business Server 2019 Edge 服务器路由, 则以前版本中的用户将无法与 XMPP 联盟合作伙伴通信, 直到所有用户都已移动到 Skype for Business Server 2019、XMPP 策略和证书已配置, XMPP 联盟合作伙伴已在 Skype for Business Server 2019 上配置, 最后, 已更新 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="15a19-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="15a19-116">从 Skype for Business Server 2019 网站中删除旧式联合身份验证关联</span><span class="sxs-lookup"><span data-stu-id="15a19-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="15a19-117">在 Skype for business 服务器2019前端服务器上, 在拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="15a19-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="15a19-118">在左窗格中, 导航到位于 " **Skype For business" 服务器**正下方的 "网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="15a19-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="15a19-119">右键单击网站, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="15a19-120">在左窗格中, 选择 "**联盟路由**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="15a19-121">在 "**站点联合路由分配**" 下, 清除 "**启用 SIP 联盟**" 复选框以通过旧环境禁用联盟路由。</span><span class="sxs-lookup"><span data-stu-id="15a19-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="15a19-122">单击 **"确定"** 以关闭 "编辑属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="15a19-123">从**拓扑生成器**中, 选择顶部节点**Skype for business 服务器**。</span><span class="sxs-lookup"><span data-stu-id="15a19-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="15a19-124">从 "**操作**" 菜单中, 单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="15a19-125">单击 "**下一步**" 完成发布过程, 然后在发布过程完成时单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="15a19-126">将旧式边缘服务器配置为非联合边缘服务器</span><span class="sxs-lookup"><span data-stu-id="15a19-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="15a19-127">在左窗格中, 导航到 "旧安装" 节点, 然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="15a19-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="15a19-128">右键单击边缘服务器, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="15a19-129">在左窗格中选择 "**常规**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="15a19-130">清除 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框, 然后选择 **"确定"** 关闭页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="15a19-131">从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="15a19-132">**发布向导**完成后, 单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="15a19-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="15a19-133">验证拓扑生成器中是否已禁用旧版 Edge 服务器的联盟。</span><span class="sxs-lookup"><span data-stu-id="15a19-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="15a19-134">在旧版边缘服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="15a19-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="15a19-135">从旧边缘服务器导出外部访问代理服务器证书和私钥。</span><span class="sxs-lookup"><span data-stu-id="15a19-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="15a19-136">在 Skype for Business Server 2019 Edge 服务器上, 然后从上一步导入 "访问代理服务器外部证书"。</span><span class="sxs-lookup"><span data-stu-id="15a19-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="15a19-137">将访问代理服务器外部证书分配给 Edge 服务器的 Skype for business Server 2019 外部接口。</span><span class="sxs-lookup"><span data-stu-id="15a19-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="15a19-138">应从受信任的 CA 请求并分配 Skype for business Server 2019 Edge 服务器的内部界面证书。</span><span class="sxs-lookup"><span data-stu-id="15a19-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="15a19-139">将以前版本的联合身份验证路由更改为使用 Skype for Business Server 2019 Edge 服务器</span><span class="sxs-lookup"><span data-stu-id="15a19-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="15a19-140">在 "拓扑生成器" 中, 在左窗格中, 导航到 " **Skype For Business 服务器 2019** " 节点, 然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="15a19-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="15a19-141">右键单击边缘服务器, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="15a19-142">在左窗格中选择 "**常规**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="15a19-143">选中 "为**此 Edge 池启用联盟 (端口 5061)**" 复选框, 然后单击 **"确定"** 关闭页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="15a19-144">从 "**操作**" 菜单中, 选择 "**发布拓扑**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="15a19-145">**发布向导**完成后, 单击 "**完成**" 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="15a19-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="15a19-146">验证在拓扑结构生成器中是否已将 "**联盟" (端口 5061)** 设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="15a19-147">更新 Skype for Business Server 2019 Edge 服务器联合身份验证下一跃点</span><span class="sxs-lookup"><span data-stu-id="15a19-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="15a19-148">在 "拓扑生成器" 中, 在左窗格中, 导航到 " **Skype For Business 服务器 2019** " 节点, 然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="15a19-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="15a19-149">展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="15a19-150">在 "**常规**" 页面上的 "**下一跃点选择**" 下, 从下拉列表中选择 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="15a19-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="15a19-151">单击 **"确定"** 以关闭 "编辑属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="15a19-152">从**拓扑生成器**中, 选择顶部节点**Skype for business 服务器**。</span><span class="sxs-lookup"><span data-stu-id="15a19-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="15a19-153">从 "**操作**" 菜单中, 单击 "**发布拓扑**" 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="15a19-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="15a19-154">配置 Skype for Business Server 2019 Edge 服务器出站媒体路径</span><span class="sxs-lookup"><span data-stu-id="15a19-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="15a19-155">从拓扑生成器的左窗格中, 导航到**Skype For Business Server 2019**节点, 然后导航到**标准版前端服务器**或**企业版前端池**下的池。</span><span class="sxs-lookup"><span data-stu-id="15a19-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="15a19-156">右键单击该池, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="15a19-157">在 "**关联**" 部分中, 选择 "**关联边缘池 (适用于媒体组件)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="15a19-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="15a19-158">从下拉框中, 选择 Skype for Business Server 2019 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="15a19-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="15a19-159">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="15a19-160">打开 Skype for Business Server 2019 Edge 服务器联合体</span><span class="sxs-lookup"><span data-stu-id="15a19-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="15a19-161">在 "拓扑生成器" 中, 在左窗格中, 导航到 " **Skype For Business 服务器 2019** " 节点, 然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="15a19-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="15a19-162">展开节点, 右键单击列出的边缘服务器, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="15a19-163">仅可对单个边缘池启用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="15a19-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="15a19-164">如果你有多个边缘池, 请选择一个以用作联盟边缘池。</span><span class="sxs-lookup"><span data-stu-id="15a19-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="15a19-165">在 "**常规**" 页面上, 验证已选中 "**为此 Edge 池启用联盟 (端口 5061)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="15a19-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="15a19-166">单击 **"确定"** 以关闭 "编辑属性" 页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="15a19-167">导航到 "网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="15a19-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="15a19-168">右键单击网站, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="15a19-169">在左窗格中, 单击 "**联盟路由**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="15a19-170">在 "**站点联合路由分配**" 下, 选择 "**启用 SIP 联盟**", 然后从列表中选择列出的 Skype For Business server 2019 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="15a19-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="15a19-171">单击 **"确定"** 以关闭 "**编辑属性**" 页面。</span><span class="sxs-lookup"><span data-stu-id="15a19-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="15a19-172">对于多站点部署, 请在每个网站上完成此过程。</span><span class="sxs-lookup"><span data-stu-id="15a19-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="15a19-173">发布边缘服务器配置更改</span><span class="sxs-lookup"><span data-stu-id="15a19-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="15a19-174">从**拓扑生成器**中, 选择顶部节点**Skype for business 服务器**。</span><span class="sxs-lookup"><span data-stu-id="15a19-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="15a19-175">从 "**操作**" 菜单中, 选择 "**发布拓扑**" 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="15a19-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="15a19-176">等待对部署中的所有池执行 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="15a19-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15a19-177">您可能会看到以下消息:**警告: 该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中可能会发生这种情况。在这种情况下, 仅有一台边缘服务器将主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要将多个联合边缘服务器部署为同时活动 (即不是迁移方案), 请验证所有联盟伙伴是否都在使用 Skype for Business 服务器。验证外部 DNS SRV 记录是否列出所有启用联盟的边缘服务器。**</span><span class="sxs-lookup"><span data-stu-id="15a19-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="15a19-178">此警告是预期的, 可以安全忽略。</span><span class="sxs-lookup"><span data-stu-id="15a19-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="15a19-179">配置 Skype for Business Server 2019 Edge 服务器</span><span class="sxs-lookup"><span data-stu-id="15a19-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="15a19-180">使所有 Skype for business 服务器2019边缘服务器联机。</span><span class="sxs-lookup"><span data-stu-id="15a19-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="15a19-181">更新外部防火墙路由规则或硬件负载平衡器设置, 以将外部访问 (通常为端口 443) 和联盟 (通常为端口 5061) 的 SIP 流量发送到 Skype for business Server 2019 Edge 服务器, 而不是旧版边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="15a19-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15a19-182">如果你没有硬件负载平衡器, 则需要更新联合身份验证的 DNS A 记录, 以解析为新的 Skype for Business 服务器访问边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="15a19-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="15a19-183">若要以最小的中断完成此操作, 请减少外部 Skype for business 服务器访问边缘 FQDN 的 TLL 值, 以便在更新 DNS 以指向新的 Skype for Business 服务器访问边缘时, 将快速更新联盟和远程访问。</span><span class="sxs-lookup"><span data-stu-id="15a19-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="15a19-184">停止每台边缘服务器计算机的**Skype For Business 服务器访问边缘**。</span><span class="sxs-lookup"><span data-stu-id="15a19-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="15a19-185">从每个旧式边缘服务器计算机上, 从 "**管理工具**" 中打开 "**服务**" 小程序。</span><span class="sxs-lookup"><span data-stu-id="15a19-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="15a19-186">在 "服务" 列表中, 找到 " **Skype for Business 服务器访问边缘**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="15a19-187">右键单击服务名称, 然后选择 "**停止**" 以停止该服务。</span><span class="sxs-lookup"><span data-stu-id="15a19-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="15a19-188">将 "启动类型" 设置为 "**已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="15a19-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="15a19-189">单击 **"确定"** 以关闭 "**属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="15a19-189">Click **OK** to close the **Properties** window.</span></span> 
    

