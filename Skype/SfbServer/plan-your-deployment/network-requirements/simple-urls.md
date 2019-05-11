---
title: Skype 中的简单 url 的业务服务器的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 摘要： DNS 记录的 Skype 实现业务服务器之前查看本主题中的简单 URL 注意事项。
ms.openlocfilehash: 6e62190f19969e635690a68ead4f2c96a32a27c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920234"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a><span data-ttu-id="37967-103">Skype 中的简单 url 的业务服务器的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="37967-103">DNS requirements for simple URLs in Skype for Business Server</span></span>

<span data-ttu-id="37967-104">**摘要：** DNS 记录的 Skype 实现业务服务器之前查看本主题中的简单 URL 注意事项。</span><span class="sxs-lookup"><span data-stu-id="37967-104">**Summary:** Review the Simple URL considerations in this topic before implementing DNS records for Skype for Business Server.</span></span>

<span data-ttu-id="37967-105">简单 Url 使您的用户更易于加入会议，又便于到 Skype 业务 Server 管理工具的管理员。</span><span class="sxs-lookup"><span data-stu-id="37967-105">Simple URLs make joining meetings easier for your users, and make getting to Skype for Business Server administrative tools easier for administrators.</span></span> <span data-ttu-id="37967-106">简单 Url 使用自己的域，该域不匹配任何您定义的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="37967-106">Simple URLs use their own domain, which must not match any of the SIP domains you define.</span></span> 

<span data-ttu-id="37967-107">Skype 业务 server 支持以下三种简单 Url： 满足，电话拨入式，和管理员。您需要设置为开会会议和电话拨入简单 Url 也是可选的管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="37967-107">Skype for Business Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="37967-108">支持简单 Url 所需的域名系统 (DNS) 记录取决于您如何定义这些简单 Url，以及是否希望以支持的简单 Url 的灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="37967-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span> 

## <a name="simple-url-scope"></a><span data-ttu-id="37967-109">简单 URL 作用域</span><span class="sxs-lookup"><span data-stu-id="37967-109">Simple URL scope</span></span>

<span data-ttu-id="37967-110">您可以配置简单 Url 具有全局范围，或者您可以在组织中指定不同的简单 Url 的每个中央站点。</span><span class="sxs-lookup"><span data-stu-id="37967-110">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="37967-111">如果指定全局简单 URL 和网站的简单 URL，该网站的简单 URL 优先级。</span><span class="sxs-lookup"><span data-stu-id="37967-111">If both a global simple URL and a site simple URL are specified, the site simple URL has precedence.</span></span> 

<span data-ttu-id="37967-112">在大多数情况下，我们建议将简单 Url 设置仅在全局级别，以便如果他们从一个网站移动到另一个用户的会议简单 URL 不会更改。</span><span class="sxs-lookup"><span data-stu-id="37967-112">In most cases, we recommend that you set simple URLs only at the global level, so that a user's Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="37967-113">异常采用不同的电话号码用于电话拨入式用户在不同的站点所需要的组织。</span><span class="sxs-lookup"><span data-stu-id="37967-113">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="37967-114">请注意，是否在网站级别的简单 URL 网站设置一个简单 URL （如的电话拨入式简单 URL)，还必须设置其他简单 Url 以及为网站级别的站点。</span><span class="sxs-lookup"><span data-stu-id="37967-114">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<span data-ttu-id="37967-115">在拓扑生成器中，您可以设置全局简单 Url。</span><span class="sxs-lookup"><span data-stu-id="37967-115">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="37967-116">要在网站级别设置的简单 URL，请使用集 CsSimpleURLConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="37967-116">To set a simple URL at the site level, use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

<span data-ttu-id="37967-117">定义简单 URL 还将需要在您的 DNS 配置设置的 A 和/或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="37967-117">Defining a simple URL will also require setting an A and/or AAAA record in your DNS configuration.</span></span>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="37967-118">简单 URL 命名和验证规则</span><span class="sxs-lookup"><span data-stu-id="37967-118">Simple URL naming and validation rules</span></span>
<span data-ttu-id="37967-119"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="37967-119"></span></span>

<span data-ttu-id="37967-120">拓扑生成器和业务 Server Management Shell cmdlet Skype 强制几个有效性规则的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="37967-120">Topology Builder and the Skype for Business Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="37967-121">您需要为 Meet 和 Dialin，设置简单 Url，但设置另一个用于管理是可选的。</span><span class="sxs-lookup"><span data-stu-id="37967-121">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="37967-122">每个 SIP 域必须单独的会议简单 URL，但您需要为整个组织只有一个 Dialin 简单 URL 和一个管理简单 URL。</span><span class="sxs-lookup"><span data-stu-id="37967-122">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="37967-123">您的组织中每个简单 URL 必须具有唯一名称，并且不能是另一个简单 URL 的前缀 （例如，您无法设置为会议的简单 URL 的 SfB2015.contoso.com/Meet 和 SfB2015.contoso.com/Meet/Dialin 为您的拨入简单 URL）。</span><span class="sxs-lookup"><span data-stu-id="37967-123">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set SfB2015.contoso.com/Meet as your Meet simple URL and SfB2015.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="37967-124">简单 URL 名称不能包含任何池，或任何端口信息的 FQDN (例如，https://FQDN:88/meet不允许)。</span><span class="sxs-lookup"><span data-stu-id="37967-124">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="37967-125">所有简单 Url 必须以前缀 https:// 开头。</span><span class="sxs-lookup"><span data-stu-id="37967-125">All simple URLs must start with the https:// prefix.</span></span> 

<span data-ttu-id="37967-126">简单 Url 只能包含字母数字字符 （即，a-z、 A-Z、 0-9 和句点 （.）。</span><span class="sxs-lookup"><span data-stu-id="37967-126">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="37967-127">如果您使用其他字符，简单 Url 可能未按预期。</span><span class="sxs-lookup"><span data-stu-id="37967-127">If you use other characters, the simple URLs might not work as expected.</span></span>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="37967-128">在部署后更改简单 Url</span><span class="sxs-lookup"><span data-stu-id="37967-128">Changing Simple URLs after deployment</span></span>
<span data-ttu-id="37967-129"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="37967-129"></span></span>

<span data-ttu-id="37967-130">如果在初始部署后更改简单 URL，您必须知道如何更改会影响您的 DNS 记录和证书的简单 Url。</span><span class="sxs-lookup"><span data-stu-id="37967-130">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="37967-131">如果简单 URL 的更改，则必须更改的 DNS 记录和证书以及。</span><span class="sxs-lookup"><span data-stu-id="37967-131">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="37967-132">例如，从更改https://SfB2015.contoso.com/Meet到https://meet.contoso.com的基 URL 从变为 SfB2015.contoso.com meet.contoso.com，因此需要更改 DNS 记录和证书来引用 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="37967-132">For example, changing from https://SfB2015.contoso.com/Meet to https://meet.contoso.com changes the base URL from SfB2015.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="37967-133">如果您已经更改中的简单 URLhttps://SfB2015.contoso.com/Meet到https://SfB2015.contoso.com/Meetings、 基 URL 的 SfB2015.contoso.com 保持不变，因此没有 DNS 或所需证书的更改。</span><span class="sxs-lookup"><span data-stu-id="37967-133">If you changed the simple URL from https://SfB2015.contoso.com/Meet to https://SfB2015.contoso.com/Meetings, the base URL of SfB2015.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="37967-134">无论何时更改简单 URL 名称，但是，必须以注册该更改每台控制器和前端服务器上运行**Enable-cscomputer** 。</span><span class="sxs-lookup"><span data-stu-id="37967-134">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

## <a name="naming-examples-for-simple-urls"></a><span data-ttu-id="37967-135">简单 url 命名示例</span><span class="sxs-lookup"><span data-stu-id="37967-135">Naming examples for Simple URLs</span></span>
<span data-ttu-id="37967-136"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="37967-136"></span></span>

<span data-ttu-id="37967-137">有三个命名简单 Url 的建议的选项。</span><span class="sxs-lookup"><span data-stu-id="37967-137">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="37967-138">选择哪个选项有如何设置您的 DNS A 记录和证书支持简单 Url 的影响。</span><span class="sxs-lookup"><span data-stu-id="37967-138">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="37967-139">在每个选项，必须在组织中配置一个会议的简单 URL，每个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="37967-139">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span> 

<span data-ttu-id="37967-140">始终需要只有一个简单 URL 中的电话拨入式，为整个组织和一个管理，无论您有多少个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="37967-140">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="37967-141">在选项 1 中，您将创建每个简单 URL 的新 SIP 域名。</span><span class="sxs-lookup"><span data-stu-id="37967-141">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="37967-142">如果使用此选项，则需要一个单独的 DNS A 记录，必须在证书中命名每个简单 URL 和每个会议简单 URL 的。</span><span class="sxs-lookup"><span data-stu-id="37967-142">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

<span data-ttu-id="37967-143">**简单 URL 命名选项 1**</span><span class="sxs-lookup"><span data-stu-id="37967-143">**Simple URL Naming Option 1**</span></span>


| <span data-ttu-id="37967-144">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="37967-144">**Simple URL**</span></span> <br/> | <span data-ttu-id="37967-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="37967-145">**Example**</span></span> <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="37967-146">满足</span><span class="sxs-lookup"><span data-stu-id="37967-146">Meet</span></span>  <br/>          | <span data-ttu-id="37967-147">https://meet.contoso.comhttps://meet.fabrikam.com，依此类推 （一个为组织中每个 SIP 域）</span><span class="sxs-lookup"><span data-stu-id="37967-147">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="37967-148">拨入</span><span class="sxs-lookup"><span data-stu-id="37967-148">Dial-in</span></span>  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| <span data-ttu-id="37967-149">管理</span><span class="sxs-lookup"><span data-stu-id="37967-149">Admin</span></span>  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

<span data-ttu-id="37967-150">选项 2 简单 Url 基于 SfB2015.contoso.com 的域名。</span><span class="sxs-lookup"><span data-stu-id="37967-150">With Option 2, simple URLs are based on the domain name SfB2015.contoso.com.</span></span> <span data-ttu-id="37967-151">因此，您需要使所有三种类型的简单 Url 只有一个 DNS A 记录。</span><span class="sxs-lookup"><span data-stu-id="37967-151">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="37967-152">此 DNS A 记录引用 SfB2015.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="37967-152">This DNS A record references SfB2015.contoso.com.</span></span> <span data-ttu-id="37967-153">此外，您仍需要单独的 DNS A 记录的其他 SIP 域中您的组织。</span><span class="sxs-lookup"><span data-stu-id="37967-153">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span> 

<span data-ttu-id="37967-154">**简单 URL 命名选项 2**</span><span class="sxs-lookup"><span data-stu-id="37967-154">**Simple URL Naming Option 2**</span></span>


| <span data-ttu-id="37967-155">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="37967-155">**Simple URL**</span></span> <br/> | <span data-ttu-id="37967-156">**示例**</span><span class="sxs-lookup"><span data-stu-id="37967-156">**Example**</span></span> <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="37967-157">满足</span><span class="sxs-lookup"><span data-stu-id="37967-157">Meet</span></span>  <br/>          | <span data-ttu-id="37967-158">https://SfB2015.contoso.com/Meethttps://SfB2015.fabrikam.com/Meet，依此类推 （一个为组织中每个 SIP 域）</span><span class="sxs-lookup"><span data-stu-id="37967-158">https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span>  <br/> |
| <span data-ttu-id="37967-159">拨入</span><span class="sxs-lookup"><span data-stu-id="37967-159">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| <span data-ttu-id="37967-160">管理</span><span class="sxs-lookup"><span data-stu-id="37967-160">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

<span data-ttu-id="37967-161">如果您具有多个 SIP 域，并希望其具有单独的会议简单 Url，但希望大程度地减少这些简单 Url 的 DNS 记录和证书要求选项 3 最为有用。</span><span class="sxs-lookup"><span data-stu-id="37967-161">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> 

<span data-ttu-id="37967-162">**简单 URL 命名选项 3**</span><span class="sxs-lookup"><span data-stu-id="37967-162">**Simple URL Naming Option 3**</span></span>


| <span data-ttu-id="37967-163">**简单 URL**</span><span class="sxs-lookup"><span data-stu-id="37967-163">**Simple URL**</span></span> <br/> | <span data-ttu-id="37967-164">**示例**</span><span class="sxs-lookup"><span data-stu-id="37967-164">**Example**</span></span> <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="37967-165">满足</span><span class="sxs-lookup"><span data-stu-id="37967-165">Meet</span></span>  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| <span data-ttu-id="37967-166">拨入</span><span class="sxs-lookup"><span data-stu-id="37967-166">Dial-in</span></span>  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| <span data-ttu-id="37967-167">管理</span><span class="sxs-lookup"><span data-stu-id="37967-167">Admin</span></span>  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="37967-168">简单 Url 的灾难恢复选项</span><span class="sxs-lookup"><span data-stu-id="37967-168">Disaster Recovery option for simple URLs</span></span>
<span data-ttu-id="37967-169"><a name="BK_Valid"> </a></span><span class="sxs-lookup"><span data-stu-id="37967-169"></span></span>

<span data-ttu-id="37967-170">如果您有多个站点包含前端池的 DNS 提供程序支持 GeoDNS，您可以设置以支持灾难恢复的简单 Url 的 DNS 记录，以便简单 URL 功能仍即使一个整个前端池不可用。</span><span class="sxs-lookup"><span data-stu-id="37967-170">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="37967-171">此灾难恢复功能支持 Meet 和电话拨入式简单 Url。</span><span class="sxs-lookup"><span data-stu-id="37967-171">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="37967-172">若要配置该，创建两个 GeoDNS 地址。</span><span class="sxs-lookup"><span data-stu-id="37967-172">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="37967-173">每个地址具有两个解析为其用于灾难恢复目的成对出现两个池的 DNS A 或 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="37967-173">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="37967-174">一个 GeoDNS 地址用于内部访问权限，并且将解析为内部 web FQDN 或负载平衡器 IP 地址的两个池。</span><span class="sxs-lookup"><span data-stu-id="37967-174">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="37967-175">用于外部访问的其他 GeoDNS 地址并且将解析为的外部 web FQDN 或负载平衡器 IP 地址的两个池。</span><span class="sxs-lookup"><span data-stu-id="37967-175">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="37967-176">下面是一个有关会议的简单 URL，并使用的池的 Fqdn 示例。</span><span class="sxs-lookup"><span data-stu-id="37967-176">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span> 

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

<span data-ttu-id="37967-177">然后，创建您会议简单 URL （如 meet.contoso.com) 解析到两个 GeoDNS 地址的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="37967-177">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

> [!NOTE]
> <span data-ttu-id="37967-178">如果您的网络使用 hairpinning （路由通过外部链接，包括来自组织内的通信的所有简单 URL 流量），然后可以仅配置的外部 GeoDNS 地址并解析为仅的会议的简单 URL外部地址。</span><span class="sxs-lookup"><span data-stu-id="37967-178">If your network uses hairpinning (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>

<span data-ttu-id="37967-179">轮循机制方法分发到两个池的请求或用于连接到一个池 （如位于地理位置靠近的池） 的主要并使用另一个池仅中的情况下使用此方法时，您都可以配置为使用每个 GeoDNS 地址连接故障。</span><span class="sxs-lookup"><span data-stu-id="37967-179">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span> 

<span data-ttu-id="37967-180">您可以设置电话拨入式简单 url 相同的配置。</span><span class="sxs-lookup"><span data-stu-id="37967-180">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="37967-181">为此，请创建类似于上一示例中的其他记录替换`dialin`的`meet`中的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="37967-181">To do so, create additional records like those in the previous example, substituting  `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="37967-182">为管理简单 URL，使用本节中前面列出的三个选项之一。</span><span class="sxs-lookup"><span data-stu-id="37967-182">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="37967-183">一旦此配置的设置方式，您必须使用监视应用程序设置 HTTP 监视的故障。</span><span class="sxs-lookup"><span data-stu-id="37967-183">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="37967-184">用于外部访问，以确保该 HTTPS 获取 lyncdiscover 的监视器。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="37967-184">For external access, monitor to make sure that HTTPS GET lyncdiscover.<sipdomain></span></span> <span data-ttu-id="37967-185">对外部 web FQDN 或负载平衡器 IP 地址的两个池的请求是成功的。</span><span class="sxs-lookup"><span data-stu-id="37967-185">requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="37967-186">例如，以下请求不能包含任何**ACCEPT**标头，必须返回**200 确定**。</span><span class="sxs-lookup"><span data-stu-id="37967-186">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="37967-187">用于内部访问，您必须监视端口 5061 上的内部 web FQDN 或负载平衡器的两个池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="37967-187">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="37967-188">如果检测到任何连接失败，则为这些池 VIP 必须关闭端口 80、 443 和 4443。</span><span class="sxs-lookup"><span data-stu-id="37967-188">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 4443.</span></span>


