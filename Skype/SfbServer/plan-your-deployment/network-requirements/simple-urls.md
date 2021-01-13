---
title: Skype for Business Server 中简单 URL 的 DNS 要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要：在实施 Skype for Business Server 的 DNS 记录之前，请查看本主题中的简单 URL 注意事项。
ms.openlocfilehash: d1c4213e1fe28c6f42cd4fa14f48bc8ce9b7bdf1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834582"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="806c7-103">Skype for Business Server 中简单 URL 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="806c7-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="806c7-104">**摘要：** 在实施 Skype for Business Server 的 DNS 记录之前，请查看本主题中的简单 URL 注意事项。</span><span class="sxs-lookup"><span data-stu-id="806c7-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="806c7-105">简单 URL 使用户更容易加入会议，并且使管理员能够更轻松地访问 Skype for Business Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="806c7-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="806c7-106">简单 URL 使用自己的域，该域不能与定义的任何 SIP 域匹配。</span><span class="sxs-lookup"><span data-stu-id="806c7-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="806c7-107">Skype for Business Server 支持以下三个简单的 URL：会议、拨入和管理。需要为会议 URL 和拨入设置简单 URL，管理简单 URL 是可选的。</span><span class="sxs-lookup"><span data-stu-id="806c7-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="806c7-108">支持简单 URL 所需的域名系统 (DNS) 记录取决于定义这些简单 URL 的方式以及是否要对简单 URL 支持灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="806c7-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="806c7-109">简单 URL 范围</span><span class="sxs-lookup"><span data-stu-id="806c7-109">Simple URL scope</span></span>

<span data-ttu-id="806c7-p103">可以将简单 URL 配置为具有 global 作用域，也可以为组织中的每个中央站点指定不同的简单 URL。如果同时指定全局简单 URL 和站点简单 URL，则站点简单 URL 具有优先权。</span><span class="sxs-lookup"><span data-stu-id="806c7-p103">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization. If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="806c7-112">在大多数情况下，我们建议您仅在全局级别设置简单 URL，以便用户的会议简单 URL 在从一个网站移动到另一个网站时不会更改。</span><span class="sxs-lookup"><span data-stu-id="806c7-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="806c7-113">例外情况是对于不同站点的拨入用户需要使用不同电话号码的组织。</span><span class="sxs-lookup"><span data-stu-id="806c7-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="806c7-114">请注意，如果要将某个站点上的一个简单 URL（如拨入简单 URL）设置为站点级别的简单 URL，您还必须将该站点上的其他简单 URL 设置为站点级别。</span><span class="sxs-lookup"><span data-stu-id="806c7-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="806c7-115">可以在拓扑生成器中设置全局简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="806c7-116">若要在网站级别设置简单 URL，请使用 Set-CsSimpleURLConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="806c7-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="806c7-117">定义简单 URL 还需要在 DNS 配置中设置 A 和/或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="806c7-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="806c7-118">简单 URL 命名和验证规则</span><span class="sxs-lookup"><span data-stu-id="806c7-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="806c7-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="806c7-119"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="806c7-120">拓扑生成器和 Skype for Business Server 命令行管理程序 cmdlet 对简单 URL 强制执行多个验证规则。</span><span class="sxs-lookup"><span data-stu-id="806c7-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="806c7-121">您必须设置会议简单 URL 和拨入简单 URL，但可以选择设置管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="806c7-122">每个 SIP 域都必须具有单独的会议简单 URL，但整个组织只需要一个拨入简单 URL 和一个管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="806c7-123">组织的每个简单 URL 必须具有唯一的名称，并且不能是另一个简单 URL (例如，您不能将 SfB2015.contoso.com/Meet 设置为会议简单 URL，将 SfB2015.contoso.com/Meet/Dialin 设置为 Dialin 简单 URL) 。</span><span class="sxs-lookup"><span data-stu-id="806c7-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="806c7-124">简单 URL 名称不能包含任何池的 FQDN，也不能包含任何端口信息 (例如，不允许任何端口 https://FQDN:88/meet) 。</span><span class="sxs-lookup"><span data-stu-id="806c7-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="806c7-125">所有简单 URL 都必须以 https:// 前缀开头。</span><span class="sxs-lookup"><span data-stu-id="806c7-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="806c7-p108">简单 URL 只能包含字母数字字符（即，a-z、A-Z、0-9 和圆点 (.)）。如果使用其他字符，则简单 URL 可能不会正常工作。</span><span class="sxs-lookup"><span data-stu-id="806c7-p108">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="806c7-128">在部署后更改简单 URL</span><span class="sxs-lookup"><span data-stu-id="806c7-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="806c7-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="806c7-129"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="806c7-130">如果在初始部署后更改简单 URL，您必须注意更改如何影响简单 URL 的 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="806c7-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="806c7-131">如果简单 URL 的基础发生更改，则还必须更改 DNS 记录和证书。</span><span class="sxs-lookup"><span data-stu-id="806c7-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="806c7-132">例如，从更改为将基 URL 从 SfB2015.contoso.com 更改为 meet.contoso.com，因此您需要更改 DNS 记录和证书以引用 https://SfB2015.contoso.com/Meet https://meet.contoso.com meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="806c7-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="806c7-133">如果将简单 URL 从更改为 ，则 SfB2015.contoso.com URL 保持不变，因此不需要 https://SfB2015.contoso.com/Meet https://SfB2015.contoso.com/Meetings 更改 DNS 或证书。</span><span class="sxs-lookup"><span data-stu-id="806c7-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="806c7-134">但是，只要更改简单 URL 名称，就必须在每个控制器和前端服务器上运行 **Enable-CsComputer** 以注册更改。</span><span class="sxs-lookup"><span data-stu-id="806c7-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="806c7-135">简单 URL 的命名示例</span><span class="sxs-lookup"><span data-stu-id="806c7-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="806c7-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="806c7-136"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="806c7-p110">有三种推荐的选项可用于命名简单 URL。您选择的选项会暗示设置支持简单 URL 的 DNS A 记录和证书的方式。在每个选项中，您必须为组织中的每个 SIP 域配置一个会议简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-p110">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="806c7-140">无论具有多少个 SIP 域，整个组织始终只需要一个拨入简单 URL 和一个管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="806c7-141">在选项 1 中，为每个简单 URL 创建新的 SIP 域名。</span><span class="sxs-lookup"><span data-stu-id="806c7-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="806c7-142">如果使用此选项，则需要为每个简单 URL 配置单独的 DNS A 记录，而且必须在证书中命名每个会议简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="806c7-143">**简单 URL 命名选项 1**</span><span class="sxs-lookup"><span data-stu-id="806c7-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="806c7-144">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="806c7-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="806c7-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="806c7-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="806c7-146">Meet</span><span class="sxs-lookup"><span data-stu-id="806c7-146">Meet</span></span>  <br/>          | <span data-ttu-id="806c7-147">https://meet.contoso.com，，等等 (组织中每个 SIP 域创建一个 https://meet.fabrikam.com) </span><span class="sxs-lookup"><span data-stu-id="806c7-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="806c7-148">拨入</span><span class="sxs-lookup"><span data-stu-id="806c7-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="806c7-149">管理员</span><span class="sxs-lookup"><span data-stu-id="806c7-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="806c7-150">在选项 2 中，简单 URL 基于域名SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="806c7-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="806c7-151">因此，只需一个可启用全部三种类型简单 URL 的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="806c7-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="806c7-152">此 DNS A 记录引用SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="806c7-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="806c7-153">此外，仍需要为组织中的其他 SIP 域配置单独的 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="806c7-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="806c7-154">**简单 URL 命名选项 2**</span><span class="sxs-lookup"><span data-stu-id="806c7-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="806c7-155">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="806c7-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="806c7-156">**示例**</span><span class="sxs-lookup"><span data-stu-id="806c7-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="806c7-157">Meet</span><span class="sxs-lookup"><span data-stu-id="806c7-157">Meet</span></span>  <br/>          | <span data-ttu-id="806c7-158">https://SfB2015.contoso.com/Meet，，等等 (组织中每个 SIP 域创建一个 https://SfB2015.fabrikam.com/Meet) </span><span class="sxs-lookup"><span data-stu-id="806c7-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="806c7-159">拨入</span><span class="sxs-lookup"><span data-stu-id="806c7-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="806c7-160">管理员</span><span class="sxs-lookup"><span data-stu-id="806c7-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="806c7-161">如果具有许多 SIP 域，并且希望每个 SIP 域具有单独的会议简单 URL，但希望最大程度地减少这些简单 URL 所要求的 DNS 记录和证书，则选项 3 是最有用的。</span><span class="sxs-lookup"><span data-stu-id="806c7-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="806c7-162">**简单 URL 命名选项 3**</span><span class="sxs-lookup"><span data-stu-id="806c7-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="806c7-163">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="806c7-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="806c7-164">**示例**</span><span class="sxs-lookup"><span data-stu-id="806c7-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="806c7-165">Meet</span><span class="sxs-lookup"><span data-stu-id="806c7-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="806c7-166">拨入</span><span class="sxs-lookup"><span data-stu-id="806c7-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="806c7-167">管理员</span><span class="sxs-lookup"><span data-stu-id="806c7-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="806c7-168">简单 URL 的灾难恢复选项</span><span class="sxs-lookup"><span data-stu-id="806c7-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="806c7-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="806c7-169"><a name="BK_Valid"> </a></span></span>

<span data-ttu-id="806c7-170">如果有多个站点包含前端池，并且 DNS 提供程序支持 GeoDNS，您可以为简单 URL 设置 DNS 记录以支持灾难恢复，以便即使整个前端池关闭，简单 URL 功能也将继续运行。</span><span class="sxs-lookup"><span data-stu-id="806c7-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="806c7-171">此灾难恢复功能支持“会议”和“拨入”简单 URL。</span><span class="sxs-lookup"><span data-stu-id="806c7-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="806c7-p113">若要进行此配置，请创建两个 GeoDNS 地址。每个地址具有两个 DNS A 或 CNAME 记录，这些记录解析到出于灾难恢复目的配对在一起的两个池。一个 GeoDNS 地址用于内部访问，并解析到两个池的内部 Web FQDN 或负载平衡器 IP 地址。另一个 GeoDNS 地址用于外部访问，并解析到两个池的外部 Web FQDN 或负载平衡器 IP 地址。下面是使用池的 FQDN 的“会议”简单 URL 的示例。</span><span class="sxs-lookup"><span data-stu-id="806c7-p113">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

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

<span data-ttu-id="806c7-177">然后，创建将“会议”简单 URL（如 meet.contoso.com）解析到两个 GeoDNS 地址的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="806c7-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="806c7-178">如果您的网络使用发夹（通过外部链接路由所有简单 URL 通信，包括来自您组织内部的通信），您可以只配置外部 GeoDNS 地址并将“会议”简单 URL 仅解析到该外部地址。</span><span class="sxs-lookup"><span data-stu-id="806c7-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="806c7-179">使用此方法时，您可以将每个 GeoDNS 地址配置为使用循环方法向两个池分发请求，或主要连接到一个池（如地理位置上接近的池）并仅在连接失败的情况下使用另一个池。</span><span class="sxs-lookup"><span data-stu-id="806c7-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="806c7-180">您可以对“拨入”简单 URL 设置相同的配置。</span><span class="sxs-lookup"><span data-stu-id="806c7-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="806c7-181">为此，请创建与上一示例中类似的其他记录，以在 DNS 记录  `dialin` `meet` 中代之以。</span><span class="sxs-lookup"><span data-stu-id="806c7-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="806c7-182">对于“管理”简单 URL，请使用本节前面所列的三个选项之一。</span><span class="sxs-lookup"><span data-stu-id="806c7-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="806c7-183">设置完此配置后，您必须使用监控应用程序来设置 HTTP 监控以留意故障。</span><span class="sxs-lookup"><span data-stu-id="806c7-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="806c7-184">对于外部访问，监视以确保 HTTPS GET lyncdiscover。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="806c7-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="806c7-185">对两个池的外部 Web FQDN 或负载平衡器 IP 地址的请求成功。</span><span class="sxs-lookup"><span data-stu-id="806c7-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="806c7-186">例如，以下请求不得包含任何 **ACCEPT** 标头且必须返回 **200 OK**。</span><span class="sxs-lookup"><span data-stu-id="806c7-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="806c7-187">对于内部访问，您必须监控两个池的内部 Web FQDN 或负载平衡器 IP 地址上的端口 5061。</span><span class="sxs-lookup"><span data-stu-id="806c7-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="806c7-188">如果检测到任何连接故障，则这些池的 VIP 必须关闭端口 80、443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="806c7-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


