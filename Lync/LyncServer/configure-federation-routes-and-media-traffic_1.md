---
title: 配置联盟路由和媒体流量
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754958"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="74779-102">配置联盟路由和媒体流量</span><span class="sxs-lookup"><span data-stu-id="74779-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="74779-103">联盟是两个或更多 SIP 域之间的一种信任关系，它允许不同组织中的用户跨越网络边界进行通信。</span><span class="sxs-lookup"><span data-stu-id="74779-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="74779-104">在迁移到 Lync Server 2013 引导池之后，需要从 Microsoft Office 通信服务器 2007 R2 边缘服务器的联合路由转换为 Lync Server 2013 边缘服务器的联合路由。</span><span class="sxs-lookup"><span data-stu-id="74779-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="74779-105">使用以下过程将联合路由和媒体流量路由从 Office 通信服务器 2007 R2 边缘服务器和控制器转换为 Lync Server 2013 边缘服务器，以实现单站点部署。</span><span class="sxs-lookup"><span data-stu-id="74779-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="74779-106">若要更改联合路由和媒体流量路由，需要为 Lync Server 2013 和 Office 通信服务器 2007 R2 边缘服务器安排维护停机时间。</span><span class="sxs-lookup"><span data-stu-id="74779-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="74779-107">整个转换过程还意味着服务中断期间无法进行联盟访问。</span><span class="sxs-lookup"><span data-stu-id="74779-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="74779-108">应将停机时间安排在预计用户活动最少的时间段内。</span><span class="sxs-lookup"><span data-stu-id="74779-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="74779-109">还应向最终用户提供包含丰富信息的通知。</span><span class="sxs-lookup"><span data-stu-id="74779-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="74779-110">相应地规划这次服务中断并正确设置组织的期望。</span><span class="sxs-lookup"><span data-stu-id="74779-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="74779-111">如果您的旧版 Office 通信服务器 2007 R2 边缘服务器配置为对访问边缘服务、Web 会议边缘服务和 A/V 边缘服务使用相同的 FQDN，则不支持此部分中的过程将联合身份验证设置转换为 Lync Server 2013 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="74779-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="74779-112">如果将旧边缘服务配置为使用相同的 FQDN，则必须首先将所有用户从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013，然后在 Lync Server 2013 边缘服务器上启用联合之前，先停止 Office 通信服务器 2007 R2 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="74779-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="74779-113">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="74779-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="74779-114"><A href="move-remaining-users-to-lync-server-2013_1.md">将其余用户移动到 Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="74779-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="74779-115">"删除服务器和服务器角色"<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="74779-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="74779-116">如果您的 XMPP 联盟通过 Lync Server 2013 边缘服务器路由，则旧版 Office 通信服务器 2007 R2 用户将无法与 XMPP 联盟伙伴通信，直到所有用户都已移动到 Lync Server 2013、已配置 XMPP 策略和证书、已在 Lync Server 2013 上配置了 XMPP 联盟伙伴，最后更新了 DNS 条目。</span><span class="sxs-lookup"><span data-stu-id="74779-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="74779-117">若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="74779-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="74779-118">还可以委派用于添加服务器角色的相应用户权限。</span><span class="sxs-lookup"><span data-stu-id="74779-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="74779-119">有关详细信息，请参阅 Standard Edition server 或 Enterprise Edition server Deployment 文档中的 "[在 Lync Server 2013 中委派安装程序权限](lync-server-2013-delegate-setup-permissions.md)"。</span><span class="sxs-lookup"><span data-stu-id="74779-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="74779-120">对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="74779-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="74779-121">将旧联盟关联从 Lync Server 2013 站点中删除</span><span class="sxs-lookup"><span data-stu-id="74779-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="74779-122">使用拓扑生成器打开试点池拓扑。</span><span class="sxs-lookup"><span data-stu-id="74779-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="74779-123">在左窗格中，导航到站点节点。</span><span class="sxs-lookup"><span data-stu-id="74779-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="74779-124">右键单击站点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="74779-125">在左窗格中，选择“联盟路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="74779-126">在“站点联盟路由分配”下，清除“启用 SIP 联盟”\*\*\*\* 旁边的复选框以通过“BackCompatSite”\*\*\*\* 禁用联盟路由。</span><span class="sxs-lookup"><span data-stu-id="74779-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="74779-127">!["编辑属性" 对话框（联合路由）](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg ""编辑属性" 对话框（联合路由）")</span><span class="sxs-lookup"><span data-stu-id="74779-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="74779-128">单击“确定”\*\*\*\* 关闭“编辑属性”页。</span><span class="sxs-lookup"><span data-stu-id="74779-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="74779-129">从“拓扑生成器”\*\*\*\* 中，选择顶部节点“Lync Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="74779-130">从“操作”\*\*\*\* 菜单中，单击“发布拓扑”\*\*\*\* 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="74779-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="74779-131">将旧边缘服务器配置为非联盟边缘服务器</span><span class="sxs-lookup"><span data-stu-id="74779-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="74779-132">从“拓扑生成器”\*\*\*\* 的“操作”\*\*\*\* 菜单中，单击“合并 Office Communications Server 2007 R2 拓扑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="74779-133">单击“下一步”\*\*\*\* 继续。</span><span class="sxs-lookup"><span data-stu-id="74779-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="74779-134">在“指定边缘设置”\*\*\*\* 上，选择当前为联盟配置的“边缘服务器内部 FQDN”\*\*\*\*，然后单击“更改”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="74779-135">![合并 OCS 2007 R2 拓扑，指定边缘设置](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "合并 OCS 2007 R2 拓扑，指定边缘设置")</span><span class="sxs-lookup"><span data-stu-id="74779-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="74779-136">单击“下一步”\*\*\*\* 并接受默认设置，直到显示“指定外部边缘”\*\*\*\* 页：</span><span class="sxs-lookup"><span data-stu-id="74779-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="74779-137">![拓扑生成器指定外部边缘页面](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "拓扑生成器指定外部边缘页面")</span><span class="sxs-lookup"><span data-stu-id="74779-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="74779-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span><span class="sxs-lookup"><span data-stu-id="74779-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="74779-139">This will remove the federation association with the BackCompatSite.</span><span class="sxs-lookup"><span data-stu-id="74779-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="74779-140">This step is important.</span><span class="sxs-lookup"><span data-stu-id="74779-140">This step is important.</span></span> <span data-ttu-id="74779-141">You must clear this option to remove the legacy federation association.</span><span class="sxs-lookup"><span data-stu-id="74779-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="74779-142">单击“下一步”\*\*\*\* 并接受向导其余页面的默认设置。</span><span class="sxs-lookup"><span data-stu-id="74779-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="74779-143">在“摘要”\*\*\*\* 中，单击“下一步”\*\*\*\* 开始合并拓扑。</span><span class="sxs-lookup"><span data-stu-id="74779-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="74779-144">在 "**状态**" 列中，验证值是否为 "**成功**"，然后单击 "**完成**" 以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="74779-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="74779-145">从“操作”\*\*\*\* 菜单中，选择“发布部署”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="74779-146">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\* 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="74779-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="74779-147">![在合并后显示网站的拓扑生成器](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "在合并后显示网站的拓扑生成器")</span><span class="sxs-lookup"><span data-stu-id="74779-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="74779-148">如在上图中所示，将位于**站点联盟路由分配**下的 **SIP 联盟**设置为**已禁用**。</span><span class="sxs-lookup"><span data-stu-id="74779-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="74779-149">在 Lync Server 2013 边缘服务器上配置证书</span><span class="sxs-lookup"><span data-stu-id="74779-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="74779-150">从旧版 Office 通信服务器 2007 R2 边缘服务器导出外部访问代理证书和私钥。</span><span class="sxs-lookup"><span data-stu-id="74779-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="74779-151">在 Lync Server 2013 边缘服务器上，导入上一步中的 "访问代理外部证书"。</span><span class="sxs-lookup"><span data-stu-id="74779-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="74779-152">将访问代理外部证书分配给边缘服务器的 Lync Server 2013 外部接口。</span><span class="sxs-lookup"><span data-stu-id="74779-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="74779-153">不应更改 Lync Server 2013 边缘服务器的内部接口证书。</span><span class="sxs-lookup"><span data-stu-id="74779-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="74779-154">将 Office Communications Server 2007 R2 联盟路由更改为使用 Lync Server 2013 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="74779-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="74779-155">在 Office 通信服务器 2007 R2 Standard Edition server 或前端服务器上，打开 Office 通信服务器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="74779-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="74779-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span><span class="sxs-lookup"><span data-stu-id="74779-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="74779-157">Select **Properties**, and then click **Global Properties**.</span><span class="sxs-lookup"><span data-stu-id="74779-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="74779-158">单击“联盟”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="74779-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="74779-159">选中用于启用联盟和公共 IM 连接的复选框。</span><span class="sxs-lookup"><span data-stu-id="74779-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="74779-160">输入 Lync Server 2013 边缘服务器的 FQDN，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="74779-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="74779-161">![OCS 全局属性（联合选项卡）](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS 全局属性（联合选项卡）")</span><span class="sxs-lookup"><span data-stu-id="74779-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="74779-162">启用 Lync Server 2013 边缘服务器联盟</span><span class="sxs-lookup"><span data-stu-id="74779-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="74779-163">从拓扑生成器的左侧窗格中，导航到 "Lync Server 2013 **Edge 池**" 节点。</span><span class="sxs-lookup"><span data-stu-id="74779-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="74779-164">展开节点，右键单击列出的边缘服务器，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="74779-165">仅可为单个边缘池启用联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="74779-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="74779-166">如果具有多个边缘池，请选择一个用作联盟边缘池。</span><span class="sxs-lookup"><span data-stu-id="74779-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="74779-167">在“常规”\*\*\*\* 页上，选中“为此边缘池启用联盟(端口 5061)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="74779-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="74779-168">![编辑属性，常规，启用边缘联盟](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "编辑属性，常规，启用边缘联盟")</span><span class="sxs-lookup"><span data-stu-id="74779-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="74779-169">单击“确定”\*\*\*\* 关闭“编辑属性”页。</span><span class="sxs-lookup"><span data-stu-id="74779-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="74779-170">接下来，导航到站点节点。</span><span class="sxs-lookup"><span data-stu-id="74779-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="74779-171">右键单击站点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="74779-172">在左窗格中，单击“联盟路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="74779-173">在 "**站点联合路由分配**" 下，选择 "**启用 SIP 联盟**"，然后从列表中选择列出的 Lync server 2013 边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="74779-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="74779-174">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="74779-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="74779-175">![编辑属性，常规，关联边缘池](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "编辑属性，常规，关联边缘池")</span><span class="sxs-lookup"><span data-stu-id="74779-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="74779-176">对于多站点部署，在每个站点上完成该过程。</span><span class="sxs-lookup"><span data-stu-id="74779-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="74779-177">配置 Lync Server 2013 边缘服务器出站媒体路径</span><span class="sxs-lookup"><span data-stu-id="74779-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="74779-178">从**拓扑生成器**中，导航到 "Lync Server 2013 池" （位于**Standard edition 前端服务器**或**Enterprise edition 前端池的后面**）。</span><span class="sxs-lookup"><span data-stu-id="74779-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="74779-179">右键单击该池，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="74779-180">在“关联”\*\*\*\* 部分，选中“关联边缘池(用于媒体组件)”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="74779-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="74779-181">从下拉框中，选择 "Lync Server 2013 边缘服务器"。</span><span class="sxs-lookup"><span data-stu-id="74779-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="74779-182">!["编辑属性" 对话框，关联边缘池](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg ""编辑属性" 对话框，关联边缘池")</span><span class="sxs-lookup"><span data-stu-id="74779-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="74779-183">单击“确定”\*\*\*\* 关闭“编辑属性”\*\*\*\* 页。</span><span class="sxs-lookup"><span data-stu-id="74779-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="74779-184">发布边缘服务器配置更改</span><span class="sxs-lookup"><span data-stu-id="74779-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="74779-185">从“拓扑生成器”\*\*\*\* 中，选择顶层节点“Lync Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="74779-186">从“操作”\*\*\*\* 菜单中，选择“发布拓扑”\*\*\*\* 并完成向导。</span><span class="sxs-lookup"><span data-stu-id="74779-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="74779-187">稍待片刻以便在部署中的所有池间执行 Active Directory 复制。</span><span class="sxs-lookup"><span data-stu-id="74779-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="74779-188">您可能会看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="74779-188">You may see the following message:</span></span><BR><span data-ttu-id="74779-189"><STRONG>警告: 拓扑包含多个联盟边缘服务器。在迁移到产品的更高版本时，可能会出现这种情况。在这种情况下，只有一个边缘服务器处于活动状态以用于联盟。请确保外部 DNS SRV 记录指向正确的边缘服务器。如果要将多个联盟边缘服务器部署为同时处于活动状态(非迁移情况下)，请确保所有联盟伙伴都在使用 Office Communications Server 2007 R2 或 Lync Server，并确保外部 DNS SRV 记录列出了所有已启用联盟的边缘服务器。</STRONG></span><span class="sxs-lookup"><span data-stu-id="74779-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="74779-190">该警告是预期警告，可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="74779-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="74779-191">验证联盟和外部用户的远程访问</span><span class="sxs-lookup"><span data-stu-id="74779-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="74779-192">在 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="74779-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="74779-193">要验证联盟和远程访问的状态，请从命令行，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="74779-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="74779-194">要启用联盟和远程访问，请从命令行，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="74779-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="74779-195">有关这些 cmdlet 的详细信息，请参阅下列主题： [set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\))和[set-csaccessedgeconfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="74779-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="74779-196">等到复制完成之后再将 Lync Server 2013 边缘服务器联机，并测试联盟和外部访问。</span><span class="sxs-lookup"><span data-stu-id="74779-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="74779-197">配置 Lync Server 2013 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="74779-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="74779-198">使所有 Lync Server 2013 边缘服务器联机。</span><span class="sxs-lookup"><span data-stu-id="74779-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="74779-199">更新外部防火墙路由规则或硬件负载平衡器设置以将外部访问的 SIP 通信（通常是端口443）和联合身份验证（通常是端口5061）发送到 Lync Server 2013 边缘服务器，而不是旧边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="74779-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="74779-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span><span class="sxs-lookup"><span data-stu-id="74779-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="74779-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span><span class="sxs-lookup"><span data-stu-id="74779-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="74779-202">接下来，从每台边缘服务器计算机停止**Lync Server 访问边缘**。</span><span class="sxs-lookup"><span data-stu-id="74779-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="74779-203">从每个旧边缘服务器计算机上，从 "**管理工具**" 中打开 "**服务**" 小程序。</span><span class="sxs-lookup"><span data-stu-id="74779-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="74779-204">在服务列表中，找到“Office Communications Server 访问边缘”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="74779-205">右键单击服务名称，然后选择“停止”\*\*\*\* 以停止该服务。</span><span class="sxs-lookup"><span data-stu-id="74779-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="74779-206">将“启动”类型设置为“已禁用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="74779-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="74779-207">单击“确定”\*\*\*\* 关闭“属性”\*\*\*\* 窗口。</span><span class="sxs-lookup"><span data-stu-id="74779-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="74779-208">测试外部用户和外部访问的连接</span><span class="sxs-lookup"><span data-stu-id="74779-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="74779-209">至少来自一个联盟域（Lync Server 2013 上的内部用户和 Office 通信服务器 2007 R2 上的用户）的用户。</span><span class="sxs-lookup"><span data-stu-id="74779-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="74779-210">测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="74779-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="74779-211">您的组织支持的每个公共 IM 服务提供商的用户（和已完成的设置）与 Lync Server 2013 上的用户和 Office 通信服务器 2007 R2 上的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="74779-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="74779-212">验证匿名用户是否能够加入会议。</span><span class="sxs-lookup"><span data-stu-id="74779-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="74779-213">在 Office 通信服务器 2007 R2 上使用远程用户访问（从 intranet 外部（但不使用 VPN 登录到 Office 通信服务器 2007 R2），并在 Lync Server 2013 上的用户和 Office 通信服务器 2007 R2 上的用户进行登录的用户。</span><span class="sxs-lookup"><span data-stu-id="74779-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="74779-214">测试 IM、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="74779-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="74779-215">在 lync server 2013 上托管的用户（使用远程用户访问（从 intranet 外部，但不使用 VPN 登录到 Lync Server 2013）与 Lync Server 2013 上的用户以及 Office 通信服务器 2007 R2 上的用户。</span><span class="sxs-lookup"><span data-stu-id="74779-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="74779-216">测试 IM、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="74779-216">Test IM, presence, A/V, and desktop sharing.</span></span>

