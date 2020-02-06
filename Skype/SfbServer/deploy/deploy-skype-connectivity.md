---
title: 在 Skype for Business 服务器中部署 Skype 连接
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
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：了解如何将 Skype for business 服务器与 Skype 消费者连接。 也称为 Skype 连接。
ms.openlocfilehash: e9c8a83b24ddbed95f2fd16f2f11b887f2241625
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798099"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a><span data-ttu-id="48223-104">在 Skype for Business 服务器中部署 Skype 连接</span><span class="sxs-lookup"><span data-stu-id="48223-104">Deploy Skype Connectivity in Skype for Business Server</span></span>

<span data-ttu-id="48223-105">**摘要：** 了解如何将 Skype for business 服务器与 Skype 消费者连接。</span><span class="sxs-lookup"><span data-stu-id="48223-105">**Summary:** Learn how to connect Skype for Business Server with Skype consumer.</span></span> <span data-ttu-id="48223-106">也称为 Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="48223-106">Also known as Skype connectivity.</span></span>
  
<span data-ttu-id="48223-107">本文介绍了 Skype 连接的部署。</span><span class="sxs-lookup"><span data-stu-id="48223-107">This article walks through deployment for Skype Connectivity.</span></span>
  
## <a name="skype-connectivity-overview-for-it-professionals"></a><span data-ttu-id="48223-108">面向 IT 专业人员的 Skype 连接概述</span><span class="sxs-lookup"><span data-stu-id="48223-108">Skype Connectivity Overview for IT Professionals</span></span>

<span data-ttu-id="48223-109">Skype 连接使 Skype for business 用户能够搜索和添加 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="48223-109">Skype Connectivity provides Skype for Business users with the ability to search for and add Skype users.</span></span> <span data-ttu-id="48223-110">Skype 连接是 Skype for Business 的一项功能，使你能够与 Skype 用户进行联盟和目录搜索。</span><span class="sxs-lookup"><span data-stu-id="48223-110">Skype Connectivity is a feature of Skype for Business that lets you enable federation and directory search with Skype users.</span></span> <span data-ttu-id="48223-111">启用 Skype 连接后，您的 Skype for Business 用户将能够搜索和添加 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="48223-111">After you enable Skype Connectivity your Skype for Business users will be able to search for and add Skype users.</span></span>
  
## <a name="skype-directory-search"></a><span data-ttu-id="48223-112">Skype 目录搜索</span><span class="sxs-lookup"><span data-stu-id="48223-112">Skype Directory Search</span></span>

<span data-ttu-id="48223-p104">Skype 目录搜索功能允许 Skype for Business 用户搜索 Skype 联系人。该搜索功能允许用户使用以下方式进行搜索：</span><span class="sxs-lookup"><span data-stu-id="48223-p104">Skype Directory Search functionality provides Skype for Business users with the ability to search for Skype contacts. The search functionality lets users search using the following:</span></span>
  
- <span data-ttu-id="48223-115">**按显示名称搜索，示例 "John Doe"** -这可能会返回许多结果，因此你可能找不到要查找的内容。</span><span class="sxs-lookup"><span data-stu-id="48223-115">**Search by display name, example "John Doe"** - This could return many results, so you might not find what you are looking for.</span></span>
    
- <span data-ttu-id="48223-116">**按显示名称加位置搜索，示例 "John Doe 于巴塞罗纳"** -这将显著缩小搜索结果的范围。</span><span class="sxs-lookup"><span data-stu-id="48223-116">**Search by display name plus location, example "John Doe in Barcelona"** - This will narrow the results of the search down considerably.</span></span>
    
- <span data-ttu-id="48223-117">**通过电子邮件进行搜索，示例 "johndoe@outlook.com"** -这在大多数情况下应返回一个结果;与指定的电子邮件完全匹配的一个。</span><span class="sxs-lookup"><span data-stu-id="48223-117">**Search by email, example "johndoe@outlook.com"** - This should return one result in most cases; the one that matches the specified email exactly.</span></span> <span data-ttu-id="48223-118">但是，如果同一电子邮件与多个账户关联，则可能返回多个结果。</span><span class="sxs-lookup"><span data-stu-id="48223-118">But if the same email is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="48223-119">**按电话号码搜索，例如 "123-123-1234"** -这在大多数情况下应返回一个结果;与指定电话完全匹配的一个。</span><span class="sxs-lookup"><span data-stu-id="48223-119">**Search by phone number, example "123-123-1234"** - This should return one result in most cases; the one that matches the specified phone exactly.</span></span> <span data-ttu-id="48223-120">电话号码必须包含国家/地区代码（例如 1-xxx-yyy-zzzz）。</span><span class="sxs-lookup"><span data-stu-id="48223-120">Phone number must include the country code (i.e. 1-xxx-yyy-zzzz).</span></span> <span data-ttu-id="48223-121">如果同一电话号码与多个账户关联，则可能返回多个结果。</span><span class="sxs-lookup"><span data-stu-id="48223-121">If the same phone number is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="48223-122">**按 Skype 用户名进行搜索，示例 "JohnDoe1456"** -如果找到精确匹配，它将作为第一个结果返回。</span><span class="sxs-lookup"><span data-stu-id="48223-122">**Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result.</span></span> <span data-ttu-id="48223-123">可能会返回其他可能的 "名称" 匹配项。</span><span class="sxs-lookup"><span data-stu-id="48223-123">Other possible "name" matches may be returned.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="48223-124">Skype 目录搜索必须能够与端口 443 上的以下 IP 地址进行通信：104.40.75.246、23.101.135.34 和 40.113.86.19。</span><span class="sxs-lookup"><span data-stu-id="48223-124">Skype Directory Search must be able to communicate with the following IP addresses on port 443: 104.40.75.246, 23.101.135.34, and 40.113.86.19.</span></span> 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a><span data-ttu-id="48223-125">Skype 目录搜索支持的部署矩阵</span><span class="sxs-lookup"><span data-stu-id="48223-125">Supported deployment matrix for Skype Directory Search</span></span>

<span data-ttu-id="48223-126">下表概述了对 Skype 目录搜索的支持。</span><span class="sxs-lookup"><span data-stu-id="48223-126">The following table outlines support for Skype Directory Search.</span></span>
  

||<span data-ttu-id="48223-127">**Skype for business 服务器前端**</span><span class="sxs-lookup"><span data-stu-id="48223-127">**Skype for Business Server Front End**</span></span>|<span data-ttu-id="48223-128">**Lync Server 2013（或更早版本）前端**</span><span class="sxs-lookup"><span data-stu-id="48223-128">**Lync Server 2013 (or older) Front End**</span></span>|<span data-ttu-id="48223-129">**批注**</span><span class="sxs-lookup"><span data-stu-id="48223-129">**Comments**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="48223-130">Skype for Business 服务器边缘</span><span class="sxs-lookup"><span data-stu-id="48223-130">Skype for Business Server Edge</span></span>  <br/> |<span data-ttu-id="48223-131">支持</span><span class="sxs-lookup"><span data-stu-id="48223-131">Supported</span></span>  <br/> |<span data-ttu-id="48223-132">否</span><span class="sxs-lookup"><span data-stu-id="48223-132">Not Supported</span></span>  <br/> |<span data-ttu-id="48223-133">Skype for business 服务器和 Edge 是 Skype 目录搜索的先决条件</span><span class="sxs-lookup"><span data-stu-id="48223-133">Skype for Business Server and Edge are prerequisites for Skype Directory Search</span></span>  <br/> |
|<span data-ttu-id="48223-134">Skype for business 服务器 Edge + Lync Server 2013 Edge 并排部署</span><span class="sxs-lookup"><span data-stu-id="48223-134">Skype for Business Server Edge + Lync Server 2013 Edge deployed side-by-side</span></span>  <br/> |<span data-ttu-id="48223-135">支持</span><span class="sxs-lookup"><span data-stu-id="48223-135">Supported</span></span>  <br/> |<span data-ttu-id="48223-136">否</span><span class="sxs-lookup"><span data-stu-id="48223-136">Not Supported</span></span>  <br/> |<span data-ttu-id="48223-p108">Skype 目录搜索流量流经 Skype for Business Server 边缘服务器。联盟流量流经管理员配置的边缘。例如，管理员可以选择继续通过不支持 Skype 目录搜索的 Lync Server 2013 边缘服务器发送联盟流量。</span><span class="sxs-lookup"><span data-stu-id="48223-p108">Skype Directory Search traffic flows through Skype for Business Server Edge servers. Federation traffic goes through edge configured by the administrator. For example, the administrator could choose to continue to send federation traffic through Lync Server 2013 Edge servers which would not support Skype Directory Search.</span></span>  <br/> |
|<span data-ttu-id="48223-140">Lync Server 2013（或更早版本）边缘</span><span class="sxs-lookup"><span data-stu-id="48223-140">Lync Server 2013 (or older) Edge</span></span>  <br/> |<span data-ttu-id="48223-141">否</span><span class="sxs-lookup"><span data-stu-id="48223-141">Not Supported</span></span>  <br/> |<span data-ttu-id="48223-142">否</span><span class="sxs-lookup"><span data-stu-id="48223-142">Not Supported</span></span>  <br/> ||
   
> [!NOTE]
> <span data-ttu-id="48223-143">在 Skype for Business 服务器前端运行的通讯录服务在边缘服务器中是否存在 Skype 搜索端口4443查找边缘。</span><span class="sxs-lookup"><span data-stu-id="48223-143">Addressbook service running on Skype for Business Server Front End finds the Edge by the existence of the Skype Search port 4443 in the Edge server.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48223-144">如果客户在其本地部署中具有多个网站，并且他们仅部署了一个 Skype for Business 服务器 Edge 服务器/池，那么来自所有网站的搜索流量将经历单个可用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="48223-144">In case a customer has multiple sites in their on-premises deployment, and if they have deployed just one Skype for Business Server Edge server/pool, then Search traffic from all sites will go through the single available Edge server.</span></span> <span data-ttu-id="48223-145">管理员需要确保所有网站的池都可以访问已部署的 Skype for Business Server Edge 服务器/池。</span><span class="sxs-lookup"><span data-stu-id="48223-145">The administrator needs to make sure the pools from all sites can access the deployed Skype for Business Server Edge server/pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48223-146">如果请求率超过 15 个请求/秒，Skype 图形服务将限制来自本地或 Office 365 客户的搜索请求。</span><span class="sxs-lookup"><span data-stu-id="48223-146">Skype graph service will throttle search requests from any on-premises or Office 365 customer if the request rate exceeds 15 requests / second.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48223-147">对于大型企业本地客户，需要使用 Skype 搜索服务对域建立白名单才能允许更高的请求率。</span><span class="sxs-lookup"><span data-stu-id="48223-147">For large enterprise on-premises customers, the domains will need to be whitelisted with the Skype search service to allow higher request rates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48223-148">如果队列中有太多挂起的请求，则 Skype for business 服务器将阻止传入的请求。</span><span class="sxs-lookup"><span data-stu-id="48223-148">Skype for Business Server will throttle incoming requests, if there are too many pending requests in the queue.</span></span> 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a><span data-ttu-id="48223-149">在 Office 365 中部署 Skype for Business Online 的 Skype 连接</span><span class="sxs-lookup"><span data-stu-id="48223-149">Deploying Skype Connectivity for Skype for Business Online in Office 365</span></span>

<span data-ttu-id="48223-p110">Skype 连接同样是 Skype for Business Online（Office 365 的一部分）的一项功能。您可以从 Office 365 门户中的 Skype for Business 管理中心启用 Skype 连接功能。</span><span class="sxs-lookup"><span data-stu-id="48223-p110">Skype Connectivity is also a feature of Skype for Business Online, which is part of Office 365. You can enable the Skype Connectivity feature from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
<span data-ttu-id="48223-152">对于 Office 365 中型企业版、Office 365 企业版、Office 365 教育版和 Office 365 政府版：登录 Office 365 门户并导航到 Skype for Business 管理中心。</span><span class="sxs-lookup"><span data-stu-id="48223-152">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the Skype for Business Administration Center.</span></span> <span data-ttu-id="48223-153">转至“外部通信”。</span><span class="sxs-lookup"><span data-stu-id="48223-153">Go to External Communications.</span></span> <span data-ttu-id="48223-154">在“公共 IM 服务提供商”下，单击“启用”。</span><span class="sxs-lookup"><span data-stu-id="48223-154">Under Public IM Service Providers, click Enable.</span></span> <span data-ttu-id="48223-155">如果您想要控制单个用户对 Skype 连接的访问，您可以通过编辑单个用户的外部通信设置来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="48223-155">If you want to control individual user access to Skype Connectivity, you can do so by editing individual users' External Communications settings.</span></span>
  
<span data-ttu-id="48223-156">对于 Office 365 小型企业高级版：登录到 Office 365，然后转到 " \>管理员服务\>设置" 即时消息、会议和会议。</span><span class="sxs-lookup"><span data-stu-id="48223-156">For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing.</span></span> <span data-ttu-id="48223-157">打开“外部通信”。</span><span class="sxs-lookup"><span data-stu-id="48223-157">Turn on External communications.</span></span> <span data-ttu-id="48223-158">“外部通信”开关会同时打开与其他使用 Skype for Business 的组织之间的 Skype 连接和通信。</span><span class="sxs-lookup"><span data-stu-id="48223-158">The External communications switch turns on both Skype Connectivity and communications with other organizations that use Skype for Business.</span></span>
  
<span data-ttu-id="48223-159">有关 Skype for Business Online 管理的更多信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="48223-159">For more information about Skype for Business Online administration, see:</span></span>
  
- [<span data-ttu-id="48223-160">允许用户连接外部 Skype for Business 用户</span><span class="sxs-lookup"><span data-stu-id="48223-160">Allow users to contact external Skype for Business users</span></span>](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [<span data-ttu-id="48223-161">无法向 Skype for business 或 Skype 外部联系人发送即时消息时应尝试的操作</span><span class="sxs-lookup"><span data-stu-id="48223-161">What to try if you can't IM Skype for Business or Skype external contacts</span></span>](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [<span data-ttu-id="48223-162">在 Skype for Business 中添加联系人</span><span class="sxs-lookup"><span data-stu-id="48223-162">Add a contact in Skype for Business</span></span>](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [<span data-ttu-id="48223-163">管理员：为单个用户配置 Skype for Business 设置</span><span class="sxs-lookup"><span data-stu-id="48223-163">Admins: Configure Skype for Business settings for individual users</span></span>](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a><span data-ttu-id="48223-164">为 Skype for Business 服务器部署 Skype 连接</span><span class="sxs-lookup"><span data-stu-id="48223-164">Deploying Skype Connectivity for Skype for Business Server</span></span>

<span data-ttu-id="48223-165">Skype for business 服务器使用联盟访问体系结构来支持与 Skype 的连接。</span><span class="sxs-lookup"><span data-stu-id="48223-165">Skype for Business Server uses the federation access architecture to support connectivity with Skype.</span></span> <span data-ttu-id="48223-166">此连接允许您的 Skype for Business Server 用户添加 Skype。</span><span class="sxs-lookup"><span data-stu-id="48223-166">This connectivity enables your Skype for Business Server users to add Skype.</span></span> <span data-ttu-id="48223-167">Skype 客户端也可向联系人列表添加 Skype for Business 用户。</span><span class="sxs-lookup"><span data-stu-id="48223-167">Skype clients can also add Skype for Business users to their contact list.</span></span> <span data-ttu-id="48223-168">基于在 Skype for Business Server 用户中设置的策略，用户将能够使用即时消息进行通信，查看彼此的状态，并启动音频和视频通话。</span><span class="sxs-lookup"><span data-stu-id="48223-168">Based on policies administratively set in Skype for Business Server users will be able to communicate using instant messaging, see each other's presence, and initiate audio and video calls.</span></span> <span data-ttu-id="48223-169">Skype 连接也是 Skype for Business Online 的一项功能，可从 Office 365 门户中的 Skype for Business 管理中心为 Skype for Business Online 客户启用。</span><span class="sxs-lookup"><span data-stu-id="48223-169">Skype connectivity is also a feature of Skype for Business Online, and can be enabled for Skype for Business Online customers from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48223-p114">如果 Skype for Business Server 已配置为通过使用公共即时消息连接 (PIC) 连接 Windows Messenger，则您的部署已配置好了 Skype 连接。您可能希望作出的唯一更改是将您的现有 Messenger PIC 条目重命名为 Skype。</span><span class="sxs-lookup"><span data-stu-id="48223-p114">If Skype for Business Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Skype connectivity. The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a><span data-ttu-id="48223-172">Skype for Business 服务器公共 IM 连接设置网站已不再可用</span><span class="sxs-lookup"><span data-stu-id="48223-172">The Skype for Business Server public IM connectivity provisioning site is no longer available</span></span>

<span data-ttu-id="48223-173">以前用于手动设置 Skype for Business 内部部署和 Skype 之间的联盟的网站不再需要，并且将在8/15/2019 上关闭。</span><span class="sxs-lookup"><span data-stu-id="48223-173">The site that was formerly used to manually provision federation between Skype for Business on-premises deployments and Skype is no longer necessary and will be shut down on 8/15/2019.</span></span> <span data-ttu-id="48223-174">使用 Skype 的联盟现在利用联盟合作伙伴发现，这与与 Skype for business Online 联盟所需的机制相同。</span><span class="sxs-lookup"><span data-stu-id="48223-174">Federation with Skype now utilizes federated partner discovery, which is the same mechanism required for federation with Skype for Business Online.</span></span>

<span data-ttu-id="48223-175">任何本地 Skype for Business 部署和 Skype 用户之间通过现有公共 IM 基础结构进行通信现在需要与 Skype for Business Online 兼容的本地边缘服务器配置。</span><span class="sxs-lookup"><span data-stu-id="48223-175">Communication between any on-premises Skype for Business deployment and Skype users via the existing Public IM infrastructure now requires the on-premises Edge Server configuration to be compatible with Skype for Business Online.</span></span>

> [!NOTE]
> <span data-ttu-id="48223-176">大多数客户不需要执行任何操作，包括与 Skype for Business Online 联合的所有部署。</span><span class="sxs-lookup"><span data-stu-id="48223-176">No action is needed by most customers, including all deployments that federate with Skype for Business Online.</span></span>
  
<span data-ttu-id="48223-177">要为其托管的每个域发布联合身份验证 DNS SRV 记录，需要本地部署。</span><span class="sxs-lookup"><span data-stu-id="48223-177">On-premises deployments are required to publish a Federation DNS SRV record for each domain that they host.</span></span> <span data-ttu-id="48223-178">指南在[DNS 规划](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中可用。</span><span class="sxs-lookup"><span data-stu-id="48223-178">Guidance is available in [DNS planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning).</span></span> <span data-ttu-id="48223-179">每个域必须由 DNS SRV 查询解析为满足域的顶级后缀匹配的边缘服务器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="48223-179">Each domain must resolve by DNS SRV query to an edge server FQDN that satisfies a top-level suffix match of the domain.</span></span> <span data-ttu-id="48223-180">例如，请考虑域 "contoso.com"：</span><span class="sxs-lookup"><span data-stu-id="48223-180">For example, consider the domain "contoso.com":</span></span>

|<span data-ttu-id="48223-181">**有效 Fqdn**</span><span class="sxs-lookup"><span data-stu-id="48223-181">**Valid FQDNs**</span></span>|<span data-ttu-id="48223-182">**注释**</span><span class="sxs-lookup"><span data-stu-id="48223-182">**Comment**</span></span>|
|:-----|:-----|
|<span data-ttu-id="48223-183">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48223-183">sip.contoso.com</span></span>   ||
|<span data-ttu-id="48223-184">sipfed.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48223-184">sipfed.contoso.com</span></span>   |<span data-ttu-id="48223-185">在每种情况下，确切的 FQDN 都必须存在于安装在边缘服务器上的外部证书的 SN 或 SAN 中。</span><span class="sxs-lookup"><span data-stu-id="48223-185">In each case, the exact FQDN must be present in either the SN or the SAN of the external certificate installed on the edge server.</span></span>   |
|<span data-ttu-id="48223-186">access.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48223-186">access.contoso.com</span></span>   ||
|<span data-ttu-id="48223-187">**无效 Fqdn**</span><span class="sxs-lookup"><span data-stu-id="48223-187">**Invalid FQDNs**</span></span>|<span data-ttu-id="48223-188">**原因**</span><span class="sxs-lookup"><span data-stu-id="48223-188">**Reason**</span></span>|
|<span data-ttu-id="48223-189">sip.contoso-edge.com</span><span class="sxs-lookup"><span data-stu-id="48223-189">sip.contoso-edge.com</span></span>   |<span data-ttu-id="48223-190">不匹配后缀。</span><span class="sxs-lookup"><span data-stu-id="48223-190">Not a suffix match.</span></span>  |
|<span data-ttu-id="48223-191">sip.it.contoso.com</span><span class="sxs-lookup"><span data-stu-id="48223-191">sip.it.contoso.com</span></span>   |<span data-ttu-id="48223-192">不是最高级别后缀匹配项。</span><span class="sxs-lookup"><span data-stu-id="48223-192">Not a top-level suffix match.</span></span>   |

<span data-ttu-id="48223-193">有关外部证书的进一步指导可在[证书规划](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)中找到。</span><span class="sxs-lookup"><span data-stu-id="48223-193">Further guidance regarding External Certificates can be found in [Certificate planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).</span></span>

#### <a name="faqs"></a><span data-ttu-id="48223-194">常见问题</span><span class="sxs-lookup"><span data-stu-id="48223-194">FAQs</span></span>

<span data-ttu-id="48223-195">**为什么正在关闭预配网站？**</span><span class="sxs-lookup"><span data-stu-id="48223-195">**Why is the provisioning website being shut down?**</span></span>
<span data-ttu-id="48223-196">在2006中部署的公共 IM （PIC）设置机制（pic.lync.com）将不再维修，并且将在8/15/2019 上关闭。</span><span class="sxs-lookup"><span data-stu-id="48223-196">The public IM (PIC) provisioning mechanism (pic.lync.com) that was deployed in 2006 is no longer serviceable and will be shut down on 8/15/2019.</span></span> <span data-ttu-id="48223-197">相反，公共 IM 联盟将采用 Skype for Business Online （称为 "合作伙伴发现"）所使用的相同联盟模型，因此本地部署可通过其联合 DNS SRV 记录公开发现。</span><span class="sxs-lookup"><span data-stu-id="48223-197">Instead, public IM federation will assume the same federation model used by Skype for Business Online, known as "partner discovery", whereby an on-premises deployment is publicly discoverable by its federation DNS SRV record(s).</span></span>

<span data-ttu-id="48223-198">**此更改是否意味着已弃用公共 IM 联合身份验证？**</span><span class="sxs-lookup"><span data-stu-id="48223-198">**Does this change mean that Public IM federation is being deprecated?**</span></span>
<span data-ttu-id="48223-199">不能。</span><span class="sxs-lookup"><span data-stu-id="48223-199">No.</span></span> <span data-ttu-id="48223-200">公共 IM 联合身份验证将继续支持许多年，直到 Skype for Business 本地产品达到生命周期结束时间。</span><span class="sxs-lookup"><span data-stu-id="48223-200">Public IM federation will continue to be supported for many years, probably until the Skype for Business on-premises product reaches end-of-life.</span></span>

<span data-ttu-id="48223-201">**我们的公司与 Skype for Business Online 有混合关系（共享地址空间），我们受到影响？**</span><span class="sxs-lookup"><span data-stu-id="48223-201">**Our company has a hybrid relationship (shared address space) with Skype for Business Online, are we affected?**</span></span>
<span data-ttu-id="48223-202">不能，因为您已经与 Skype for Business Online 联盟，所以此更改不会影响您。</span><span class="sxs-lookup"><span data-stu-id="48223-202">No, since you are already federating with Skype for Business Online, this change will not affect you.</span></span>
 
<span data-ttu-id="48223-203">**此更改意味着我们的公司必须启用与 Skype for Business Online 的联盟？**</span><span class="sxs-lookup"><span data-stu-id="48223-203">**Does this change mean that our company has to enable federation with Skype for Business Online?**</span></span>
<span data-ttu-id="48223-204">不能。</span><span class="sxs-lookup"><span data-stu-id="48223-204">No.</span></span> <span data-ttu-id="48223-205">如果你的 edge 服务器代理设置未启用与 Skype for Business Online 托管提供商（sipfed.online.lync.com）的联盟，此更改将不会影响。</span><span class="sxs-lookup"><span data-stu-id="48223-205">If your edge server proxy settings do not enable federation with the Skype for Business Online hosting provider (sipfed.online.lync.com) then this change will not affect that.</span></span> <span data-ttu-id="48223-206">但是，用于与 Skype for Business Online 进行联盟的相同 DNS 和证书要求现在也适用于与 Skype 用户联盟。</span><span class="sxs-lookup"><span data-stu-id="48223-206">However, the same DNS and certificate requirements that apply to federating with Skype for Business Online now also apply to federating with Skype users.</span></span>
 
<span data-ttu-id="48223-207">**我们的公司规模较大，因此不能更改其边缘配置，因为管理法规/合规性或等理由我们可以执行哪些操作？**</span><span class="sxs-lookup"><span data-stu-id="48223-207">**Our company is large and cannot change its edge configuration due to regulatory/compliance/etc reasons … what can we do?**</span></span>
<span data-ttu-id="48223-208">任何不能根据指定更改边缘服务器配置的本地组织都应尽早联系产品支持人员。</span><span class="sxs-lookup"><span data-stu-id="48223-208">Any on-premises organization that cannot change its edge server configuration as specified should reach out to product support at the earliest opportunity.</span></span>

### <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="48223-209">启用联盟和公共 IM 连接 (PIC)</span><span class="sxs-lookup"><span data-stu-id="48223-209">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="48223-210">现在重点介绍 Skype for Business 服务器环境和配置 Skype 连接所需的管理任务。</span><span class="sxs-lookup"><span data-stu-id="48223-210">Now focus on the Skype for Business Server environment and administrative tasks required to configure Skype Connectivity.</span></span> <span data-ttu-id="48223-211">在此部分，我们假定管理员已部署了 Skype for Business Server 并配置了外部访问（即边缘服务器）。</span><span class="sxs-lookup"><span data-stu-id="48223-211">In this section, we assume that the administrator has deployed Skype for Business Server and configured external access, also known as Edge servers.</span></span> 
  
<span data-ttu-id="48223-p123">要启用联盟和 PIC，需要执行三个主要步骤。包括：</span><span class="sxs-lookup"><span data-stu-id="48223-p123">There are three primary steps required to enable federation and PIC. These are:</span></span>
  
1. <span data-ttu-id="48223-214">配置联盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="48223-214">Configure Federation and PIC</span></span>
    
2. <span data-ttu-id="48223-215">配置至少一个策略以支持联盟的用户访问</span><span class="sxs-lookup"><span data-stu-id="48223-215">Configure at least one policy to support federated user access</span></span>
    
3. <span data-ttu-id="48223-216">配置 Skype PIC 提供商设置</span><span class="sxs-lookup"><span data-stu-id="48223-216">Configure the Skype PIC provider setting</span></span>
    
#### <a name="1-configure-federation-and-pic"></a><span data-ttu-id="48223-217">1. 配置联盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="48223-217">1. Configure Federation and PIC</span></span>

<span data-ttu-id="48223-p124">需要联盟，Skype 用户才能与您的组织中的 Skype for Business 用户进行通信。公共即时消息连接 (PIC) 是一种联盟类别，必须配置它，您的 Skype for Business 用户才能够与 Skype 用户进行通信。联盟和 PIC 可使用 Skype for Business Server 控制面板进行配置。</span><span class="sxs-lookup"><span data-stu-id="48223-p124">Federation is required to enable Skype users to communicate with Skype for Business users in your organization. Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business users to communicate with Skype users. Federation and PIC are configured by using the Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="48223-221">Lync Server 2010 （实时通信服务器、Office 通信服务器）之前的产品版本不再支持 PIC 联盟。</span><span class="sxs-lookup"><span data-stu-id="48223-221">PIC federation is no longer supported by product releases prior to Lync Server 2010 (Live Communication Server, Office Communications Server).</span></span> <span data-ttu-id="48223-222">PIC 联盟支持的平台包括 Skype for Business Server、Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="48223-222">The supported platforms for PIC federation include Skype for Business Server, Lync Server 2013, and Lync Server 2010.</span></span> 
  
<span data-ttu-id="48223-p126">需要联盟，Skype 用户才能与您的组织中的 Skype for Business 用户进行通信。公共即时消息连接 (PIC) 是一种联盟类别，必须配置它，您的 Skype for Business Server 用户才能够与 Skype 用户进行通信。联盟和 PIC 可使用 Skype for Business Server 控制面板的边缘配置对话框进行配置，如图所示。</span><span class="sxs-lookup"><span data-stu-id="48223-p126">Federation is required to enable Skype users to communicate with Skype for Business users in your organization. Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business Server users to communicate with Skype users. Federation and PIC are configured by using the Edge configuration dialog of the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![定义新边缘池](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> <span data-ttu-id="48223-227">要让搜索正常运行，EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 属性需要在公共提供商设置中设为 true（参见后续说明）。</span><span class="sxs-lookup"><span data-stu-id="48223-227">EnableSkypeIdRouting and EnableSkypeDirectorySearch attributes need to be set to true in the public provider settings (see later instructions) for Search to work.</span></span> 
  
<span data-ttu-id="48223-p127">这将完成必须在服务器上执行的管理任务。您现在可以设置 Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="48223-p127">This completes the administrative tasks that must be performed on the server. You are now set up for Skype Connectivity.</span></span>
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="48223-230">2. 至少配置一个用于支持联合用户访问的策略</span><span class="sxs-lookup"><span data-stu-id="48223-230">2. Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="48223-231">使用 Skype for Business Server 控制面板，管理员必须配置一个或多个外部用户访问策略来控制 Skype 用户能否与内部 Skype for Business Server 用户进行协作。</span><span class="sxs-lookup"><span data-stu-id="48223-231">Using the Skype for Business Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Skype for Business Server users.</span></span>
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a><span data-ttu-id="48223-232">3. 配置 Skype PIC 提供程序设置</span><span class="sxs-lookup"><span data-stu-id="48223-232">3. Configure the Skype PIC provider setting</span></span>

<span data-ttu-id="48223-233">使用 Skype for Business Server 命令行管理程序，管理员必须配置 Skype for Business 客户端策略以将 Skype 显示为附加 PIC 提供商。</span><span class="sxs-lookup"><span data-stu-id="48223-233">Using the Skype for Business Server Management Shell, an administrator must configure the Skype for Business client policy to display Skype as an additional PIC provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="48223-234">公共即时消息连接（PIC）服务提供商的用户无法在你的组织中参与 IM 或会议，直到你还配置了至少一个策略（本过程前面的步骤2）以支持公用 IM 连接。</span><span class="sxs-lookup"><span data-stu-id="48223-234">Users of the Public Instant Messaging Connectivity (PIC) service providers can't participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span> 
  
<span data-ttu-id="48223-235">对于新安装，您可以使用 Skype for Business Server 控制面板启用 Skype 公共提供商，从而配置 Skype 连接，如图所示。</span><span class="sxs-lookup"><span data-stu-id="48223-235">For new installations you can configure Skype Connectivity by enabling a Skype Public Provider using the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![SIP 联盟提供商](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> <span data-ttu-id="48223-237">要在升级为 Skype for Business Server 时配置 Skype 连接，您必须删除并重新添加现有 Skype 公共提供商。</span><span class="sxs-lookup"><span data-stu-id="48223-237">To configure Skype Connectivity when upgrading to Skype for Business Server you must remove and re-add the existing Skype public provider.</span></span> 
  
<span data-ttu-id="48223-p128">也可以仅使用 PowerShell 配置 Skype 连接。要使用 PowerShell 配置 Skype 连接：</span><span class="sxs-lookup"><span data-stu-id="48223-p128">Configuring Skype Connectivity can also be done using only PowerShell. To configure Skype Connectivity using PowerShell:</span></span>
  
1. <span data-ttu-id="48223-240">从 Skype for Business Server 前端服务器，打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="48223-240">From a Skype for Business Server Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="48223-241">运行以下两个命令：</span><span class="sxs-lookup"><span data-stu-id="48223-241">Run the following two commands:</span></span>
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > <span data-ttu-id="48223-242">如果您的环境中没有 PIC 提供商，并且要创建新的 PIC 提供商，则您无需运行 Remove-CsPublicProvider cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48223-242">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the Remove-CsPublicProvider cmdlet.</span></span> 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    <span data-ttu-id="48223-243">这些不太明显的参数有什么作用？</span><span class="sxs-lookup"><span data-stu-id="48223-243">What do the less obvious parameters do?</span></span>
    
   - <span data-ttu-id="48223-244">ProxyFqdn：Skype 联盟边缘的位置（由 Microsoft 掌控/维护）</span><span class="sxs-lookup"><span data-stu-id="48223-244">ProxyFqdn: location of Skype federation edge (owned/maintained by Microsoft)</span></span>
    
   - <span data-ttu-id="48223-245">IconURL： Lync &amp; Skype for business 客户端使用的图标直观地标识 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="48223-245">IconURL: icon used by Lync &amp; Skype for Business client to visually identify Skype contacts</span></span>
    
   - <span data-ttu-id="48223-246">NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：设置这些设置允许用户输入 Skype 用户的 MSAs，而无需了解有关 "装修" 非 Microsoft 域的 "msn.com"。</span><span class="sxs-lookup"><span data-stu-id="48223-246">NameDecorationRoutingDomain and NameDecorationExcludedDomainList: setting these allows users to enter Skype users' MSAs without needing to know about "decorating" non-Microsoft domains with "msn.com".</span></span> <span data-ttu-id="48223-247">这样，就不需要为 ExcludedDomainList 中未提供的所有域键入 "user （contoso） @msn .com"。</span><span class="sxs-lookup"><span data-stu-id="48223-247">This eliminates the need to type "user(contoso.com)@msn.com" for all domains that are NOT in the ExcludedDomainList.</span></span> <span data-ttu-id="48223-248">SfB 客户端将自动格式化 MSA（如果域不在 Excluded 列表中）。</span><span class="sxs-lookup"><span data-stu-id="48223-248">The SfB client will automatically format the MSA if the domain is NOT in the Excluded list.</span></span> <span data-ttu-id="48223-249">我们已将最常用的 Microsoft 帐户域添加到排除列表。</span><span class="sxs-lookup"><span data-stu-id="48223-249">We've added the most common Microsoft Account domains to the excluded list.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="48223-250">如果作出了更改，则必须删除并重新添加公共提供商。</span><span class="sxs-lookup"><span data-stu-id="48223-250">Public Provider must be removed and added new if changes are made.</span></span> <span data-ttu-id="48223-251">不允许进行就地更改。</span><span class="sxs-lookup"><span data-stu-id="48223-251">No in-place changes are allowed.</span></span> 
  
     > [!NOTE]
     > <span data-ttu-id="48223-252">在 Lync Server 2013 CU5 &amp;中添加了 OFFICE 2013 SP1 中的 lync 桌面客户端，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户添加了 "装饰" 非 Microsoft 域所需的 Skype 联系人以标识和将其路由到 Skype 的情况（格式为： user （contoso） @msn .com）。</span><span class="sxs-lookup"><span data-stu-id="48223-252">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to "decorate" non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="48223-253">这些新设置将允许在 "添加 Skype 联系人" 对话框中使用 "添加 Skype 联系人" 对话框自动设置地址格式，如果该对话框中不包含域 NameDecorationRoutingDomain，则该对话框应设置为 msn.com）（我们目前可以支持 msn.com、live.com、Hotmail.com、outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="48223-253">These new settings will allow automatic formatting of the address user's enter in the "Add Skype contact" dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span> 
  
3. <span data-ttu-id="48223-254">通过 Skype for Business 客户端，用户现在可以搜索和添加 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="48223-254">From a Skype for Business client users can now search for and add a Skype user.</span></span>
    
## <a name="clients-and-interoperability-matrix"></a><span data-ttu-id="48223-255">客户端和互操作性矩阵</span><span class="sxs-lookup"><span data-stu-id="48223-255">Clients and Interoperability Matrix</span></span>

<span data-ttu-id="48223-256">下表概括介绍了最新版本的 Skype 消费者产品与最新版本的 Skype for Business 之间的互操作状况。</span><span class="sxs-lookup"><span data-stu-id="48223-256">The following table outlines the status of interop between the latest version of Skype consumer and the latest version of Skype for Business.</span></span>
  

|<span data-ttu-id="48223-257">**Skype 客户端**</span><span class="sxs-lookup"><span data-stu-id="48223-257">**Skype Clients**</span></span>|<span data-ttu-id="48223-258">**添加联系人、IM、状态、语音和视频呼叫**</span><span class="sxs-lookup"><span data-stu-id="48223-258">**Add contacts, IM, presence, audio, and video calling**</span></span>|<span data-ttu-id="48223-259">**注释**</span><span class="sxs-lookup"><span data-stu-id="48223-259">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48223-260">Skype Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="48223-260">Skype Windows Desktop</span></span>  <br/> |<span data-ttu-id="48223-261">7.6 或更高版本，Windows XP 和更高版本</span><span class="sxs-lookup"><span data-stu-id="48223-261">7.6 or higher, Windows XP and higher</span></span>  <br/> |<span data-ttu-id="48223-262">**新增**：为在 windows XP 和 windows Vista 上运行的 windows Skype 客户端添加的支持 **（需要最新的客户端版本7.26 或更高版本）**</span><span class="sxs-lookup"><span data-stu-id="48223-262">**NEW**: Support added for Windows Skype client running on Windows XP, and Windows Vista **(requires latest client version 7.26 or higher)**</span></span> <br/> |
|<span data-ttu-id="48223-263">Skype 移动 - Android 手机和平板电脑 </span><span class="sxs-lookup"><span data-stu-id="48223-263">Skype Mobile - Android Phone and Tablet</span></span>  <br/> |<span data-ttu-id="48223-264">6.19 或更高版本，运行 Android OS 4.0.3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="48223-264">6.19 or higher, running Android OS version 4.0.3 or higher</span></span>  <br/> |<span data-ttu-id="48223-265">低规格设备可能不支持视频呼叫</span><span class="sxs-lookup"><span data-stu-id="48223-265">Low spec devices may not support video calling</span></span>  <br/> |
|<span data-ttu-id="48223-266">Skype Mobile-iOS</span><span class="sxs-lookup"><span data-stu-id="48223-266">Skype Mobile - iOS</span></span>  <br/> |<span data-ttu-id="48223-267">6.11 或更高版本，在 IOS 7 或更高版本上</span><span class="sxs-lookup"><span data-stu-id="48223-267">6.11 or higher, on IOS 7 or higher</span></span>  <br/> |<span data-ttu-id="48223-268">在 iPhone 4 和更早版本、iPod 第 4 代和更早版本、Pad 第 1 代上不受支持</span><span class="sxs-lookup"><span data-stu-id="48223-268">Not supported are iPhone 4 and earlier, iPod 4th generation and earlier, iPad 1st generation</span></span>  <br/> |
|<span data-ttu-id="48223-269">Skype Mac</span><span class="sxs-lookup"><span data-stu-id="48223-269">Skype Mac</span></span>  <br/> |<span data-ttu-id="48223-270">7.19 或更高版本，在 Mac OS X 10.9 (Mavericks) 或更高版本上</span><span class="sxs-lookup"><span data-stu-id="48223-270">7.19 or higher, on Mac OS X 10.9 (Mavericks) or higher</span></span>  <br/> |<span data-ttu-id="48223-271">需要 Mac OSX 10.9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="48223-271">Requires Mac OSX 10.9 or higher</span></span>  <br/> |
|<span data-ttu-id="48223-272">Skype 通用 Windows 应用 (Windows 10) 桌面和移动版</span><span class="sxs-lookup"><span data-stu-id="48223-272">Skype Universal Windows App (Windows 10) Desktop and Mobile</span></span>  <br/> |<span data-ttu-id="48223-273">Windows 10（Redstone 1 更新或更高版本）</span><span class="sxs-lookup"><span data-stu-id="48223-273">Windows 10 (Redstone 1 update or later)</span></span>  <br/> |<span data-ttu-id="48223-274">Windows 通用应用将在 2016 年秋季收到更新，该更新添加了互操作性支持</span><span class="sxs-lookup"><span data-stu-id="48223-274">Windows Universal App will receive update in Fall 2016 adding interop support</span></span>  <br/> |
   
<span data-ttu-id="48223-275">下表概括介绍了最新版本的 Skype for Business 与最新版本的 Skype 消费者产品之间的互操作状况。</span><span class="sxs-lookup"><span data-stu-id="48223-275">The following table outlines the status of interop between the latest version of Skype for Business and the latest version of Skype consumer.</span></span> 
  
|<span data-ttu-id="48223-276">**客户端**</span><span class="sxs-lookup"><span data-stu-id="48223-276">**Client**</span></span>|<span data-ttu-id="48223-277">**Skype 目录搜索和添加联系人**</span><span class="sxs-lookup"><span data-stu-id="48223-277">**Skype Directory Search and Add Contacts**</span></span>|<span data-ttu-id="48223-278">**Skype A/V、IM 互操作**</span><span class="sxs-lookup"><span data-stu-id="48223-278">**Skype A/V, IM interop**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="48223-279">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48223-279">Skype for Business</span></span>  <br/> |<span data-ttu-id="48223-280">是</span><span class="sxs-lookup"><span data-stu-id="48223-280">Yes</span></span>  <br/> |<span data-ttu-id="48223-281">是</span><span class="sxs-lookup"><span data-stu-id="48223-281">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-282">Mac 版 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="48223-282">Skype for Business on Mac</span></span>  <br/> |<span data-ttu-id="48223-283">可以添加（无搜索）</span><span class="sxs-lookup"><span data-stu-id="48223-283">Can add (no search)</span></span>  <br/> |<span data-ttu-id="48223-284">是</span><span class="sxs-lookup"><span data-stu-id="48223-284">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-285">Lync Desktop 2013</span><span class="sxs-lookup"><span data-stu-id="48223-285">Lync Desktop 2013</span></span>  <br/> |<span data-ttu-id="48223-286">可以添加（无搜索）</span><span class="sxs-lookup"><span data-stu-id="48223-286">Can add (no search)</span></span>  <br/> |<span data-ttu-id="48223-287">是</span><span class="sxs-lookup"><span data-stu-id="48223-287">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-288">Lync Web App - 联机和本地</span><span class="sxs-lookup"><span data-stu-id="48223-288">Lync Web App - online and on-premises</span></span>  <br/> |<span data-ttu-id="48223-289">不适用</span><span class="sxs-lookup"><span data-stu-id="48223-289">N/A</span></span>  <br/> |<span data-ttu-id="48223-290">不适用</span><span class="sxs-lookup"><span data-stu-id="48223-290">N/A</span></span>  <br/> |
|<span data-ttu-id="48223-291">Lync 移动 - Windows Phone</span><span class="sxs-lookup"><span data-stu-id="48223-291">Lync Mobile - Windows Phone</span></span>  <br/> |<span data-ttu-id="48223-292">即将提供</span><span class="sxs-lookup"><span data-stu-id="48223-292">Coming Soon</span></span>  <br/> |<span data-ttu-id="48223-293">是</span><span class="sxs-lookup"><span data-stu-id="48223-293">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-294">Lync 移动 - Android</span><span class="sxs-lookup"><span data-stu-id="48223-294">Lync Mobile - Android</span></span>  <br/> |<span data-ttu-id="48223-295">即将提供</span><span class="sxs-lookup"><span data-stu-id="48223-295">Coming Soon</span></span>  <br/> |<span data-ttu-id="48223-296">是</span><span class="sxs-lookup"><span data-stu-id="48223-296">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-297">Lync 移动 - iOS</span><span class="sxs-lookup"><span data-stu-id="48223-297">Lync Mobile - iOS</span></span>  <br/> |<span data-ttu-id="48223-298">即将提供</span><span class="sxs-lookup"><span data-stu-id="48223-298">Coming Soon</span></span>  <br/> |<span data-ttu-id="48223-299">是</span><span class="sxs-lookup"><span data-stu-id="48223-299">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-300">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="48223-300">Lync Room System</span></span>  <br/> |<span data-ttu-id="48223-301">即将提供</span><span class="sxs-lookup"><span data-stu-id="48223-301">Coming Soon</span></span>  <br/> |<span data-ttu-id="48223-302">是</span><span class="sxs-lookup"><span data-stu-id="48223-302">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-303">Lync Modern App (Win 8.1)</span><span class="sxs-lookup"><span data-stu-id="48223-303">Lync Modern App (Win 8.1)</span></span>  <br/> |<span data-ttu-id="48223-304">是</span><span class="sxs-lookup"><span data-stu-id="48223-304">Yes</span></span>  <br/> |<span data-ttu-id="48223-305">是</span><span class="sxs-lookup"><span data-stu-id="48223-305">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-306">Lync Mac 2011</span><span class="sxs-lookup"><span data-stu-id="48223-306">Lync Mac 2011</span></span>  <br/> |<span data-ttu-id="48223-307">可以添加（无搜索）</span><span class="sxs-lookup"><span data-stu-id="48223-307">Can add (no search)</span></span>  <br/> |<span data-ttu-id="48223-308">是</span><span class="sxs-lookup"><span data-stu-id="48223-308">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-309">Lync Desktop 2010</span><span class="sxs-lookup"><span data-stu-id="48223-309">Lync Desktop 2010</span></span>  <br/> |<span data-ttu-id="48223-310">可以添加（无搜索）</span><span class="sxs-lookup"><span data-stu-id="48223-310">Can add (no search)</span></span>  <br/> |<span data-ttu-id="48223-311">是</span><span class="sxs-lookup"><span data-stu-id="48223-311">Yes</span></span>  <br/> |
|<span data-ttu-id="48223-312">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="48223-312">Lync Phone Edition</span></span>  <br/> |<span data-ttu-id="48223-313">不适用</span><span class="sxs-lookup"><span data-stu-id="48223-313">N/A</span></span>  <br/> |<span data-ttu-id="48223-314">不适用</span><span class="sxs-lookup"><span data-stu-id="48223-314">N/A</span></span>  <br/> |
|<span data-ttu-id="48223-315">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="48223-315">Lync Attendant</span></span>  <br/> |<span data-ttu-id="48223-316">不适用</span><span class="sxs-lookup"><span data-stu-id="48223-316">N/A</span></span>  <br/> |<span data-ttu-id="48223-317">不适用</span><span class="sxs-lookup"><span data-stu-id="48223-317">N/A</span></span>  <br/> |
   

