---
title: 配置联盟路由和媒体流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。 迁移到你的试点池之后，需要从先前版本边缘服务器的联合路由转换为 Skype for Business Server 2019 边缘服务器的联合路由。
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754032"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="a35c4-104">配置联盟路由和媒体流量</span><span class="sxs-lookup"><span data-stu-id="a35c4-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="a35c4-105">联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。</span><span class="sxs-lookup"><span data-stu-id="a35c4-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="a35c4-106">迁移到你的试点池之后，需要从以前版本的边缘服务器的联合路由转换为 Skype for Business Server 2019 边缘服务器的联合路由。</span><span class="sxs-lookup"><span data-stu-id="a35c4-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="a35c4-107">使用以下过程可将联合路由和媒体流量路由从以前版本的边缘服务器和控制器转换为 Skype for business Server 2019 Edge 服务器（针对单站点部署）。</span><span class="sxs-lookup"><span data-stu-id="a35c4-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a35c4-108">若要更改联合路由和媒体流量路由，需要为 Skype for Business Server 2019 和早期版本边缘服务器安排维护停机时间。</span><span class="sxs-lookup"><span data-stu-id="a35c4-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="a35c4-109">整个转换过程还意味着服务中断期间无法进行联盟访问。</span><span class="sxs-lookup"><span data-stu-id="a35c4-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="a35c4-110">应将停机时间安排在预计用户活动最少的时间段内。</span><span class="sxs-lookup"><span data-stu-id="a35c4-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="a35c4-111">还应向最终用户提供包含丰富信息的通知。</span><span class="sxs-lookup"><span data-stu-id="a35c4-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="a35c4-112">相应地规划这次服务中断并正确设置组织的期望。</span><span class="sxs-lookup"><span data-stu-id="a35c4-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a35c4-113">如果您的旧边缘服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN，则不支持本节中的过程。</span><span class="sxs-lookup"><span data-stu-id="a35c4-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="a35c4-114">如果将旧边缘服务配置为使用相同的 FQDN，则必须先迁移所有用户，然后在 Skype for Business Server 2019 边缘服务器上启用联合之前，解除以前版本的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a35c4-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a35c4-115">如果您的 XMPP 联盟通过 Skype for Business Server 2019 边缘服务器进行路由，则以前版本中的用户将无法与 XMPP 联盟伙伴通信，直到所有用户都已移动到 Skype for Business Server 2019、已配置 XMPP 策略和证书、已在 Skype for Business Server 2019 上配置 XMPP 联盟伙伴，最后更新了 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="a35c4-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="a35c4-116">从 Skype for Business Server 2019 网站中删除旧版联合身份验证关联</span><span class="sxs-lookup"><span data-stu-id="a35c4-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="a35c4-117">在 Skype for Business Server 2019 前端服务器上，在拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="a35c4-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="a35c4-118">在左窗格中，导航到位于**Skype For Business Server**正下方的 "网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="a35c4-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="a35c4-119">右键单击站点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="a35c4-120">在左侧窗格中，选择“联盟路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="a35c4-121">在 "**站点联合路由分配**" 下，清除 "**启用 SIP 联盟**" 复选框以禁用通过旧环境的联盟路由。</span><span class="sxs-lookup"><span data-stu-id="a35c4-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="a35c4-122">单击“确定”\*\*\*\* 关闭“编辑属性”页。</span><span class="sxs-lookup"><span data-stu-id="a35c4-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="a35c4-123">从**拓扑生成器**中，选择顶部节点 " **Skype for business Server**"。</span><span class="sxs-lookup"><span data-stu-id="a35c4-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="a35c4-124">从“操作”\*\*\*\* 菜单上，单击“发布拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="a35c4-125">单击 "**下一步**" 完成发布过程，然后在发布过程完成后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="a35c4-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="a35c4-126">将旧边缘服务器配置为非联盟边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a35c4-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="a35c4-127">在左窗格中，导航到 "旧安装" 节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="a35c4-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a35c4-128">右键单击该边缘服务器，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a35c4-129">在左窗格中，选择“常规”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="a35c4-130">清除 "**为此边缘池启用联盟（端口5061）** " 复选框，然后选择 **"确定"** 关闭该页面。</span><span class="sxs-lookup"><span data-stu-id="a35c4-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="a35c4-131">从“操作”\*\*\*\* 菜单中，选择“发布部署”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a35c4-132">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\* 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="a35c4-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="a35c4-133">验证是否在拓扑生成器中禁用了旧版边缘服务器的联盟。</span><span class="sxs-lookup"><span data-stu-id="a35c4-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="a35c4-134">在旧版边缘服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="a35c4-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="a35c4-135">从旧版边缘服务器导出外部访问代理证书和私钥。</span><span class="sxs-lookup"><span data-stu-id="a35c4-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="a35c4-136">在 Skype for Business Server 2019 边缘服务器上，然后导入上一步中的访问代理外部证书。</span><span class="sxs-lookup"><span data-stu-id="a35c4-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="a35c4-137">将访问代理外部证书分配给边缘服务器的 Skype for Business Server 2019 外部接口。</span><span class="sxs-lookup"><span data-stu-id="a35c4-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="a35c4-138">应从受信任的 CA 请求并分配 Skype for business Server 2019 边缘服务器的内部接口证书。</span><span class="sxs-lookup"><span data-stu-id="a35c4-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="a35c4-139">将以前版本的联盟路由更改为使用 Skype for Business Server 2019 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a35c4-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="a35c4-140">从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="a35c4-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a35c4-141">右键单击该边缘服务器，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a35c4-142">在左窗格中，选择“常规”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="a35c4-143">选中 "为**此边缘池启用联盟（端口5061）**" 复选框，然后单击 **"确定"** 关闭该页面。</span><span class="sxs-lookup"><span data-stu-id="a35c4-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="a35c4-144">从“操作”\*\*\*\* 菜单中，选择“发布部署”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="a35c4-145">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\* 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="a35c4-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="a35c4-146">验证是否已在拓扑生成器中将**联合身份验证（端口5061）** 设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="a35c4-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="a35c4-147">更新 Skype for Business Server 2019 边缘服务器联合下一个跃点</span><span class="sxs-lookup"><span data-stu-id="a35c4-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="a35c4-148">从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="a35c4-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a35c4-149">展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="a35c4-150">在 "**常规**" 页面的 "**下一跃点选择**" 下，从下拉列表中选择 "Skype for business Server 2019 池"。</span><span class="sxs-lookup"><span data-stu-id="a35c4-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="a35c4-151">单击“确定”\*\*\*\* 关闭“编辑属性”页。</span><span class="sxs-lookup"><span data-stu-id="a35c4-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="a35c4-152">从**拓扑生成器**中，选择顶部节点 " **Skype for business Server**"。</span><span class="sxs-lookup"><span data-stu-id="a35c4-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="a35c4-153">从“操作”\*\*\*\* 菜单中，单击“发布拓扑”\*\*\*\* 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="a35c4-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="a35c4-154">配置 Skype for Business Server 2019 边缘服务器出站媒体路径</span><span class="sxs-lookup"><span data-stu-id="a35c4-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="a35c4-155">从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "低于**Standard edition 前端服务器**" 或 " **Enterprise Edition 前端池**" 的池。</span><span class="sxs-lookup"><span data-stu-id="a35c4-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="a35c4-156">右键单击该池，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="a35c4-157">在“关联”\*\*\*\* 部分，选中“关联边缘池(用于媒体组件)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="a35c4-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="a35c4-158">从下拉框中，选择 Skype for Business Server 2019 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a35c4-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="a35c4-159">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="a35c4-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="a35c4-160">启用 Skype for Business Server 2019 边缘服务器联盟</span><span class="sxs-lookup"><span data-stu-id="a35c4-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="a35c4-161">从拓扑生成器的左侧窗格中，导航到 " **Skype For Business Server 2019** " 节点，然后导航到 "**边缘池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="a35c4-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="a35c4-162">展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a35c4-163">仅可为单个边缘池启用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="a35c4-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="a35c4-164">如果具有多个边缘池，请选择一个用作联盟边缘池。</span><span class="sxs-lookup"><span data-stu-id="a35c4-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="a35c4-165">在 "**常规**" 页面上，验证是否已选中 "**为此边缘池启用联盟（端口5061）** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a35c4-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="a35c4-166">单击“确定”\*\*\*\* 关闭“编辑属性”页。</span><span class="sxs-lookup"><span data-stu-id="a35c4-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="a35c4-167">导航到 "网站" 节点。</span><span class="sxs-lookup"><span data-stu-id="a35c4-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="a35c4-168">右键单击站点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="a35c4-169">在左窗格中，单击“联盟路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="a35c4-170">在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后从列表中选择列出的 Skype For Business Server 2019 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a35c4-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="a35c4-171">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="a35c4-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="a35c4-172">对于多站点部署，在每个站点上完成该过程。</span><span class="sxs-lookup"><span data-stu-id="a35c4-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="a35c4-173">发布边缘服务器配置更改</span><span class="sxs-lookup"><span data-stu-id="a35c4-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="a35c4-174">从**拓扑生成器**中，选择顶部节点 " **Skype for business Server**"。</span><span class="sxs-lookup"><span data-stu-id="a35c4-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="a35c4-175">从“操作”\*\*\*\* 菜单中，选择“发布拓扑”\*\*\*\* 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="a35c4-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="a35c4-176">稍待片刻以便在部署中的所有池间执行 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="a35c4-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a35c4-177">您可能会看到以下消息：**警告：该拓扑包含多个联合边缘服务器。在迁移到产品的较新版本的过程中，可能会发生这种情况。在这种情况下，将只有一台边缘服务器主动用于联盟。验证外部 DNS SRV 记录是否指向正确的边缘服务器。如果要将多个联合边缘服务器部署为同时处于活动状态（即不是迁移方案），请验证所有联盟伙伴是否都在使用 Skype for Business Server。验证外部 DNS SRV 记录是否列出所有启用了联合身份验证的边缘服务器。**</span><span class="sxs-lookup"><span data-stu-id="a35c4-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="a35c4-178">该警告是预期警告，可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="a35c4-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="a35c4-179">配置 Skype for Business Server 2019 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a35c4-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="a35c4-180">使所有 Skype for Business Server 2019 边缘服务器联机。</span><span class="sxs-lookup"><span data-stu-id="a35c4-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="a35c4-181">更新外部防火墙路由规则或硬件负载平衡器设置以将外部访问的 SIP 通信（通常是端口443）和联合身份验证（通常是端口5061）发送到 Skype for business Server 2019 边缘服务器，而不是旧边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a35c4-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a35c4-182">如果没有硬件负载平衡器，则需要更新联合的 DNS A 记录以解析为新的 Skype for Business Server 访问边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="a35c4-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="a35c4-183">若要实现此目的，最大程度地减少中断，请减小外部 Skype for Business Server 访问边缘 FQDN 的 TLL 值，以便在将 DNS 更新为指向新的 Skype for Business Server 访问边缘时，将快速更新联合身份验证和远程访问。</span><span class="sxs-lookup"><span data-stu-id="a35c4-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="a35c4-184">从每台边缘服务器计算机停止**Skype For Business Server 访问边缘**。</span><span class="sxs-lookup"><span data-stu-id="a35c4-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="a35c4-185">从每个旧边缘服务器计算机上，从 "**管理工具**" 中打开 "**服务**" 小程序。</span><span class="sxs-lookup"><span data-stu-id="a35c4-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="a35c4-186">在 "服务" 列表中，查找**Skype For Business Server 访问边缘**。</span><span class="sxs-lookup"><span data-stu-id="a35c4-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="a35c4-187">右键单击服务名称，然后选择“停止”\*\*\*\* 以停止该服务。</span><span class="sxs-lookup"><span data-stu-id="a35c4-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="a35c4-188">将“启动”类型设置为“已禁用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a35c4-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="a35c4-189">单击“确定”\*\*\*\* 关闭“属性”\*\*\*\* 窗口。</span><span class="sxs-lookup"><span data-stu-id="a35c4-189">Click **OK** to close the **Properties** window.</span></span> 
    

