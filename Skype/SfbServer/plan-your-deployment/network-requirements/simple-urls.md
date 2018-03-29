---
title: 在 Skype 的简单 Url 的业务服务器 2015年的 DNS 要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要： 为 Skype 的 DNS 记录实施的业务服务器 2015年前查看本主题中的简单的 URL 注意事项。
ms.openlocfilehash: 989ea4f518c1917311759158bbe29355f400138b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server-2015"></a><span data-ttu-id="f0c0f-103">在 Skype 的简单 Url 的业务服务器 2015年的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="f0c0f-103">DNS requirements for simple URLs in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f0c0f-104">**摘要：**实现业务服务器 2015 DNS 记录为 Skype 之前，请查看本主题中的简单的 URL 注意事项。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f0c0f-105">简单的 Url 让您的用户更方便地加入会议，并使您能够获取到 Skype 业务服务器管理工具更容易为管理员。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="f0c0f-106">简单的 Url 使用自己不匹配任何您定义的 SIP 域的域。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 
  
<span data-ttu-id="f0c0f-107">Skype 业务服务器支持以下三个简单的 Url： 满足，拨入和管理员。需要的满足和拨入设置简单的 Url 和管理简单的 URL 是可选的。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="f0c0f-108">支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 
  
## <a name="simple-url-scope"></a><span data-ttu-id="f0c0f-109">简单的 URL 范围</span><span class="sxs-lookup"><span data-stu-id="f0c0f-109">Simple URL scope</span></span>

<span data-ttu-id="f0c0f-110">您可以配置您简单的 Url 具有全局作用域，或您的组织中可以指定为每个中心站点的不同简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="f0c0f-111">指定全局简单的 URL 和网站简单的 URL，如果网站简单 URL 具有优先权。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 
  
<span data-ttu-id="f0c0f-112">在大多数情况下，建议，这样如果他们从一个站点移动到另一个用户的满足简单的 URL 不会更改您只能在全球范围内，设置简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="f0c0f-113">异常将需要为在不同站点中的拨入用户使用不同电话号码的组织。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="f0c0f-114">请注意，如果您在站点级简单的 URL 设置为设置一个简单的 URL （如拨入简单 URL 中)，您还必须在该站点也是站点级设置其他简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>
  
<span data-ttu-id="f0c0f-115">在拓扑生成器，您可以设置全局简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="f0c0f-116">若要在站点级别设置简单的 URL，请使用组 CsSimpleURLConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>
  
<span data-ttu-id="f0c0f-117">定义简单的 URL 也需要在您的 DNS 配置设置的 A 和/或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>
  
## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="f0c0f-118">简单的 URL 命名和验证规则</span><span class="sxs-lookup"><span data-stu-id="f0c0f-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="f0c0f-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f0c0f-119"></span></span>

<span data-ttu-id="f0c0f-120">拓扑生成器和业务服务器管理外壳 cmdlet 的 Skype 实施几个有效性规则为您简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="f0c0f-121">您需要简单的 Url 和设置的满足拨入，但是设置一个用于管理是可选的。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="f0c0f-122">每个 SIP 域必须单独满足简单的 URL，但您需要为您的整个组织只有一个拨入简单的 URL 和一个管理简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>
  
<span data-ttu-id="f0c0f-123">您的组织中每个简单的 URL 必须具有唯一的名称，而不能是另一个简单的 URL 前缀 （例如，您无法设置作为您满足简单的 URL 的 SfB2015.contoso.com/Meet 和 SfB2015.contoso.com/Meet/Dialin 为您拨入简单的 URL）。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="f0c0f-124">简单的 URL 名称不能包含任何您的池，或任何端口信息的 FQDN (例如，https://FQDN:88/meet不允许)。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="f0c0f-125">所有简单的 Url 必须以 https:// 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-125">All simple URLs must start with the https:// prefix.</span></span> 
  
<span data-ttu-id="f0c0f-126">简单的 Url 只能包含字母数字字符 （a-z、 A-Z、 0-9 和句点 （.）。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="f0c0f-127">如果您使用其他字符，简单的 Url 可能无法按预期的方式。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-127">If you use other characters, the simple URLs might not work as expected.</span></span>
  
## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="f0c0f-128">在部署后更改简单的 Url</span><span class="sxs-lookup"><span data-stu-id="f0c0f-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="f0c0f-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f0c0f-129"></span></span>

<span data-ttu-id="f0c0f-130">如果您在初始部署后更改简单的 URL，您必须了解如何更改会影响您的 DNS 记录和证书的简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="f0c0f-131">然后简单的 URL 的更改时，如果必须更改 DNS 记录和证书也。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="f0c0f-132">例如，从更改https://SfB2015.contoso.com/Meet到https://meet.contoso.com从 SfB2015.contoso.com 到 meet.contoso.com，更改的基 URL，因此需要更改 DNS 记录和证书请参阅 meet.contoso.com。如果您更改了从简单的 URLhttps://SfB2015.contoso.com/Meet到https://SfB2015.contoso.com/Meetings、 基 URL 的 SfB2015.contoso.com 保持不变，因而没有 DNS 或需要证书更改。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com. If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>
  
<span data-ttu-id="f0c0f-133">无论何时更改一个简单的 URL 名称，但是，必须注册该更改每个控制器和前端服务器上运行**启用 CsComputer** 。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-133">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>
  
## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="f0c0f-134">对于简单的 Url 命名示例</span><span class="sxs-lookup"><span data-stu-id="f0c0f-134">Naming examples for Simple URLs</span></span>
<span data-ttu-id="f0c0f-135"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f0c0f-135"></span></span>

<span data-ttu-id="f0c0f-136">有三种建议的方法来命名自己简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-136">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="f0c0f-137">选择哪个选项有含义如何设置您的 DNS A 记录和证书支持简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-137">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="f0c0f-138">在每个选项，必须在组织中配置一个满足简单的 URL 的每个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-138">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 
  
<span data-ttu-id="f0c0f-139">在您的整个组织的拨入和一个用于管理，不管有多少个 SIP 域始终需要只是一个简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-139">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>
  
<span data-ttu-id="f0c0f-140">选项 1，则在您创建新的 SIP 域名称对于每个简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-140">In Option 1, you create a new SIP domain name for each simple URL.</span></span>
  
<span data-ttu-id="f0c0f-141">如果使用此选项时，您需要单独的 DNS A 记录，每个简单的 URL 和每个满足简单的 URL 必须命名您的证书中。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-141">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>
  
<span data-ttu-id="f0c0f-142">**简单的 URL 命名选项 1**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-142">**Simple URL Naming Option 1**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0c0f-143">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-143">**Simple URL**</span></span> <br/> |<span data-ttu-id="f0c0f-144">**示例**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-144">**Example**</span></span> <br/> |
|<span data-ttu-id="f0c0f-145">会议</span><span class="sxs-lookup"><span data-stu-id="f0c0f-145">Meet</span></span>  <br/> |<span data-ttu-id="f0c0f-146">https://meet.contoso.comhttps://meet.fabrikam.com，依此类推 （一个用于您的组织中的每个 SIP 域）</span><span class="sxs-lookup"><span data-stu-id="f0c0f-146">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
|<span data-ttu-id="f0c0f-147">拨入</span><span class="sxs-lookup"><span data-stu-id="f0c0f-147">Dial-in</span></span>  <br/> |https://dialin.contoso.com  <br/> |
|<span data-ttu-id="f0c0f-148">管理员</span><span class="sxs-lookup"><span data-stu-id="f0c0f-148">Admin</span></span>  <br/> |https://admin.contoso.com  <br/> |
   
<span data-ttu-id="f0c0f-149">使用选项 2，简单的 Url 基于 SfB2015.contoso.com 的域名称。因此，您需要只有一个 DNS A 记录，它使所有三种类型的简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-149">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="f0c0f-150">此 DNS A 记录引用 SfB2015.contoso.com。此外，您仍然需要单独的 DNS A 记录其他 SIP 域的组织中。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-150">This DNS A record references SfB2015.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 
  
<span data-ttu-id="f0c0f-151">**简单的 URL 命名选项 2**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-151">**Simple URL Naming Option 2**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0c0f-152">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-152">**Simple URL**</span></span> <br/> |<span data-ttu-id="f0c0f-153">**示例**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-153">**Example**</span></span> <br/> |
|<span data-ttu-id="f0c0f-154">会议</span><span class="sxs-lookup"><span data-stu-id="f0c0f-154">Meet</span></span>  <br/> |<span data-ttu-id="f0c0f-155">https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet，依此类推 （一个用于您的组织中的每个 SIP 域）</span><span class="sxs-lookup"><span data-stu-id="f0c0f-155">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
|<span data-ttu-id="f0c0f-156">拨入</span><span class="sxs-lookup"><span data-stu-id="f0c0f-156">Dial-in</span></span>  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|<span data-ttu-id="f0c0f-157">管理员</span><span class="sxs-lookup"><span data-stu-id="f0c0f-157">Admin</span></span>  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
<span data-ttu-id="f0c0f-158">选项 3 是最有用的如果您有多个 SIP 域，并且您希望它们有单独满足简单的 Url，但想要最小化这些简单的 Url 的 DNS 记录和证书要求。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-158">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 
  
<span data-ttu-id="f0c0f-159">**简单的 URL 命名选项 3**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-159">**Simple URL Naming Option 3**</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0c0f-160">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-160">**Simple URL**</span></span> <br/> |<span data-ttu-id="f0c0f-161">**示例**</span><span class="sxs-lookup"><span data-stu-id="f0c0f-161">**Example**</span></span> <br/> |
|<span data-ttu-id="f0c0f-162">会议</span><span class="sxs-lookup"><span data-stu-id="f0c0f-162">Meet</span></span>  <br/> |https://SfB2015.contoso.com/contosoSIPdomain/Meet  <br/> https://SfB2015.contoso.com/fabrikamSIPdomain/Meet  <br/> |
|<span data-ttu-id="f0c0f-163">拨入</span><span class="sxs-lookup"><span data-stu-id="f0c0f-163">Dial-in</span></span>  <br/> |https://SfB2015.contoso.com/Dialin  <br/> |
|<span data-ttu-id="f0c0f-164">管理员</span><span class="sxs-lookup"><span data-stu-id="f0c0f-164">Admin</span></span>  <br/> |https://SfB2015.contoso.com/Admin  <br/> |
   
## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="f0c0f-165">简单的 Url 的灾难恢复选项</span><span class="sxs-lookup"><span data-stu-id="f0c0f-165">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="f0c0f-166"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="f0c0f-166"></span></span>

<span data-ttu-id="f0c0f-167">如果您有包含前端池的多个站点，并且 DNS 提供程序支持 GeoDNS，您可以设置您的 DNS 记录的简单的 Url 来支持灾难恢复，，这样简单的 URL 功能仍然存在，即使一个整个前端池出现故障。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-167">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="f0c0f-168">此灾难恢复功能支持“会议”和“拨入”简单 URL。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-168">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>
  
<span data-ttu-id="f0c0f-p113">若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-p113">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 
  
```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

<span data-ttu-id="f0c0f-174">然后，创建将“会议”简单 URL（如 meet.contoso.com）解析到两个 GeoDNS 地址的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-174">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f0c0f-175">如果您的网络使用 hairpinning （路由通过外部链接，其中包括来自组织内部的通信的所有简单的 URL 通信），然后只需配置外部的 GeoDNS 地址并解决您满足简单的 URL，仅外部地址。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-175">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>
  
<span data-ttu-id="f0c0f-176">使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-176">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 
  
<span data-ttu-id="f0c0f-177">您可以对“拨入”简单 URL 设置相同的配置。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-177">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="f0c0f-178">若要执行此操作，创建类似于前面的示例中的其他记录替换`dialin`的`meet`中的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-178">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="f0c0f-179">对于“管理”简单 URL，请使用本节前面所列的三个选项之一。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-179">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>
  
<span data-ttu-id="f0c0f-180">设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-180">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="f0c0f-181">对于外部访问，监视，以确保该 HTTPS 得到 lyncdiscover。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="f0c0f-181">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="f0c0f-182">到外部站点的两个池的 FQDN 或负载平衡器 IP 地址的请求才会成功。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-182">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="f0c0f-183">例如，以下请求不能包含任何**ACCEPT**标头，并且必须返回**200 确定**。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-183">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>
  
```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="f0c0f-p116">对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。如果检测到任何连接失败，这些池的 VIP 必须关闭端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="f0c0f-p116">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>
  

