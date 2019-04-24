---
title: 部署和配置 Mobility Skype 业务服务器
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将指导您完成配置用于 Mobility service，允许您的移动设备能够利用业务服务器移动功能的 Skype 业务服务器安装现有 Skype 的步骤。
ms.openlocfilehash: c9203bb90f4d4659819a4336c21f08e58785dfde
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233259"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="7b7e6-103">部署和配置 Mobility Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="7b7e6-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="7b7e6-104">本文将指导您完成配置用于 Mobility service，允许您的移动设备能够利用业务服务器移动功能的 Skype 业务服务器安装现有 Skype 的步骤。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="7b7e6-105">无审阅[规划适用于业务服务器 Skype 移动性](../plan-your-deployment/mobility.md)文章，您应该就可以继续使用下面的步骤部署移动到您的业务服务器环境的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="7b7e6-106">步骤如下所示（并且此表中包含权限列表）：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="7b7e6-107">**阶段**</span><span class="sxs-lookup"><span data-stu-id="7b7e6-107">**Phase**</span></span>|<span data-ttu-id="7b7e6-108">**权限**</span><span class="sxs-lookup"><span data-stu-id="7b7e6-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="7b7e6-109">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="7b7e6-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="7b7e6-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="7b7e6-110">Domain Admins</span></span>  <br/> <span data-ttu-id="7b7e6-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="7b7e6-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="7b7e6-112">修改证书</span><span class="sxs-lookup"><span data-stu-id="7b7e6-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="7b7e6-113">本地管理员</span><span class="sxs-lookup"><span data-stu-id="7b7e6-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="7b7e6-114">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="7b7e6-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="7b7e6-115">本地管理员</span><span class="sxs-lookup"><span data-stu-id="7b7e6-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="7b7e6-116">使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="7b7e6-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="7b7e6-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="7b7e6-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="7b7e6-118">测试移动功能部署</span><span class="sxs-lookup"><span data-stu-id="7b7e6-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="7b7e6-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b7e6-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="7b7e6-120">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="7b7e6-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="7b7e6-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7b7e6-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="7b7e6-122">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="7b7e6-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="7b7e6-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7b7e6-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="7b7e6-p102">以下所有部分都包含假定你已阅读规划主题的步骤。如果有任何让你感到困惑的地方，请随时查阅此处的信息。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="7b7e6-126">MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7b7e6-127">业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7b7e6-128">与使用 MCX 的旧客户端的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="7b7e6-129">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="7b7e6-129">Create DNS records</span></span>
<span data-ttu-id="7b7e6-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-130"></span></span>

<span data-ttu-id="7b7e6-131">您可能已经具有这些业务服务器环境中，您 Skype 的一部分，但您需要创建以下记录的自动发现工作：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="7b7e6-132">支持从组织网络内部进行连接的移动用户的内部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="7b7e6-133">支持从组织网络外部进行连接的移动用户的外部（或公共）DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="7b7e6-134">这些记录可以是 A（主机）名称或 CNAME 记录（你不必同时创建两者，我们这里只是将步骤都介绍一遍）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="7b7e6-135">创建内部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="7b7e6-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="7b7e6-136">以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="7b7e6-137">单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="7b7e6-138">在控制台窗口的左侧窗格中，您将需要转到域的承载到您的 Skype 的业务 Server 前端服务器，并展开存在的**正向查找区域**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="7b7e6-139">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="7b7e6-140">您的前端服务器 （标准版或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="7b7e6-141">任何主机 A 或 AAAA 记录的控制器或控制器池 （可选配置，您可以在部署中）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="7b7e6-142">记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建别名 (CNAME)**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="7b7e6-143">在**别名**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="7b7e6-144">在**完全限定的域名 (目标主机的 FQDN**，您需要键入或浏览到前端池 （或单个前端服务器或控制器池或控制器），上面的步骤 4 中标识的内部 Web 服务 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="7b7e6-145">输入后，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="7b7e6-146">您将需要在您 Skype 业务服务器环境中支持每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="7b7e6-147">创建外部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="7b7e6-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="7b7e6-148">这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="7b7e6-149">在此时间点，SIP 域应已存在那里 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="7b7e6-150">请展开此 SIP 域的**正向查找区域**，否则请打开它。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="7b7e6-151">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="7b7e6-152">您的前端服务器 （标准版或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="7b7e6-153">任何主机 A 或 AAAA 记录的控制器或控制器池 （可选配置，您可以在部署中）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="7b7e6-154">拥有该信息后，应该能够选择用于**新建别名 (CNAME)** 的选项。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="7b7e6-155">现在，你应该能够输入**别名**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="7b7e6-156">接下来应在**目标主机的 FQDN**中输入区域，这将需要为前端池 （或单个前端服务器或控制器池或控制器），在步骤 3 上述标识的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="7b7e6-157">您可能需要保存在这里，或者如果您需要在您 Skype 业务服务器环境中的每个 SIP 域的正向查找区域中创建额外的 CNAME 记录，您应这样一来，而您已准备好，一旦保存您的工作。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="7b7e6-158">创建内部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="7b7e6-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="7b7e6-159">以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="7b7e6-160">单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="7b7e6-161">在控制台窗口的左侧窗格中，您将需要转到域的承载到您的 Skype 的业务 Server 前端服务器，并展开存在的**正向查找区域**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="7b7e6-162">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="7b7e6-163">您的前端服务器 （标准版或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="7b7e6-164">任何主机 A 或 AAAA 记录的控制器或控制器池 （可选配置，您可以在部署中）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="7b7e6-165">记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建主机 (A 或 AAAA)**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="7b7e6-166">在**名称**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="7b7e6-167">在**IP 地址**文本框中，键入内部 Web 服务 IP 地址前端池 （或单个前端服务器或控制器池或控制器），上面的步骤 4 中标识。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="7b7e6-168">完成此操作后，单击**添加主机**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="7b7e6-169">您将需要在您 Skype 业务服务器环境中支持每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="7b7e6-170">为此，请根据需要多次重复步骤 6-8。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="7b7e6-171">完成后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="7b7e6-172">创建外部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="7b7e6-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="7b7e6-173">这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="7b7e6-174">在此时间点，SIP 域应已存在那里 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="7b7e6-175">请展开此 SIP 域的**正向查找区域**，否则请打开它。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="7b7e6-176">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="7b7e6-177">您的前端服务器 （标准版或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="7b7e6-178">任何主机 A 或 AAAA 记录的控制器或控制器池 （可选配置，您可以在部署中）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="7b7e6-179">拥有该信息后，应该能够选择用于创建**新主机 A 或 AAAA** 的选项。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="7b7e6-180">现在，你应该能够输入**名称**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="7b7e6-181">接下来应在**IP 地址**中输入区域，这将需要前端池 （或单个前端服务器或控制器池或控制器），上面的步骤 3 中标识的 IP。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="7b7e6-182">您可能需要保存在这里，或者如果您需要创建其他 A 或 AAAA 记录的每个 SIP 域的正向查找区域中的业务服务器环境您 Skype，则您应这样一来，但是一次您已准备好，保存您的工作。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="7b7e6-183">修改证书</span><span class="sxs-lookup"><span data-stu-id="7b7e6-183">Modify certificates</span></span>
<span data-ttu-id="7b7e6-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-184"></span></span>

<span data-ttu-id="7b7e6-185">如果您有疑问规划周围证书，我们已列出的我们[规划适用于业务服务器 Skype 移动性](../plan-your-deployment/mobility.md)的文章中。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="7b7e6-186">阅读该文章后，我们将引导你完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="7b7e6-187">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="7b7e6-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="7b7e6-188">从你的证书颁发机构 (CA) 请求新证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="7b7e6-189">使用 PowerShell 通过替换内容更新你的就地证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="7b7e6-190">检查证书将在 Microsoft 管理控制台 (MMC) 的证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="7b7e6-191">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="7b7e6-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="7b7e6-192">首先，你可能需要检查哪些证书是就地证书，以及它们是否具有所需的条目。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="7b7e6-193">为此，您需要登录到您的 Skype 业务服务器使用的是本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="7b7e6-194">此帐户可能还需要对证书颁发机构 (CA) 具有权限才能执行下面的某些步骤。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="7b7e6-195">打开 Skype 业务 Server Management Shell （您可以使用搜索来查找其，如果您没有其固定到开始菜单或任务栏）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="7b7e6-p110">你必须了解在尝试添加更新证书之前已分配哪些证书。因此，在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="7b7e6-p111">步骤 3 中的信息对你具有唯一性。你需要仔细检查，以确定你是否具有为所有内容分配的单个证书，或者是否具有为所需的不同组件分配的不同证书。**Use** 参数将告知你证书的使用方式，**Thumbprint** 参数将告知你所有证书都相同还是具有多个证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="7b7e6-p112">如果你已在规划部分中建议 SAN 条目，则可方便使用。如果没有，你需要从你的证书颁发机构请求一个新证书或多个证书（具体取决于你的配置）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="7b7e6-203">从你的证书颁发机构 (CA) 请求一个新证书或多个证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="7b7e6-204">检查你具有哪些 SAN 条目后，你就知道你具有**单个证书**（通过上述步骤检查后），并且你知道自己没有所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="7b7e6-205">需要向你的 CA 发出新证书请求。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="7b7e6-206">打开业务 Server PowerShell 您 Skype:</span><span class="sxs-lookup"><span data-stu-id="7b7e6-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="7b7e6-207">对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="7b7e6-208">现在，如果您有多个 SIP 域，则无法使用 AllSipDomain 参数，如上面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="7b7e6-209">你需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="7b7e6-210">当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="7b7e6-211">例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="7b7e6-212">或者，检查你具有哪些 SAN 条目后，你发现你具有**多个证书**，其中并不包含你所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="7b7e6-213">需要向你的 CA 发出新证书请求。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="7b7e6-214">打开业务 Server PowerShell 您 Skype:</span><span class="sxs-lookup"><span data-stu-id="7b7e6-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="7b7e6-215">对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="7b7e6-216">现在，如果您有多个 SIP 域，则无法使用 AllSipDomain 参数，如上面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="7b7e6-217">你需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="7b7e6-218">当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="7b7e6-219">例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="7b7e6-220">由 CA 生成新证书后，你需要对其进行分配。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7b7e6-221">使用 Skype for Business Server 命令行管理程序分配证书</span><span class="sxs-lookup"><span data-stu-id="7b7e6-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="7b7e6-222">根据你在上面的“是否需要新证书”部分中发现的内容，你需要运行以下命令**之一**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="7b7e6-223">如果所有内容具有单个证书（指纹相同），则需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="7b7e6-224">如果某些内容具有不同证书（指纹都不同），请改为运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="7b7e6-225">在 Microsoft 管理控制台 (MMC) 中查看证书</span><span class="sxs-lookup"><span data-stu-id="7b7e6-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="7b7e6-p117">你可以选择使用 MMC 的证书管理单元查看你的证书。只需在搜索中键入 MMC，它应作为应用程序选项弹出。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="7b7e6-p118">要添加证书管理单元，你需要单击**文件**，然后单击**添加/删除管理单元...**（或者键盘快捷方式 **Ctrl+M** 也会奏效）。**证书**将成为左侧窗格中的一个选项，选中它并在弹出窗口中单击**计算机帐户**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="7b7e6-230">仍在弹出窗口中，你极有可能在承载需要查看的证书的计算机上执行此操作，因此如果是那样，请选择**本地计算机**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="7b7e6-231">如果你正在远程计算机上工作，请将单选按钮更改为**其他计算机**，然后输入该计算机的 FQDN 或使用**浏览**按钮通过 AD 搜索该计算机。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="7b7e6-232">选择的计算机后, 需要**完成**准备好后，单击，然后单击**确定**以添加到 MMC 管理单元中。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="7b7e6-233">展开**证书**部分中 MMC 中的左侧窗格。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="7b7e6-234">还需展开**个人**文件夹，然后选择**证书**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="7b7e6-235">这样，你可以在此存储中查看证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="7b7e6-236">你需要查找要查看的证书，右键单击它，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b7e6-237">你如何知道这是什么证书？</span><span class="sxs-lookup"><span data-stu-id="7b7e6-237">How do you know what certificate this is?</span></span> <span data-ttu-id="7b7e6-238">它应分配给所有服务器场，或者是一个证书或您可能遇到的内容不同，如默认、 内部 Web 服务等的多个证书，在这种情况下，您可能需要查看多个证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="7b7e6-239">多个证书将具有相同的指纹。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="7b7e6-p122">进入**证书**视图后，选择**详细信息**。这样，你可以在选择**主题**时看到证书主题名称，并且会显示分配的主题名称和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="7b7e6-p123">你还需要检查**使用者替代名称**条目。你将发现以下一个或多个条目：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="7b7e6-244">没有为此池，池名称或单台服务器名称如果此池。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="7b7e6-245">向其分配证书的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="7b7e6-246">简单 URL 记录，一般为 meet 和 dialin。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="7b7e6-247">Web 内部服务和 Web 服务外部名称 （例如，webpool01.contoso.net、 webpool01.contoso.com），基于作出选择拓扑生成器和替代的 Web 服务选择中。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="7b7e6-248">如果已分配 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="7b7e6-249">如果分配有多个证书，你需要对其进行检查（查看上述备注）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="7b7e6-250">因此，如果您发现 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录，您就得到这已经配置。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="7b7e6-251">你可以关闭 MMC。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="7b7e6-252">如果未分配这些证书，你需要发出新证书请求（上面概述）或需要在请求后进行安装（我们建议使用上述 PowerShell 实现该目的）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="7b7e6-253">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="7b7e6-253">Configure the reverse proxy</span></span>
<span data-ttu-id="7b7e6-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-254"></span></span>

<span data-ttu-id="7b7e6-p125">不应严格遵循以下步骤。因为在该产品的早期版本中，我们已引导你配置 Threat Management Gateway (TMG)，如果你未使用该产品，你需要从其创建自己的版本。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="7b7e6-257">Microsoft 产品，作为不再提供 TMG 和如果仍需要对其进行配置，您可以查看[Lync Server 2013 的步骤](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="7b7e6-258">但的以下信息的用于很多通常，即使没有我们可以提供特定演练步骤有每台反向代理的方法。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="7b7e6-259">需要考虑以下两个主要事项：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="7b7e6-260">是否要通过 HTTPS（推荐）执行你的初始自动发现请求？</span><span class="sxs-lookup"><span data-stu-id="7b7e6-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="7b7e6-261">如果你具有 Web 发布规则，则需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="7b7e6-262">如果你还没有 Web 发布规则，则需要进行创建。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="7b7e6-263">如果你正在通过 HTTP 执行你的初始自动发现请求，则还需要创建或修改该规则。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7b7e6-264">**重要**代理超时值是一个数字，部署部署不同而有所不同。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="7b7e6-265">您应监视您的部署和修改客户端的最佳体验的值。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="7b7e6-266">您可能能够将值设置为 200 低。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="7b7e6-267">如果要在您的环境中支持 Lync 移动客户端，您应将值设置为 960 以便从 Office 365 的推送通知超时其 900 的超时值。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="7b7e6-268">很可能需要增加的超时值，以避免客户端断开连接的值为太低，或减少如果通过代理连接不断开但清除已断开客户端后，很长时间。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="7b7e6-269">监视和基准什么是通常针对您的环境是确定适当的设置为此值只准确方法。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="7b7e6-270">为你的外部自动发现 SAN 和 URL 修改现有 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="7b7e6-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="7b7e6-271">打开您的反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="7b7e6-272">您需要找到您的 web 发布规则，并选择编辑选项 （也可能在一个菜单或选项卡上，根据您的反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="7b7e6-273">应指明此 web 发布规则应用于的区域。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="7b7e6-274">你需要为传入站点或站点请求修改此规则。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="7b7e6-275">你要**添加**新条目。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="7b7e6-276">键入自动发现网站 （我们将使用的示例是 lyncdiscover.contoso.com） 的名称，然后单击**确定**或**保存**，具体取决于您的反向代理的格式。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="7b7e6-277">你可能会有一个其中具有自动发现 SAN 条目的新证书。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="7b7e6-278">需要在也安装并配置为使用根据反向代理服务器的设置。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="7b7e6-279">配置完成后，请务必保存所有内容。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="7b7e6-280">如果您的反向代理服务器有**测试**功能，则请制作使用它，以确保所有内容是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="7b7e6-281">现在，您可能需要重复这些步骤，如果您有控制器或控制器池您的环境中 （这意味着您有第二个规则）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="7b7e6-282">为外部自动发现 URL 创建 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="7b7e6-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="7b7e6-283">打开您的反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="7b7e6-284">您需要查找其中在界面创建您的 web 发布规则，并选择**新建**或**创建**选项 （也可能在一个菜单或选项卡上，根据您的反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="7b7e6-285">你要查找用于创建新的 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="7b7e6-286">通常，你需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="7b7e6-287">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="7b7e6-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="7b7e6-288">**规则操作**：**允许**规则在这种情况下，您让内容地通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="7b7e6-289">你选择的**发布**规则或选项将为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="7b7e6-290">这需要为 **SSL** 以供外部访问，请选择该选项。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="7b7e6-291">您将需要发布**内部发布**，应用程序的路径，然后在前端池的负载平衡器 （或如果您具有的控制器池的负载平衡器的 FQDN） 的外部 Web 服务输入的 FQDN，示例将是 sfb_pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="7b7e6-292">您应键入**/**\* 根据要发布的路径，但您还需要为**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="7b7e6-p131">有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="7b7e6-295">**接受请求**，但应为域名。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="7b7e6-296">对于**名称**，你应输入 **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="7b7e6-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="7b7e6-297"><sipdomain>（这是外部自动发现服务 URL）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="7b7e6-298">现在，如果您正在为前端池上的外部 Web 服务 URL 创建规则，您需要键入您的前端池 (例如，lyncwebextpool01.contoso.com) 上的外部 Web 服务的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="7b7e6-299">将**路径**选项中，而您需要输入**/**\* 此处。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="7b7e6-300">你需要选择具有最新公共证书的 **SSL 侦听器**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="7b7e6-301">**身份验证委派**应设置为**无委派**，但直接客户端身份验证**应**被允许。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="7b7e6-302">规则应设置为**所有用户**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="7b7e6-303">这应是创建此规则所需的所有信息，并且允许你继续操作。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="7b7e6-304">你需要确保已转发**原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="7b7e6-305">还需要设置 **Web 服务器**端口，为此，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="7b7e6-306">**将请求重定向到 HTTP 端口**，端口号应为 **8080**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="7b7e6-307">**将请求重定向到 SSL 端口**，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="7b7e6-308">一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="7b7e6-309">为端口 80 创建 Web 发布规则（可选）</span><span class="sxs-lookup"><span data-stu-id="7b7e6-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="7b7e6-310">打开您的反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="7b7e6-311">您需要查找其中在界面创建您的 web 发布规则，并选择**新建**或**创建**选项 （也可能在一个菜单或选项卡上，根据您的反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="7b7e6-312">你要查找用于创建新的 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="7b7e6-313">通常，你需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="7b7e6-314">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="7b7e6-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="7b7e6-315">**规则操作**：**允许**规则在这种情况下，您让内容地通过反向代理。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="7b7e6-316">你选择的**发布**规则或选项将为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="7b7e6-317">这必须为**用于连接发布的 Web 服务器或场的不安全连接**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="7b7e6-318">您将需要针对**内部发布**，发布一条路径，然后为前端池的负载平衡器的**VIP 地址**输入的 FQDN，sfb_pool01.contoso.local 就是一个示例。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="7b7e6-319">您应键入**/**\* 根据要发布的路径，但您还需要为**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="7b7e6-p134">有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="7b7e6-322">**接受请求**，但应为域名。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="7b7e6-323">对于**名称**，你应输入 **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="7b7e6-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="7b7e6-324"><sipdomain>（这是外部自动发现服务 URL）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="7b7e6-325">将**路径**选项中，而您需要输入**/**\* 此处。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="7b7e6-326">您将需要选择 web 侦听器，或允许您创建一个用于您的反向代理。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="7b7e6-327">**身份验证委派**应设置为**无委派**，但直接客户端身份验证**不应**被允许。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="7b7e6-328">规则应设置为**所有用户**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="7b7e6-329">这应是创建此规则所需的所有信息，并且允许你继续操作。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="7b7e6-330">需要设置 **Web 服务器**端口，为此，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="7b7e6-331">**将请求重定向到 HTTP 端口**，端口号应为 **8080**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="7b7e6-332">**将请求重定向到 SSL 端口**，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="7b7e6-333">一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="7b7e6-334">使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="7b7e6-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="7b7e6-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-335"></span></span>

<span data-ttu-id="7b7e6-336">混合环境中的业务服务器 Skype 是合并内部部署环境和 O365 环境。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="7b7e6-337">如果您的混合环境中工作的企业服务器有 Skype，自动发现服务需要能够找到用户从这些环境之一。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="7b7e6-p137">要让移动客户端发现用户所在位置，需要使用新的统一资源定位器 (URL) 配置自动发现服务。步骤包括：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="7b7e6-340">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="7b7e6-341">运行以下命令以获取您的业务服务器环境的 Skype 属性**ProxyFQDN**的值：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="7b7e6-342">然后，仍在 shell 窗口中，运行：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="7b7e6-343">其中 [identity] 使用共享 SIP 地址空间的域名替换。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="7b7e6-344">测试移动功能部署</span><span class="sxs-lookup"><span data-stu-id="7b7e6-344">Test your Mobility deployment</span></span>
<span data-ttu-id="7b7e6-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-345"></span></span>

<span data-ttu-id="7b7e6-346">一旦业务服务器自动发现服务的业务服务器 Mobility Service 和 Skype 部署 Skype，您需要运行测试事务，以确保您的部署工作均右。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="7b7e6-347">你可以运行 **Test-CsUcwaConference** 来测试两个用户能否创建和加入会议以及在会议中通信。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="7b7e6-348">你需要两个用户（实际或测试）及其完整凭据来执行此测试。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="7b7e6-349">此命令将这两个 Skype 工时业务客户端以及 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="7b7e6-350">对于业务服务器 2015年的 Skype 上的 Lync Server 2010 客户端，您需要运行**Test-CsMcxP2PIM**以测试。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="7b7e6-351">Lync Server 2010 用户仍需要是实际的用户或预定义的测试用户，您将需要凭据的密码。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="7b7e6-352">MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7b7e6-353">业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7b7e6-354">与使用 MCX 的旧客户端的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="7b7e6-355">测试 Skype for Business 和 Lync 2013 移动客户端的会议功能</span><span class="sxs-lookup"><span data-stu-id="7b7e6-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="7b7e6-356">安装**Business Server Management Shell 的 Skype**和**Ocscore**的任何计算机上**以 CsAdministrator**角色成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-357">启动**Business Server Management Shell 的 Skype** （您可能会在搜索中键入名称或转到**所有程序**并选择它）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="7b7e6-358">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="7b7e6-p141">还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="7b7e6-361">测试 Lync 2010 移动客户端的会议功能</span><span class="sxs-lookup"><span data-stu-id="7b7e6-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="7b7e6-362">MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7b7e6-363">业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7b7e6-364">与使用 MCX 的旧客户端的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="7b7e6-365">安装**Business Server Management Shell 的 Skype**和**Ocscore**的任何计算机上**以 CsAdministrator**角色成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-366">启动**Business Server Management Shell 的 Skype** （您可能会在搜索中键入名称或转到**所有程序**并选择它）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="7b7e6-367">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="7b7e6-p143">还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="7b7e6-370">要进一步查看命令过程，你可以参阅 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="7b7e6-371">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="7b7e6-371">Configure for push notifications</span></span>
<span data-ttu-id="7b7e6-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-372"></span></span>

<span data-ttu-id="7b7e6-373">即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="7b7e6-374">但是，什么是推送通知？</span><span class="sxs-lookup"><span data-stu-id="7b7e6-374">But what are push notifications?</span></span> <span data-ttu-id="7b7e6-375">它们是事件警报，如新的或错过的 IM 邀请，或收到的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="7b7e6-376">业务服务器 Mobility service 的 Skype 业务 Server 推送通知服务，为 Windows Phone 用户然后发送通知到 Microsoft 推送通知服务 (MSNS) 向基于云的 Skype 发送这些通知。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="7b7e6-377">此功能未更改从 Lync Server 2013，但如果您有 Skype 业务服务器，您需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="7b7e6-378">为业务 Server 边缘服务器 Skype，添加新的宿主提供程序，业务 online，Microsoft Skype，然后设置宿主提供商联盟之间您的组织和 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="7b7e6-p145">通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。默认情况下，推送通知已关闭。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="7b7e6-381">测试你的联盟配置和推送通知。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="7b7e6-382">针对推送通知配置你的 Skype for Business 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="7b7e6-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="7b7e6-383">使用登录到安装了**业务 Server Management Shell 的 Skype**和**Ocscore**的计算机**CsAdministrator**角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-384">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7b7e6-385">添加业务服务器联机宿主提供商 Skype。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="7b7e6-386">例如：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="7b7e6-p146">你不能与一个宿主提供程序建立多个联盟关系。因此，如果你已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 SkypeOnline 也是如此。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="7b7e6-389">设置您的组织与 Skype 的推送通知服务之间的业务联机宿主提供商联盟。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="7b7e6-390">在命令行中，你需要键入：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="7b7e6-391">启用推送通知</span><span class="sxs-lookup"><span data-stu-id="7b7e6-391">Enable push notifications</span></span>

1. <span data-ttu-id="7b7e6-392">使用登录到安装了**业务 Server Management Shell 的 Skype**和**Ocscore**的计算机**CsAdministrator**角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-393">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7b7e6-394">启用推送通知：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="7b7e6-395">启用联盟：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="7b7e6-396">测试联盟和推送通知</span><span class="sxs-lookup"><span data-stu-id="7b7e6-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="7b7e6-397">使用登录到安装了**业务 Server Management Shell 的 Skype**和**Ocscore**的计算机**CsAdministrator**角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-398">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7b7e6-399">测试联盟配置：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="7b7e6-400">例如：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="7b7e6-401">测试你的推送通知：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="7b7e6-402">例如：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="7b7e6-403">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="7b7e6-403">Configure Mobility policy</span></span>
<span data-ttu-id="7b7e6-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="7b7e6-404"></span></span>

<span data-ttu-id="7b7e6-405">您可以使用业务服务器，以确定谁可以使用 Mobility service 的 Skype，用单位电话呼叫，语音 IP 电话 (VoIP) 或视频，以及是否 WiFi 将需要 VoIP 或视频。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="7b7e6-406">使用通过工号拨号功能，移动用户可以在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="7b7e6-407">该线路另一端上的人员不会看到移动用户的移动电话号码，并且可以让移动用户避免产生拨出呼叫费用。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="7b7e6-408">设置 VoIP 和视频后，用户可以接收和发出 VoIP 呼叫和视频。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="7b7e6-409">WiFi 用法的设置确定通过蜂窝数据网络使用 WiFi 网络是否需要用户的移动设备。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="7b7e6-410">移动、 通过单位电话呼叫和 VoIP 和视频功能是默认启用的。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="7b7e6-411">禁用了 VoIp 和视频需要 WiFi 的设置。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="7b7e6-412">管理员可以全局、按网站或按用户对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="7b7e6-413">为了能够使用移动功能和呼叫用单位电话，用户必须是：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="7b7e6-414">为业务 Server 启用的 Skype</span><span class="sxs-lookup"><span data-stu-id="7b7e6-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="7b7e6-415">启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="7b7e6-416">分配已将**EnableMobility**选项设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="7b7e6-417">对于希望能使用通过工号拨号功能的用户，他们还必须：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="7b7e6-418">分配已选择**允许多部电话同时响铃**选项的语音策略。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="7b7e6-419">分配有**EnableOutsideVoice**将设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7b7e6-p150">未启用企业语音的用户可以使用其移动设备发出 Skype 至 Skype VoIP 呼叫，也可以使用“单击以加入”链接来通过移动设备加入会议（如果已为与其关联的语音策略设置相应的选项）。规划主题中有更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="7b7e6-422">修改全局移动策略</span><span class="sxs-lookup"><span data-stu-id="7b7e6-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="7b7e6-423">使用登录到安装了**业务 Server Management Shell 的 Skype**和**Ocscore**的计算机**CsAdministrator**角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-424">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7b7e6-425">关闭访问移动功能和单位电话呼叫全局通过键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="7b7e6-426">关闭关闭移动访问的情况下，可以关闭用单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="7b7e6-427">但不能关闭不还关闭用单位电话呼叫的移动。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="7b7e6-428">有关详细信息，查看[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="7b7e6-429">修改由网站的移动策略</span><span class="sxs-lookup"><span data-stu-id="7b7e6-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="7b7e6-430">使用登录到安装了**业务 Server Management Shell 的 Skype**和**Ocscore**的计算机**CsAdministrator**角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-431">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7b7e6-p152">你可以创建站点级别的策略、禁用 VoIP 和视频，以及按网站启用“IP 音频需要 WiFi”和“IP 视频需要 WiFi”。键入：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="7b7e6-434">在 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps) 中了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="7b7e6-435">修改用户移动策略</span><span class="sxs-lookup"><span data-stu-id="7b7e6-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="7b7e6-436">使用登录到安装了**业务 Server Management Shell 的 Skype**和**Ocscore**的计算机**CsAdministrator**角色的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="7b7e6-437">启动**Skype 的业务 Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7b7e6-438">创建用户级别的移动策略，并关闭移动功能和呼叫用单位电话的用户。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="7b7e6-439">键入：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="7b7e6-440">包含示例数据的另一个示例：</span><span class="sxs-lookup"><span data-stu-id="7b7e6-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="7b7e6-441">关闭关闭移动访问的情况下，可以关闭用单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="7b7e6-442">但不能关闭不还关闭用单位电话呼叫的移动。</span><span class="sxs-lookup"><span data-stu-id="7b7e6-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

