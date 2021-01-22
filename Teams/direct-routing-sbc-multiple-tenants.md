---
title: 配置会话边界控制器 - 多个租户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何为 SBC (会话边界控制器) 为 Microsoft 合作伙伴和/或 PSTN 运营商提供多个租户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343e2d1aedefd34de452df8da6ce9a5ad1a726ba
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923844"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="ef6e5-103">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="ef6e5-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="ef6e5-104">直接路由支持在 SBC (一个) 控制器，为多个租户提供服务。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="ef6e5-105">此方案专为 Microsoft 合作伙伴和/或 PSTN 运营商（本文档稍后称为运营商）设计。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="ef6e5-106">运营商将交付给 Microsoft Teams 的电话服务销售给客户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="ef6e5-107">运营商：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-107">A carrier:</span></span>
- <span data-ttu-id="ef6e5-108">在数据中心部署和管理 SBC (客户无需实现 SBC，并且从 Teams 客户端客户端服务中的运营商接收电话) 。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="ef6e5-109">将 SBC 与多个租户互连。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="ef6e5-110">为客户提供 PSTN 服务。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="ef6e5-111">管理端到端呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="ef6e5-112">PSTN 服务单独收费。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="ef6e5-113">Microsoft 不管理运营商。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="ef6e5-114">Microsoft 提供 PBX (Microsoft Phone System) 和 Teams 客户端。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="ef6e5-115">Microsoft 还会认证可与 Microsoft Phone 系统一起使用的电话和认证 SDC。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="ef6e5-116">在选择运营商之前，请确保你的选择具有经过认证的 SBC，并可以端到端地管理语音质量。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="ef6e5-117">下面是配置方案的技术实现步骤。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="ef6e5-118">**仅运营商：**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-118">**Carrier only:**</span></span>
1. <span data-ttu-id="ef6e5-119">根据经过认证的 SBC 供应商的说明部署 [SBC，并针对托管方案配置它](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="ef6e5-120">在运营商租户中注册基本域名，并请求通配符证书。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="ef6e5-121">为属于基本域的每位客户注册子域。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="ef6e5-122">**具有客户全局管理员的运营商：**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="ef6e5-123">将子域名称添加到客户租户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="ef6e5-124">激活子域名称。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="ef6e5-125">配置从运营商到客户租户的中继并预配用户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="ef6e5-126">*请确保了解 DNS 基础知识以及如何在 Microsoft 365 或 Office 365 中管理域名。在继续下一步之前，请查看"获取有关 [Microsoft 365 或 Office 365 域](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 的帮助"。*</span><span class="sxs-lookup"><span data-stu-id="ef6e5-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="ef6e5-127">部署和配置 SBC</span><span class="sxs-lookup"><span data-stu-id="ef6e5-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="ef6e5-128">若要详细了解如何为 SBC 托管方案部署和配置 SBC，请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="ef6e5-129">**AudioCodes：**[直接路由](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)配置说明，"将 AudioCodes SBC 连接到 Microsoft Teams 直接路由托管模型配置说明"中所述的 SBC 托管方案的配置。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="ef6e5-130">**Oracle：**[直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，"Microsoft"部分介绍了 SBC 托管方案的配置。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="ef6e5-131">**功能区通信：** 请参阅功能区 [通信 SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)配置指南，了解如何配置功能区核心系列 SBC 的文档，并参阅本页功能区最佳实践 - 为 Microsoft Teams Direct Routing [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)配置运营商</span><span class="sxs-lookup"><span data-stu-id="ef6e5-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="ef6e5-132">**TE-Systems (anynode) ：**  请在 [TE-Systems Community](https://community.te-systems.de/) 页面上注册，了解如何为多个租户配置 anynode SBC 的文档和示例。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="ef6e5-133">**Metaswitch：**  有关如何为多个租户启用 Perimeta SBC 的文档，请在 [Metaswitch 社区](https://manuals.metaswitch.com/MAN39555) 页上注册。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://manuals.metaswitch.com/MAN39555) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="ef6e5-134">请注意如何配置"联系人"标头。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="ef6e5-135">联系人标头用于查找传入邀请消息上的客户租户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="ef6e5-136">注册基本域和子域</span><span class="sxs-lookup"><span data-stu-id="ef6e5-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="ef6e5-137">对于托管方案，需要创建：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="ef6e5-138">运营商拥有的一个基域名。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="ef6e5-139">属于每个客户租户中基本域名的一部分的子域。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="ef6e5-140">在下面的示例中：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-140">In the following example:</span></span>
- <span data-ttu-id="ef6e5-141">Adatum 是一家运营商，通过提供 Internet 和电话服务为多个客户提供服务。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="ef6e5-142">Woodgrove Bank、Contoso 和 Adventure Works 是三个拥有 Microsoft 365 或 Office 365 域但从 Adatum 接收电话服务的客户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="ef6e5-143">子域 **必须与** 在将邀请发送到 Microsoft 365 或 Office 365 时为客户配置的中继的 FQDN 名称和联系人标头中的 FQDN 匹配。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="ef6e5-144">当呼叫到达 Microsoft 365 或 Office 365 直接路由接口时，该接口使用联系人标头查找应查找用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="ef6e5-145">直接路由不使用邀请上的电话号码查找，因为某些客户可能拥有非 DID 号码，这些号码可能与多个租户重叠。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="ef6e5-146">因此，"联系人"标头中的 FQDN 名称需要标识要按电话号码查找用户的确切租户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="ef6e5-147">*有关在 Microsoft  [365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 组织中创建域名详细信息，请查看"获取有关 Office 365 域的帮助"。*</span><span class="sxs-lookup"><span data-stu-id="ef6e5-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="ef6e5-148">下图总结了基本域、子域和联系人标头的要求。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![显示域和联系人头的要求的示意图](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="ef6e5-150">SBC 需要证书来验证连接。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="ef6e5-151">对于 SBC 托管方案，运营商需要使用 CN 和/或 SAN .base_domain (请求证书，*\* 例如 \* .customers.adatum.biz) 。*</span><span class="sxs-lookup"><span data-stu-id="ef6e5-151">For the SBC hosting scenario, the carrier needs to request a certificate with CN and/or SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="ef6e5-152">此证书可用于对从单个 SBC 提供的多个租户的连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="ef6e5-153">下表是一个配置示例。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="ef6e5-154">新域名</span><span class="sxs-lookup"><span data-stu-id="ef6e5-154">New domain name</span></span> |<span data-ttu-id="ef6e5-155">类型</span><span class="sxs-lookup"><span data-stu-id="ef6e5-155">Type</span></span>|<span data-ttu-id="ef6e5-156">已注册</span><span class="sxs-lookup"><span data-stu-id="ef6e5-156">Registered</span></span>  |<span data-ttu-id="ef6e5-157">适用于 SBC 的证书 CN/SAN</span><span class="sxs-lookup"><span data-stu-id="ef6e5-157">Certificate CN/SAN for SBC</span></span>  |<span data-ttu-id="ef6e5-158">示例中的租户默认域</span><span class="sxs-lookup"><span data-stu-id="ef6e5-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="ef6e5-159">SBC 在向用户发送呼叫时必须在联系人标头中呈现的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="ef6e5-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="ef6e5-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-160">customers.adatum.biz</span></span>|    <span data-ttu-id="ef6e5-161">基本</span><span class="sxs-lookup"><span data-stu-id="ef6e5-161">Base</span></span>     |     <span data-ttu-id="ef6e5-162">在运营商租户中</span><span class="sxs-lookup"><span data-stu-id="ef6e5-162">In carrier tenant</span></span>  |    <span data-ttu-id="ef6e5-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="ef6e5-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-164">adatum.biz</span></span>      |<span data-ttu-id="ef6e5-165">NA，这是一个服务租户，没有用户</span><span class="sxs-lookup"><span data-stu-id="ef6e5-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="ef6e5-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="ef6e5-167">子域</span><span class="sxs-lookup"><span data-stu-id="ef6e5-167">Subdomain</span></span>  |    <span data-ttu-id="ef6e5-168">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="ef6e5-168">In a customer tenant</span></span>  |    <span data-ttu-id="ef6e5-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="ef6e5-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="ef6e5-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="ef6e5-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="ef6e5-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="ef6e5-173">子域</span><span class="sxs-lookup"><span data-stu-id="ef6e5-173">Subdomain</span></span> | <span data-ttu-id="ef6e5-174">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="ef6e5-174">In a customer tenant</span></span>   |   <span data-ttu-id="ef6e5-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="ef6e5-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef6e5-176">contoso.com</span></span>   |<span data-ttu-id="ef6e5-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="ef6e5-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="ef6e5-179">子域</span><span class="sxs-lookup"><span data-stu-id="ef6e5-179">Subdomain</span></span> | <span data-ttu-id="ef6e5-180">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="ef6e5-180">In a customer tenant</span></span> |   <span data-ttu-id="ef6e5-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="ef6e5-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="ef6e5-182">adventureworks.com</span></span> | <span data-ttu-id="ef6e5-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="ef6e5-184">若要配置基域和子域，请执行下面所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="ef6e5-185">在示例中，我们将在 Woodgrove Bank 租户 (customers.adatum.biz) 中为一个 (sbc1.customers.adatum.biz配置基本域名和) 。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="ef6e5-186">使用sbcX.customers.adatum.biz在运营商租户中启用语音。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="ef6e5-187">sbcX 可以是任何唯一且有效的字母数字主机名。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="ef6e5-188">在运营商租户中注册基本域名</span><span class="sxs-lookup"><span data-stu-id="ef6e5-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="ef6e5-189">**这些操作在运营商租户中执行。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="ef6e5-190">确保你拥有运营商租户中的适当权限</span><span class="sxs-lookup"><span data-stu-id="ef6e5-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="ef6e5-191">只有以全局管理员登录 Microsoft 365 管理中心时，才能添加新域。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="ef6e5-192">若要验证你拥有的角色，请登录到 Microsoft 365 管理中心 (，转到"用户活动用户"，然后验证你具有全局 https://portal.office.com)   >  管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="ef6e5-193">有关管理员角色以及如何在 Microsoft 365 或 Office 365 中分配角色的信息，请参阅"[关于管理员角色"。](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)</span><span class="sxs-lookup"><span data-stu-id="ef6e5-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="ef6e5-194">将基本域添加到租户并验证</span><span class="sxs-lookup"><span data-stu-id="ef6e5-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="ef6e5-195">在 Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **添加域"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="ef6e5-196">在 **"输入你拥有域"框中** ，键入基本域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="ef6e5-197">在下面的示例中，基本域 *customers.adatum.biz。*</span><span class="sxs-lookup"><span data-stu-id="ef6e5-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![显示"添加域"页面的屏幕截图](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="ef6e5-199">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-199">Click **Next**.</span></span>
4. <span data-ttu-id="ef6e5-200">在示例中，租户已adatum.biz已验证域名。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="ef6e5-201">向导不会要求进行其他验证，customers.adatum.biz已注册名称的子域。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="ef6e5-202">但是，如果添加以前尚未验证的 FQDN，则需要完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="ef6e5-203">验证过程 [如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![显示已验证域名的确认的屏幕截图](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="ef6e5-205">单击 **"** 下一步"，在"更新 **DNS** 设置"页上，选择"我将自己 **添加 DNS** 记录"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="ef6e5-206">在下一页上， (Exchange、SharePoint 或 Teams/Skype for Business) 域名，请单击"下一步"，然后单击"完成 **"。** </span><span class="sxs-lookup"><span data-stu-id="ef6e5-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="ef6e5-207">确保新域位于"设置完成"状态。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![显示状态为"设置已完成"的域的屏幕截图](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="ef6e5-209">激活域名</span><span class="sxs-lookup"><span data-stu-id="ef6e5-209">Activate the domain name</span></span>

<span data-ttu-id="ef6e5-210">注册域名后，需要通过添加至少一个 E1、E3 或 E5 许可用户，并分配 SIP 地址与所创建基础域匹配的 SIP 地址的 FQDN 部分来激活它。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-210">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="ef6e5-211">激活域后，许可证 (最多可能需要 24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

> [!NOTE]
> <span data-ttu-id="ef6e5-212">运营商租户必须至少保留分配给租户的一个 E1/E3/E5/M365 商业版许可证，以避免删除 Skype for Business 配置。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-212">The Carrier tenant must keep at least one E1/E3/E5/M365 Business license assigned to the tenant to avoid removal of the Skype for Business configuration.</span></span> 

<span data-ttu-id="ef6e5-213">*有关在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 组织中添加用户的信息，请查看"获取有关 Microsoft 365 或 Office 365 域的帮助"。*</span><span class="sxs-lookup"><span data-stu-id="ef6e5-213">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="ef6e5-214">例如：test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-214">For example: test@customers.adatum.biz</span></span>

![基本域激活页面的屏幕截图](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="ef6e5-216">在客户租户中注册子域名称</span><span class="sxs-lookup"><span data-stu-id="ef6e5-216">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="ef6e5-217">需要为每个客户创建唯一的子域名称。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-217">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="ef6e5-218">本示例在具有默认域名的租户sbc1.customers.adatum.biz创建子域woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-218">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="ef6e5-219">**以下所有操作均在客户租户中。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-219">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="ef6e5-220">确保在客户租户中拥有适当的权限</span><span class="sxs-lookup"><span data-stu-id="ef6e5-220">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="ef6e5-221">只有以全局管理员登录 Microsoft 365 管理中心时，才能添加新域。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-221">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="ef6e5-222">若要验证你拥有的角色，请登录到 Microsoft 365 管理中心 (，转到"用户活动用户"，然后验证你具有全局 https://portal.office.com)   >  管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-222">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="ef6e5-223">有关管理员角色以及如何在 Microsoft 365 或 Office 365 中分配角色的信息，请参阅"[关于管理员角色"。](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)</span><span class="sxs-lookup"><span data-stu-id="ef6e5-223">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="ef6e5-224">将子域添加到客户租户并进行验证</span><span class="sxs-lookup"><span data-stu-id="ef6e5-224">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="ef6e5-225">在 Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **添加域"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-225">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="ef6e5-226">在 **"输入你拥有域"框中** ，键入此租户的子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-226">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="ef6e5-227">在下面的示例中，子域sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-227">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    !["添加域"页的屏幕截图](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="ef6e5-229">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-229">Click **Next**.</span></span>
4. <span data-ttu-id="ef6e5-230">FQDN 从未在租户中注册过。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-230">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="ef6e5-231">下一步需要验证域。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-231">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="ef6e5-232">改为 **选择"添加 TXT 记录"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-232">Select **Add a TXT record instead**.</span></span> 

    !["验证域"页的屏幕截图](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="ef6e5-234">单击 **"** 下一步"，并记下生成的 TXT 值以验证域名。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-234">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    !["验证域"页面上的文本记录的屏幕截图](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="ef6e5-236">使用运营商的 DNS 托管提供商中上一步骤中的值创建 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-236">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![显示创建 TXT 记录的屏幕截图](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="ef6e5-238">有关详细信息，请参阅在任何 DNS 托管提供商创建 [DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-238">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="ef6e5-239">返回到客户的 Microsoft 365 管理中心，并单击"验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-239">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="ef6e5-240">下一页上，选择 **"我将自己添加 DNS** 记录"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-240">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    !["更新 DNS 设置"页上的选项的屏幕截图](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="ef6e5-242">在"**选择联机服务"** 页面上，清除所有选项，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-242">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    !["选择联机服务"页面的屏幕截图](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="ef6e5-244">在 **"更新** **DNS 设置"页上单击"完成** "。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-244">Click **Finish** on the **Update DNS settings** page.</span></span>

    !["更新 DNS 设置"页的屏幕截图](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="ef6e5-246">确保状态为"设置 **已完成"。**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-246">Ensure that the status is **Setup complete**.</span></span> 
    
    ![显示安装完成状态的页面的屏幕截图](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> <span data-ttu-id="ef6e5-248">单个客户端的基本 URL 和子域必须位于同一租户中，才能添加 _直接路由_ 中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-248">The base URL and the subdomain for the individual client have to be on the same tenant to enable you to add a _direct route_ trunk.</span></span>

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="ef6e5-249">激活子域名称</span><span class="sxs-lookup"><span data-stu-id="ef6e5-249">Activate the subdomain name</span></span>

<span data-ttu-id="ef6e5-250">注册域名后，需要通过至少添加一个用户并分配 SIP 地址与客户租户中创建的子域匹配的 SIP 地址的 FQDN 部分来激活该域名。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-250">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="ef6e5-251">激活子域后，可以从用户吊销 (最多可能需要 24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-251">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="ef6e5-252">*有关在 [Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 组织中添加用户的信息，请查看"获取有关 Microsoft 365 或 Office 365 域的帮助"。*</span><span class="sxs-lookup"><span data-stu-id="ef6e5-252">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="ef6e5-253">例如：test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ef6e5-253">For example: test@sbc1.customers.adatum.biz</span></span>

![激活子域页面的屏幕截图](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="ef6e5-255">创建中继并预配用户</span><span class="sxs-lookup"><span data-stu-id="ef6e5-255">Create a trunk and provision users</span></span>

<span data-ttu-id="ef6e5-256">在直接路由的初始版本中，Microsoft 要求使用 New-CSOnlinePSTNGateway 将中继添加到 (租户) 租户。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-256">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="ef6e5-257">但是，由于两个原因，这一点未得到证实为最佳：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-257">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="ef6e5-258">**开销管理**。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-258">**Overhead management**.</span></span> <span data-ttu-id="ef6e5-259">例如，卸载或清空 SBC 会更改某些参数，例如启用或禁用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-259">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="ef6e5-260">更改端口需要通过运行 Set-CSOnlinePSTNGateway (更改多个租户中的) ，但实际上是相同的 SBC。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-260">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="ef6e5-261">**开销处理**。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-261">**Overhead processing**.</span></span> <span data-ttu-id="ef6e5-262">收集和监视中继运行状况数据 - 从多个逻辑中继收集的 SIP 选项，事实上，这些逻辑中继是同一 SBC 和相同的物理中继，这会降低路由数据的处理速度。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-262">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="ef6e5-263">基于此反馈，Microsoft 将引入新逻辑来为客户租户预配中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-263">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="ef6e5-264">引入了两个新实体：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-264">Two new entities were introduced:</span></span>
-    <span data-ttu-id="ef6e5-265">使用命令 New-CSOnlinePSTNGateway 在运营商租户中注册的运营商中继，例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-265">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="ef6e5-266">派生的中继，不需要注册。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-266">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="ef6e5-267">它只是从运营商中继添加的所需主机名。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-267">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="ef6e5-268">它从运营商中继派生其所有配置参数。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-268">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="ef6e5-269">无需在 PowerShell 中创建派生的中继，并且与运营商中继的关联基于 FQDN 名称 (请参阅下面) 。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-269">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="ef6e5-270">**预配逻辑和示例**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-270">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="ef6e5-271">运营商只需使用) 命令在运营商域 (中继中设置和管理单个中继Set-CSOnlinePSTNGateway中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-271">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="ef6e5-272">在以上示例中，它adatum.biz;</span><span class="sxs-lookup"><span data-stu-id="ef6e5-272">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="ef6e5-273">在客户租户中，运营商只需将派生的中继 FQDN 添加到用户的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-273">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="ef6e5-274">无需为中继New-CSOnlinePSTNGateway运行连接。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-274">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="ef6e5-275">如名称所示，派生的中继从运营商中继继承或派生所有配置参数。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-275">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="ef6e5-276">示例：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-276">Examples:</span></span>
-    <span data-ttu-id="ef6e5-277">Customers.adatum.biz – 需要在运营商租户中创建的运营商中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-277">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="ef6e5-278">Sbc1.customers.adatum.biz – 不需要在 PowerShell 中创建的客户租户中的派生中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-278">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="ef6e5-279">只需在联机语音路由策略的客户租户中添加派生的中继的名称，而无需创建它。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-279">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="ef6e5-280">运营商需要设置 DNS 记录，将派生的中继 FQDN 解析为运营商 SBC IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-280">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="ef6e5-281">对运营商租户 (中继) 所做的更改会自动应用到派生的中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-281">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="ef6e5-282">例如，运营商可以更改运营商中继上的 SIP 端口，此更改适用于所有派生的中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-282">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="ef6e5-283">配置中继的新逻辑简化了管理，因为无需转到每个租户并更改每个中继上的参数。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-283">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="ef6e5-284">选项仅发送到运营商中继 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-284">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="ef6e5-285">运营商中继的运行状况状态将应用到所有派生的中继，并用于路由决策。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-285">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="ef6e5-286">了解有关直接路由 [选项的详细信息](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-286">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="ef6e5-287">运营商可以清空运营商中继，所有派生的中继也将清空。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-287">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="ef6e5-288">**从以前的模型迁移到运营商中继**</span><span class="sxs-lookup"><span data-stu-id="ef6e5-288">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="ef6e5-289">若要从运营商托管模型的当前实现迁移到新模型，运营商需要为客户租户重新配置中继。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-289">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="ef6e5-290">使用以下方法从客户租户中删除中继Remove-CSOnlinePSTNGateway (将中继留在运营商租户中) -</span><span class="sxs-lookup"><span data-stu-id="ef6e5-290">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="ef6e5-291">我们强烈建议尽快迁移到新解决方案，因为我们将使用运营商和派生的中继模型增强监视和预配。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-291">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="ef6e5-292">请参阅 [SBC 供应商有关](#deploy-and-configure-the-sbc) 配置在"联系人"标头中发送子域的 FQDN 名称的说明。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-292">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="ef6e5-293">设置多租户故障转移的注意事项</span><span class="sxs-lookup"><span data-stu-id="ef6e5-293">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="ef6e5-294">若要为多租户环境设置故障转移，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-294">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="ef6e5-295">对于每个租户，为两个不同的 SDC 添加 FQNS。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-295">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="ef6e5-296">例如：</span><span class="sxs-lookup"><span data-stu-id="ef6e5-296">For example:</span></span>

   <span data-ttu-id="ef6e5-297">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef6e5-297">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="ef6e5-298">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef6e5-298">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="ef6e5-299">在用户的联机语音路由策略中，指定两个 SDC。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-299">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="ef6e5-300">如果一个 SBC 失败，路由策略将调用路由到第二个 SBC。</span><span class="sxs-lookup"><span data-stu-id="ef6e5-300">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="ef6e5-301">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef6e5-301">See also</span></span>

[<span data-ttu-id="ef6e5-302">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="ef6e5-302">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="ef6e5-303">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="ef6e5-303">Configure Direct Routing</span></span>](direct-routing-configure.md)
