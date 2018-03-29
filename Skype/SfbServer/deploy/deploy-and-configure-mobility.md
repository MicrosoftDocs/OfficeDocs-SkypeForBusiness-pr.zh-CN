---
title: 部署和配置 Skype for Business Server 2015 的移动功能
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 这篇文章将引导您完成配置为使用移动服务，使您能够充分利用 Skype 业务服务器移动功能的移动设备业务服务器 2015年安装现有 Skype 的步骤。
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a><span data-ttu-id="a177f-103">部署和配置 Skype for Business Server 2015 的移动功能</span><span class="sxs-lookup"><span data-stu-id="a177f-103">Deploy and Configure Mobility for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a177f-104">这篇文章将引导您完成配置为使用移动服务，使您能够充分利用 Skype 业务服务器移动功能的移动设备业务服务器 2015年安装现有 Skype 的步骤。</span><span class="sxs-lookup"><span data-stu-id="a177f-104">This article will walk you through the steps to configure an existing Skype for Business Server 2015 installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="a177f-105">我们已看过[规划业务服务器 2015年的 Skype 的移动性](../plan-your-deployment/mobility.md)文章，您应该可以继续下面的步骤将部署移动到您 Skype 业务服务器 2015年环境。</span><span class="sxs-lookup"><span data-stu-id="a177f-105">Having reviewed the [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server 2015 environment.</span></span> <span data-ttu-id="a177f-106">步骤如下所示（并且此表中包含权限列表）：</span><span class="sxs-lookup"><span data-stu-id="a177f-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="a177f-107">**阶段**</span><span class="sxs-lookup"><span data-stu-id="a177f-107">**Phase**</span></span>|<span data-ttu-id="a177f-108">**权限**</span><span class="sxs-lookup"><span data-stu-id="a177f-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a177f-109">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a177f-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="a177f-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a177f-110">Domain Admins</span></span>  <br/> <span data-ttu-id="a177f-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="a177f-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="a177f-112">修改证书</span><span class="sxs-lookup"><span data-stu-id="a177f-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="a177f-113">本地管理员</span><span class="sxs-lookup"><span data-stu-id="a177f-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a177f-114">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="a177f-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="a177f-115">本地管理员</span><span class="sxs-lookup"><span data-stu-id="a177f-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="a177f-116">使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="a177f-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="a177f-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="a177f-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="a177f-118">测试移动功能部署</span><span class="sxs-lookup"><span data-stu-id="a177f-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="a177f-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a177f-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="a177f-120">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="a177f-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="a177f-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a177f-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="a177f-122">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="a177f-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="a177f-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a177f-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="a177f-p102">以下所有部分都包含假定你已阅读规划主题的步骤。如果有任何让你感到困惑的地方，请随时查阅此处的信息。</span><span class="sxs-lookup"><span data-stu-id="a177f-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="a177f-126">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="a177f-126">Create DNS records</span></span>
<span data-ttu-id="a177f-127"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-127"></span></span>

<span data-ttu-id="a177f-128">您可能已经为您的业务服务器环境中，Skype 的一部分，但您需要创建以下有关自动搜索工作记录：</span><span class="sxs-lookup"><span data-stu-id="a177f-128">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="a177f-129">支持从组织网络内部进行连接的移动用户的内部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-129">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="a177f-130">支持从组织网络外部进行连接的移动用户的外部（或公共）DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-130">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="a177f-131">这些记录可以是 A（主机）名称或 CNAME 记录（你不必同时创建两者，我们这里只是将步骤都介绍一遍）。</span><span class="sxs-lookup"><span data-stu-id="a177f-131">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="a177f-132">创建内部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a177f-132">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="a177f-133">以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="a177f-133">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a177f-134">单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a177f-134">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a177f-135">在控制台窗口的左侧窗格中，您需要转到域的业务服务器的前端服务器，对于家庭到您 Skype 就展开**正向搜索区域**存在。</span><span class="sxs-lookup"><span data-stu-id="a177f-135">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a177f-136">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="a177f-136">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a177f-137">您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-137">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a177f-138">任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-138">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a177f-139">记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建别名 (CNAME)**。</span><span class="sxs-lookup"><span data-stu-id="a177f-139">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="a177f-140">在**别名**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="a177f-140">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a177f-141">在**完全合格的域名称 (FQDN 目标主机的**，您需要键入或浏览到内部 Web 服务 FQDN 前端池 （或单个前端服务器，或总监池或控制器），在上面的步骤 4 中标识。</span><span class="sxs-lookup"><span data-stu-id="a177f-141">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="a177f-142">输入后，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="a177f-142">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="a177f-143">您将需要在您 Skype 业务服务器环境中支持每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-143">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="a177f-144">创建外部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="a177f-144">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="a177f-145">这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a177f-145">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a177f-146">在此时间点，SIP 域应该存在存在于 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="a177f-146">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="a177f-147">请展开此 SIP 域的**正向查找区域**，否则请打开它。</span><span class="sxs-lookup"><span data-stu-id="a177f-147">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a177f-148">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="a177f-148">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a177f-149">您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-149">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a177f-150">任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-150">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a177f-151">拥有该信息后，应该能够选择用于**新建别名 (CNAME)** 的选项。</span><span class="sxs-lookup"><span data-stu-id="a177f-151">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="a177f-152">现在，你应该能够输入**别名**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="a177f-152">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a177f-153">下一步应该有一个区域进入一个**目标主机的 FQDN**，则需要为前端池 （或单个前端服务器，或总监池或控制器），上面的第 3 步中标识出的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a177f-153">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a177f-154">您可能需要保存在这里，或者如果您需要在您 Skype 业务服务器环境中的每个 SIP 域的正向查找区域中创建附加的 CNAME 记录，您应该做，但一旦你已准备好，保存您的工作。</span><span class="sxs-lookup"><span data-stu-id="a177f-154">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="a177f-155">创建内部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="a177f-155">Create an internal DNS A record</span></span>

1. <span data-ttu-id="a177f-156">以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="a177f-156">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="a177f-157">单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。</span><span class="sxs-lookup"><span data-stu-id="a177f-157">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="a177f-158">在控制台窗口的左侧窗格中，您需要转到域的业务服务器的前端服务器，对于家庭到您 Skype 就展开**正向搜索区域**存在。</span><span class="sxs-lookup"><span data-stu-id="a177f-158">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="a177f-159">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="a177f-159">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a177f-160">您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-160">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a177f-161">任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-161">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="a177f-162">记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建主机 (A 或 AAAA)**。</span><span class="sxs-lookup"><span data-stu-id="a177f-162">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="a177f-163">在**名称**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="a177f-163">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="a177f-164">在**IP 地址**文本框中，键入前端池 （或单个前端服务器，或总监池或控制器），内部 Web 服务 IP 地址标识在上面的步骤 4 中。</span><span class="sxs-lookup"><span data-stu-id="a177f-164">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="a177f-165">完成此操作后，单击**添加主机**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a177f-165">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="a177f-166">您将需要在您 Skype 业务服务器环境中支持每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-166">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="a177f-167">为此，请根据需要多次重复步骤 6-8。</span><span class="sxs-lookup"><span data-stu-id="a177f-167">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="a177f-168">完成后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="a177f-168">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="a177f-169">创建外部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="a177f-169">Create an external DNS A record</span></span>

1. <span data-ttu-id="a177f-170">这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="a177f-170">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="a177f-171">在此时间点，SIP 域应该存在存在于 Skype 业务服务器 2015年个。</span><span class="sxs-lookup"><span data-stu-id="a177f-171">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="a177f-172">请展开此 SIP 域的**正向查找区域**，否则请打开它。</span><span class="sxs-lookup"><span data-stu-id="a177f-172">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="a177f-173">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="a177f-173">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="a177f-174">您的前端服务器 （常用或企业） 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-174">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="a177f-175">任何主机 A 或 AAAA 记录为主任或主任池 （部署中可能会有可选配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-175">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="a177f-176">拥有该信息后，应该能够选择用于创建**新主机 A 或 AAAA** 的选项。</span><span class="sxs-lookup"><span data-stu-id="a177f-176">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="a177f-177">现在，你应该能够输入**名称**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="a177f-177">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="a177f-178">下一步应在**IP 地址**中输入区域，这将需要前端池 （或单个前端服务器，或总监池或控制器），在上面的步骤 3 中标识的 IP。</span><span class="sxs-lookup"><span data-stu-id="a177f-178">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="a177f-179">您可能需要保存在这里，或者如果您需要创建其他 A 或 AAAA 记录每个 SIP 域的正向查找区域中供您的企业服务器环境的 Skype，您应该做的但一次就可以，保存您的工作。</span><span class="sxs-lookup"><span data-stu-id="a177f-179">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="a177f-180">修改证书</span><span class="sxs-lookup"><span data-stu-id="a177f-180">Modify certificates</span></span>
<span data-ttu-id="a177f-181"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-181"></span></span>

<span data-ttu-id="a177f-182">如果您有关于规划围绕证书的问题，我们已经记录，在我们[规划业务服务器 2015年的 Skype 的移动性](../plan-your-deployment/mobility.md)的文章。</span><span class="sxs-lookup"><span data-stu-id="a177f-182">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="a177f-183">阅读该文章后，我们将引导你完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a177f-183">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="a177f-184">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="a177f-184">Do I need new certificates?</span></span>
    
- <span data-ttu-id="a177f-185">从你的证书颁发机构 (CA) 请求新证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-185">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="a177f-186">使用 PowerShell 通过替换内容更新你的就地证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-186">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="a177f-187">检查使用证书管理单元在 Microsoft 管理控制台 (MMC) 的证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-187">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="a177f-188">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="a177f-188">Do I need new certificates?</span></span>

1. <span data-ttu-id="a177f-189">首先，你可能需要检查哪些证书是就地证书，以及它们是否具有所需的条目。</span><span class="sxs-lookup"><span data-stu-id="a177f-189">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="a177f-190">为此，您需要登录到您的业务服务器 2015年服务器的本地管理员帐户的 Skype。</span><span class="sxs-lookup"><span data-stu-id="a177f-190">To do that, you'll need to log into your Skype for Business Server 2015 server with an account that's a local Administrator.</span></span> <span data-ttu-id="a177f-191">此帐户可能还需要对证书颁发机构 (CA) 具有权限才能执行下面的某些步骤。</span><span class="sxs-lookup"><span data-stu-id="a177f-191">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="a177f-192">打开 Skype 业务服务器命令行管理程序 （您可以使用搜索来找到它，如果您没有固定到您的开始菜单或任务条）。</span><span class="sxs-lookup"><span data-stu-id="a177f-192">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="a177f-p109">你必须了解在尝试添加更新证书之前已分配哪些证书。因此，在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a177f-p109">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="a177f-p110">步骤 3 中的信息对你具有唯一性。你需要仔细检查，以确定你是否具有为所有内容分配的单个证书，或者是否具有为所需的不同组件分配的不同证书。**Use** 参数将告知你证书的使用方式，**Thumbprint** 参数将告知你所有证书都相同还是具有多个证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-p110">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="a177f-p111">如果你已在规划部分中建议 SAN 条目，则可方便使用。如果没有，你需要从你的证书颁发机构请求一个新证书或多个证书（具体取决于你的配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-p111">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="a177f-200">从你的证书颁发机构 (CA) 请求一个新证书或多个证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-200">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="a177f-201">检查你具有哪些 SAN 条目后，你就知道你具有**单个证书**（通过上述步骤检查后），并且你知道自己没有所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="a177f-201">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="a177f-202">需要向你的 CA 发出新证书请求。</span><span class="sxs-lookup"><span data-stu-id="a177f-202">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a177f-203">打开您的 Skype 业务服务器 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a177f-203">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a177f-204">对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="a177f-204">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a177f-p113">现在，如果你有多个 SIP 域，则无法使用如上述示例中所示的 AllSipDomain 参数。你需要改为使用 DomainName 参数。当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="a177f-p113">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="a177f-209">或者，检查你具有哪些 SAN 条目后，你发现你具有**多个证书**，其中并不包含你所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="a177f-209">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="a177f-210">需要向你的 CA 发出新证书请求。</span><span class="sxs-lookup"><span data-stu-id="a177f-210">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="a177f-211">打开您的 Skype 业务服务器 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a177f-211">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="a177f-212">对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="a177f-212">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="a177f-p115">现在，如果你有多个 SIP 域，则无法使用如上述示例中所示的 AllSipDomain 参数。你需要改为使用 DomainName 参数。当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="a177f-p115">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="a177f-217">由 CA 生成新证书后，你需要对其进行分配。</span><span class="sxs-lookup"><span data-stu-id="a177f-217">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a177f-218">使用 Skype for Business Server 命令行管理程序分配证书</span><span class="sxs-lookup"><span data-stu-id="a177f-218">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="a177f-219">根据你在上面的“是否需要新证书”部分中发现的内容，你需要运行以下命令**之一**。</span><span class="sxs-lookup"><span data-stu-id="a177f-219">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="a177f-220">如果所有内容具有单个证书（指纹相同），则需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a177f-220">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="a177f-221">如果某些内容具有不同证书（指纹都不同），请改为运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a177f-221">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="a177f-222">在 Microsoft 管理控制台 (MMC) 中查看证书</span><span class="sxs-lookup"><span data-stu-id="a177f-222">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="a177f-p116">你可以选择使用 MMC 的证书管理单元查看你的证书。只需在搜索中键入 MMC，它应作为应用程序选项弹出。</span><span class="sxs-lookup"><span data-stu-id="a177f-p116">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="a177f-p117">要添加证书管理单元，你需要单击**文件**，然后单击**添加/删除管理单元...**（或者键盘快捷方式 **Ctrl+M** 也会奏效）。**证书**将成为左侧窗格中的一个选项，选中它并在弹出窗口中单击**计算机帐户**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a177f-p117">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="a177f-227">仍在弹出窗口中，你极有可能在承载需要查看的证书的计算机上执行此操作，因此如果是那样，请选择**本地计算机**。</span><span class="sxs-lookup"><span data-stu-id="a177f-227">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="a177f-228">如果你正在远程计算机上工作，请将单选按钮更改为**其他计算机**，然后输入该计算机的 FQDN 或使用**浏览**按钮通过 AD 搜索该计算机。</span><span class="sxs-lookup"><span data-stu-id="a177f-228">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="a177f-229">选择的计算机后, 您需要**完成**准备完成后，单击，然后单击**确定**以将该管理单元添加到 MMC。</span><span class="sxs-lookup"><span data-stu-id="a177f-229">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="a177f-230">展开在 MMC 的左侧窗格中的**证书**部分。</span><span class="sxs-lookup"><span data-stu-id="a177f-230">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="a177f-231">还需展开**个人**文件夹，然后选择**证书**。</span><span class="sxs-lookup"><span data-stu-id="a177f-231">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="a177f-232">这样，你可以在此存储中查看证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-232">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="a177f-233">你需要查找要查看的证书，右键单击它，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="a177f-233">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a177f-234">你如何知道这是什么证书？</span><span class="sxs-lookup"><span data-stu-id="a177f-234">How do you know what certificate this is?</span></span> <span data-ttu-id="a177f-235">它应该是分配给您的服务器场中，所有内容都是单个证书或可能有的不同技能，如默认值、 内部 Web 服务等多个证书，这种情况下，您可能需要查看多个证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-235">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="a177f-236">多个证书将具有相同的指纹。</span><span class="sxs-lookup"><span data-stu-id="a177f-236">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="a177f-p121">进入**证书**视图后，选择**详细信息**。这样，你可以在选择**主题**时看到证书主题名称，并且会显示分配的主题名称和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="a177f-p121">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="a177f-p122">你还需要检查**使用者替代名称**条目。你将发现以下一个或多个条目：</span><span class="sxs-lookup"><span data-stu-id="a177f-p122">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="a177f-241">为该池的池名称或如果此单个服务器名称不是一个池。</span><span class="sxs-lookup"><span data-stu-id="a177f-241">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="a177f-242">向其分配证书的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="a177f-242">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="a177f-243">简单 URL 记录，一般为 meet 和 dialin。</span><span class="sxs-lookup"><span data-stu-id="a177f-243">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="a177f-244">Web 服务内部和 Web 服务外部名称 （例如，webpool01.contoso.net，webpool01.contoso.com），根据所做的选择中拓扑生成器和覆盖的 Web 服务选择。</span><span class="sxs-lookup"><span data-stu-id="a177f-244">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="a177f-245">如果已分配，lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。</span><span class="sxs-lookup"><span data-stu-id="a177f-245">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="a177f-246">如果分配有多个证书，你需要对其进行检查（查看上述备注）。</span><span class="sxs-lookup"><span data-stu-id="a177f-246">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="a177f-247">因此，如果您发现 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>的记录，您果然已经配置。</span><span class="sxs-lookup"><span data-stu-id="a177f-247">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="a177f-248">你可以关闭 MMC。</span><span class="sxs-lookup"><span data-stu-id="a177f-248">You can close the MMC.</span></span>
    
9. <span data-ttu-id="a177f-249">如果未分配这些证书，你需要发出新证书请求（上面概述）或需要在请求后进行安装（我们建议使用上述 PowerShell 实现该目的）。</span><span class="sxs-lookup"><span data-stu-id="a177f-249">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="a177f-250">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="a177f-250">Configure the reverse proxy</span></span>
<span data-ttu-id="a177f-251"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-251"></span></span>

<span data-ttu-id="a177f-p124">不应严格遵循以下步骤。因为在该产品的早期版本中，我们已引导你配置 Threat Management Gateway (TMG)，如果你未使用该产品，你需要从其创建自己的版本。</span><span class="sxs-lookup"><span data-stu-id="a177f-p124">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="a177f-254">作为一种产品，Microsoft 不再提供 TMG，如果仍然需要对其进行配置，您可以查看[Lync Server 2013 步骤](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a177f-254">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="a177f-255">但以下信息的目的是更通常会有帮助，即使没有我们可以为每个反向代理有提供特定演练步骤的方法。</span><span class="sxs-lookup"><span data-stu-id="a177f-255">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="a177f-256">需要考虑以下两个主要事项：</span><span class="sxs-lookup"><span data-stu-id="a177f-256">We have two main things to consider:</span></span>
  
- <span data-ttu-id="a177f-257">是否要通过 HTTPS（推荐）执行你的初始自动发现请求？</span><span class="sxs-lookup"><span data-stu-id="a177f-257">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="a177f-258">如果你具有 Web 发布规则，则需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="a177f-258">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="a177f-259">如果你还没有 Web 发布规则，则需要进行创建。</span><span class="sxs-lookup"><span data-stu-id="a177f-259">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="a177f-260">如果你正在通过 HTTP 执行你的初始自动发现请求，则还需要创建或修改该规则。</span><span class="sxs-lookup"><span data-stu-id="a177f-260">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a177f-261">**重要**代理服务器的超时值是大量部署部署而异。</span><span class="sxs-lookup"><span data-stu-id="a177f-261">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="a177f-262">应监视您的部署，并修改客户端的最佳体验的值。</span><span class="sxs-lookup"><span data-stu-id="a177f-262">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="a177f-263">您可以将值设置为 200 低。</span><span class="sxs-lookup"><span data-stu-id="a177f-263">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="a177f-264">如果您在您的环境中支持 Lync 移动客户端，您应将值设置为 960 从 Office 365 的推式通知超时允许其超时值为 900。</span><span class="sxs-lookup"><span data-stu-id="a177f-264">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="a177f-265">很可能需要增大超时值，以避免客户端断开连接时的值是太低，或减少的数量，如果通过代理服务器建立连接，请勿断开连接，但清除客户端已断开连接后很长时间。</span><span class="sxs-lookup"><span data-stu-id="a177f-265">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="a177f-266">监视和基线什么是适合您的环境通常是只有准确的方法来确定此值的相应设置。</span><span class="sxs-lookup"><span data-stu-id="a177f-266">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="a177f-267">为你的外部自动发现 SAN 和 URL 修改现有 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="a177f-267">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="a177f-268">打开您的反向代理界面。</span><span class="sxs-lookup"><span data-stu-id="a177f-268">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a177f-269">您需要找到您的 web 发布规则，并选择编辑选项 （它可能在菜单或选项卡，具体取决于您的反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-269">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="a177f-270">应指出此 web 发布规则应用于某个区域。</span><span class="sxs-lookup"><span data-stu-id="a177f-270">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="a177f-271">你需要为传入站点或站点请求修改此规则。</span><span class="sxs-lookup"><span data-stu-id="a177f-271">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="a177f-272">你要**添加**新条目。</span><span class="sxs-lookup"><span data-stu-id="a177f-272">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="a177f-273">键入网站名称的自动发现 （我们将使用的示例中为 lyncdiscover.contoso.com），并单击**确定**或**保存**，具体取决于您的反向代理服务器的格式。</span><span class="sxs-lookup"><span data-stu-id="a177f-273">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="a177f-274">你可能会有一个其中具有自动发现 SAN 条目的新证书。</span><span class="sxs-lookup"><span data-stu-id="a177f-274">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="a177f-275">需要同时安装并配置用于根据反向代理服务器的设置。</span><span class="sxs-lookup"><span data-stu-id="a177f-275">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="a177f-276">配置完成后，请务必保存所有内容。</span><span class="sxs-lookup"><span data-stu-id="a177f-276">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="a177f-277">如果您的反向代理服务器具有**测试**功能，然后请使用它，以确保一切正常。</span><span class="sxs-lookup"><span data-stu-id="a177f-277">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="a177f-278">现在，您可能需要重复这些步骤，如果您有一个控制器或控制器池环境中的 （这意味着您拥有第二条规则）。</span><span class="sxs-lookup"><span data-stu-id="a177f-278">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="a177f-279">为外部自动发现 URL 创建 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="a177f-279">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="a177f-280">打开您的反向代理界面。</span><span class="sxs-lookup"><span data-stu-id="a177f-280">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a177f-281">您需要找到其中界面中创建 web 发布规则，并选择**新建**或**创建**选项 （它可能在菜单或选项卡，具体取决于您的反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-281">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a177f-282">你要查找用于创建新的 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="a177f-282">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a177f-283">通常，你需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="a177f-283">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a177f-284">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="a177f-284">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a177f-285">**规则操作**：**允许**规则在这种情况下，要让东西通过反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="a177f-285">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a177f-286">你选择的**发布**规则或选项将为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="a177f-286">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a177f-287">这需要为 **SSL** 以供外部访问，请选择该选项。</span><span class="sxs-lookup"><span data-stu-id="a177f-287">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="a177f-288">您将需要为**内部发布**，发布路径和前端池的负载平衡器 （或如果您有一个导演池的负载平衡器的 FQDN） 上的外部 Web 服务输入的 FQDN，一个例子就是 sfb_pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="a177f-288">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a177f-289">您应该键入**/**为路径，才能发布，但您还需要**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="a177f-289">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="a177f-p130">有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a177f-p130">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a177f-292">**接受请求**，但应为域名。</span><span class="sxs-lookup"><span data-stu-id="a177f-292">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a177f-293">对于**名称**，你应输入 **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="a177f-293">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a177f-294"><sipdomain>（这是外部的自动发现服务 URL）。</span><span class="sxs-lookup"><span data-stu-id="a177f-294"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="a177f-295">现在，如果前端池上的外部 Web 服务 url，您正在创建一条规则，您需要键入 FQDN 的前端池 (例如，lyncwebextpool01.contoso.com) 上的外部 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="a177f-295">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="a177f-296">将**路径**选项，您将需要输入**/**在此处。</span><span class="sxs-lookup"><span data-stu-id="a177f-296">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="a177f-297">你需要选择具有最新公共证书的 **SSL 侦听器**。</span><span class="sxs-lookup"><span data-stu-id="a177f-297">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="a177f-298">**身份验证委派**应设置为**无委派**，但直接客户端身份验证**应**被允许。</span><span class="sxs-lookup"><span data-stu-id="a177f-298">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="a177f-299">规则应设置为**所有用户**。</span><span class="sxs-lookup"><span data-stu-id="a177f-299">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a177f-300">这应是创建此规则所需的所有信息，并且允许你继续操作。</span><span class="sxs-lookup"><span data-stu-id="a177f-300">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a177f-301">你需要确保已转发**原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="a177f-301">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="a177f-302">还需要设置 **Web 服务器**端口，为此，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a177f-302">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a177f-303">**将请求重定向到 HTTP 端口**，端口号应为 **8080**。</span><span class="sxs-lookup"><span data-stu-id="a177f-303">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a177f-304">**将请求重定向到 SSL 端口**，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="a177f-304">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="a177f-305">一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="a177f-305">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="a177f-306">为端口 80 创建 Web 发布规则（可选）</span><span class="sxs-lookup"><span data-stu-id="a177f-306">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="a177f-307">打开您的反向代理界面。</span><span class="sxs-lookup"><span data-stu-id="a177f-307">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="a177f-308">您需要找到其中界面中创建 web 发布规则，并选择**新建**或**创建**选项 （它可能在菜单或选项卡，具体取决于您的反向代理配置）。</span><span class="sxs-lookup"><span data-stu-id="a177f-308">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="a177f-309">你要查找用于创建新的 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="a177f-309">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="a177f-310">通常，你需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="a177f-310">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="a177f-311">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="a177f-311">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="a177f-312">**规则操作**：**允许**规则在这种情况下，要让东西通过反向代理服务器。</span><span class="sxs-lookup"><span data-stu-id="a177f-312">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="a177f-313">你选择的**发布**规则或选项将为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="a177f-313">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="a177f-314">这必须为**用于连接发布的 Web 服务器或场的不安全连接**。</span><span class="sxs-lookup"><span data-stu-id="a177f-314">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="a177f-315">您将需要为**内部发布**，发布路径并为前端池的负载平衡器的**VIP 地址**输入的 FQDN，一个例子就是 sfb_pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="a177f-315">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="a177f-316">您应该键入**/**为路径，才能发布，但您还需要**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="a177f-316">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="a177f-p133">有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a177f-p133">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="a177f-319">**接受请求**，但应为域名。</span><span class="sxs-lookup"><span data-stu-id="a177f-319">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="a177f-320">对于**名称**，你应输入 **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="a177f-320">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="a177f-321"><sipdomain>（这是外部的自动发现服务 URL）。</span><span class="sxs-lookup"><span data-stu-id="a177f-321"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="a177f-322">将**路径**选项，您将需要输入**/**在此处。</span><span class="sxs-lookup"><span data-stu-id="a177f-322">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="a177f-323">您需要选择一个 web 侦听器，或允许反向代理为您创建一个。</span><span class="sxs-lookup"><span data-stu-id="a177f-323">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="a177f-324">**身份验证委派**应设置为**无委派**，但直接客户端身份验证**不应**被允许。</span><span class="sxs-lookup"><span data-stu-id="a177f-324">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="a177f-325">规则应设置为**所有用户**。</span><span class="sxs-lookup"><span data-stu-id="a177f-325">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="a177f-326">这应是创建此规则所需的所有信息，并且允许你继续操作。</span><span class="sxs-lookup"><span data-stu-id="a177f-326">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="a177f-327">需要设置 **Web 服务器**端口，为此，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a177f-327">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="a177f-328">**将请求重定向到 HTTP 端口**，端口号应为 **8080**。</span><span class="sxs-lookup"><span data-stu-id="a177f-328">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="a177f-329">**将请求重定向到 SSL 端口**，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="a177f-329">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="a177f-330">一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="a177f-330">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="a177f-331">使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="a177f-331">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="a177f-332"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-332"></span></span>

<span data-ttu-id="a177f-333">混合环境中的业务服务器 2015 Skype 是组合内部部署的环境和 O365 的环境。</span><span class="sxs-lookup"><span data-stu-id="a177f-333">Hybrid environments in Skype for Business Server 2015 are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="a177f-334">如果在混合环境中工作的业务服务器有 Skype，自动发现服务需要能够找到从这些环境中的用户。</span><span class="sxs-lookup"><span data-stu-id="a177f-334">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="a177f-p136">要让移动客户端发现用户所在位置，需要使用新的统一资源定位器 (URL) 配置自动发现服务。步骤包括：</span><span class="sxs-lookup"><span data-stu-id="a177f-p136">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="a177f-337">企业服务器管理外壳程序打开 Skype。</span><span class="sxs-lookup"><span data-stu-id="a177f-337">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="a177f-338">运行以下操作以获取为您的企业服务器环境的 Skype 的**ProxyFQDN**属性的值：</span><span class="sxs-lookup"><span data-stu-id="a177f-338">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
  ```
  Get-CsHostingProvider
  ```

3. <span data-ttu-id="a177f-339">然后，仍在 shell 窗口中，运行：</span><span class="sxs-lookup"><span data-stu-id="a177f-339">Then, still in the shell window, run:</span></span>
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    <span data-ttu-id="a177f-340">其中 [identity] 使用共享 SIP 地址空间的域名替换。</span><span class="sxs-lookup"><span data-stu-id="a177f-340">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="a177f-341">测试移动功能部署</span><span class="sxs-lookup"><span data-stu-id="a177f-341">Test your Mobility deployment</span></span>
<span data-ttu-id="a177f-342"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-342"></span></span>

<span data-ttu-id="a177f-343">一旦您已经部署 Skype 业务服务器移动服务和 Skype 业务服务器自动发现服务，您需要运行一个测试交易记录，以确保您的部署工作均正确。</span><span class="sxs-lookup"><span data-stu-id="a177f-343">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="a177f-344">你可以运行 **Test-CsUcwaConference** 来测试两个用户能否创建和加入会议以及在会议中通信。</span><span class="sxs-lookup"><span data-stu-id="a177f-344">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="a177f-345">你需要两个用户（实际或测试）及其完整凭据来执行此测试。</span><span class="sxs-lookup"><span data-stu-id="a177f-345">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="a177f-346">此命令适用于这两种 Skype 业务客户端以及 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="a177f-346">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="a177f-347">Lync Server 2010 中的客户端，您需要运行**测试 CsMcxP2PIM**进行测试。</span><span class="sxs-lookup"><span data-stu-id="a177f-347">For Lync Server 2010 clients, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="a177f-348">Lync Server 2010 用户仍必须是实际用户或预定义的测试用户，而您需要其密码凭据。</span><span class="sxs-lookup"><span data-stu-id="a177f-348">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="a177f-349">测试 Skype for Business 和 Lync 2013 移动客户端的会议功能</span><span class="sxs-lookup"><span data-stu-id="a177f-349">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="a177f-350">**企业服务器管理外壳的 Skype**和**Ocscore**的安装位置的任何计算机上**CsAdministrator**角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-350">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-351">启动**业务服务器管理外壳的 Skype** （您可能在搜索中键入的名称或者转到**所有程序**，然后选择它）。</span><span class="sxs-lookup"><span data-stu-id="a177f-351">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a177f-352">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="a177f-352">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a177f-p139">还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。</span><span class="sxs-lookup"><span data-stu-id="a177f-p139">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="a177f-355">测试 Lync 2010 移动客户端的会议功能</span><span class="sxs-lookup"><span data-stu-id="a177f-355">Test conferencing for Lync 2010 mobile clients</span></span>

1. <span data-ttu-id="a177f-356">**企业服务器管理外壳的 Skype**和**Ocscore**的安装位置的任何计算机上**CsAdministrator**角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-357">启动**业务服务器管理外壳的 Skype** （您可能在搜索中键入的名称或者转到**所有程序**，然后选择它）。</span><span class="sxs-lookup"><span data-stu-id="a177f-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="a177f-358">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="a177f-358">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="a177f-p140">还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。</span><span class="sxs-lookup"><span data-stu-id="a177f-p140">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

<span data-ttu-id="a177f-361">若要查看命令过程进一步，您可以签出[测试 CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)和[测试 CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a177f-361">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="a177f-362">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="a177f-362">Configure for push notifications</span></span>
<span data-ttu-id="a177f-363"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-363"></span></span>

<span data-ttu-id="a177f-364">即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。</span><span class="sxs-lookup"><span data-stu-id="a177f-364">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="a177f-365">但什么是推送通知？</span><span class="sxs-lookup"><span data-stu-id="a177f-365">But what are pusn notifications?</span></span> <span data-ttu-id="a177f-366">它们是事件警报，如新的或错过的 IM 邀请，或收到的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="a177f-366">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="a177f-367">为业务服务器推送通知服务，该服务然后将通知发送到 Microsoft 推送通知服务 (MSNS) 为 Windows Phone 用户，业务服务器 2015年移动服务 Skype 将这些通知发送到基于云的 Skype。</span><span class="sxs-lookup"><span data-stu-id="a177f-367">The Skype for Business Server 2015 Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="a177f-368">此功能不会改变从 Lync Server 2013，但如果 Skype 业务服务器，您需要执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a177f-368">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="a177f-369">为 Skype 业务服务器 2015年边缘服务器，添加新的宿主提供商，Microsoft Skype 的在线业务，然后设置托管提供商联盟组织和 Skype 之间的在线业务。</span><span class="sxs-lookup"><span data-stu-id="a177f-369">For a Skype for Business Server 2015 Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="a177f-p142">通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。默认情况下，推送通知已关闭。</span><span class="sxs-lookup"><span data-stu-id="a177f-p142">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="a177f-372">测试你的联盟配置和推送通知。</span><span class="sxs-lookup"><span data-stu-id="a177f-372">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="a177f-373">针对推送通知配置你的 Skype for Business 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="a177f-373">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="a177f-374">在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-374">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-375">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a177f-375">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a177f-376">添加业务服务器在线托管提供商 Skype。</span><span class="sxs-lookup"><span data-stu-id="a177f-376">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="a177f-377">例如：</span><span class="sxs-lookup"><span data-stu-id="a177f-377">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="a177f-p143">你不能与一个宿主提供程序建立多个联盟关系。因此，如果你已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 SkypeOnline 也是如此。</span><span class="sxs-lookup"><span data-stu-id="a177f-p143">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="a177f-380">设置托管提供商之间的联盟组织与 Skype 的推送通知服务的在线业务。</span><span class="sxs-lookup"><span data-stu-id="a177f-380">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="a177f-381">在命令行中，你需要键入：</span><span class="sxs-lookup"><span data-stu-id="a177f-381">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="a177f-382">启用推送通知</span><span class="sxs-lookup"><span data-stu-id="a177f-382">Enable push notifications</span></span>

1. <span data-ttu-id="a177f-383">在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-384">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a177f-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a177f-385">启用推送通知：</span><span class="sxs-lookup"><span data-stu-id="a177f-385">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="a177f-386">启用联盟：</span><span class="sxs-lookup"><span data-stu-id="a177f-386">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="a177f-387">测试联盟和推送通知</span><span class="sxs-lookup"><span data-stu-id="a177f-387">Test federation and push notifications</span></span>

1. <span data-ttu-id="a177f-388">在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-388">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-389">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a177f-389">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a177f-390">测试联盟配置：</span><span class="sxs-lookup"><span data-stu-id="a177f-390">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="a177f-391">例如：</span><span class="sxs-lookup"><span data-stu-id="a177f-391">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="a177f-392">测试你的推送通知：</span><span class="sxs-lookup"><span data-stu-id="a177f-392">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="a177f-393">例如：</span><span class="sxs-lookup"><span data-stu-id="a177f-393">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="a177f-394">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="a177f-394">Configure Mobility policy</span></span>
<span data-ttu-id="a177f-395"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="a177f-395"></span></span>

<span data-ttu-id="a177f-396">您可以使用 Skype 的业务服务器 2015 来确定哪些用户可以使用您的移动服务，调用通过工作，语音通信 (VoIP)，IP 或视频，以及 WiFi 是 VoIP 或视频需要。</span><span class="sxs-lookup"><span data-stu-id="a177f-396">You have the ability with Skype for Business Server 2015 to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="a177f-397">使用通过工号拨号功能，移动用户可以在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。</span><span class="sxs-lookup"><span data-stu-id="a177f-397">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="a177f-398">该线路另一端上的人员不会看到移动用户的移动电话号码，并且可以让移动用户避免产生拨出呼叫费用。</span><span class="sxs-lookup"><span data-stu-id="a177f-398">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="a177f-399">设置 VoIP 和视频后，用户可以接收和发出 VoIP 呼叫和视频。</span><span class="sxs-lookup"><span data-stu-id="a177f-399">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="a177f-400">WiFi 用法的设置确定通过蜂窝数据网络使用 WiFi 网络是否需要用户的移动设备。</span><span class="sxs-lookup"><span data-stu-id="a177f-400">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="a177f-401">移动性、 工作，通过电话和 VoIP 和视频功能是默认启用的。</span><span class="sxs-lookup"><span data-stu-id="a177f-401">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="a177f-402">禁用了 VoIp 和视频需要 WiFi 的设置。</span><span class="sxs-lookup"><span data-stu-id="a177f-402">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="a177f-403">管理员可以全局、按网站或按用户对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="a177f-403">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="a177f-404">若要能够使用移动功能并调用通过工作，用户必须是：</span><span class="sxs-lookup"><span data-stu-id="a177f-404">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="a177f-405">启用对 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="a177f-405">Enabled for Skype for Business Server 2015</span></span>
    
- <span data-ttu-id="a177f-406">启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="a177f-406">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="a177f-407">分配具有**EnableMobility**选项设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="a177f-407">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="a177f-408">对于希望能使用通过工号拨号功能的用户，他们还必须：</span><span class="sxs-lookup"><span data-stu-id="a177f-408">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="a177f-409">分配已选择**允许多部电话同时响铃**选项的语音策略。</span><span class="sxs-lookup"><span data-stu-id="a177f-409">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="a177f-410">分配具有**EnableOutsideVoice**设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="a177f-410">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a177f-p147">未启用企业语音的用户可以使用其移动设备发出 Skype 至 Skype VoIP 呼叫，也可以使用“单击以加入”链接来通过移动设备加入会议（如果已为与其关联的语音策略设置相应的选项）。规划主题中有更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="a177f-p147">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="a177f-413">修改全局移动策略</span><span class="sxs-lookup"><span data-stu-id="a177f-413">Modify global Mobility policy</span></span>

1. <span data-ttu-id="a177f-414">在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-414">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-415">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a177f-415">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a177f-416">请关闭移动性和呼叫通过工作访问全局通过键入：</span><span class="sxs-lookup"><span data-stu-id="a177f-416">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="a177f-417">关闭移动访问关闭的情况下，可以关闭工作通过调用。</span><span class="sxs-lookup"><span data-stu-id="a177f-417">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a177f-418">但是，您不能关闭移动还关闭工作通过调用关闭的情况下。</span><span class="sxs-lookup"><span data-stu-id="a177f-418">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="a177f-419">有关更多信息，敬请[组 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a177f-419">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="a177f-420">修改网站的移动策略</span><span class="sxs-lookup"><span data-stu-id="a177f-420">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="a177f-421">在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-421">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-422">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a177f-422">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a177f-p149">你可以创建站点级别的策略、禁用 VoIP 和视频，以及按网站启用“IP 音频需要 WiFi”和“IP 视频需要 WiFi”。键入：</span><span class="sxs-lookup"><span data-stu-id="a177f-p149">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="a177f-425">了解更多信息，请访问[新建 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a177f-425">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="a177f-426">修改用户的移动策略</span><span class="sxs-lookup"><span data-stu-id="a177f-426">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="a177f-427">在以是为计算机安装了**业务服务器管理外壳的 Skype**和**Ocscore** **CsAdministrator**角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a177f-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="a177f-428">启动**业务服务器管理外壳的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="a177f-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a177f-429">创建用户级别移动策略并关闭移动性和呼叫通过用户的工作。</span><span class="sxs-lookup"><span data-stu-id="a177f-429">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="a177f-430">键入：</span><span class="sxs-lookup"><span data-stu-id="a177f-430">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="a177f-431">包含示例数据的另一个示例：</span><span class="sxs-lookup"><span data-stu-id="a177f-431">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="a177f-432">关闭移动访问关闭的情况下，可以关闭工作通过调用。</span><span class="sxs-lookup"><span data-stu-id="a177f-432">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="a177f-433">但是，您不能关闭移动还关闭工作通过调用关闭的情况下。</span><span class="sxs-lookup"><span data-stu-id="a177f-433">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

