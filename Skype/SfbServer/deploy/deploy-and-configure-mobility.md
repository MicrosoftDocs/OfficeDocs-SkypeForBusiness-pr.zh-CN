---
title: 部署和配置 Skype for Business Server 的移动功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将介绍配置现有 Skype for Business Server 安装以使用 Mobility Service 的步骤，以便你的移动设备能够利用 Skype for Business Server Mobility 功能。
ms.openlocfilehash: 2ba0a81350dac6e47f4e909b4cfba256ee90de18
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103858"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="8b23f-103">部署和配置 Skype for Business Server 的移动功能</span><span class="sxs-lookup"><span data-stu-id="8b23f-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="8b23f-104">本文将介绍配置现有 Skype for Business Server 安装以使用 Mobility Service 的步骤，以便你的移动设备能够利用 Skype for Business Server Mobility 功能。</span><span class="sxs-lookup"><span data-stu-id="8b23f-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="8b23f-105">查看 Plan [for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) 一文后，您应该已准备好继续执行以下步骤，将 Mobility 部署到 Skype for Business Server 环境中。</span><span class="sxs-lookup"><span data-stu-id="8b23f-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="8b23f-106">步骤如下， (在此表中包括权限列表) ：</span><span class="sxs-lookup"><span data-stu-id="8b23f-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="8b23f-107">**阶段**</span><span class="sxs-lookup"><span data-stu-id="8b23f-107">**Phase**</span></span>|<span data-ttu-id="8b23f-108">**权限**</span><span class="sxs-lookup"><span data-stu-id="8b23f-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="8b23f-109">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="8b23f-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="8b23f-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="8b23f-110">Domain Admins</span></span>  <br/> <span data-ttu-id="8b23f-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="8b23f-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="8b23f-112">修改证书</span><span class="sxs-lookup"><span data-stu-id="8b23f-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="8b23f-113">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8b23f-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="8b23f-114">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="8b23f-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="8b23f-115">本地管理员</span><span class="sxs-lookup"><span data-stu-id="8b23f-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="8b23f-116">使用混合部署配置移动性自动发现</span><span class="sxs-lookup"><span data-stu-id="8b23f-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="8b23f-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="8b23f-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="8b23f-118">测试移动部署</span><span class="sxs-lookup"><span data-stu-id="8b23f-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="8b23f-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8b23f-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="8b23f-120">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="8b23f-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="8b23f-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="8b23f-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="8b23f-122">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="8b23f-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="8b23f-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="8b23f-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="8b23f-124">以下所有部分都包含假定你已阅读规划主题的步骤。</span><span class="sxs-lookup"><span data-stu-id="8b23f-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="8b23f-125">如果有任何令人困惑的事情，请随时查看相关信息。</span><span class="sxs-lookup"><span data-stu-id="8b23f-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="8b23f-126">Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="8b23f-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8b23f-127">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="8b23f-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="8b23f-128">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="8b23f-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="8b23f-129">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="8b23f-129">Create DNS records</span></span>
<span data-ttu-id="8b23f-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="8b23f-131">你可能已经拥有这些记录作为 Skype for Business Server 环境的一部分，但你需要创建以下记录，自动发现功能可以正常工作：</span><span class="sxs-lookup"><span data-stu-id="8b23f-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="8b23f-132">内部 DNS 记录，用于支持从组织网络内部进行连接的移动用户。</span><span class="sxs-lookup"><span data-stu-id="8b23f-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="8b23f-133">外部 (或公共) DNS 记录，以支持从组织网络外部进行连接的移动用户。</span><span class="sxs-lookup"><span data-stu-id="8b23f-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="8b23f-134">这些记录可以是 a (host) names 或 CNAME records (you don't have to make both， we're just including the steps for everything here) .</span><span class="sxs-lookup"><span data-stu-id="8b23f-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="8b23f-135">创建内部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="8b23f-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="8b23f-136">在作为 **Domain Admins** 组或 **DnsAdmins** 组的成员的网络中登录到 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="8b23f-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="8b23f-137">Click **Start**， Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu) ， and then click **DNS** to open the DNS administrative snap-in.</span><span class="sxs-lookup"><span data-stu-id="8b23f-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="8b23f-138">在控制台窗口的左侧窗格中，你需要转到 Skype for Business Server 前端服务器所位于的域，然后在那里展开"前向 **查找** 区域"。</span><span class="sxs-lookup"><span data-stu-id="8b23f-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="8b23f-139">花一点时间查看你拥有以下哪项：</span><span class="sxs-lookup"><span data-stu-id="8b23f-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="8b23f-140">前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="8b23f-141">控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="8b23f-142">记录此名称后，右键单击 SIP 域名，然后从菜单中选择 **"CNAME (") "** 新别名"。</span><span class="sxs-lookup"><span data-stu-id="8b23f-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="8b23f-143">在 **"别名"** 文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="8b23f-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="8b23f-144">在目标主机的完全限定域名 **(FQDN** 中，需要键入或浏览到前端池 (或单个前端服务器、控制器池或控制器) 的内部 Web 服务 FQDN，如上面的步骤 4 所示。</span><span class="sxs-lookup"><span data-stu-id="8b23f-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="8b23f-145">输入时单击"确定"。</span><span class="sxs-lookup"><span data-stu-id="8b23f-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="8b23f-146">你需要在 Skype for Business Server 环境中支持的每个 SIP 域的向前查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="8b23f-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="8b23f-147">创建外部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="8b23f-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="8b23f-148">这些步骤是通用的，因为我们无法告诉你可能使用哪种公共 DNS 提供商，但仍希望帮助您解决。请使用能够在那里新建 DNS 记录的帐户登录到公共 DNS 提供商。</span><span class="sxs-lookup"><span data-stu-id="8b23f-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="8b23f-149">此时，Skype for Business Server 的 SIP 域应该已存在。</span><span class="sxs-lookup"><span data-stu-id="8b23f-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="8b23f-150">展开此 SIP **域的** "前向查找区域"，或者以其他方式打开它。</span><span class="sxs-lookup"><span data-stu-id="8b23f-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="8b23f-151">花一点时间查看你拥有以下哪项：</span><span class="sxs-lookup"><span data-stu-id="8b23f-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="8b23f-152">前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="8b23f-153">控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="8b23f-154">获得该信息后，应该能够选择一个选项，以使用 **CNAME (创建新别名) 。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="8b23f-155">现在您应该能够输入别名，您需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="8b23f-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="8b23f-156">接下来，应该有一个要输入目标主机 **的 FQDN** 的区域，这应该是前端池 (或单台前端服务器的 FQDN，或上面步骤 3 中标识的控制器池或控制器) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="8b23f-157">你可能需要在此处保存，或者如果你需要在 Skype for Business Server 环境中每个 SIP 域的向前查找区域中创建其他 CNAME 记录，你应这样做，但一旦准备就绪，请保存你的工作。</span><span class="sxs-lookup"><span data-stu-id="8b23f-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="8b23f-158">创建内部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="8b23f-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="8b23f-159">在作为 **Domain Admins** 组或 **DnsAdmins** 组的成员的网络中登录到 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="8b23f-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="8b23f-160">Click **Start**， Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu) ， and then click **DNS** to open the DNS administrative snap-in.</span><span class="sxs-lookup"><span data-stu-id="8b23f-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="8b23f-161">在控制台窗口的左侧窗格中，你需要转到 Skype for Business Server 前端服务器所位于的域，然后在那里展开"前向 **查找** 区域"。</span><span class="sxs-lookup"><span data-stu-id="8b23f-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="8b23f-162">花一点时间查看你拥有以下哪项：</span><span class="sxs-lookup"><span data-stu-id="8b23f-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="8b23f-163">前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="8b23f-164">控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="8b23f-165">记录此名称后，右键单击 SIP 域名，然后从菜单中选择"新建主机 (A 或 **AAAA**) 选择" 新建主机"。</span><span class="sxs-lookup"><span data-stu-id="8b23f-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="8b23f-166">在" **名称** "文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="8b23f-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="8b23f-167">在 **"IP** 地址"文本框中，键入前端池或单个前端服务器 (或控制器池或控制器) 的内部 Web 服务 IP 地址，如上面的步骤 4 所示。</span><span class="sxs-lookup"><span data-stu-id="8b23f-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="8b23f-168">完成此操作后，单击 **"添加主机**"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="8b23f-169">你需要在 Skype for Business Server 环境中支持的每个 SIP 域的向前查找区域中创建新的自动发现 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="8b23f-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="8b23f-170">为此，请根据需要多次重复步骤 6-8。</span><span class="sxs-lookup"><span data-stu-id="8b23f-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="8b23f-171">完成后，单击 **完成。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="8b23f-172">创建外部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="8b23f-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="8b23f-173">这些步骤是通用的，因为我们无法告诉你可能使用哪种公共 DNS 提供商，但仍希望帮助您解决。请使用能够在那里新建 DNS 记录的帐户登录到公共 DNS 提供商。</span><span class="sxs-lookup"><span data-stu-id="8b23f-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="8b23f-174">此时，Skype for Business Server 的 SIP 域应该已存在。</span><span class="sxs-lookup"><span data-stu-id="8b23f-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="8b23f-175">展开此 SIP **域的** "前向查找区域"，或者以其他方式打开它。</span><span class="sxs-lookup"><span data-stu-id="8b23f-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="8b23f-176">花一点时间查看你拥有以下哪项：</span><span class="sxs-lookup"><span data-stu-id="8b23f-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="8b23f-177">前端服务器或 Standard (Enterprise) 或前端池的任何主机 A 或 AAAA (记录) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="8b23f-178">控制器或控制器池的任何主机 A 或 AAAA 记录 (部署策略中可能具有的可选) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="8b23f-179">获得该信息后，应该能够选择一个选项来创建新 **主机 A 或 AAAA。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="8b23f-180">现在，您应该能够输入 **Name，** 您需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="8b23f-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="8b23f-181">接下来，应该有一个要输入 IP 地址的区域，这应该是前端池 (或单个前端服务器的 **IP、** 控制器池或控制器) ，如上面的步骤 3 所示。</span><span class="sxs-lookup"><span data-stu-id="8b23f-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="8b23f-182">你可能需要在此处保存，或者如果你需要在 Skype for Business Server 环境的每个 SIP 域的向前查找区域中创建其他 A 或 AAAA 记录，你应这样做，但一旦准备就绪，请保存你的工作。</span><span class="sxs-lookup"><span data-stu-id="8b23f-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="8b23f-183">修改证书</span><span class="sxs-lookup"><span data-stu-id="8b23f-183">Modify certificates</span></span>
<span data-ttu-id="8b23f-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="8b23f-185">如果你对规划证书有疑问，我们已在 Plan [for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) 一文记录了这一点。</span><span class="sxs-lookup"><span data-stu-id="8b23f-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="8b23f-186">查看后，我们将演练以下内容：</span><span class="sxs-lookup"><span data-stu-id="8b23f-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="8b23f-187">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="8b23f-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="8b23f-188">从 CA 证书颁发机构请求 (证书) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="8b23f-189">使用 PowerShell 使用替换项更新就地证书。</span><span class="sxs-lookup"><span data-stu-id="8b23f-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="8b23f-190">使用 Microsoft 管理控制台中的"证书"管理单元检查 (MMC) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="8b23f-191">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="8b23f-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="8b23f-192">首先，你可能需要检查并查看哪些证书已就位，以及它们是否有所需的条目。</span><span class="sxs-lookup"><span data-stu-id="8b23f-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="8b23f-193">为此，你需要使用本地管理员帐户登录 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="8b23f-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="8b23f-194">此帐户可能还需要对 CA 证书颁发机构 (，) 执行其中一些步骤。</span><span class="sxs-lookup"><span data-stu-id="8b23f-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="8b23f-195">打开 Skype for Business Server 命令行管理程序 (如果你未将 Skype for Business Server 命令行管理程序固定到"开始"菜单或任务栏菜单，可以使用搜索) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="8b23f-196">在尝试添加更新的证书之前，了解已分配哪些证书至关重要。</span><span class="sxs-lookup"><span data-stu-id="8b23f-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="8b23f-197">因此，在命令中键入：</span><span class="sxs-lookup"><span data-stu-id="8b23f-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="8b23f-198">步骤 3 中的信息将是唯一的。</span><span class="sxs-lookup"><span data-stu-id="8b23f-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="8b23f-199">你需要查看它以确定你是否拥有一个已分配用于多个项的证书，或者您是否为需要它们的不同组件分配了不同的证书。</span><span class="sxs-lookup"><span data-stu-id="8b23f-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="8b23f-200">**Use** 参数将告知您证书的使用方式 **，Thumbprint** 参数将告知您证书是全部相同的证书还是多个证书。</span><span class="sxs-lookup"><span data-stu-id="8b23f-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="8b23f-201">如果您的规划部分中推荐了 SAN 条目，则没有问题。</span><span class="sxs-lookup"><span data-stu-id="8b23f-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="8b23f-202">如果没有，则需要请求新证书或多个证书 (证书颁发机构) 配置。</span><span class="sxs-lookup"><span data-stu-id="8b23f-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="8b23f-203">从 CA 证书颁发机构请求新证书 (证书) </span><span class="sxs-lookup"><span data-stu-id="8b23f-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="8b23f-204">检查了具有哪些 SAN 条目后，通过上述 **)** 步骤检查后，即知道您拥有单个证书 (，并且你知道您没有所需的全部条目。</span><span class="sxs-lookup"><span data-stu-id="8b23f-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="8b23f-205">需要向 CA 提出新的证书请求。</span><span class="sxs-lookup"><span data-stu-id="8b23f-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="8b23f-206">打开 Skype for Business Server PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8b23f-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="8b23f-207">对于缺少的自动发现服务 SAN (将 -Ca 参数替换为你自己的证书颁发机构路径) ：</span><span class="sxs-lookup"><span data-stu-id="8b23f-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="8b23f-208">现在，如果您有多个 SIP 域，则不能像上面的示例一样使用 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="8b23f-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="8b23f-209">您需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="8b23f-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="8b23f-210">使用 DomainName 参数时，必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8b23f-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="8b23f-211">例如， (-Ca 参数替换为您自己的证书颁发机构路径) ：</span><span class="sxs-lookup"><span data-stu-id="8b23f-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="8b23f-212">或者，在查看你拥有哪些 SAN 条目后，发现你拥有多个证书，这些证书没有所需的全部条目。</span><span class="sxs-lookup"><span data-stu-id="8b23f-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="8b23f-213">需要向 CA 提出新的证书请求。</span><span class="sxs-lookup"><span data-stu-id="8b23f-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="8b23f-214">打开 Skype for Business Server PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8b23f-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="8b23f-215">对于缺少的自动发现服务 SAN (将 -Ca 参数替换为你自己的证书颁发机构路径) ：</span><span class="sxs-lookup"><span data-stu-id="8b23f-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="8b23f-216">现在，如果您有多个 SIP 域，则不能像上面的示例一样使用 AllSipDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="8b23f-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="8b23f-217">您需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="8b23f-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="8b23f-218">使用 DomainName 参数时，必须定义 lyncdiscoverinternal 和 lyncdiscover 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8b23f-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="8b23f-219">示例包括 (-Ca 参数替换为您自己的证书颁发机构路径) ：</span><span class="sxs-lookup"><span data-stu-id="8b23f-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="8b23f-220">CA 生成新证书后，你将需要分配它们。</span><span class="sxs-lookup"><span data-stu-id="8b23f-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="8b23f-221">使用 Skype for Business Server 命令行管理程序分配证书</span><span class="sxs-lookup"><span data-stu-id="8b23f-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="8b23f-222">根据你在上面的是否需要新的认证部分中找到的内容，你需要运行 **以下操作** 之一。</span><span class="sxs-lookup"><span data-stu-id="8b23f-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="8b23f-223">如果有一个证书用于所有 (指纹完全相同) 则需要运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="8b23f-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="8b23f-224">如果你有不同的证书，但指纹 (都是不同的) ，请改为运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="8b23f-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="8b23f-225">在 MICROSOFT 管理控制台中查看 (MMC) </span><span class="sxs-lookup"><span data-stu-id="8b23f-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="8b23f-226">可以选择使用 MMC 的"证书"管理单元查看证书。</span><span class="sxs-lookup"><span data-stu-id="8b23f-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="8b23f-227">只需在搜索中键入 MMC，它应作为应用程序选项弹出。</span><span class="sxs-lookup"><span data-stu-id="8b23f-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="8b23f-228">若要添加证书管理单元，你需要单击文件，然后添加/删除管理单元 **...** (或键盘快捷方式 **Ctrl+M** 也将) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="8b23f-229">**证书** 将是左侧窗格中的一个选项，选择它，然后在弹出窗口中，然后选择下一步的计算机 **帐户**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="8b23f-230">仍在弹出窗口中，你很可能正在位于需要查看的证书的主页上执行此操作，因此，如果位于本地计算机上，请保留选择。 </span><span class="sxs-lookup"><span data-stu-id="8b23f-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="8b23f-231">如果正在远程计算机上工作，将单选按钮更改为"其他计算机"，然后输入该计算机的 FQDN 或使用"浏览"按钮通过AD 搜索该计算机。 </span><span class="sxs-lookup"><span data-stu-id="8b23f-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="8b23f-232">选择计算机后，你需要在准备就绪时单击"完成"，然后单击"确定"以将管理单元添加到 MMC。</span><span class="sxs-lookup"><span data-stu-id="8b23f-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="8b23f-233">展开MMC 左侧窗格中的"证书"部分。</span><span class="sxs-lookup"><span data-stu-id="8b23f-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="8b23f-234">同时展开 **"个人**"文件夹，然后选择"证书 **"。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="8b23f-235">这使你可以在此存储中查看证书。</span><span class="sxs-lookup"><span data-stu-id="8b23f-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="8b23f-236">您需要找到要查看的证书，右键单击它，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8b23f-237">您如何知道这是一个证书？</span><span class="sxs-lookup"><span data-stu-id="8b23f-237">How do you know what certificate this is?</span></span> <span data-ttu-id="8b23f-238">它应是分配给服务器场中所有内容的单一证书，或者您可能具有用于不同内容的多个证书，如 Default、Internal Web Services 等，在这种情况下，您可能需要查看多个证书。</span><span class="sxs-lookup"><span data-stu-id="8b23f-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="8b23f-239">多个证书将具有相同的指纹。</span><span class="sxs-lookup"><span data-stu-id="8b23f-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="8b23f-240">进入证书视图后 **，选择详细信息\*\*\*\*。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="8b23f-241">这将在选择"主题"时看到证书主题名称，并且将显示分配的主题名称和关联属性。</span><span class="sxs-lookup"><span data-stu-id="8b23f-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="8b23f-242">你还需要检查主题备用 **名称** 条目。</span><span class="sxs-lookup"><span data-stu-id="8b23f-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="8b23f-243">你将找到以下一个或多个内容：</span><span class="sxs-lookup"><span data-stu-id="8b23f-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="8b23f-244">此池的池名称，或单个服务器名称（如果不是池）。</span><span class="sxs-lookup"><span data-stu-id="8b23f-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="8b23f-245">证书分配到的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="8b23f-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="8b23f-246">简单 URL 记录，通常为 meet 和 dialin。</span><span class="sxs-lookup"><span data-stu-id="8b23f-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="8b23f-247">Web 服务内部名称和 Web 服务外部名称 (，例如，webpool01.contoso.net、webpool01.contoso.com) ，这些名称基于在拓扑生成器和覆盖的 Web 服务选择中做出的选择。</span><span class="sxs-lookup"><span data-stu-id="8b23f-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="8b23f-248">如果已分配，则 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="8b23f-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="8b23f-249">和 lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="8b23f-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="8b23f-250">记录。</span><span class="sxs-lookup"><span data-stu-id="8b23f-250">records.</span></span>
    
     <span data-ttu-id="8b23f-251">如果分配了多个证书，则需要检查多个证书 (检查上述) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="8b23f-252">因此，如果您找到 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="8b23f-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="8b23f-253">和 lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="8b23f-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="8b23f-254">记录，你已对此进行配置。</span><span class="sxs-lookup"><span data-stu-id="8b23f-254">records, you've got this configured already.</span></span> <span data-ttu-id="8b23f-255">你可以关闭 MMC。</span><span class="sxs-lookup"><span data-stu-id="8b23f-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="8b23f-256">如果未分配证书，你将需要提出上述 (列出的新证书请求) 或者需要安装它们请求后 (我们建议针对该证书的 powerShell 进行以下) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="8b23f-257">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="8b23f-257">Configure the reverse proxy</span></span>
<span data-ttu-id="8b23f-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="8b23f-259">不应完全遵循以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8b23f-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="8b23f-260">这是因为在该产品的以前版本中，我们已演示了配置威胁管理网关 (TMG) 例如，如果未使用该配置，则需要从该版本创建自己的版本。</span><span class="sxs-lookup"><span data-stu-id="8b23f-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="8b23f-261">TMG 不再由 Microsoft 作为产品提供，如果您仍然需要对其进行配置，您可以查看 [Lync Server 2013 步骤](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility)。</span><span class="sxs-lookup"><span data-stu-id="8b23f-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility).</span></span> <span data-ttu-id="8b23f-262">但是，以下信息更普遍有用，即使我们无法为上述每个反向代理提供特定的演练步骤。</span><span class="sxs-lookup"><span data-stu-id="8b23f-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="8b23f-263">我们需要考虑两个主要问题：</span><span class="sxs-lookup"><span data-stu-id="8b23f-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="8b23f-264">是否打算通过 HTTPS 服务器执行初始自动发现 (建议) ？</span><span class="sxs-lookup"><span data-stu-id="8b23f-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="8b23f-265">如果你有 Web 发布规则，则需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="8b23f-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="8b23f-266">如果还没有 Web 发布规则，则需要创建它。</span><span class="sxs-lookup"><span data-stu-id="8b23f-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="8b23f-267">如果通过 HTTP 执行初始自动发现请求，则还需要创建或修改该规则。</span><span class="sxs-lookup"><span data-stu-id="8b23f-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b23f-268">**重要** 代理的退出值是因部署而异的数值。</span><span class="sxs-lookup"><span data-stu-id="8b23f-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="8b23f-269">您应监视部署并修改值，以获得最佳客户端体验。</span><span class="sxs-lookup"><span data-stu-id="8b23f-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="8b23f-270">你可以将该值设置为低至 200。</span><span class="sxs-lookup"><span data-stu-id="8b23f-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="8b23f-271">如果要在环境中支持 Lync 移动客户端，则应该将值设置为 960，以允许从 Office 365 发送推送通知的退出时间，其退出值为 900。</span><span class="sxs-lookup"><span data-stu-id="8b23f-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="8b23f-272">很可能您必须增加退出值以避免在值太低时客户端断开连接，或者，如果通过代理的连接没有断开连接但在客户端断开连接后清除，则减少此数目。</span><span class="sxs-lookup"><span data-stu-id="8b23f-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="8b23f-273">监视和确定环境常规情况是确定此值的适当设置的唯一准确方法。</span><span class="sxs-lookup"><span data-stu-id="8b23f-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="8b23f-274">修改外部自动发现 SAN 和 URL 的现有 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="8b23f-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="8b23f-275">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="8b23f-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="8b23f-276">你需要找到 Web 发布规则，并选择"编辑"选项 (它可能位于菜单或选项卡上，具体取决于反向代理配置) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="8b23f-277">应存在一个指出此 Web 发布规则所应用到的内容的区域。</span><span class="sxs-lookup"><span data-stu-id="8b23f-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="8b23f-278">您需要修改传入网站或网站请求的此规则。</span><span class="sxs-lookup"><span data-stu-id="8b23f-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="8b23f-279">你将添加新条目。 </span><span class="sxs-lookup"><span data-stu-id="8b23f-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="8b23f-280">键入自动发现站点的名称 (我们将使用的示例是 lyncdiscover.contoso.com) ，并单击"确定"或"保存"，具体取决于反向代理的格式。 </span><span class="sxs-lookup"><span data-stu-id="8b23f-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="8b23f-281">你可能有一个新证书，该证书中具有自动发现 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="8b23f-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="8b23f-282">这也需要进行安装，并配置为根据反向代理的设置使用。</span><span class="sxs-lookup"><span data-stu-id="8b23f-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="8b23f-283">确保在配置完成后保存所有内容。</span><span class="sxs-lookup"><span data-stu-id="8b23f-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="8b23f-284">如果反向代理具有 **测试** 功能，请使用它，以确保一切正常。</span><span class="sxs-lookup"><span data-stu-id="8b23f-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="8b23f-285">现在，如果您的环境中具有控制器或控制器池，您可能需要重复这些步骤 (这意味着您具有第二个规则) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="8b23f-286">为外部自动发现 URL 创建 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="8b23f-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="8b23f-287">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="8b23f-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="8b23f-288">你需要在界面中查找创建 Web 发布规则的位置，并选择"新建"或"创建"选项 (它可能位于菜单或选项卡上，具体取决于反向代理配置) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="8b23f-289">您正在寻找创建新 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="8b23f-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="8b23f-290">通常，您需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="8b23f-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="8b23f-291">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="8b23f-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="8b23f-292">**规则** 操作：在这种情况下， **它是允许规则** ，你可以让某些内容通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="8b23f-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="8b23f-293">您 **选择的** 发布规则或选项将是单个 **网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="8b23f-294">这应该是用于外部访问 **的 SSL，** 请选择该选项。</span><span class="sxs-lookup"><span data-stu-id="8b23f-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="8b23f-295">您需要发布内部发布的路径，并输入前端池负载平衡器 (上的外部 Web 服务的 FQDN 或控制器池负载平衡器（如果有一个) ）的 FQDN，例如 sfb_pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="8b23f-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="8b23f-296">应键入 _ 作为要发布的路径，但还需要 **/\\** _\*转发原始主机头\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b23f-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="8b23f-297">有一个公共或外部 **名称详细信息** 或信息的选项。</span><span class="sxs-lookup"><span data-stu-id="8b23f-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="8b23f-298">这是你可以输入的位置：</span><span class="sxs-lookup"><span data-stu-id="8b23f-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="8b23f-299">**接受请求**，但它应该用于域名。</span><span class="sxs-lookup"><span data-stu-id="8b23f-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="8b23f-300">对于 **"名称**"，应输入 **lyncdiscover。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="8b23f-301"><sipdomain> (这是外部自动发现服务 URL) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="8b23f-302">现在，如果要为前端池上的外部 Web 服务 URL 创建规则，则需要为前端池上的外部 Web 服务键入 FQDN (例如，lyncwebextpool01.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="8b23f-303">有一个 **Path** 选项，你需要在此处输入 **/\\** \*。</span><span class="sxs-lookup"><span data-stu-id="8b23f-303">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="8b23f-304">您需要使用最新的公共证书选择 **SSL** 侦听器。</span><span class="sxs-lookup"><span data-stu-id="8b23f-304">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="8b23f-305">**身份验证委派** 应设置为" **无委派"，** 但 **应允许直接客户端** 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b23f-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="8b23f-306">该规则应设置为 **所有用户**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="8b23f-307">这应该是创建此规则所需的全部信息，并允许您继续操作。</span><span class="sxs-lookup"><span data-stu-id="8b23f-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="8b23f-308">你将需要确保转发原始 **主机** 头。</span><span class="sxs-lookup"><span data-stu-id="8b23f-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="8b23f-309">**还需要设置 Web** 服务器端口，您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b23f-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="8b23f-310">**将请求重定向到 HTTP 端口**，端口号应为 **8080。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="8b23f-311">**将请求重定向到 SSL 端口** ，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="8b23f-312">配置所有内容后，需要保存或应用它们，然后测试规则。</span><span class="sxs-lookup"><span data-stu-id="8b23f-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="8b23f-313">为端口 80 创建 Web 发布规则 (可选) </span><span class="sxs-lookup"><span data-stu-id="8b23f-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="8b23f-314">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="8b23f-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="8b23f-315">你需要在界面中查找创建 Web 发布规则的位置，并选择"新建"或"创建"选项 (它可能位于菜单或选项卡上，具体取决于反向代理配置) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="8b23f-316">您正在寻找创建新 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="8b23f-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="8b23f-317">通常，您需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="8b23f-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="8b23f-318">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="8b23f-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="8b23f-319">**规则** 操作：在这种情况下， **它是允许规则** ，你可以让某些内容通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="8b23f-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="8b23f-320">您 **选择的** 发布规则或选项将是单个 **网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="8b23f-321">这应该是一 **个非安全连接，用于连接到已发布的 Web 服务器或服务器场**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="8b23f-322">您需要发布内部发布的路径，并输入前端池负载平衡器 VIP 地址的 FQDN，例如 sfb_pool01.contoso.local。 </span><span class="sxs-lookup"><span data-stu-id="8b23f-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="8b23f-323">应键入 _ 作为要发布的路径，但还需要 **/\\** _\*转发原始主机头\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b23f-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="8b23f-324">有一个公共或外部 **名称详细信息** 或信息的选项。</span><span class="sxs-lookup"><span data-stu-id="8b23f-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="8b23f-325">这是你可以输入的位置：</span><span class="sxs-lookup"><span data-stu-id="8b23f-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="8b23f-326">**接受请求**，但它应该用于域名。</span><span class="sxs-lookup"><span data-stu-id="8b23f-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="8b23f-327">对于 **"名称**"，应输入 **lyncdiscover。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="8b23f-328"><sipdomain> (这是外部自动发现服务 URL) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="8b23f-329">有一个 **Path** 选项，你需要在此处输入 **/\\** \*。</span><span class="sxs-lookup"><span data-stu-id="8b23f-329">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="8b23f-330">你需要选择一个 Web 侦听器，或允许反向代理创建一个。</span><span class="sxs-lookup"><span data-stu-id="8b23f-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="8b23f-331">**身份验证委派** 应设置为" **无委派"，** 但 **不允许直接客户端** 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8b23f-331">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="8b23f-332">该规则应设置为 **所有用户**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="8b23f-333">这应该是创建此规则所需的全部信息，并允许您继续操作。</span><span class="sxs-lookup"><span data-stu-id="8b23f-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="8b23f-334">**需要设置 Web** 服务器端口，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b23f-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="8b23f-335">**将请求重定向到 HTTP 端口**，端口号应为 **8080。**</span><span class="sxs-lookup"><span data-stu-id="8b23f-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="8b23f-336">**将请求重定向到 SSL 端口** ，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="8b23f-337">配置所有内容后，需要保存或应用它们，然后测试规则。</span><span class="sxs-lookup"><span data-stu-id="8b23f-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="8b23f-338">使用混合部署配置移动性自动发现</span><span class="sxs-lookup"><span data-stu-id="8b23f-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="8b23f-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="8b23f-340">Skype for Business Server 中的混合环境是组合本地和 O365 环境的环境。</span><span class="sxs-lookup"><span data-stu-id="8b23f-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="8b23f-341">当你让 Skype for Business Server 在混合环境中工作时，自动发现服务需要能够从其中任一环境中查找用户。</span><span class="sxs-lookup"><span data-stu-id="8b23f-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="8b23f-342">若要让移动客户端发现用户所在的位置，需要将自动发现服务配置为使用新的统一资源定位器 (URL) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="8b23f-343">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="8b23f-343">The steps are:</span></span>
  
1. <span data-ttu-id="8b23f-344">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="8b23f-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="8b23f-345">运行以下代码，获取 Skype for Business Server 环境的属性 **ProxyFQDN** 的值：</span><span class="sxs-lookup"><span data-stu-id="8b23f-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="8b23f-346">然后，仍在 shell 窗口中运行：</span><span class="sxs-lookup"><span data-stu-id="8b23f-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="8b23f-347">其中 [identity] 使用共享 SIP 地址空间的域名替换。</span><span class="sxs-lookup"><span data-stu-id="8b23f-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="8b23f-348">测试移动部署</span><span class="sxs-lookup"><span data-stu-id="8b23f-348">Test your Mobility deployment</span></span>
<span data-ttu-id="8b23f-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="8b23f-350">部署 Skype for Business Server Mobility Service 和 Skype for Business Server 自动发现服务后，你需要运行测试事务，以确保你的部署正常工作。</span><span class="sxs-lookup"><span data-stu-id="8b23f-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="8b23f-351">可以运行 **Test-CsUcwaConference** 来测试两个用户创建、加入会议以及参加会议进行通信的能力。</span><span class="sxs-lookup"><span data-stu-id="8b23f-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="8b23f-352">你需要两个用户 (真实或测试) 及其完整凭据来执行此测试。</span><span class="sxs-lookup"><span data-stu-id="8b23f-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="8b23f-353">此命令适用于 Skype for Business 客户端和 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="8b23f-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="8b23f-354">对于 Skype for Business Server 2015 上的 Lync Server 2010 客户端，你需要运行 **Test-CsMcxP2PIM** 进行测试。</span><span class="sxs-lookup"><span data-stu-id="8b23f-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="8b23f-355">Lync Server 2010 用户仍将是实际用户或预定义的测试用户，并且您需要其密码凭据。</span><span class="sxs-lookup"><span data-stu-id="8b23f-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="8b23f-356">Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="8b23f-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8b23f-357">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="8b23f-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="8b23f-358">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="8b23f-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="8b23f-359">测试 Skype for Business 和 Lync 2013 移动客户端的会议</span><span class="sxs-lookup"><span data-stu-id="8b23f-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="8b23f-360">以 **CsAdministrator** 角色成员登录到安装了 Skype for **Business Server** 命令行管理程序和 **Ocscore** 的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="8b23f-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-361">启动 **Skype for Business Server** 命令行管理程序 (在搜索中键入名称或转到"所有程序"并选择它) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="8b23f-362">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="8b23f-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="8b23f-363">还可以在脚本中设置凭据，然后将它们传递到测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b23f-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="8b23f-364">我们在下面有一个示例。</span><span class="sxs-lookup"><span data-stu-id="8b23f-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="8b23f-365">测试 Lync 2010 移动客户端的会议</span><span class="sxs-lookup"><span data-stu-id="8b23f-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="8b23f-366">Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。</span><span class="sxs-lookup"><span data-stu-id="8b23f-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="8b23f-367">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="8b23f-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="8b23f-368">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="8b23f-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="8b23f-369">以 **CsAdministrator** 角色成员登录到安装了 Skype for **Business Server** 命令行管理程序和 **Ocscore** 的任何计算机上。</span><span class="sxs-lookup"><span data-stu-id="8b23f-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-370">启动 **Skype for Business Server** 命令行管理程序 (在搜索中键入名称或转到"所有程序"并选择它) 。</span><span class="sxs-lookup"><span data-stu-id="8b23f-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="8b23f-371">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="8b23f-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="8b23f-372">还可以在脚本中设置凭据，然后将它们传递到测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8b23f-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="8b23f-373">我们在下面有一个示例。</span><span class="sxs-lookup"><span data-stu-id="8b23f-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="8b23f-374">若要进一步查看命令过程，可以查阅 [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8b23f-374">To review the command procedures further, you can check out [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="8b23f-375">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="8b23f-375">Configure for push notifications</span></span>
<span data-ttu-id="8b23f-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="8b23f-377">即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（形式为锁屏提醒、图标或警报）。</span><span class="sxs-lookup"><span data-stu-id="8b23f-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="8b23f-378">但是什么是推送通知？</span><span class="sxs-lookup"><span data-stu-id="8b23f-378">But what are push notifications?</span></span> <span data-ttu-id="8b23f-379">它们是事件警报，如新的或错过的 IM 邀请，或接收的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="8b23f-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="8b23f-380">Skype for Business Server Mobility Service 会向基于云的 Skype for Business Server 推送通知服务发送这些通知，该服务随后会向 Windows Phone 用户的 Microsoft 推送通知服务 (MSNS) 发送通知。</span><span class="sxs-lookup"><span data-stu-id="8b23f-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="8b23f-381">此功能与 Lync Server 2013 不同，但如果你有 Skype for Business Server，你将希望执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8b23f-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="8b23f-382">对于 Skype for Business Server 边缘服务器，添加一个新的宿主提供商 Microsoft Skype for Business Online，然后在组织与 Skype for Business Online 之间设置宿主提供商联盟。</span><span class="sxs-lookup"><span data-stu-id="8b23f-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="8b23f-383">通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。</span><span class="sxs-lookup"><span data-stu-id="8b23f-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="8b23f-384">默认情况下，推送通知已关闭。</span><span class="sxs-lookup"><span data-stu-id="8b23f-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="8b23f-385">测试联合配置和推送通知。</span><span class="sxs-lookup"><span data-stu-id="8b23f-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="8b23f-386">为 Skype for Business 边缘服务器配置推送通知</span><span class="sxs-lookup"><span data-stu-id="8b23f-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="8b23f-387">使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b23f-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-388">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8b23f-389">添加 Skype for Business Server 联机托管提供商。</span><span class="sxs-lookup"><span data-stu-id="8b23f-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="8b23f-390">例如：</span><span class="sxs-lookup"><span data-stu-id="8b23f-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="8b23f-391">不能与单个宿主提供商建立多个联盟关系。</span><span class="sxs-lookup"><span data-stu-id="8b23f-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="8b23f-392">因此，如果你已设置与 sipfed.online.lync.com 建立联盟关系的宿主提供商，请不要为它添加其他宿主提供商，即使宿主提供商的标识不是 SkypeOnline。</span><span class="sxs-lookup"><span data-stu-id="8b23f-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="8b23f-393">在 Skype for Business Online 上设置组织与推送通知服务之间的宿主提供商联盟。</span><span class="sxs-lookup"><span data-stu-id="8b23f-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="8b23f-394">在命令行中，你需要键入：</span><span class="sxs-lookup"><span data-stu-id="8b23f-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="8b23f-395">启用推送通知</span><span class="sxs-lookup"><span data-stu-id="8b23f-395">Enable push notifications</span></span>

1. <span data-ttu-id="8b23f-396">使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b23f-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-397">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8b23f-398">启用推送通知：</span><span class="sxs-lookup"><span data-stu-id="8b23f-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="8b23f-399">启用联盟：</span><span class="sxs-lookup"><span data-stu-id="8b23f-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="8b23f-400">测试联合和推送通知</span><span class="sxs-lookup"><span data-stu-id="8b23f-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="8b23f-401">使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b23f-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-402">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8b23f-403">测试联盟配置：</span><span class="sxs-lookup"><span data-stu-id="8b23f-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="8b23f-404">例如：</span><span class="sxs-lookup"><span data-stu-id="8b23f-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="8b23f-405">测试推送通知：</span><span class="sxs-lookup"><span data-stu-id="8b23f-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="8b23f-406">例如：</span><span class="sxs-lookup"><span data-stu-id="8b23f-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="8b23f-407">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="8b23f-407">Configure Mobility policy</span></span>
<span data-ttu-id="8b23f-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="8b23f-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="8b23f-409">你能够使用 Skype for Business Server 来确定谁可以使用你的移动服务、通过工位呼叫、IP 语音 (VoIP) 或视频，以及 VoIP 或视频是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="8b23f-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="8b23f-410">通过工号呼叫可让移动用户在拨打和接听电话时使用工作电话号码，而不是其移动电话号码。</span><span class="sxs-lookup"><span data-stu-id="8b23f-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="8b23f-411">线路另一端的用户不会看到移动用户的移动电话号码，这样移动用户就不会产生传出呼叫费用。</span><span class="sxs-lookup"><span data-stu-id="8b23f-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="8b23f-412">设置 VoIP 和视频后，用户可以接听并拨打 VoIP 电话和视频。</span><span class="sxs-lookup"><span data-stu-id="8b23f-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="8b23f-413">WiFi 使用情况的设置确定是否需要用户的移动设备才能通过手机数据网络使用 WiFi 网络。</span><span class="sxs-lookup"><span data-stu-id="8b23f-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="8b23f-414">默认情况下，移动功能、通过工电话呼叫以及 VoIP 和视频功能全部启用。</span><span class="sxs-lookup"><span data-stu-id="8b23f-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="8b23f-415">禁用 VoIP 和视频需要 WiFi 的设置。</span><span class="sxs-lookup"><span data-stu-id="8b23f-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="8b23f-416">管理员能够全局、按站点或按用户更改此内容。</span><span class="sxs-lookup"><span data-stu-id="8b23f-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="8b23f-417">为了能够使用移动功能和通过工位呼叫功能，用户需要：</span><span class="sxs-lookup"><span data-stu-id="8b23f-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="8b23f-418">为 Skype for Business Server 启用</span><span class="sxs-lookup"><span data-stu-id="8b23f-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="8b23f-419">启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="8b23f-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="8b23f-420">分配了将 **EnableMobility** 选项设置为 True 的移动 **策略**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="8b23f-421">若要使用户能够使用通过工位呼叫功能，他们还需要：</span><span class="sxs-lookup"><span data-stu-id="8b23f-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="8b23f-422">分配了已选中"启用 **电话同时响铃"选项的** 语音策略。</span><span class="sxs-lookup"><span data-stu-id="8b23f-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="8b23f-423">分配了 **EnableOutsideVoice** 设置为 True 的移动 **策略**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8b23f-424">未启用 企业语音 的用户可以使用其移动设备拨打 Skype 到 Skype VoIP 呼叫，或在移动设备上使用"单击加入"链接加入会议（如果为与其关联的语音策略设置了适当的选项）。</span><span class="sxs-lookup"><span data-stu-id="8b23f-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="8b23f-425">规划主题中更详细地介绍。</span><span class="sxs-lookup"><span data-stu-id="8b23f-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="8b23f-426">修改全局移动策略</span><span class="sxs-lookup"><span data-stu-id="8b23f-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="8b23f-427">使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b23f-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-428">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8b23f-429">通过键入：</span><span class="sxs-lookup"><span data-stu-id="8b23f-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="8b23f-430">你可以关闭通过工电话呼叫功能，而无需关闭对移动功能的访问。</span><span class="sxs-lookup"><span data-stu-id="8b23f-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="8b23f-431">但是，如果不同时关闭通过工位呼叫，你无法关闭移动功能。</span><span class="sxs-lookup"><span data-stu-id="8b23f-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="8b23f-432">有关详细信息，请查看 [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8b23f-432">For more info, check out [Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="8b23f-433">按站点修改移动策略</span><span class="sxs-lookup"><span data-stu-id="8b23f-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="8b23f-434">使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b23f-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-435">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8b23f-436">你可以创建站点级别的策略、关闭 VoIP 和视频、按站点启用"IP 音频需要 WiFi"和"IP 视频需要 WiFi"。</span><span class="sxs-lookup"><span data-stu-id="8b23f-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="8b23f-437">类型：</span><span class="sxs-lookup"><span data-stu-id="8b23f-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="8b23f-438">有关详细信息，请通过 [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)了解。</span><span class="sxs-lookup"><span data-stu-id="8b23f-438">Learn more at [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="8b23f-439">按用户修改移动策略</span><span class="sxs-lookup"><span data-stu-id="8b23f-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="8b23f-440">使用 **CsAdministrator** 角色成员帐户登录到安装了 **Skype for Business Server** 命令行管理程序和 **Ocscore** 的计算机。</span><span class="sxs-lookup"><span data-stu-id="8b23f-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="8b23f-441">启动 **Skype for Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="8b23f-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8b23f-442">创建用户级别的移动策略，并按用户关闭移动和通过工位呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="8b23f-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="8b23f-443">类型：</span><span class="sxs-lookup"><span data-stu-id="8b23f-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="8b23f-444">示例数据的进一步示例：</span><span class="sxs-lookup"><span data-stu-id="8b23f-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="8b23f-445">你可以关闭通过工电话呼叫功能，而无需关闭对移动功能的访问。</span><span class="sxs-lookup"><span data-stu-id="8b23f-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="8b23f-446">但是，如果不同时关闭通过工位呼叫，你无法关闭移动功能。</span><span class="sxs-lookup"><span data-stu-id="8b23f-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
