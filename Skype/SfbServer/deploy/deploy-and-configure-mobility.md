---
title: 为 Skype for Business 服务器部署和配置移动
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文将指导你完成配置现有 Skype for Business 服务器安装以使用移动服务的步骤, 使你的移动设备能够利用 Skype for Business Server 移动功能。
ms.openlocfilehash: 35b9ca6a69dc5add9331aa5399a59a572bdf6906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303552"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="73ffa-103">为 Skype for Business 服务器部署和配置移动</span><span class="sxs-lookup"><span data-stu-id="73ffa-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="73ffa-104">本文将指导你完成配置现有 Skype for Business 服务器安装以使用移动服务的步骤, 使你的移动设备能够利用 Skype for Business Server 移动功能。</span><span class="sxs-lookup"><span data-stu-id="73ffa-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="73ffa-105">如果已查看[skype for Business server 文章的移动性计划](../plan-your-deployment/mobility.md), 您应该准备好继续执行以下步骤, 以将移动性部署到 Skype For business 服务器环境中。</span><span class="sxs-lookup"><span data-stu-id="73ffa-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="73ffa-106">步骤如下所示（并且此表中包含权限列表）：</span><span class="sxs-lookup"><span data-stu-id="73ffa-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="73ffa-107">**阶段**</span><span class="sxs-lookup"><span data-stu-id="73ffa-107">**Phase**</span></span>|<span data-ttu-id="73ffa-108">**权限**</span><span class="sxs-lookup"><span data-stu-id="73ffa-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="73ffa-109">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="73ffa-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="73ffa-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="73ffa-110">Domain Admins</span></span>  <br/> <span data-ttu-id="73ffa-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="73ffa-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="73ffa-112">修改证书</span><span class="sxs-lookup"><span data-stu-id="73ffa-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="73ffa-113">本地管理员</span><span class="sxs-lookup"><span data-stu-id="73ffa-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="73ffa-114">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="73ffa-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="73ffa-115">本地管理员</span><span class="sxs-lookup"><span data-stu-id="73ffa-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="73ffa-116">使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="73ffa-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="73ffa-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="73ffa-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="73ffa-118">测试移动功能部署</span><span class="sxs-lookup"><span data-stu-id="73ffa-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="73ffa-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="73ffa-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="73ffa-120">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="73ffa-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="73ffa-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="73ffa-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="73ffa-122">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="73ffa-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="73ffa-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="73ffa-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="73ffa-p102">以下所有部分都包含假定你已阅读规划主题的步骤。如果有任何让你感到困惑的地方，请随时查阅此处的信息。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="73ffa-126">在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="73ffa-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="73ffa-127">所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="73ffa-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="73ffa-128">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="73ffa-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="73ffa-129">创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="73ffa-129">Create DNS records</span></span>
<span data-ttu-id="73ffa-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-130"></span></span>

<span data-ttu-id="73ffa-131">您可能已将这些内容作为 Skype for Business 服务器环境的一部分, 但您需要创建以下记录才能使自动发现正常工作:</span><span class="sxs-lookup"><span data-stu-id="73ffa-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="73ffa-132">支持从组织网络内部进行连接的移动用户的内部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="73ffa-133">支持从组织网络外部进行连接的移动用户的外部（或公共）DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="73ffa-134">这些记录可以是 A（主机）名称或 CNAME 记录（你不必同时创建两者，我们这里只是将步骤都介绍一遍）。</span><span class="sxs-lookup"><span data-stu-id="73ffa-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="73ffa-135">创建内部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="73ffa-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="73ffa-136">以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="73ffa-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="73ffa-137">单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。</span><span class="sxs-lookup"><span data-stu-id="73ffa-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="73ffa-138">在控制台窗口的左侧窗格中, 你需要转到 Skype for business 服务器前端服务器所在的域, 然后展开此处的**正向查找区域**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="73ffa-139">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="73ffa-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="73ffa-140">前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="73ffa-141">控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="73ffa-142">记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建别名 (CNAME)**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="73ffa-143">在**别名**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="73ffa-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="73ffa-144">在**完全限定的域名 (目标主机的 FQDN**中, 你需要键入或浏览到位于上述步骤4中标识的前端池 (或单个前端服务器, 或控制器池) 的内部 WEB 服务 FQDN。</span><span class="sxs-lookup"><span data-stu-id="73ffa-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="73ffa-145">输入后，单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="73ffa-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="73ffa-146">你将需要在 Skype for Business Server 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="73ffa-147">创建外部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="73ffa-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="73ffa-148">这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="73ffa-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="73ffa-149">在此时间点, Skype for business 服务器应该已存在一个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="73ffa-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="73ffa-150">请展开此 SIP 域的**正向查找区域**，否则请打开它。</span><span class="sxs-lookup"><span data-stu-id="73ffa-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="73ffa-151">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="73ffa-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="73ffa-152">前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="73ffa-153">控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="73ffa-154">拥有该信息后，应该能够选择用于**新建别名 (CNAME)** 的选项。</span><span class="sxs-lookup"><span data-stu-id="73ffa-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="73ffa-155">现在，你应该能够输入**别名**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="73ffa-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="73ffa-156">接下来, 应该有一个要在**目标主机的 FQDN**中输入的区域, 这将需要是你的前端池 (或单个前端服务器或控制器池) 的 fqdn, 在上述步骤3中标识。</span><span class="sxs-lookup"><span data-stu-id="73ffa-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="73ffa-157">你可能需要保存在此处, 或者如果你需要在 Skype for Business Server 环境中的每个 SIP 域的正向查找区域中创建其他 CNAME 记录, 你应该执行此操作, 但在准备好后, 请保存你的工作。</span><span class="sxs-lookup"><span data-stu-id="73ffa-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="73ffa-158">创建内部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="73ffa-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="73ffa-159">以 **Domain Admins** 组成员或 **DnsAdmins** 组成员的身份登录网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="73ffa-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="73ffa-160">单击**开始**，选择**管理工具**（如果它不是“开始”菜单的选项，你可能需要对其进行**搜索**），然后单击 **DNS** 以打开 DNS 管理单元。</span><span class="sxs-lookup"><span data-stu-id="73ffa-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="73ffa-161">在控制台窗口的左侧窗格中, 你需要转到 Skype for business 服务器前端服务器所在的域, 然后展开此处的**正向查找区域**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="73ffa-162">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="73ffa-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="73ffa-163">前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="73ffa-164">控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="73ffa-165">记下此信息后，右键单击你的 SIP 域名，然后从菜单中选择**新建主机 (A 或 AAAA)**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="73ffa-166">在**名称**文本框中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="73ffa-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="73ffa-167">在 " **IP 地址**" 文本框中, 键入您的前端池 (或单个前端服务器, 或控制器池或 director) 的内部 WEB 服务 IP 地址, 在上述步骤4中标识。</span><span class="sxs-lookup"><span data-stu-id="73ffa-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="73ffa-168">完成此操作后，单击**添加主机**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="73ffa-169">你需要在 Skype for Business Server 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="73ffa-170">为此，请根据需要多次重复步骤 6-8。</span><span class="sxs-lookup"><span data-stu-id="73ffa-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="73ffa-171">完成后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="73ffa-172">创建外部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="73ffa-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="73ffa-173">这些步骤是常规步骤，因为我们无法知道你正在使用的是哪个公共 DNS 提供程序，但我们仍希望帮助你排忧解难。请使用能够创建新的 DNS 记录的帐户登录到你的公共 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="73ffa-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="73ffa-174">在此时间点, Skype for business 服务器应该已存在一个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="73ffa-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="73ffa-175">请展开此 SIP 域的**正向查找区域**，否则请打开它。</span><span class="sxs-lookup"><span data-stu-id="73ffa-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="73ffa-176">检查一下你是否具有以下记录：</span><span class="sxs-lookup"><span data-stu-id="73ffa-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="73ffa-177">前端服务器 (标准或企业) 或前端池的任何主机 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="73ffa-178">控制器或控制器池的任何主机 A 或 AAAA 记录 (您在部署中可能具有的可选配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="73ffa-179">拥有该信息后，应该能够选择用于创建**新主机 A 或 AAAA** 的选项。</span><span class="sxs-lookup"><span data-stu-id="73ffa-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="73ffa-180">现在，你应该能够输入**名称**，你需要在此处输入 lyncdiscover 作为外部自动发现服务 URL。</span><span class="sxs-lookup"><span data-stu-id="73ffa-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="73ffa-181">接下来, 应在**Ip Addresss**中输入要输入的区域, 这将需要是你的前端池 (或单个前端服务器, 或控制器池或 director) 的 IP, 在上述步骤3中标识。</span><span class="sxs-lookup"><span data-stu-id="73ffa-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="73ffa-182">你可能需要保存在此处, 或者如果你需要在每个 SIP 域的正向查找区域中为 Skype for business Server 环境创建额外的 A 或 AAAA 记录, 你应该执行此操作, 但一旦准备就绪, 请保存你的工作。</span><span class="sxs-lookup"><span data-stu-id="73ffa-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="73ffa-183">修改证书</span><span class="sxs-lookup"><span data-stu-id="73ffa-183">Modify certificates</span></span>
<span data-ttu-id="73ffa-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-184"></span></span>

<span data-ttu-id="73ffa-185">如果您对证书的规划有疑问, 我们已经记录了我们[针对 Skype for Business 服务器的移动性计划](../plan-your-deployment/mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="73ffa-186">阅读该文章后，我们将引导你完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="73ffa-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="73ffa-187">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="73ffa-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="73ffa-188">从你的证书颁发机构 (CA) 请求新证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="73ffa-189">使用 PowerShell 通过替换内容更新你的就地证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="73ffa-190">使用 Microsoft 管理控制台 (MMC) 中的 "证书" 管理单元检查证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="73ffa-191">是否需要新证书？</span><span class="sxs-lookup"><span data-stu-id="73ffa-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="73ffa-192">首先，你可能需要检查哪些证书是就地证书，以及它们是否具有所需的条目。</span><span class="sxs-lookup"><span data-stu-id="73ffa-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="73ffa-193">若要执行此操作, 您需要使用本地管理员帐户登录 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="73ffa-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="73ffa-194">此帐户可能还需要对证书颁发机构 (CA) 具有权限才能执行下面的某些步骤。</span><span class="sxs-lookup"><span data-stu-id="73ffa-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="73ffa-195">打开 Skype for Business 服务器管理外壳程序 (如果未将其固定到 "开始" 菜单或任务栏, 则可以使用 "搜索" 来查找它)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="73ffa-p110">你必须了解在尝试添加更新证书之前已分配哪些证书。因此，在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="73ffa-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="73ffa-p111">步骤 3 中的信息对你具有唯一性。你需要仔细检查，以确定你是否具有为所有内容分配的单个证书，或者是否具有为所需的不同组件分配的不同证书。**Use** 参数将告知你证书的使用方式，**Thumbprint** 参数将告知你所有证书都相同还是具有多个证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="73ffa-p112">如果你已在规划部分中建议 SAN 条目，则可方便使用。如果没有，你需要从你的证书颁发机构请求一个新证书或多个证书（具体取决于你的配置）。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="73ffa-203">从你的证书颁发机构 (CA) 请求一个新证书或多个证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="73ffa-204">检查你具有哪些 SAN 条目后，你就知道你具有**单个证书**（通过上述步骤检查后），并且你知道自己没有所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="73ffa-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="73ffa-205">需要向你的 CA 发出新证书请求。</span><span class="sxs-lookup"><span data-stu-id="73ffa-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="73ffa-206">打开 Skype for Business 服务器 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="73ffa-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="73ffa-207">对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="73ffa-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="73ffa-208">现在, 如果您有多个 SIP 域, 则不能使用 AllSipDomain 参数, 如上例中所示。</span><span class="sxs-lookup"><span data-stu-id="73ffa-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="73ffa-209">你需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="73ffa-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="73ffa-210">当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。</span><span class="sxs-lookup"><span data-stu-id="73ffa-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="73ffa-211">例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="73ffa-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="73ffa-212">或者，检查你具有哪些 SAN 条目后，你发现你具有**多个证书**，其中并不包含你所需的所有条目。</span><span class="sxs-lookup"><span data-stu-id="73ffa-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="73ffa-213">需要向你的 CA 发出新证书请求。</span><span class="sxs-lookup"><span data-stu-id="73ffa-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="73ffa-214">打开 Skype for Business 服务器 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="73ffa-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="73ffa-215">对于缺少的自动发现服务 SAN（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="73ffa-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="73ffa-216">现在, 如果您有多个 SIP 域, 则不能使用 AllSipDomain 参数, 如上例中所示。</span><span class="sxs-lookup"><span data-stu-id="73ffa-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="73ffa-217">你需要改为使用 DomainName 参数。</span><span class="sxs-lookup"><span data-stu-id="73ffa-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="73ffa-218">当你使用 DomainName 参数时，你必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。</span><span class="sxs-lookup"><span data-stu-id="73ffa-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="73ffa-219">例如（将 -Ca 参数替换为你自己的证书颁发机构路径）：</span><span class="sxs-lookup"><span data-stu-id="73ffa-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="73ffa-220">由 CA 生成新证书后，你需要对其进行分配。</span><span class="sxs-lookup"><span data-stu-id="73ffa-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="73ffa-221">使用 Skype for Business Server 命令行管理程序分配证书</span><span class="sxs-lookup"><span data-stu-id="73ffa-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="73ffa-222">根据你在上面的“是否需要新证书”部分中发现的内容，你需要运行以下命令**之一**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="73ffa-223">如果所有内容具有单个证书（指纹相同），则需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="73ffa-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="73ffa-224">如果某些内容具有不同证书（指纹都不同），请改为运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="73ffa-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="73ffa-225">在 Microsoft 管理控制台 (MMC) 中查看证书</span><span class="sxs-lookup"><span data-stu-id="73ffa-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="73ffa-p117">你可以选择使用 MMC 的证书管理单元查看你的证书。只需在搜索中键入 MMC，它应作为应用程序选项弹出。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="73ffa-p118">要添加证书管理单元，你需要单击**文件**，然后单击**添加/删除管理单元...**（或者键盘快捷方式 **Ctrl+M** 也会奏效）。**证书**将成为左侧窗格中的一个选项，选中它并在弹出窗口中单击**计算机帐户**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="73ffa-230">仍在弹出窗口中，你极有可能在承载需要查看的证书的计算机上执行此操作，因此如果是那样，请选择**本地计算机**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="73ffa-231">如果你正在远程计算机上工作，请将单选按钮更改为**其他计算机**，然后输入该计算机的 FQDN 或使用**浏览**按钮通过 AD 搜索该计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="73ffa-232">选择计算机后, 需要在 "准备就绪" 后单击 "**完成**", 然后单击 **"确定"** 以将该管理单元添加到 MMC。</span><span class="sxs-lookup"><span data-stu-id="73ffa-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="73ffa-233">展开 MMC 左侧窗格中的 "**证书**" 部分。</span><span class="sxs-lookup"><span data-stu-id="73ffa-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="73ffa-234">还需展开**个人**文件夹，然后选择**证书**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="73ffa-235">这样，你可以在此存储中查看证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="73ffa-236">你需要查找要查看的证书，右键单击它，然后选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="73ffa-237">你如何知道这是什么证书？</span><span class="sxs-lookup"><span data-stu-id="73ffa-237">How do you know what certificate this is?</span></span> <span data-ttu-id="73ffa-238">它应该是分配给你的场的所有内容的单个证书, 或者你可以为不同的内容 (如默认、内部 Web 服务等) 使用多个证书, 在这种情况下, 你可能需要查看多个证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="73ffa-239">多个证书将具有相同的指纹。</span><span class="sxs-lookup"><span data-stu-id="73ffa-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="73ffa-p122">进入**证书**视图后，选择**详细信息**。这样，你可以在选择**主题**时看到证书主题名称，并且会显示分配的主题名称和关联的属性。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="73ffa-p123">你还需要检查**使用者替代名称**条目。你将发现以下一个或多个条目：</span><span class="sxs-lookup"><span data-stu-id="73ffa-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="73ffa-244">此池的池名称, 如果不是池, 则为单个服务器名称。</span><span class="sxs-lookup"><span data-stu-id="73ffa-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="73ffa-245">向其分配证书的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="73ffa-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="73ffa-246">简单 URL 记录，一般为 meet 和 dialin。</span><span class="sxs-lookup"><span data-stu-id="73ffa-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="73ffa-247">Web 服务内部和 Web 服务外部名称 (例如, webpool01.contoso.net、webpool01.contoso.com), 基于在拓扑生成器和 ridden 的 Web 服务选择中所做的选择。</span><span class="sxs-lookup"><span data-stu-id="73ffa-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="73ffa-248">如果已分配, 则 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="73ffa-249">如果分配有多个证书，你需要对其进行检查（查看上述备注）。</span><span class="sxs-lookup"><span data-stu-id="73ffa-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="73ffa-250">因此, 如果你发现 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>记录已配置。</span><span class="sxs-lookup"><span data-stu-id="73ffa-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="73ffa-251">你可以关闭 MMC。</span><span class="sxs-lookup"><span data-stu-id="73ffa-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="73ffa-252">如果未分配这些证书，你需要发出新证书请求（上面概述）或需要在请求后进行安装（我们建议使用上述 PowerShell 实现该目的）。</span><span class="sxs-lookup"><span data-stu-id="73ffa-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="73ffa-253">配置反向代理</span><span class="sxs-lookup"><span data-stu-id="73ffa-253">Configure the reverse proxy</span></span>
<span data-ttu-id="73ffa-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-254"></span></span>

<span data-ttu-id="73ffa-p125">不应严格遵循以下步骤。因为在该产品的早期版本中，我们已引导你配置 Threat Management Gateway (TMG)，如果你未使用该产品，你需要从其创建自己的版本。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="73ffa-257">TMG 不再由 Microsoft 作为产品提供, 如果仍需要配置它, 你可以查看[Lync Server 2013 步骤](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="73ffa-258">但是, 以下信息的预期更普遍有用, 即使没有办法可以为每个反向代理提供特定的演练步骤。</span><span class="sxs-lookup"><span data-stu-id="73ffa-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="73ffa-259">需要考虑以下两个主要事项：</span><span class="sxs-lookup"><span data-stu-id="73ffa-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="73ffa-260">是否要通过 HTTPS（推荐）执行你的初始自动发现请求？</span><span class="sxs-lookup"><span data-stu-id="73ffa-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="73ffa-261">如果你具有 Web 发布规则，则需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="73ffa-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="73ffa-262">如果你还没有 Web 发布规则，则需要进行创建。</span><span class="sxs-lookup"><span data-stu-id="73ffa-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="73ffa-263">如果你正在通过 HTTP 执行你的初始自动发现请求，则还需要创建或修改该规则。</span><span class="sxs-lookup"><span data-stu-id="73ffa-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="73ffa-264">**重要提示**代理超时值是一个数字, 该数字将因部署而异。</span><span class="sxs-lookup"><span data-stu-id="73ffa-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="73ffa-265">应监视你的部署并修改客户端最佳体验的值。</span><span class="sxs-lookup"><span data-stu-id="73ffa-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="73ffa-266">你可以将值设置为低至200。</span><span class="sxs-lookup"><span data-stu-id="73ffa-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="73ffa-267">如果你在你的环境中支持 Lync 移动客户端, 则应将该值设置为960以允许来自 Office 365 的推送通知超时, 该超时值为900。</span><span class="sxs-lookup"><span data-stu-id="73ffa-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="73ffa-268">很有可能必须增加超时值以避免客户端在值太低时断开连接, 或者, 如果通过代理的连接不能断开连接, 但在客户端断开连接后很长时间, 则会减少数字。</span><span class="sxs-lookup"><span data-stu-id="73ffa-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="73ffa-269">监视和设置环境的常规功能是确定此值的适当设置的唯一准确方式。</span><span class="sxs-lookup"><span data-stu-id="73ffa-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="73ffa-270">为你的外部自动发现 SAN 和 URL 修改现有 Web 发布规则</span><span class="sxs-lookup"><span data-stu-id="73ffa-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="73ffa-271">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="73ffa-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="73ffa-272">您需要找到 web 发布规则, 然后选择 "编辑" 选项 (它可能位于菜单或选项卡上, 具体取决于您的反向代理配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="73ffa-273">应存在一个区域, 指明应用此 web 发布规则的内容。</span><span class="sxs-lookup"><span data-stu-id="73ffa-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="73ffa-274">你需要为传入站点或站点请求修改此规则。</span><span class="sxs-lookup"><span data-stu-id="73ffa-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="73ffa-275">你要**添加**新条目。</span><span class="sxs-lookup"><span data-stu-id="73ffa-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="73ffa-276">键入自动发现网站的名称 (我们将使用的示例为 lyncdiscover.contoso.com), 然后单击 **"确定" 或 "** **保存**", 具体取决于你的反向代理的格式。</span><span class="sxs-lookup"><span data-stu-id="73ffa-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="73ffa-277">你可能会有一个其中具有自动发现 SAN 条目的新证书。</span><span class="sxs-lookup"><span data-stu-id="73ffa-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="73ffa-278">这还需要安装, 并根据您的反向代理设置进行配置以供使用。</span><span class="sxs-lookup"><span data-stu-id="73ffa-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="73ffa-279">配置完成后，请务必保存所有内容。</span><span class="sxs-lookup"><span data-stu-id="73ffa-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="73ffa-280">如果反向代理具有**测试**功能, 请使用它来确保一切正常工作。</span><span class="sxs-lookup"><span data-stu-id="73ffa-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="73ffa-281">现在, 如果你的环境中有 Director 或控制器池, 你可能需要重复这些步骤 (这意味着你有第二条规则)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="73ffa-282">为外部自动发现 URL 创建 web 发布规则</span><span class="sxs-lookup"><span data-stu-id="73ffa-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="73ffa-283">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="73ffa-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="73ffa-284">您需要找到在界面上创建 web 发布规则的位置, 然后选择 "**新建**" 或 "**创建**" 选项 (它可能位于菜单或选项卡上, 具体取决于您的反向代理配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="73ffa-285">你要查找用于创建新的 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="73ffa-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="73ffa-286">通常，你需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="73ffa-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="73ffa-287">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="73ffa-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="73ffa-288">**规则操作**: 在这种情况下, 这是一个**允许**规则, 你可以通过反向代理来传递内容。</span><span class="sxs-lookup"><span data-stu-id="73ffa-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="73ffa-289">你选择的**发布**规则或选项将为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="73ffa-290">这需要为 **SSL** 以供外部访问，请选择该选项。</span><span class="sxs-lookup"><span data-stu-id="73ffa-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="73ffa-291">你将需要发布**内部发布**的路径, 并在你的前端池的负载平衡器 (或控制器池的负载平衡器的 fqdn (如果有)) 上输入外部 Web 服务的 fqdn, 例如, sfb_pool01。</span><span class="sxs-lookup"><span data-stu-id="73ffa-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="73ffa-292">应键入\*\* / \*\*\* 作为要发布的路径, 但也需要**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="73ffa-p131">有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="73ffa-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="73ffa-295">**接受请求**，但应为域名。</span><span class="sxs-lookup"><span data-stu-id="73ffa-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="73ffa-296">对于**名称**，你应输入 **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="73ffa-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="73ffa-297"><sipdomain>(这是外部自动发现服务 URL)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="73ffa-298">现在, 如果你要为前端池上的外部 Web 服务 URL 创建规则, 你需要在你的前端池 (如 lyncwebextpool01.contoso.com) 上键入外部 Web 服务的 FQDN (例如,)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="73ffa-299">将出现 "**路径**" 选项, 您需要在此处输入\*\* / \**"*"。</span><span class="sxs-lookup"><span data-stu-id="73ffa-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="73ffa-300">你需要选择具有最新公共证书的 **SSL 侦听器**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="73ffa-301">**身份验证委派**应设置为**无委派**，但直接客户端身份验证**应**被允许。</span><span class="sxs-lookup"><span data-stu-id="73ffa-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="73ffa-302">规则应设置为**所有用户**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="73ffa-303">这应是创建此规则所需的所有信息，并且允许你继续操作。</span><span class="sxs-lookup"><span data-stu-id="73ffa-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="73ffa-304">你需要确保已转发**原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="73ffa-305">还需要设置 **Web 服务器**端口，为此，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73ffa-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="73ffa-306">**将请求重定向到 HTTP 端口**，端口号应为 **8080**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="73ffa-307">**将请求重定向到 SSL 端口**，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="73ffa-308">一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="73ffa-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="73ffa-309">为端口 80 创建 Web 发布规则（可选）</span><span class="sxs-lookup"><span data-stu-id="73ffa-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="73ffa-310">打开反向代理接口。</span><span class="sxs-lookup"><span data-stu-id="73ffa-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="73ffa-311">您需要找到在界面上创建 web 发布规则的位置, 然后选择 "**新建**" 或 "**创建**" 选项 (它可能位于菜单或选项卡上, 具体取决于您的反向代理配置)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="73ffa-312">你要查找用于创建新的 Web 发布规则的选项。</span><span class="sxs-lookup"><span data-stu-id="73ffa-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="73ffa-313">通常，你需要输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="73ffa-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="73ffa-314">**名称**：规则的名称</span><span class="sxs-lookup"><span data-stu-id="73ffa-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="73ffa-315">**规则操作**: 在这种情况下, 这是一个**允许**规则, 你可以通过反向代理来传递内容。</span><span class="sxs-lookup"><span data-stu-id="73ffa-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="73ffa-316">你选择的**发布**规则或选项将为**单个网站或负载平衡器**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="73ffa-317">这必须为**用于连接发布的 Web 服务器或场的不安全连接**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="73ffa-318">你将需要发布**内部发布**的路径, 并输入你的前端池的负载平衡器的**VIP 地址**的 FQDN, 例如, sfb_pool01。</span><span class="sxs-lookup"><span data-stu-id="73ffa-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="73ffa-319">应键入\*\* / \*\*\* 作为要发布的路径, 但也需要**转发原始主机头**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="73ffa-p134">有一个**公共或外部名称**详细信息或信息的选项。你可在其中输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="73ffa-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="73ffa-322">**接受请求**，但应为域名。</span><span class="sxs-lookup"><span data-stu-id="73ffa-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="73ffa-323">对于**名称**，你应输入 **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="73ffa-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="73ffa-324"><sipdomain>(这是外部自动发现服务 URL)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="73ffa-325">将出现 "**路径**" 选项, 您需要在此处输入\*\* / \**"*"。</span><span class="sxs-lookup"><span data-stu-id="73ffa-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="73ffa-326">您需要选择 web 侦听器, 或者允许反向代理为您创建一个侦听器。</span><span class="sxs-lookup"><span data-stu-id="73ffa-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="73ffa-327">**身份验证委派**应设置为**无委派**，但直接客户端身份验证**不应**被允许。</span><span class="sxs-lookup"><span data-stu-id="73ffa-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="73ffa-328">规则应设置为**所有用户**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="73ffa-329">这应是创建此规则所需的所有信息，并且允许你继续操作。</span><span class="sxs-lookup"><span data-stu-id="73ffa-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="73ffa-330">需要设置 **Web 服务器**端口，为此，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73ffa-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="73ffa-331">**将请求重定向到 HTTP 端口**，端口号应为 **8080**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="73ffa-332">**将请求重定向到 SSL 端口**，端口号应为 **4443**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="73ffa-333">一切均配置好后，你需要对其进行保存或应用，然后你将需要测试该规则。</span><span class="sxs-lookup"><span data-stu-id="73ffa-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="73ffa-334">使用混合部署配置移动性的自动发现</span><span class="sxs-lookup"><span data-stu-id="73ffa-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="73ffa-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-335"></span></span>

<span data-ttu-id="73ffa-336">Skype for Business 服务器中的混合环境是结合了内部部署和 O365 环境的环境。</span><span class="sxs-lookup"><span data-stu-id="73ffa-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="73ffa-337">当您的 Skype for Business 服务器在混合环境中工作时, 自动发现服务需要能够从这些环境中的任一环境找到用户。</span><span class="sxs-lookup"><span data-stu-id="73ffa-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="73ffa-p137">要让移动客户端发现用户所在位置，需要使用新的统一资源定位器 (URL) 配置自动发现服务。步骤包括：</span><span class="sxs-lookup"><span data-stu-id="73ffa-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="73ffa-340">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="73ffa-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="73ffa-341">运行以下内容, 获取 Skype for business Server 环境的属性**ProxyFQDN**的值:</span><span class="sxs-lookup"><span data-stu-id="73ffa-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="73ffa-342">然后，仍在 shell 窗口中，运行：</span><span class="sxs-lookup"><span data-stu-id="73ffa-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="73ffa-343">其中 [identity] 使用共享 SIP 地址空间的域名替换。</span><span class="sxs-lookup"><span data-stu-id="73ffa-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="73ffa-344">测试移动功能部署</span><span class="sxs-lookup"><span data-stu-id="73ffa-344">Test your Mobility deployment</span></span>
<span data-ttu-id="73ffa-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-345"></span></span>

<span data-ttu-id="73ffa-346">部署 Skype for business Server 移动服务和 Skype for business Server 自动发现服务后, 你将需要运行测试事务, 以确保你的部署正确工作。</span><span class="sxs-lookup"><span data-stu-id="73ffa-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="73ffa-347">你可以运行 **Test-CsUcwaConference** 来测试两个用户能否创建和加入会议以及在会议中通信。</span><span class="sxs-lookup"><span data-stu-id="73ffa-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="73ffa-348">你需要两个用户（实际或测试）及其完整凭据来执行此测试。</span><span class="sxs-lookup"><span data-stu-id="73ffa-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="73ffa-349">此命令将同时适用于 Skype for business 客户端和 Lync Server 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="73ffa-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="73ffa-350">对于 Skype for business Server 2015 上的 Lync Server 2010 客户端, 你需要运行**测试 CsMcxP2PIM**进行测试。</span><span class="sxs-lookup"><span data-stu-id="73ffa-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="73ffa-351">您的 Lync Server 2010 用户仍必须是实际用户或预定义的测试用户, 并且您需要其密码凭据。</span><span class="sxs-lookup"><span data-stu-id="73ffa-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="73ffa-352">在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="73ffa-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="73ffa-353">所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="73ffa-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="73ffa-354">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="73ffa-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="73ffa-355">测试 Skype for Business 和 Lync 2013 移动客户端的会议功能</span><span class="sxs-lookup"><span data-stu-id="73ffa-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="73ffa-356">在安装了**Skype For Business Server Management Shell**和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-357">启动**Skype For Business Server 命令行管理**程序 (您可以在 "搜索" 中键入名称, 或选择 "**所有程序**" 并选择它)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="73ffa-358">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="73ffa-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="73ffa-p141">还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="73ffa-361">测试 Lync 2010 移动客户端的会议功能</span><span class="sxs-lookup"><span data-stu-id="73ffa-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="73ffa-362">在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="73ffa-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="73ffa-363">所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="73ffa-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="73ffa-364">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="73ffa-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="73ffa-365">在安装了**Skype For Business Server Management Shell**和**Ocscore**的任何计算机上以**CsAdministrator**角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="73ffa-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-366">启动**Skype For Business Server 命令行管理**程序 (您可以在 "搜索" 中键入名称, 或选择 "**所有程序**" 并选择它)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="73ffa-367">在命令行中输入：</span><span class="sxs-lookup"><span data-stu-id="73ffa-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="73ffa-p143">还可以在脚本中设置凭据并将这些凭据传送给测试 cmdlet。示例如下。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="73ffa-370">要进一步查看命令过程，你可以参阅 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="73ffa-371">配置推送通知</span><span class="sxs-lookup"><span data-stu-id="73ffa-371">Configure for push notifications</span></span>
<span data-ttu-id="73ffa-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-372"></span></span>

<span data-ttu-id="73ffa-373">即使 Skype 或 Lync 应用处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。</span><span class="sxs-lookup"><span data-stu-id="73ffa-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="73ffa-374">但什么是推送通知？</span><span class="sxs-lookup"><span data-stu-id="73ffa-374">But what are push notifications?</span></span> <span data-ttu-id="73ffa-375">它们是事件警报，如新的或错过的 IM 邀请，或收到的语音邮件。</span><span class="sxs-lookup"><span data-stu-id="73ffa-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="73ffa-376">Skype for Business Server 移动服务将这些通知发送到基于云的 Skype for business 服务器推送通知服务, 然后向 Windows Phone 用户发送通知到 Microsoft 推送通知服务 (MSNS)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="73ffa-377">Lync Server 2013 未更改此功能, 但如果你有 Skype for business 服务器, 你将需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="73ffa-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="73ffa-378">对于 Skype for Business 服务器 Edge 服务器, 请添加新的托管提供商、Microsoft Skype for Business Online, 然后在您的组织和 Skype for business Online 之间设置托管提供商联盟。</span><span class="sxs-lookup"><span data-stu-id="73ffa-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="73ffa-p145">通过运行 **Set-CsPushNotificationConfiguration** cmdlet 启用推送通知。默认情况下，推送通知已关闭。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="73ffa-381">测试你的联盟配置和推送通知。</span><span class="sxs-lookup"><span data-stu-id="73ffa-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="73ffa-382">针对推送通知配置你的 Skype for Business 边缘服务器</span><span class="sxs-lookup"><span data-stu-id="73ffa-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="73ffa-383">使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-384">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73ffa-385">添加 Skype for Business Server online 托管提供商。</span><span class="sxs-lookup"><span data-stu-id="73ffa-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="73ffa-386">例如：</span><span class="sxs-lookup"><span data-stu-id="73ffa-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="73ffa-p146">你不能与一个宿主提供程序建立多个联盟关系。因此，如果你已设置一个与 sipfed.online.lync.com 建立了联盟关系的宿主提供程序，请不要为其添加其他宿主提供程序，即使该宿主提供程序的标识不是 SkypeOnline 也是如此。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="73ffa-389">在 Skype for business Online 中设置你的组织和推送通知服务之间的托管提供程序联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="73ffa-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="73ffa-390">在命令行中，你需要键入：</span><span class="sxs-lookup"><span data-stu-id="73ffa-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="73ffa-391">启用推送通知</span><span class="sxs-lookup"><span data-stu-id="73ffa-391">Enable push notifications</span></span>

1. <span data-ttu-id="73ffa-392">使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-393">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73ffa-394">启用推送通知：</span><span class="sxs-lookup"><span data-stu-id="73ffa-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="73ffa-395">启用联盟：</span><span class="sxs-lookup"><span data-stu-id="73ffa-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="73ffa-396">测试联盟和推送通知</span><span class="sxs-lookup"><span data-stu-id="73ffa-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="73ffa-397">使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-398">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73ffa-399">测试联盟配置：</span><span class="sxs-lookup"><span data-stu-id="73ffa-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="73ffa-400">例如：</span><span class="sxs-lookup"><span data-stu-id="73ffa-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="73ffa-401">测试你的推送通知：</span><span class="sxs-lookup"><span data-stu-id="73ffa-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="73ffa-402">例如：</span><span class="sxs-lookup"><span data-stu-id="73ffa-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="73ffa-403">配置移动策略</span><span class="sxs-lookup"><span data-stu-id="73ffa-403">Configure Mobility policy</span></span>
<span data-ttu-id="73ffa-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="73ffa-404"></span></span>

<span data-ttu-id="73ffa-405">你可以使用 Skype for Business 服务器来确定谁可以使用你的移动服务、通过工作、IP 语音 (VoIP) 或视频通话, 以及 VoIP 或视频是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="73ffa-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="73ffa-406">使用通过工号拨号功能，移动用户可以在发出和接收呼叫时使用其工作电话号码，而不是其移动电话号码。</span><span class="sxs-lookup"><span data-stu-id="73ffa-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="73ffa-407">该线路另一端上的人员不会看到移动用户的移动电话号码，并且可以让移动用户避免产生拨出呼叫费用。</span><span class="sxs-lookup"><span data-stu-id="73ffa-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="73ffa-408">设置 VoIP 和视频后，用户可以接收和发出 VoIP 呼叫和视频。</span><span class="sxs-lookup"><span data-stu-id="73ffa-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="73ffa-409">WiFi 用法的设置确定通过蜂窝数据网络使用 WiFi 网络是否需要用户的移动设备。</span><span class="sxs-lookup"><span data-stu-id="73ffa-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="73ffa-410">移动、通过工作通话, 并且 VoIP 和视频功能在默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="73ffa-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="73ffa-411">禁用了 VoIp 和视频需要 WiFi 的设置。</span><span class="sxs-lookup"><span data-stu-id="73ffa-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="73ffa-412">管理员可以全局、按网站或按用户对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="73ffa-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="73ffa-413">若要能够通过工作使用移动功能和通话, 用户必须:</span><span class="sxs-lookup"><span data-stu-id="73ffa-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="73ffa-414">已启用 Skype for Business 服务器</span><span class="sxs-lookup"><span data-stu-id="73ffa-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="73ffa-415">启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="73ffa-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="73ffa-416">分配了**EnableMobility**选项设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="73ffa-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="73ffa-417">对于希望能使用通过工号拨号功能的用户，他们还必须：</span><span class="sxs-lookup"><span data-stu-id="73ffa-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="73ffa-418">分配已选择**允许多部电话同时响铃**选项的语音策略。</span><span class="sxs-lookup"><span data-stu-id="73ffa-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="73ffa-419">分配了**EnableOutsideVoice**设置为**True**的移动策略。</span><span class="sxs-lookup"><span data-stu-id="73ffa-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="73ffa-p150">未启用企业语音的用户可以使用其移动设备发出 Skype 至 Skype VoIP 呼叫，也可以使用“单击以加入”链接来通过移动设备加入会议（如果已为与其关联的语音策略设置相应的选项）。规划主题中有更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="73ffa-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="73ffa-422">修改全局移动策略</span><span class="sxs-lookup"><span data-stu-id="73ffa-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="73ffa-423">使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-424">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73ffa-425">通过键入以下内容来关闭对移动和通过工作全球通话的访问</span><span class="sxs-lookup"><span data-stu-id="73ffa-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="73ffa-426">您可以通过工作来关闭呼叫, 而无需关闭移动访问。</span><span class="sxs-lookup"><span data-stu-id="73ffa-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="73ffa-427">但是, 如果未关闭 "通过工作进行呼叫", 则无法关闭行动。</span><span class="sxs-lookup"><span data-stu-id="73ffa-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="73ffa-428">有关详细信息, 请参阅[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="73ffa-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="73ffa-429">按网站修改移动策略</span><span class="sxs-lookup"><span data-stu-id="73ffa-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="73ffa-430">使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-431">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73ffa-p152">你可以创建站点级别的策略、禁用 VoIP 和视频，以及按网站启用“IP 音频需要 WiFi”和“IP 视频需要 WiFi”。键入：</span><span class="sxs-lookup"><span data-stu-id="73ffa-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="73ffa-434">在 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps) 中了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="73ffa-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="73ffa-435">按用户修改移动策略</span><span class="sxs-lookup"><span data-stu-id="73ffa-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="73ffa-436">使用**CsAdministrator**角色成员的帐户登录到安装了**Skype For Business Server Management Shell**和**Ocscore**的计算机。</span><span class="sxs-lookup"><span data-stu-id="73ffa-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="73ffa-437">启动**Skype For Business Server 命令行管理程序**。</span><span class="sxs-lookup"><span data-stu-id="73ffa-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="73ffa-438">创建用户级移动策略, 并通过用户的工作方式关闭移动性和呼叫。</span><span class="sxs-lookup"><span data-stu-id="73ffa-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="73ffa-439">键入：</span><span class="sxs-lookup"><span data-stu-id="73ffa-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="73ffa-440">包含示例数据的另一个示例：</span><span class="sxs-lookup"><span data-stu-id="73ffa-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="73ffa-441">您可以通过工作来关闭呼叫, 而无需关闭移动访问。</span><span class="sxs-lookup"><span data-stu-id="73ffa-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="73ffa-442">但是, 如果未关闭 "通过工作进行呼叫", 则无法关闭行动。</span><span class="sxs-lookup"><span data-stu-id="73ffa-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

