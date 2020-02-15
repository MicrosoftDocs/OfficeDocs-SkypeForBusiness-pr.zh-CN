---
title: 为 Skype for business Server 部署和配置移动功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将指导您完成配置现有 Skype for Business Server 安装以使用移动服务的步骤，从而使您的移动设备能够充分利用 Skype for business Server 移动功能。
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029063"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="c484e-103">为 Skype for business Server 部署和配置移动功能</span><span class="sxs-lookup"><span data-stu-id="c484e-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="c484e-104">本文将指导您完成配置现有 Skype for Business Server 安装以使用移动服务的步骤，从而使您的移动设备能够充分利用 Skype for business Server 移动功能。</span><span class="sxs-lookup"><span data-stu-id="c484e-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="c484e-105">查看了[Skype For Business server 的移动性计划](../plan-your-deployment/mobility.md)，应准备好继续执行以下步骤，以将移动性部署到 Skype For business server 环境中。</span><span class="sxs-lookup"><span data-stu-id="c484e-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="c484e-106">步骤如下所示（我们将在此表中加入权限列表中）：</span><span class="sxs-lookup"><span data-stu-id="c484e-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="c484e-107">**阶段**</span><span class="sxs-lookup"><span data-stu-id="c484e-107">**Phase**</span></span>|<span data-ttu-id="c484e-108">**权限**</span><span class="sxs-lookup"><span data-stu-id="c484e-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c484e-109">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c484e-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="c484e-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="c484e-110">Domain Admins</span></span>  <br/> <span data-ttu-id="c484e-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="c484e-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="c484e-112">修改证书</span><span class="sxs-lookup"><span data-stu-id="c484e-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="c484e-113">本地管理员</span><span class="sxs-lookup"><span data-stu-id="c484e-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="c484e-114">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="c484e-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="c484e-115">本地管理员</span><span class="sxs-lookup"><span data-stu-id="c484e-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="c484e-116">为具有混合部署的移动性配置自动发现</span><span class="sxs-lookup"><span data-stu-id="c484e-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="c484e-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="c484e-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="c484e-118">测试移动性部署</span><span class="sxs-lookup"><span data-stu-id="c484e-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="c484e-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c484e-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="c484e-120">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="c484e-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="c484e-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c484e-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="c484e-122">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="c484e-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="c484e-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="c484e-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="c484e-124">以下所有部分都包含假设您已阅读规划主题的步骤。</span><span class="sxs-lookup"><span data-stu-id="c484e-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="c484e-125">如果有任何困惑，请随时查看此处的信息。</span><span class="sxs-lookup"><span data-stu-id="c484e-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="c484e-126">Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。</span><span class="sxs-lookup"><span data-stu-id="c484e-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c484e-127">所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="c484e-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c484e-128">具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="c484e-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="c484e-129">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c484e-129">Create DNS records</span></span>
<span data-ttu-id="c484e-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="c484e-131">您可能已将这些作为 Skype for Business Server 环境的一部分，但您需要创建以下记录才能使自动发现正常工作：</span><span class="sxs-lookup"><span data-stu-id="c484e-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="c484e-132">支持从组织网络内部进行连接的移动用户的内部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="c484e-133">支持从组织网络外部连接的移动用户的外部（或公共） DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="c484e-134">这些记录可以是（主机）名称或 CNAME 记录（无需同时执行这两种操作）。</span><span class="sxs-lookup"><span data-stu-id="c484e-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="c484e-135">创建内部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="c484e-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="c484e-136">以**Domain Admins**组或**DnsAdmins**组成员的身份登录到网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="c484e-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="c484e-137">单击 "**开始**"，选择 "**管理工具**" （如果不是 "开始" 菜单上的选项，您可能需要进行**搜索**），然后单击 " **dns** " 以打开 "dns 管理" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="c484e-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="c484e-138">在控制台窗口的左侧窗格中，需要转到位于 Skype for business Server 前端服务器的主域，然后在此处展开 "**正向查找区域**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="c484e-139">请花点时间查看你的以下哪一项：</span><span class="sxs-lookup"><span data-stu-id="c484e-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c484e-140">前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c484e-141">控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="c484e-142">记下此项后，右键单击您的 SIP 域名，然后从菜单中选择 "**新建别名（CNAME）** "。</span><span class="sxs-lookup"><span data-stu-id="c484e-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="c484e-143">在 "**别名名称**" 文本框中，为内部自动发现服务 URL 键入 lyncdiscoverinternal. 作为主机名。</span><span class="sxs-lookup"><span data-stu-id="c484e-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="c484e-144">在**完全限定的域名（FQDN 用于目标主机**中，需要键入或浏览到前端池（或单个前端服务器，或控制器池或控制器）的内部 WEB 服务 FQDN （在上面的步骤4中确定）。</span><span class="sxs-lookup"><span data-stu-id="c484e-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="c484e-145">输入此输入时，单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="c484e-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="c484e-146">您需要在 Skype for Business Server 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="c484e-147">创建外部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="c484e-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="c484e-148">这些步骤是一般性的，因为我们无法知道您可能正在使用什么公共 DNS 提供程序，但我们仍希望帮助你。请使用能够将新的 DNS 记录放在其中的帐户登录到您的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="c484e-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="c484e-149">在此时间点，SIP 域应已存在于 Skype for business Server 中。</span><span class="sxs-lookup"><span data-stu-id="c484e-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="c484e-150">展开此 SIP 域的**正向查找区域**，或以其他方式打开它。</span><span class="sxs-lookup"><span data-stu-id="c484e-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="c484e-151">请花点时间查看你的以下哪一项：</span><span class="sxs-lookup"><span data-stu-id="c484e-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c484e-152">前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c484e-153">控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="c484e-154">拥有该信息后，您应该能够选择用于创建**新别名（CNAME）** 的选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="c484e-155">现在，您应该能够输入**别名**，您需要在此处输入外部自动发现服务 URL 的 lyncdiscover.。</span><span class="sxs-lookup"><span data-stu-id="c484e-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="c484e-156">接下来，应该有一个要输入到**目标主机的 fqdn**中的区域，这将需要是前端池（或单个前端服务器，或控制器池或控制器）的 fqdn，在上面的步骤3中进行了标识。</span><span class="sxs-lookup"><span data-stu-id="c484e-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="c484e-157">您可能需要在此处保存，或者如果需要在 Skype for Business Server 环境中的每个 SIP 域的正向查找区域中创建其他 CNAME 记录，则应执行此操作，但在准备好后，请保存您的工作。</span><span class="sxs-lookup"><span data-stu-id="c484e-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="c484e-158">创建内部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="c484e-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="c484e-159">以**Domain Admins**组或**DnsAdmins**组成员的身份登录到网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="c484e-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="c484e-160">单击 "**开始**"，选择 "**管理工具**" （如果不是 "开始" 菜单上的选项，您可能需要进行**搜索**），然后单击 " **dns** " 以打开 "dns 管理" 管理单元。</span><span class="sxs-lookup"><span data-stu-id="c484e-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="c484e-161">在控制台窗口的左侧窗格中，需要转到位于 Skype for business Server 前端服务器的主域，然后在此处展开 "**正向查找区域**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="c484e-162">请花点时间查看你的以下哪一项：</span><span class="sxs-lookup"><span data-stu-id="c484e-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c484e-163">前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c484e-164">控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="c484e-165">记下此项后，右键单击您的 SIP 域名，然后从菜单中选择 "**新建主机（A 或 AAAA）** "。</span><span class="sxs-lookup"><span data-stu-id="c484e-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="c484e-166">在 "**名称**" 文本框中，为 "内部自动发现服务" URL 键入 lyncdiscoverinternal. 作为主机名。</span><span class="sxs-lookup"><span data-stu-id="c484e-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="c484e-167">在 " **IP 地址**" 文本框中，键入前端池（或单个前端服务器，或控制器池或控制器）的内部 WEB 服务 IP 地址，这些地址在上述步骤4中确定。</span><span class="sxs-lookup"><span data-stu-id="c484e-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="c484e-168">完成此操作后，单击 "**添加主机**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c484e-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="c484e-169">您需要在 Skype for business Server 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="c484e-170">为此，请根据需要重复步骤6-8 多次。</span><span class="sxs-lookup"><span data-stu-id="c484e-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="c484e-171">完成后，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="c484e-172">创建外部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="c484e-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="c484e-173">这些步骤是一般性的，因为我们无法知道您可能正在使用什么公共 DNS 提供程序，但我们仍希望帮助你。请使用能够将新的 DNS 记录放在其中的帐户登录到您的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="c484e-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="c484e-174">在此时间点，SIP 域应已存在于 Skype for business Server 中。</span><span class="sxs-lookup"><span data-stu-id="c484e-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="c484e-175">展开此 SIP 域的**正向查找区域**，或以其他方式打开它。</span><span class="sxs-lookup"><span data-stu-id="c484e-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="c484e-176">请花点时间查看你的以下哪一项：</span><span class="sxs-lookup"><span data-stu-id="c484e-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="c484e-177">前端服务器（标准版或企业版）或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="c484e-178">控制器或控制器池的任何主机 A 或 AAAA 记录（您在部署中可能已有的可选配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="c484e-179">拥有该信息后，您应该能够选择用于创建**新主机 a 或 AAAA**的选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="c484e-180">现在，您应该能够输入**名称**，您需要在此处输入外部自动发现服务 URL 的 lyncdiscover.。</span><span class="sxs-lookup"><span data-stu-id="c484e-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="c484e-181">接下来，应该有一个区域可在**Ip Addresss**中输入，这将需要是前端池（或单个前端服务器，或控制器池或控制器）的 ip，在上面的步骤3中进行了标识。</span><span class="sxs-lookup"><span data-stu-id="c484e-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="c484e-182">您可能需要保存到此处，或者，如果需要在每个 SIP 域的正向查找区域中为 Skype for Business Server 环境创建额外的 A 或 AAAA 记录，则应执行此操作，但在准备好后，请保存您的工作。</span><span class="sxs-lookup"><span data-stu-id="c484e-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="c484e-183">修改证书</span><span class="sxs-lookup"><span data-stu-id="c484e-183">Modify certificates</span></span>
<span data-ttu-id="c484e-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="c484e-185">如果你对证书规划有疑问，我们已在计划中介绍了[Skype for Business Server 文章的移动性](../plan-your-deployment/mobility.md)方面的问题。</span><span class="sxs-lookup"><span data-stu-id="c484e-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="c484e-186">审阅之后，我们将指导您完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="c484e-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="c484e-187">我是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="c484e-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="c484e-188">从证书颁发机构（CA）请求新证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="c484e-189">使用 PowerShell 更新就地证书和替换。</span><span class="sxs-lookup"><span data-stu-id="c484e-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="c484e-190">使用 Microsoft 管理控制台（MMC）中的 "证书" 管理单元检查证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="c484e-191">我是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="c484e-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="c484e-192">首先，您可能需要检查并查看哪些证书是现成的，以及它们是否具有所需的条目。</span><span class="sxs-lookup"><span data-stu-id="c484e-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="c484e-193">为此，你需要使用本地管理员帐户登录到你的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="c484e-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="c484e-194">此帐户可能还需要对颁发证书颁发机构（CA）拥有权限，其中一些步骤也可能需要。</span><span class="sxs-lookup"><span data-stu-id="c484e-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="c484e-195">打开 Skype for Business Server 命令行管理程序（如果未将其固定到 "开始" 菜单或任务栏，则可以使用 "搜索" 来查找它）。</span><span class="sxs-lookup"><span data-stu-id="c484e-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="c484e-196">在尝试添加已更新的证书之前，必须先了解已分配的证书，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="c484e-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="c484e-197">在命令中，键入：</span><span class="sxs-lookup"><span data-stu-id="c484e-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="c484e-198">步骤3中的信息将对您是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c484e-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="c484e-199">您需要对其进行查找，以确定是否已为多个项目分配了一个证书，或者是否为需要的不同组件分配了不同的证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="c484e-200">**使用**参数将告诉你证书的使用方式，以及**指纹**参数将告知你是使用相同的证书还是多个证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="c484e-201">如果我们的 "规划" 部分中有建议的 SAN 条目，那么您是个理想之用。</span><span class="sxs-lookup"><span data-stu-id="c484e-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="c484e-202">如果不是，则需要从证书颁发机构请求一个新证书或多个证书（具体取决于您的配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="c484e-203">从证书颁发机构（CA）请求新证书或证书</span><span class="sxs-lookup"><span data-stu-id="c484e-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="c484e-204">检查以查看您拥有的 SAN 条目后，您会知道您有一个**证书**（通过上述步骤进行检查后），并且您了解到您没有所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="c484e-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="c484e-205">需要向你的 CA 发出新的证书请求。</span><span class="sxs-lookup"><span data-stu-id="c484e-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="c484e-206">打开 Skype for Business Server PowerShell：</span><span class="sxs-lookup"><span data-stu-id="c484e-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="c484e-207">对于缺少的自动发现服务 SAN （将-Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="c484e-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="c484e-208">现在，如果您有多个 SIP 域，则不能使用 AllSipDomain 参数，如上面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c484e-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="c484e-209">你需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="c484e-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="c484e-210">使用 DomainName 参数时，您必须定义 lyncdiscoverinternal. 和 lyncdiscover. 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c484e-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="c484e-211">例如（将-Ca 参数替换为您自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="c484e-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="c484e-212">或者，在检查以查看您拥有的 SAN 条目之后，您发现您有**多个证书**没有您所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="c484e-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="c484e-213">需要向你的 CA 发出新的证书请求。</span><span class="sxs-lookup"><span data-stu-id="c484e-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="c484e-214">打开 Skype for Business Server PowerShell：</span><span class="sxs-lookup"><span data-stu-id="c484e-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="c484e-215">对于缺少的自动发现服务 SAN （将-Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="c484e-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="c484e-216">现在，如果您有多个 SIP 域，则不能使用 AllSipDomain 参数，如上面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="c484e-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="c484e-217">你需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="c484e-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="c484e-218">使用 DomainName 参数时，您必须定义 lyncdiscoverinternal. 和 lyncdiscover. 记录的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c484e-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="c484e-219">例如（将-Ca 参数替换为您自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="c484e-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="c484e-220">在 CA 生成新证书后，您需要对其进行分配。</span><span class="sxs-lookup"><span data-stu-id="c484e-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c484e-221">使用 Skype for Business Server 命令行管理程序分配证书</span><span class="sxs-lookup"><span data-stu-id="c484e-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="c484e-222">根据您在上面的 "我需要新的认证" 一节中找到的内容，您需要运行以下各**项之一**。</span><span class="sxs-lookup"><span data-stu-id="c484e-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="c484e-223">如果你有一个证书用于所有内容（指纹完全相同），则需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c484e-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="c484e-224">如果你的事物有不同的证书（指纹都是不同的），请改为运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="c484e-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="c484e-225">在 Microsoft 管理控制台（MMC）中查看证书</span><span class="sxs-lookup"><span data-stu-id="c484e-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="c484e-226">您可以选择使用 MMC 的 "证书" 管理单元查看您的证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="c484e-227">只需将 MMC 键入到搜索中，就应将其作为应用程序选项进行弹出。</span><span class="sxs-lookup"><span data-stu-id="c484e-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="c484e-228">若要添加证书管理单元，需要单击 "**文件**"，然后 "**添加/删除管理单元 ...** " （或键盘快捷方式**Ctrl + M**也有效）。</span><span class="sxs-lookup"><span data-stu-id="c484e-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="c484e-229">**证书**将是左侧窗格中的一个选项，在弹出窗口中依次选择 "**计算机帐户**" 和 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="c484e-230">仍在弹出窗口中，在您需要查看的证书所在的计算机上执行此操作时，请在**本地计算机**上保留所选内容（如果这样做的话）。</span><span class="sxs-lookup"><span data-stu-id="c484e-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="c484e-231">如果正在远程计算机上工作，请将单选按钮更改为**另一台计算机**，然后输入该计算机的 FQDN 或使用 "**浏览**" 按钮，通过 AD 搜索该计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="c484e-232">选择计算机后，需要在准备好后单击 "**完成**"，然后单击 **"确定"** 以将该管理单元添加到 MMC。</span><span class="sxs-lookup"><span data-stu-id="c484e-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="c484e-233">在 MMC 的左侧窗格中展开 "**证书**" 部分。</span><span class="sxs-lookup"><span data-stu-id="c484e-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="c484e-234">同时展开 "**个人**" 文件夹，然后选择 "**证书**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="c484e-235">这将允许您查看此存储中的证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="c484e-236">您需要找到要查看的证书，右键单击该证书，然后选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c484e-237">您如何知道这是什么证书？</span><span class="sxs-lookup"><span data-stu-id="c484e-237">How do you know what certificate this is?</span></span> <span data-ttu-id="c484e-238">它应该是分配给服务器场所有内容的单个证书，或者您可能有不同事物的多个证书，如默认设置、内部 Web 服务等。在这种情况下，您可能需要查看多个证书。</span><span class="sxs-lookup"><span data-stu-id="c484e-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="c484e-239">多个证书将具有相同的指纹。</span><span class="sxs-lookup"><span data-stu-id="c484e-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="c484e-240">进入**证书**视图后，请选择 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="c484e-241">这将允许您在选择 "**主题**" 时查看证书主题名称，并显示分配的主题名称和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="c484e-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="c484e-242">你还需要检查**主题替代名称**条目。</span><span class="sxs-lookup"><span data-stu-id="c484e-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="c484e-243">您将找到以下一个或多个选项：</span><span class="sxs-lookup"><span data-stu-id="c484e-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="c484e-244">此池的池名称，如果不是池，则为单个服务器名称。</span><span class="sxs-lookup"><span data-stu-id="c484e-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="c484e-245">证书分配到的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="c484e-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="c484e-246">简单的 URL 记录，通常是 "符合" 和 "拨入"。</span><span class="sxs-lookup"><span data-stu-id="c484e-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="c484e-247">Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），这取决于在拓扑生成器和替代 Web 服务选择中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="c484e-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="c484e-248">如果已分配，则为 lyncdiscover.。\<sipdomain\>和 lyncdiscoverinternal.。\<sipdomain\>记录。</span><span class="sxs-lookup"><span data-stu-id="c484e-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="c484e-249">如果分配了多个证书，则需要检查多个证书（请选中上面的注释）。</span><span class="sxs-lookup"><span data-stu-id="c484e-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="c484e-250">如果找到 lyncdiscover.，则为。\<sipdomain\>和 lyncdiscoverinternal.。\<sipdomain\>记录，您已进行了此配置。</span><span class="sxs-lookup"><span data-stu-id="c484e-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="c484e-251">您可以关闭 MMC。</span><span class="sxs-lookup"><span data-stu-id="c484e-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="c484e-252">如果未分配，则需要创建新的证书请求（如上所述），或者需要将其安装在 post 请求中（我们建议上述针对此的 PowerShell）。</span><span class="sxs-lookup"><span data-stu-id="c484e-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="c484e-253">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="c484e-253">Configure the reverse proxy</span></span>
<span data-ttu-id="c484e-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="c484e-255">下面的步骤并不应完全遵循。</span><span class="sxs-lookup"><span data-stu-id="c484e-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="c484e-256">这是因为在产品的早期版本中，我们已向你介绍了，例如，配置威胁管理网关（TMG），如果你未使用，则需要从那里使用自己的版本。</span><span class="sxs-lookup"><span data-stu-id="c484e-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="c484e-257">TMG 不再由 Microsoft 作为产品提供，如果仍需要对其进行配置，则可以查看[Lync Server 2013 步骤](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c484e-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="c484e-258">但是，以下信息的预期更为普遍，即使无法为每个反向代理提供具体的演练步骤，也是如此。</span><span class="sxs-lookup"><span data-stu-id="c484e-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="c484e-259">要考虑的主要事项有两个：</span><span class="sxs-lookup"><span data-stu-id="c484e-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="c484e-260">您是否要通过 HTTPS 执行初始自动发现请求（我们建议这样做）？</span><span class="sxs-lookup"><span data-stu-id="c484e-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="c484e-261">如果您有 web 发布规则，则需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="c484e-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="c484e-262">如果还没有 web 发布规则，则需要创建它。</span><span class="sxs-lookup"><span data-stu-id="c484e-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="c484e-263">如果你正在通过 HTTP 执行初始自动发现请求，则还需要创建或修改该规则。</span><span class="sxs-lookup"><span data-stu-id="c484e-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c484e-264">**重要说明**代理超时值是一个数字，该数字将因部署而异。</span><span class="sxs-lookup"><span data-stu-id="c484e-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="c484e-265">您应监视您的部署并修改客户端的最佳体验的价值。</span><span class="sxs-lookup"><span data-stu-id="c484e-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="c484e-266">您可以将值设置为低达200。</span><span class="sxs-lookup"><span data-stu-id="c484e-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="c484e-267">如果您在您的环境中支持 Lync 移动客户端，则应将值设置为960，以允许来自 Office 365 的推送通知超时（超时值为900）。</span><span class="sxs-lookup"><span data-stu-id="c484e-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="c484e-268">很可能需要增加超时值，以避免在值太低时客户端断开连接，或者如果在客户端断开连接后，通过代理连接不会断开连接，则减少号码。</span><span class="sxs-lookup"><span data-stu-id="c484e-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="c484e-269">监视和设置环境的常规设置是确定此值的适当设置的唯一准确方式。</span><span class="sxs-lookup"><span data-stu-id="c484e-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="c484e-270">修改外部自动发现 SAN 和 URL 的现有 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="c484e-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="c484e-271">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="c484e-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c484e-272">您需要找到 web 发布规则，然后选择 "编辑" 选项（它可能位于菜单或选项卡上，具体取决于反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="c484e-273">应有一个区域，指出该 web 发布规则的应用内容。</span><span class="sxs-lookup"><span data-stu-id="c484e-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="c484e-274">您需要为传入的网站或网站的请求修改此规则。</span><span class="sxs-lookup"><span data-stu-id="c484e-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="c484e-275">你**将添加**新条目。</span><span class="sxs-lookup"><span data-stu-id="c484e-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="c484e-276">键入自动发现网站的名称（我们将使用的示例是 lyncdiscover.contoso.com），然后单击 **"确定" 或 "** **保存**"，具体取决于反向代理的格式。</span><span class="sxs-lookup"><span data-stu-id="c484e-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="c484e-277">您可能具有一个新证书，其中包含自动发现 SAN 条目。</span><span class="sxs-lookup"><span data-stu-id="c484e-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="c484e-278">还需要安装并配置为根据反向代理的设置使用。</span><span class="sxs-lookup"><span data-stu-id="c484e-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="c484e-279">完成配置后，请务必保存所有内容。</span><span class="sxs-lookup"><span data-stu-id="c484e-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="c484e-280">如果反向代理具有**测试**功能，请使用它，以确保一切正常工作。</span><span class="sxs-lookup"><span data-stu-id="c484e-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="c484e-281">现在，如果您的环境中有一个控制器或控制器池（这意味着您有第二个规则），您可能需要重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c484e-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="c484e-282">为外部自动发现 URL 创建 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="c484e-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="c484e-283">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="c484e-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c484e-284">您需要在界面中创建 web 发布规则的位置查找，然后选择 "**新建**" 或 "**创建**" 选项（它可能位于菜单或选项卡上，具体取决于反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="c484e-285">您正在寻找创建新的 web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="c484e-286">通常情况下，您需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="c484e-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="c484e-287">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="c484e-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="c484e-288">**规则操作**：在这种情况下，这是**允许**的规则，您可以通过反向代理进行某个传递。</span><span class="sxs-lookup"><span data-stu-id="c484e-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="c484e-289">您要选择的**发布**规则或选项为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="c484e-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="c484e-290">这需要是用于外部访问的**SSL** ，请选择该选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="c484e-291">您需要发布**内部发布**的路径，并在前端池的负载平衡器（或控制器池的负载平衡器的 fqdn （如果有））中输入外部 Web 服务的 fqdn，例如，sfb_pool01 为 "contoso. 本地"。</span><span class="sxs-lookup"><span data-stu-id="c484e-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="c484e-292">应键入\*\* / \*\*\* 作为要发布的路径，但还需要**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="c484e-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="c484e-293">将有一个用于**公用或外部名称**详细信息或信息的选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="c484e-294">你可以在此处输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="c484e-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="c484e-295">**接受请求**，但它应针对域名。</span><span class="sxs-lookup"><span data-stu-id="c484e-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="c484e-296">对于**名称**，您应输入 " **lyncdiscover."。**</span><span class="sxs-lookup"><span data-stu-id="c484e-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="c484e-297"><sipdomain>（这是外部自动发现服务 URL）。</span><span class="sxs-lookup"><span data-stu-id="c484e-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="c484e-298">现在，如果要为前端池上的外部 Web 服务 URL 创建规则，则需要为前端池上的外部 Web 服务键入 FQDN （例如，lyncwebextpool01.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="c484e-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="c484e-299">将有一个**路径**选项，您需要在此处输入\*\* / \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c484e-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="c484e-300">你需要选择具有最新公共证书的**SSL 侦听器**。</span><span class="sxs-lookup"><span data-stu-id="c484e-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="c484e-301">**身份验证委派**应设置为 "**无委派**"，但**应**允许直接客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="c484e-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="c484e-302">应将规则设置为 "**所有用户**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="c484e-303">这应该是创建此规则所需的所有信息，并允许您继续操作。</span><span class="sxs-lookup"><span data-stu-id="c484e-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="c484e-304">您需要确保**原始主机标头**已转发。</span><span class="sxs-lookup"><span data-stu-id="c484e-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="c484e-305">还需要设置**Web 服务器**端口，您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c484e-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="c484e-306">将**请求重定向到 HTTP 端口**，端口号应为**8080**。</span><span class="sxs-lookup"><span data-stu-id="c484e-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="c484e-307">将**请求重定向到 SSL 端口**，端口号应为**4443**。</span><span class="sxs-lookup"><span data-stu-id="c484e-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="c484e-308">配置所有内容后，需要保存或应用这些内容，然后您将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="c484e-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="c484e-309">为端口80创建 web 发布规则（可选）</span><span class="sxs-lookup"><span data-stu-id="c484e-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="c484e-310">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="c484e-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="c484e-311">您需要在界面中创建 web 发布规则的位置查找，然后选择 "**新建**" 或 "**创建**" 选项（它可能位于菜单或选项卡上，具体取决于反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="c484e-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="c484e-312">您正在寻找创建新的 web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="c484e-313">通常情况下，您需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="c484e-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="c484e-314">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="c484e-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="c484e-315">**规则操作**：在这种情况下，这是**允许**的规则，您可以通过反向代理进行某个传递。</span><span class="sxs-lookup"><span data-stu-id="c484e-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="c484e-316">您要选择的**发布**规则或选项为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="c484e-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="c484e-317">这需要是**连接到发布的 Web 服务器或服务器场的非安全连接**。</span><span class="sxs-lookup"><span data-stu-id="c484e-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="c484e-318">您需要发布**内部发布**的路径，并输入前端池的负载平衡器的**VIP 地址**的 FQDN，例如，sfb_pool01 为 "contoso. 本地"。</span><span class="sxs-lookup"><span data-stu-id="c484e-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="c484e-319">应键入\*\* / \*\*\* 作为要发布的路径，但还需要**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="c484e-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="c484e-320">将有一个用于**公用或外部名称**详细信息或信息的选项。</span><span class="sxs-lookup"><span data-stu-id="c484e-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="c484e-321">你可以在此处输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="c484e-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="c484e-322">**接受请求**，但它应针对域名。</span><span class="sxs-lookup"><span data-stu-id="c484e-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="c484e-323">对于**名称**，您应输入 " **lyncdiscover."。**</span><span class="sxs-lookup"><span data-stu-id="c484e-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="c484e-324"><sipdomain>（这是外部自动发现服务 URL）。</span><span class="sxs-lookup"><span data-stu-id="c484e-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="c484e-325">将有一个**路径**选项，您需要在此处输入\*\* / \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c484e-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="c484e-326">你需要选择 web 侦听器，或允许反向代理为你创建一个侦听器。</span><span class="sxs-lookup"><span data-stu-id="c484e-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="c484e-327">**身份验证委派**应设置为 "**无委派**"，但**不应**允许直接客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="c484e-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="c484e-328">应将规则设置为 "**所有用户**"。</span><span class="sxs-lookup"><span data-stu-id="c484e-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="c484e-329">这应该是创建此规则所需的所有信息，并允许您继续操作。</span><span class="sxs-lookup"><span data-stu-id="c484e-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="c484e-330">需要设置**Web 服务器**端口，将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c484e-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="c484e-331">将**请求重定向到 HTTP 端口**，端口号应为**8080**。</span><span class="sxs-lookup"><span data-stu-id="c484e-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="c484e-332">将**请求重定向到 SSL 端口**，端口号应为**4443**。</span><span class="sxs-lookup"><span data-stu-id="c484e-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="c484e-333">配置所有内容后，需要保存或应用这些内容，然后您将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="c484e-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="c484e-334">为具有混合部署的移动性配置自动发现</span><span class="sxs-lookup"><span data-stu-id="c484e-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="c484e-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="c484e-336">Skype for Business Server 中的混合环境是结合了本地和 O365 环境的环境。</span><span class="sxs-lookup"><span data-stu-id="c484e-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="c484e-337">当您的 Skype for Business Server 在混合环境中工作时，自动发现服务需要能够从这些环境中的任一环境中查找用户。</span><span class="sxs-lookup"><span data-stu-id="c484e-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="c484e-338">若要让移动客户端发现用户所在的位置，则需要使用新的统一资源定位器（URL）配置自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="c484e-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="c484e-339">步骤如下：</span><span class="sxs-lookup"><span data-stu-id="c484e-339">The steps are:</span></span>
  
1. <span data-ttu-id="c484e-340">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="c484e-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="c484e-341">运行以下命令，获取 Skype for Business Server 环境的属性**ProxyFQDN**的值：</span><span class="sxs-lookup"><span data-stu-id="c484e-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="c484e-342">然后，仍在命令行管理程序窗口中运行：</span><span class="sxs-lookup"><span data-stu-id="c484e-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="c484e-343">其中 [identity] 使用共享 SIP 地址空间的域名替换。</span><span class="sxs-lookup"><span data-stu-id="c484e-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="c484e-344">测试移动性部署</span><span class="sxs-lookup"><span data-stu-id="c484e-344">Test your Mobility deployment</span></span>
<span data-ttu-id="c484e-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="c484e-346">部署 Skype for Business Server 移动服务和 Skype for business Server 自动发现服务后，您需要运行测试事务，以确保部署的工作正确。</span><span class="sxs-lookup"><span data-stu-id="c484e-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="c484e-347">您可以运行**test-csucwaconference**以测试两个用户在会议中创建、加入和交流的能力。</span><span class="sxs-lookup"><span data-stu-id="c484e-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="c484e-348">你将需要两个用户（实际或测试）及其完整凭据来执行此测试。</span><span class="sxs-lookup"><span data-stu-id="c484e-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="c484e-349">此命令将适用于 Skype for business 客户端和 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="c484e-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="c484e-350">对于 Skype for Business Server 2015 上的 Lync Server 2010 客户端，您需要运行**测试 test-csmcxp2pim**以进行测试。</span><span class="sxs-lookup"><span data-stu-id="c484e-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="c484e-351">你的 Lync Server 2010 用户仍必须是实际用户或预定义的测试用户，并且你将需要其密码凭据。</span><span class="sxs-lookup"><span data-stu-id="c484e-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="c484e-352">Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。</span><span class="sxs-lookup"><span data-stu-id="c484e-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c484e-353">所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="c484e-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c484e-354">具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="c484e-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="c484e-355">为 Skype for Business 和 Lync 2013 移动客户端测试会议</span><span class="sxs-lookup"><span data-stu-id="c484e-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="c484e-356">在安装了**Skype For Business Server 命令行管理**程序和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c484e-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-357">启动**Skype For Business Server 命令行管理程序**（可以在 "搜索" 中键入名称，也可以选择 "转到**所有程序**" 并选择它）。</span><span class="sxs-lookup"><span data-stu-id="c484e-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="c484e-358">在命令行中，输入：</span><span class="sxs-lookup"><span data-stu-id="c484e-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="c484e-359">此外，还可以在脚本中设置凭据并将其传递给测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c484e-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="c484e-360">下面举例介绍了这一点。</span><span class="sxs-lookup"><span data-stu-id="c484e-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="c484e-361">为 Lync 2010 移动客户端测试会议</span><span class="sxs-lookup"><span data-stu-id="c484e-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="c484e-362">Skype for Business Server 2019 中不再提供对旧版移动客户端的 MCX （移动服务）支持。</span><span class="sxs-lookup"><span data-stu-id="c484e-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="c484e-363">所有当前 Skype for Business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="c484e-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="c484e-364">具有使用 MCX 的旧版客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="c484e-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="c484e-365">在安装了**Skype For Business Server 命令行管理**程序和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c484e-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-366">启动**Skype For Business Server 命令行管理程序**（可以在 "搜索" 中键入名称，也可以选择 "转到**所有程序**" 并选择它）。</span><span class="sxs-lookup"><span data-stu-id="c484e-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="c484e-367">在命令行中，输入：</span><span class="sxs-lookup"><span data-stu-id="c484e-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="c484e-368">此外，还可以在脚本中设置凭据并将其传递给测试 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c484e-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="c484e-369">下面举例介绍了这一点。</span><span class="sxs-lookup"><span data-stu-id="c484e-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="c484e-370">若要进一步查看命令过程，可以查看[test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)和[test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c484e-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="c484e-371">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="c484e-371">Configure for push notifications</span></span>
<span data-ttu-id="c484e-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="c484e-373">即使在 Skype 或 Lync 应用处于非活动状态时，也可以将徽章、图标或警报等推送通知发送到移动设备。</span><span class="sxs-lookup"><span data-stu-id="c484e-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="c484e-374">但什么是推送通知？</span><span class="sxs-lookup"><span data-stu-id="c484e-374">But what are push notifications?</span></span> <span data-ttu-id="c484e-375">它们是事件警报，如新的或错过的 IM 邀请，或接收到的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="c484e-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="c484e-376">Skype for Business Server 移动服务将这些通知发送到基于云的 Skype for Business Server 推送通知服务，后者随后会将通知发送给 Windows Phone 用户的 Microsoft 推送通知服务（MSNS）。</span><span class="sxs-lookup"><span data-stu-id="c484e-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="c484e-377">此功能在 Lync Server 2013 中保持不变，但如果你有 Skype for Business 服务器，你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c484e-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="c484e-378">对于 Skype for Business Server 边缘服务器，请添加新的托管提供程序、Microsoft Skype for Business Online，然后在您的组织和 Skype for business Online 之间设置托管提供程序联盟。</span><span class="sxs-lookup"><span data-stu-id="c484e-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="c484e-379">通过运行**CsPushNotificationConfiguration** cmdlet 启用推送通知。</span><span class="sxs-lookup"><span data-stu-id="c484e-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="c484e-380">默认情况下，推送通知已关闭。</span><span class="sxs-lookup"><span data-stu-id="c484e-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="c484e-381">测试联合身份验证配置和推送通知。</span><span class="sxs-lookup"><span data-stu-id="c484e-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="c484e-382">为推送通知配置 Skype for Business 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="c484e-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="c484e-383">使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-384">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="c484e-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c484e-385">添加 Skype for Business Server online 托管提供商。</span><span class="sxs-lookup"><span data-stu-id="c484e-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="c484e-386">例如：</span><span class="sxs-lookup"><span data-stu-id="c484e-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="c484e-387">同一个托管提供程序不能有多个联合关系。</span><span class="sxs-lookup"><span data-stu-id="c484e-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="c484e-388">因此，如果您已经设置了与 sipfed.online.lync.com 具有联合关系的托管提供程序，则不要为其添加另一个托管提供程序，即使承载提供程序的标识是 SkypeOnline 以外的其他内容也是如此。</span><span class="sxs-lookup"><span data-stu-id="c484e-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="c484e-389">在您的组织和 Skype for Business Online 的推送通知服务之间设置托管提供程序联盟。</span><span class="sxs-lookup"><span data-stu-id="c484e-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="c484e-390">在命令行中，需要键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="c484e-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="c484e-391">启用推送通知</span><span class="sxs-lookup"><span data-stu-id="c484e-391">Enable push notifications</span></span>

1. <span data-ttu-id="c484e-392">使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-393">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="c484e-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c484e-394">启用推送通知：</span><span class="sxs-lookup"><span data-stu-id="c484e-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="c484e-395">启用联盟：</span><span class="sxs-lookup"><span data-stu-id="c484e-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="c484e-396">测试联盟和推送通知</span><span class="sxs-lookup"><span data-stu-id="c484e-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="c484e-397">使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-398">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="c484e-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c484e-399">测试联合身份验证配置：</span><span class="sxs-lookup"><span data-stu-id="c484e-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="c484e-400">例如：</span><span class="sxs-lookup"><span data-stu-id="c484e-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="c484e-401">测试推送通知：</span><span class="sxs-lookup"><span data-stu-id="c484e-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="c484e-402">例如：</span><span class="sxs-lookup"><span data-stu-id="c484e-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="c484e-403">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="c484e-403">Configure Mobility policy</span></span>
<span data-ttu-id="c484e-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="c484e-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="c484e-405">您可以使用 Skype for Business Server 来确定哪些用户可以使用移动服务、通过工作呼叫、IP 语音（VoIP）或视频，以及 VoIP 或视频是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="c484e-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="c484e-406">通过工作进行呼叫可让移动用户在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。</span><span class="sxs-lookup"><span data-stu-id="c484e-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="c484e-407">行另一端的人将看不到移动用户的手机号码，并允许移动用户避免传出呼叫费用。</span><span class="sxs-lookup"><span data-stu-id="c484e-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="c484e-408">在设置 VoIP 和视频时，用户可以采用并发出 VoIP 呼叫和视频。</span><span class="sxs-lookup"><span data-stu-id="c484e-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="c484e-409">WiFi 使用的设置决定了用户的移动设备是否需要通过蜂窝数据网络使用 WiFi 网络。</span><span class="sxs-lookup"><span data-stu-id="c484e-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="c484e-410">默认情况下，移动、通过工作呼叫以及 VoIP 和视频功能均已启用。</span><span class="sxs-lookup"><span data-stu-id="c484e-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="c484e-411">禁用 VoIP 和视频需要 WiFi 的设置。</span><span class="sxs-lookup"><span data-stu-id="c484e-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="c484e-412">管理员可以按网站或按用户更改全局权限。</span><span class="sxs-lookup"><span data-stu-id="c484e-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="c484e-413">若要能够通过工作使用移动功能和呼叫，用户必须：</span><span class="sxs-lookup"><span data-stu-id="c484e-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="c484e-414">为 Skype for Business Server 启用</span><span class="sxs-lookup"><span data-stu-id="c484e-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="c484e-415">启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="c484e-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="c484e-416">分配了一个将**EnableMobility**选项设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="c484e-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="c484e-417">为使用户能够通过工作使用呼叫，他们还需要：</span><span class="sxs-lookup"><span data-stu-id="c484e-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="c484e-418">为选择 "**启用同时响铃的电话**" 选项分配了语音策略。</span><span class="sxs-lookup"><span data-stu-id="c484e-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="c484e-419">分配了一个将**EnableOutsideVoice**设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="c484e-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c484e-420">未启用企业语音的用户可以使用其移动设备进行 Skype 到 Skype VoIP 呼叫，也可以在移动设备上使用 "单击此处加入会议" （如果为其关联的语音策略设置了相应的选项）加入会议。带有.</span><span class="sxs-lookup"><span data-stu-id="c484e-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="c484e-421">规划主题中有更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c484e-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="c484e-422">修改全局移动策略</span><span class="sxs-lookup"><span data-stu-id="c484e-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="c484e-423">使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-424">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="c484e-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c484e-425">通过键入以下内容，禁止访问移动性并通过工作全球化呼叫：</span><span class="sxs-lookup"><span data-stu-id="c484e-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="c484e-426">您可以在不关闭对移动性的访问的情况下关闭通过工作的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c484e-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="c484e-427">但您不能关闭移动功能，而无需通过工作关闭呼叫。</span><span class="sxs-lookup"><span data-stu-id="c484e-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="c484e-428">有关详细信息，请参阅[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c484e-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="c484e-429">按网站修改移动策略</span><span class="sxs-lookup"><span data-stu-id="c484e-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="c484e-430">使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-431">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="c484e-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c484e-432">您可以创建站点级别的策略，关闭 VoIP 和视频，启用 IP 音频的需要 WiFi，并需要按站点的 IP 视频的 WiFi。</span><span class="sxs-lookup"><span data-stu-id="c484e-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="c484e-433">类型：</span><span class="sxs-lookup"><span data-stu-id="c484e-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="c484e-434">有关详细信息，请参阅[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c484e-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="c484e-435">按用户修改移动策略</span><span class="sxs-lookup"><span data-stu-id="c484e-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="c484e-436">使用**CsAdministrator**角色的成员的帐户登录到安装了**Skype For Business Server 命令行管理程序**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="c484e-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="c484e-437">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="c484e-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c484e-438">创建用户级别移动策略，并通过用户的工作方式关闭移动性和呼叫。</span><span class="sxs-lookup"><span data-stu-id="c484e-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="c484e-439">类型：</span><span class="sxs-lookup"><span data-stu-id="c484e-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="c484e-440">示例数据的另一个示例：</span><span class="sxs-lookup"><span data-stu-id="c484e-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="c484e-441">您可以在不关闭对移动性的访问的情况下关闭通过工作的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c484e-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="c484e-442">但您不能关闭移动功能，而无需通过工作关闭呼叫。</span><span class="sxs-lookup"><span data-stu-id="c484e-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

