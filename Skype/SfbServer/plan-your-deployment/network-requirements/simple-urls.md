---
title: Skype for Business 服务器中的简单 Url 的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在为 Skype for business 服务器实施 DNS 记录之前，请查看本主题中的简单 URL 注意事项。
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888471"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="2fb5c-103">Skype for Business 服务器中的简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="2fb5c-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="2fb5c-104">**摘要：** 在为 Skype for Business 服务器实施 DNS 记录之前，请查看本主题中的简单 URL 注意事项。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="2fb5c-105">简单的 Url 使你的用户加入会议更容易，并且让管理员可以更轻松地访问 Skype for Business 服务器管理工具。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="2fb5c-106">简单 Url 使用其自己的域，这些域必须与你定义的任何 SIP 域不匹配。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="2fb5c-107">Skype for Business 服务器支持以下三个简单的 Url： "开会"、"拨入" 和 "管理员"。您需要为 "满足" 和 "拨入" 设置简单的 Url，"管理员简单 URL" 是可选的。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="2fb5c-108">需要支持简单 Url 的域名系统（DNS）记录取决于你定义这些简单 Url 的方式，以及你是否希望支持简单 Url 的灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="2fb5c-109">简单的 URL 范围</span><span class="sxs-lookup"><span data-stu-id="2fb5c-109">Simple URL scope</span></span>

<span data-ttu-id="2fb5c-110">你可以将简单 Url 配置为具有全局范围，或者你可以为你的组织中的每个中心网站指定不同的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="2fb5c-111">如果同时指定了全局简单 url 和网站简单 URL，则网站简单 URL 优先。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="2fb5c-112">在大多数情况下，我们建议你仅在全局级别设置简单的 Url，以便用户的 "满足简单 URL" 从一个网站移动到另一个网站时不会更改。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="2fb5c-113">例外情况是需要对不同站点上的电话拨入用户使用不同电话号码的组织。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="2fb5c-114">请注意，如果在网站上将一个简单的 URL （如拨入式简单 URL）设置为网站级简单 URL，则还必须将该网站上的其他简单 Url 设置为网站级别。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="2fb5c-115">可以在拓扑生成器中设置全局简单的 Url。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="2fb5c-116">若要在网站级别设置简单的 URL，请使用 CsSimpleURLConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="2fb5c-117">定义简单的 URL 还需要在 DNS 配置中设置 A 和/或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="2fb5c-118">简单的 URL 命名和验证规则</span><span class="sxs-lookup"><span data-stu-id="2fb5c-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="2fb5c-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="2fb5c-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="2fb5c-120">拓扑生成器和 Skype for Business Server Management Shell cmdlet 针对你的简单 Url 强制执行几条验证规则。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="2fb5c-121">您需要为 "满足" 和 "拨入" 设置简单的 Url，但为 "管理员" 设置一个是可选的。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="2fb5c-122">每个 SIP 域都必须具有单独的 "匹配" 的 "匹配" 简单 URL，但对于整个组织，只需一个拨入简单的 url 和一个管理员简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="2fb5c-123">组织中的每个简单 URL 都必须具有唯一的名称，并且不能是另一个简单 URL 的前缀（例如，不能将 SfB2015.contoso.com/Meet 设置为您的 "满足简单 url" 和 "SfB2015.contoso.com/Meet/Dialin" 作为拨入简单 URL）。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="2fb5c-124">简单的 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息（例如https://FQDN:88/meet ，不允许）。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="2fb5c-125">所有简单的 Url 必须以 https://前缀开头。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="2fb5c-126">简单 Url 只能包含字母数字字符（即 a-z、a-z、0-9 和句号（.）。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="2fb5c-127">如果使用其他字符，则简单 Url 可能不会按预期工作。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-127">If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="2fb5c-128">在部署后更改简单的 Url</span><span class="sxs-lookup"><span data-stu-id="2fb5c-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="2fb5c-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="2fb5c-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="2fb5c-130">如果你在初始部署后更改简单的 URL，你必须知道更改对简单 Url 的 DNS 记录和证书有何影响。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="2fb5c-131">如果简单 URL 的基础发生更改，则您还必须更改 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="2fb5c-132">例如，从https://SfB2015.contoso.com/Meet https://meet.contoso.com SfB2015.contoso.com 更改为 meet.contoso.com 的基本 URL，因此你需要更改 DNS 记录和证书才能引用 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="2fb5c-133">如果将简单 URL 更改https://SfB2015.contoso.com/Meet为 "与https://SfB2015.contoso.com/Meetings"，SfB2015.contoso.com 的基 url 保持不变，因此不需要任何 DNS 或证书更改。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="2fb5c-134">但是，当您更改简单的 URL 名称时，必须在每个 Director 和前端服务器上运行**Enable-CsComputer**以注册更改。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="2fb5c-135">简单 Url 的命名示例</span><span class="sxs-lookup"><span data-stu-id="2fb5c-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="2fb5c-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="2fb5c-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="2fb5c-137">有三个推荐选项可用于命名简单 Url。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-137">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="2fb5c-138">选择哪个选项对您设置 DNS A 记录和支持简单 Url 的证书有何影响。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-138">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="2fb5c-139">在每个选项中，必须为组织中的每个 SIP 域配置一个 "满足简单 URL"。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-139">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="2fb5c-140">你始终只需要在整个组织中使用一个简单的 URL 进行拨入，一个用于管理，无论你拥有多少个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="2fb5c-141">在选项1中，为每个简单的 URL 创建一个新的 SIP 域名。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="2fb5c-142">如果使用此选项，则每个简单 URL 都需要一个单独的 DNS A 记录，并且每个 "满足简单 URL" 都必须在证书中命名。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="2fb5c-143">**简单的 URL 命名选项1**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="2fb5c-144">**简单的 URL**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="2fb5c-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2fb5c-146">会议</span><span class="sxs-lookup"><span data-stu-id="2fb5c-146">Meet</span></span>  <br/>          | <span data-ttu-id="2fb5c-147">https://meet.contoso.com， https://meet.fabrikam.com等等（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="2fb5c-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="2fb5c-148">拨入</span><span class="sxs-lookup"><span data-stu-id="2fb5c-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="2fb5c-149">Iis</span><span class="sxs-lookup"><span data-stu-id="2fb5c-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="2fb5c-150">通过选项2，简单 Url 基于域名 SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="2fb5c-151">因此，只需一个 DNS A 记录即可启用所有三种类型的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="2fb5c-152">此 DNS A 记录引用 SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="2fb5c-153">此外，你的组织中的其他 SIP 域仍需要单独的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="2fb5c-154">**简单的 URL 命名选项2**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="2fb5c-155">**简单的 URL**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="2fb5c-156">**示例**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2fb5c-157">会议</span><span class="sxs-lookup"><span data-stu-id="2fb5c-157">Meet</span></span>  <br/>          | <span data-ttu-id="2fb5c-158">https://SfB2015.contoso.com/Meet， https://SfB2015.fabrikam.com/Meet等等（组织中的每个 SIP 域一个）</span><span class="sxs-lookup"><span data-stu-id="2fb5c-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="2fb5c-159">拨入</span><span class="sxs-lookup"><span data-stu-id="2fb5c-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="2fb5c-160">Iis</span><span class="sxs-lookup"><span data-stu-id="2fb5c-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="2fb5c-161">如果你有多个 SIP 域，而你希望它们具有单独的符合简单的 Url，但希望尽量减少这些简单 Url 的 DNS 记录和证书要求，则选项3非常有用。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="2fb5c-162">**简单的 URL 命名选项3**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="2fb5c-163">**简单的 URL**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="2fb5c-164">**示例**</span><span class="sxs-lookup"><span data-stu-id="2fb5c-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2fb5c-165">会议</span><span class="sxs-lookup"><span data-stu-id="2fb5c-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="2fb5c-166">拨入</span><span class="sxs-lookup"><span data-stu-id="2fb5c-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="2fb5c-167">Iis</span><span class="sxs-lookup"><span data-stu-id="2fb5c-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="2fb5c-168">简单 Url 的灾难恢复选项</span><span class="sxs-lookup"><span data-stu-id="2fb5c-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="2fb5c-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="2fb5c-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="2fb5c-170">如果你有多个包含前端池的网站，并且 DNS 提供程序支持 GeoDNS，你可以为简单的 Url 设置 DNS 记录以支持灾难恢复，以便即使一个完整的前端池停止运行，简单的 URL 功能也会继续。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="2fb5c-171">此灾难恢复功能支持 "开会" 和 "拨入" 简单 Url。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="2fb5c-172">若要配置此设置，请创建两个 GeoDNS 地址。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-172">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="2fb5c-173">每个地址都有两个 DNS A 或 CNAME 记录，它们可解析为两个池，这些记录结合在一起以供灾难恢复之用。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-173">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="2fb5c-174">一个 GeoDNS 地址用于内部访问，并解析为两个池的内部 web FQDN 或负载平衡器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-174">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="2fb5c-175">其他 GeoDNS 地址用于外部访问，并解析为两个池的外部 web FQDN 或负载平衡器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-175">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="2fb5c-176">下面是使用池的 Fqdn 的 "满足简单 URL" 的示例。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-176">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

<span data-ttu-id="2fb5c-177">然后，创建将您的 "满足简单 URL" （如 meet.contoso.com）解析为两个 GeoDNS 地址的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="2fb5c-178">如果你的网络使用 hairpinning （通过外部链接路由所有简单的 URL 流量，包括来自组织内部的流量），则只需配置外部 GeoDNS 地址并将你的 "仅限" 简单 URL 解析为仅外部地址。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="2fb5c-179">使用此方法时，你可以将每个 GeoDNS 地址配置为使用循环复用方法将请求分配到两个池，或主要连接到一个池（如位于地理位置较近的池），并使用另一个池（仅限情况连接失败。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="2fb5c-180">你可以为拨入式简单 URL 设置相同配置。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="2fb5c-181">若要执行此操作，请创建如前面的示例中所示`dialin`的`meet`其他记录，并在 DNS 记录中替换。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="2fb5c-182">对于 "管理员简单 URL"，请使用本节前面列出的三个选项之一。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="2fb5c-183">设置此配置后，必须使用监视应用程序设置 HTTP 监视以监视失败。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="2fb5c-184">对于外部访问，请进行监视以确保 HTTPS 获取 lyncdiscover。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="2fb5c-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="2fb5c-185">对两个池的外部 web FQDN 或负载平衡器 IP 地址的请求成功。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="2fb5c-186">例如，以下请求不得包含任何**ACCEPT**标头，并且必须返回**200 OK**。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="2fb5c-187">对于内部访问，你必须在两个池的内部 web FQDN 或负载平衡器 IP 地址上监视端口5061。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="2fb5c-188">如果检测到任何连接失败，这些池的 VIP 必须关闭端口80、443和4443。</span><span class="sxs-lookup"><span data-stu-id="2fb5c-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


