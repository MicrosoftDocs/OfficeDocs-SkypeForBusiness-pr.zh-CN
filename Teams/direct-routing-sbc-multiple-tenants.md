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
description: 了解如何为 Microsoft 合作伙伴和/或 PSTN 护 (商配置一) 个会话边界控制器。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91ca12f3e0d9720800ad9b0bcf946df8d31b3e86
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814238"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="4b387-103">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="4b387-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="4b387-104">直接路由支持将一个会话边界 (SBC 控制器配置为 (SBC 和) 租户。</span><span class="sxs-lookup"><span data-stu-id="4b387-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="4b387-105">此方案适用于 Microsoft 合作伙伴和/或 PSTN 转网商，即称为 Carrier。本文档后面部分称为商。</span><span class="sxs-lookup"><span data-stu-id="4b387-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="4b387-106">一位教师会将电信服务发送给 Microsoft Teams 给客户。</span><span class="sxs-lookup"><span data-stu-id="4b387-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="4b387-107">在执行以下操作时：</span><span class="sxs-lookup"><span data-stu-id="4b387-107">A carrier:</span></span>
- <span data-ttu-id="4b387-108">在其数据中心中部署和管理 SBC (客户无需实施 SBC，他们会从 Teams 客户端客户端服务购买商的电话服务) 。</span><span class="sxs-lookup"><span data-stu-id="4b387-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="4b387-109">将 SBC 与多个租户连接。</span><span class="sxs-lookup"><span data-stu-id="4b387-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="4b387-110">向客户提供 PSTN 服务。</span><span class="sxs-lookup"><span data-stu-id="4b387-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="4b387-111">管理通话质量端到端。</span><span class="sxs-lookup"><span data-stu-id="4b387-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="4b387-112">为 PSTN 服务单独收费。</span><span class="sxs-lookup"><span data-stu-id="4b387-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="4b387-113">Microsoft 不管理商。</span><span class="sxs-lookup"><span data-stu-id="4b387-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="4b387-114">Microsoft 提供了一个 PBX (Microsoft Phone System) 客户端。</span><span class="sxs-lookup"><span data-stu-id="4b387-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client.</span></span> <span data-ttu-id="4b387-115">Microsoft 还会认证手机和可与 Microsoft Phone 系统一起使用的证书 SBC。</span><span class="sxs-lookup"><span data-stu-id="4b387-115">Microsoft also certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="4b387-116">在选择运行机构之前，请确保您的选择有认证的 SBC 并且可以将语音质量端管理到结束。</span><span class="sxs-lookup"><span data-stu-id="4b387-116">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="4b387-117">以下是配置方案的技术实现步骤。</span><span class="sxs-lookup"><span data-stu-id="4b387-117">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="4b387-118">**仅执行以下操作：**</span><span class="sxs-lookup"><span data-stu-id="4b387-118">**Carrier only:**</span></span>
1. <span data-ttu-id="4b387-119">部署 SBC 并根据已认证的 SBC 供应商的说明对 [托管方案进行配置](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="4b387-119">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="4b387-120">在条件租户中注册一个基域名，并请求通配符证书。</span><span class="sxs-lookup"><span data-stu-id="4b387-120">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="4b387-121">为每个客户注册一个子域，这是基域的一部分。</span><span class="sxs-lookup"><span data-stu-id="4b387-121">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="4b387-122">**具有客户全局管理员的机会：**</span><span class="sxs-lookup"><span data-stu-id="4b387-122">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="4b387-123">将子域名添加到客户租户。</span><span class="sxs-lookup"><span data-stu-id="4b387-123">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="4b387-124">激活子域名。</span><span class="sxs-lookup"><span data-stu-id="4b387-124">Activate the subdomain name.</span></span>
3. <span data-ttu-id="4b387-125">配置从承告商到客户租户的中断，并设置用户。</span><span class="sxs-lookup"><span data-stu-id="4b387-125">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="4b387-126">*请确保了解 DNS 基础知识以及在 Microsoft 365 或 Office 365 中管理域名的方式。进 [一步继续尝试之前，请先查看有关 Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 域的帮助。*</span><span class="sxs-lookup"><span data-stu-id="4b387-126">*Please make sure you understand DNS basics and how the domain name is managed in Microsoft 365 or Office 365. Review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="4b387-127">部署和配置 SBC</span><span class="sxs-lookup"><span data-stu-id="4b387-127">Deploy and configure the SBC</span></span>

<span data-ttu-id="4b387-128">有关如何为 SBC 托管方案部署和配置 SBC 的详细步骤，请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="4b387-128">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="4b387-129">**AudioCodes：**[直接路由配置备注](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，将"AudioCodes SBC 连接到 Microsoft Teams 直接路由托管模型配置笔记"中所述的 SBC 托管方案配置。</span><span class="sxs-lookup"><span data-stu-id="4b387-129">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in "Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note."</span></span> 
- <span data-ttu-id="4b387-130">**Oracle：**[直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，SBC 托管方案的配置将在"Microsoft"部分中进行介绍。</span><span class="sxs-lookup"><span data-stu-id="4b387-130">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="4b387-131">**功能区通信：**  有关如何配置功能区内部 SBC 和此页面功能区的最佳实践的文档，请参阅"关于 CBC [Core Microsoft Teams"](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 的文档的参考指南 - 为 Microsoft Teams 直接路由 [SBC 边缘配置 Corts](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span><span class="sxs-lookup"><span data-stu-id="4b387-131">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)</span></span>
- <span data-ttu-id="4b387-132">**TE-Systems 字段 (任何节) ：**  请在 [TE-Systems"社区](https://community.te-systems.de/) "页面上注册文档，以及如何为多个租户配置任何节点 SBC 的示例。</span><span class="sxs-lookup"><span data-stu-id="4b387-132">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>
- <span data-ttu-id="4b387-133">**Metaswitch：**  请登记 ["Metaswitch 社区"](https://sso.metaswitch.com/UI/Login) 页，以获取有关如何为多个租户启用 Perimeta SBC 的文档。</span><span class="sxs-lookup"><span data-stu-id="4b387-133">**Metaswitch:**  Please register on the [Metaswitch Community page](https://sso.metaswitch.com/UI/Login) for documentation on how to enable Perimeta SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="4b387-134">请注意如何配置"联系人"标题。</span><span class="sxs-lookup"><span data-stu-id="4b387-134">Please pay attention to how to configure the "Contact" header.</span></span> <span data-ttu-id="4b387-135">联系人头用于在传入邀请邮件中查找客户租户。</span><span class="sxs-lookup"><span data-stu-id="4b387-135">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="4b387-136">注册基域和子域</span><span class="sxs-lookup"><span data-stu-id="4b387-136">Register a base domain and subdomains</span></span>

<span data-ttu-id="4b387-137">对于托管方案，你需要创建：</span><span class="sxs-lookup"><span data-stu-id="4b387-137">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="4b387-138">一个由管理器拥有的基域名。</span><span class="sxs-lookup"><span data-stu-id="4b387-138">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="4b387-139">每个客户租户中作为基域名的一个子域。</span><span class="sxs-lookup"><span data-stu-id="4b387-139">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="4b387-140">在以下示例中：</span><span class="sxs-lookup"><span data-stu-id="4b387-140">In the following example:</span></span>
- <span data-ttu-id="4b387-141">Adatum 是通过提供 Internet 和电话服务来商为多名客户提供服务。</span><span class="sxs-lookup"><span data-stu-id="4b387-141">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="4b387-142">Woodgrove Bank、Contoso 和 Adventure Works 是三名有 Microsoft 365 或 Office 365 域但从 Adatum 接收电话服务的三名客户。</span><span class="sxs-lookup"><span data-stu-id="4b387-142">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Microsoft 365 or Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="4b387-143">子域 **名必须** 与将要为客户配置的中断的 FQDN 名称和联系人标题中的 FQDN 匹配，才能在将邀请发送给 Microsoft 365 或 Office 365 时，搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="4b387-143">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="4b387-144">当呼叫到达 Microsoft 365 或 Office 365 直接路由接口时，接口使用联系人标题查找应该在其中查找用户的租户。</span><span class="sxs-lookup"><span data-stu-id="4b387-144">When a call arrives at the Microsoft 365 or Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="4b387-145">直接路由不在邀请上使用电话号码查找，因此某些客户可能在多个租户中有可以重叠的非 DID 号码。</span><span class="sxs-lookup"><span data-stu-id="4b387-145">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="4b387-146">因此，需要在联系人头中的 FQDN 名称来确定确切的租户，以通过电话号码查找该用户。</span><span class="sxs-lookup"><span data-stu-id="4b387-146">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="4b387-147">*请查看  [有关在 Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 组织中创建域名的详细信息，查看有关 Office 365 域的帮助。*</span><span class="sxs-lookup"><span data-stu-id="4b387-147">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="4b387-148">下图汇总了基域、子域和联系人头的要求。</span><span class="sxs-lookup"><span data-stu-id="4b387-148">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![显示对域和联系人头的要求的图表](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="4b387-150">SBC 需要证书才能对连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4b387-150">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="4b387-151">对于 SBC 托管方案，运行商需使用 SAN \* \* .base_domain (（例如 \* .customers.adatum.biz) ）请求证customers.adatum.biz) 。 \*</span><span class="sxs-lookup"><span data-stu-id="4b387-151">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="4b387-152">此证书可用于验证从单个 SBC 提供的多个租户的连接。</span><span class="sxs-lookup"><span data-stu-id="4b387-152">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="4b387-153">下表是了一个配置的示例。</span><span class="sxs-lookup"><span data-stu-id="4b387-153">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="4b387-154">新域名</span><span class="sxs-lookup"><span data-stu-id="4b387-154">New domain name</span></span> |<span data-ttu-id="4b387-155">类型</span><span class="sxs-lookup"><span data-stu-id="4b387-155">Type</span></span>|<span data-ttu-id="4b387-156">已注册</span><span class="sxs-lookup"><span data-stu-id="4b387-156">Registered</span></span>  |<span data-ttu-id="4b387-157">SAN for SBC 证书</span><span class="sxs-lookup"><span data-stu-id="4b387-157">Certificate SAN for SBC</span></span>  |<span data-ttu-id="4b387-158">示例中的租户默认域</span><span class="sxs-lookup"><span data-stu-id="4b387-158">Tenant default domain in the example</span></span>  |<span data-ttu-id="4b387-159">向用户发送呼叫时，SBC 必须出现在联系人头眉中</span><span class="sxs-lookup"><span data-stu-id="4b387-159">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="4b387-160">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-160">customers.adatum.biz</span></span>|    <span data-ttu-id="4b387-161">基数</span><span class="sxs-lookup"><span data-stu-id="4b387-161">Base</span></span>     |     <span data-ttu-id="4b387-162">在任意租户中</span><span class="sxs-lookup"><span data-stu-id="4b387-162">In carrier tenant</span></span>  |    <span data-ttu-id="4b387-163">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-163">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="4b387-164">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-164">adatum.biz</span></span>      |<span data-ttu-id="4b387-165">NA，这是一个服务租户，没有用户</span><span class="sxs-lookup"><span data-stu-id="4b387-165">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="4b387-166">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-166">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="4b387-167">子域</span><span class="sxs-lookup"><span data-stu-id="4b387-167">Subdomain</span></span>  |    <span data-ttu-id="4b387-168">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="4b387-168">In a customer tenant</span></span>  |    <span data-ttu-id="4b387-169">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-169">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="4b387-170">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="4b387-170">woodgrovebank.us</span></span>  |  <span data-ttu-id="4b387-171">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-171">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="4b387-172">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-172">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="4b387-173">子域</span><span class="sxs-lookup"><span data-stu-id="4b387-173">Subdomain</span></span> | <span data-ttu-id="4b387-174">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="4b387-174">In a customer tenant</span></span>   |   <span data-ttu-id="4b387-175">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-175">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="4b387-176">contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b387-176">contoso.com</span></span>   |<span data-ttu-id="4b387-177">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-177">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="4b387-178">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-178">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="4b387-179">子域</span><span class="sxs-lookup"><span data-stu-id="4b387-179">Subdomain</span></span> | <span data-ttu-id="4b387-180">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="4b387-180">In a customer tenant</span></span> |   <span data-ttu-id="4b387-181">\*.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-181">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="4b387-182">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="4b387-182">adventureworks.com</span></span> | <span data-ttu-id="4b387-183">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-183">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="4b387-184">若要配置基值和子域，请按照下述步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="4b387-184">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="4b387-185">在此示例中，我们将在 Woodgrove Bank 租 (customers.adatum.biz) 户) 客户配置一个域名和一个 (sbc1.customers.adatum.biz子。</span><span class="sxs-lookup"><span data-stu-id="4b387-185">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="4b387-186">使用 sbcX.customers.adatum.biz在任意租户中启用语音。</span><span class="sxs-lookup"><span data-stu-id="4b387-186">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span> <span data-ttu-id="4b387-187">sbcX 可以是任何唯一的有效字母数字主机名。</span><span class="sxs-lookup"><span data-stu-id="4b387-187">sbcX can be any unique and valid alphanumeric hostname.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="4b387-188">在任命者租户中注册基域名</span><span class="sxs-lookup"><span data-stu-id="4b387-188">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="4b387-189">**这些操作在任意租户中执行。**</span><span class="sxs-lookup"><span data-stu-id="4b387-189">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="4b387-190">确保一位运行者租户具有适当的权利</span><span class="sxs-lookup"><span data-stu-id="4b387-190">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="4b387-191">只有在你以全局管理员的形式登录到 Microsoft 365 管理中心时，才能添加新的域。</span><span class="sxs-lookup"><span data-stu-id="4b387-191">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="4b387-192">若要验证所拥有的角色，请登录到 Microsoft 365 管理中心 (， https://portal.office.com) 转到 **"用户**  >  **活动**用户"，然后验证你是否具有全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="4b387-192">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="4b387-193">若要详细了解管理员角色以及如何在 Microsoft 365 或 Office 365 中分配角色，请参阅 ["关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)"。</span><span class="sxs-lookup"><span data-stu-id="4b387-193">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="4b387-194">将基域添加到租户并验证</span><span class="sxs-lookup"><span data-stu-id="4b387-194">Add a base domain to the tenant and verify it</span></span>

1. <span data-ttu-id="4b387-195">在 Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **"添加域**。</span><span class="sxs-lookup"><span data-stu-id="4b387-195">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="4b387-196">在" **输入自行输入的域** "框中，键入基域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4b387-196">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="4b387-197">在以下示例中，基域*是customers.adatum.biz。*</span><span class="sxs-lookup"><span data-stu-id="4b387-197">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![显示"添加域"页面的屏幕截图](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="4b387-199">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-199">Click **Next**.</span></span>
4. <span data-ttu-id="4b387-200">在示例中，租户已经adatum.biz为经过验证的域名。</span><span class="sxs-lookup"><span data-stu-id="4b387-200">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="4b387-201">向导不要求您进行额外验证，因为customers.adatum.biz是已经注册的名称的子域。</span><span class="sxs-lookup"><span data-stu-id="4b387-201">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="4b387-202">但是，如果添加之前尚未验证的 FQDN，则需要完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="4b387-202">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="4b387-203">验证过程将在下 [面进行介绍](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="4b387-203">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![显示已验证的域名确认的屏幕截图](media/direct-routing-3-sbc-verify-domain.png)

5. <span data-ttu-id="4b387-205">单击 **"下**一步 **"，在"更新 DNS 设置"** 页面上， **选择"自己添加 DNS 记录"并** 单击"下 **一步**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-205">Click **Next**, and on the **Update DNS Settings** page, select **I'll add the DNS records myself** and click **Next**.</span></span>
6. <span data-ttu-id="4b387-206">在下一页上，除非 (想要对 Exchange、SharePoint 或 Skype for Business) 使用域名，否则清除所有值，单击**Finish\*\*\*\*"完成**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-206">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="4b387-207">请确保新域处于设置完整状态。</span><span class="sxs-lookup"><span data-stu-id="4b387-207">Make sure your new domain is in the Setup complete status.</span></span>

    ![屏幕截图显示域和设置状态为完成的域](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="4b387-209">激活域名</span><span class="sxs-lookup"><span data-stu-id="4b387-209">Activate the domain name</span></span>

<span data-ttu-id="4b387-210">注册域名后，需要通过添加至少一个 E1、E3 或 E5 许可用户并向 SIP 地址的 FQDN 部分分配 SIP 地址，并分配与所创建基域匹配的 FQDN 部分的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="4b387-210">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> <span data-ttu-id="4b387-211">许可证在域激活后可能会 (最长可能需要 24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="4b387-211">License can be revoked after the domain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="4b387-212">*请查看有关 [Microsoft 365 或 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) ，了解有关在 Microsoft 365 或 Office 365 组织中添加用户的详细信息。*</span><span class="sxs-lookup"><span data-stu-id="4b387-212">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="4b387-213">例如：test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-213">For example: test@customers.adatum.biz</span></span>

![基域激活页面的屏幕截图](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="4b387-215">在客户租户中注册子域名</span><span class="sxs-lookup"><span data-stu-id="4b387-215">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="4b387-216">需要为每位客户创建唯一的子域名。</span><span class="sxs-lookup"><span data-stu-id="4b387-216">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="4b387-217">在此示例中，将在具有默认sbc1.customers.adatum.biz域名的租户中创建一个woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="4b387-217">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="4b387-218">**以下所有操作都位于客户租户中。**</span><span class="sxs-lookup"><span data-stu-id="4b387-218">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="4b387-219">确保客户租户中具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="4b387-219">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="4b387-220">只有在你以全局管理员的形式登录到 Microsoft 365 管理中心时，才能添加新的域。</span><span class="sxs-lookup"><span data-stu-id="4b387-220">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="4b387-221">若要验证所拥有的角色，请登录到 Microsoft 365 管理中心 (， https://portal.office.com) 转到 **"用户**  >  **活动**用户"，然后验证你是否具有全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="4b387-221">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="4b387-222">若要详细了解管理员角色以及如何在 Microsoft 365 或 Office 365 中分配角色，请参阅 ["关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)"。</span><span class="sxs-lookup"><span data-stu-id="4b387-222">For more information about admin roles and how to assign a role in Microsoft 365 or Office 365, see [About admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="4b387-223">将子域添加到客户租户并验证</span><span class="sxs-lookup"><span data-stu-id="4b387-223">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="4b387-224">在 Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **"添加域**。</span><span class="sxs-lookup"><span data-stu-id="4b387-224">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="4b387-225">在" **输入您拥有的域"** 框中，键入此租户子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4b387-225">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="4b387-226">在下面的示例中，子域sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="4b387-226">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    !["添加域"页面的屏幕截图](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="4b387-228">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-228">Click **Next**.</span></span>
4. <span data-ttu-id="4b387-229">FQDN 从未在租户中注册过。</span><span class="sxs-lookup"><span data-stu-id="4b387-229">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="4b387-230">在下一步中，你需要验证域。</span><span class="sxs-lookup"><span data-stu-id="4b387-230">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="4b387-231">则 **改为选择"添加 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-231">Select **Add a TXT record instead**.</span></span> 

    !["验证域"页的屏幕截图](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="4b387-233">单击 **"** 下一步"，并注意生成的用于验证域名的 TXT 值。</span><span class="sxs-lookup"><span data-stu-id="4b387-233">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    !["验证域"页面上文本记录的屏幕截图](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="4b387-235">使用注册机号的 DNS 托管提供商步骤中的值创建 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="4b387-235">Create the TXT record with the value from the previous step in carrier's DNS hosting provider.</span></span>

    ![屏幕截图显示如何创建 TXT 记录](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="4b387-237">有关详细信息，请参阅在任何 [DNS 托管提供商处创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="4b387-237">For more information, refer to [Create DNS records at any DNS hosting provider](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="4b387-238">返回到客户的 Microsoft 365 管理中心，然后单击 **"验证**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-238">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="4b387-239">在下一页上，**选择我将自己添加 DNS 记录，然后单击"下\*\*\*\*一步**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-239">On the next page, select **I'll add the DNS records myself** and click **Next**.</span></span>

    !["更新 DNS 设置"页面上选项的屏幕截图](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="4b387-241">在"选择 **你的联机服务"页面上** ，清除所有选项，然后单击"下 **一步**"。</span><span class="sxs-lookup"><span data-stu-id="4b387-241">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    !["选择联机服务"页面的屏幕截图](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="4b387-243">在 **"更新 DNS 设置** "页 **上单击"完成** "。</span><span class="sxs-lookup"><span data-stu-id="4b387-243">Click **Finish** on the **Update DNS settings** page.</span></span>

    !["更新 DNS 设置"页面的屏幕截图](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="4b387-245">确保状态为**完成。**</span><span class="sxs-lookup"><span data-stu-id="4b387-245">Ensure that the status is **Setup complete**.</span></span> 
    
    ![显示设置完成状态的页面的屏幕截图](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="4b387-247">激活子域名</span><span class="sxs-lookup"><span data-stu-id="4b387-247">Activate the subdomain name</span></span>

<span data-ttu-id="4b387-248">注册域名后，需要通过添加至少一个用户并向 SIP 地址的 FQDN 部分分配一个 SIP 地址，该地址与客户租户中创建的子域相匹配。</span><span class="sxs-lookup"><span data-stu-id="4b387-248">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span> <span data-ttu-id="4b387-249">在子域激活后，可以从用户中撤销许可证 (最长可能需要 24 小时) 。</span><span class="sxs-lookup"><span data-stu-id="4b387-249">License can be revoked from user after the subdomain activation (it can take up to 24 hours).</span></span>

<span data-ttu-id="4b387-250">*请查看有关 [Microsoft 365 或 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) ，了解有关在 Microsoft 365 或 Office 365 组织中添加用户的详细信息。*</span><span class="sxs-lookup"><span data-stu-id="4b387-250">*Please review [Get help with Microsoft 365 or Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Microsoft 365 or Office 365 organizations.*</span></span>

<span data-ttu-id="4b387-251">例如：test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="4b387-251">For example: test@sbc1.customers.adatum.biz</span></span>

![子域页面的激活屏幕截图](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="4b387-253">创建中断和预订用户</span><span class="sxs-lookup"><span data-stu-id="4b387-253">Create a trunk and provision users</span></span>

<span data-ttu-id="4b387-254">在初始版本的直接路由中，Microsoft 需要将中断添加到使用 New-CSOnlinePSTNGateway 开发 () 中，前者才能使用该延时运行中。</span><span class="sxs-lookup"><span data-stu-id="4b387-254">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="4b387-255">但是，这未获得过于以下两个原因的原因：</span><span class="sxs-lookup"><span data-stu-id="4b387-255">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="4b387-256">**开展管理**。</span><span class="sxs-lookup"><span data-stu-id="4b387-256">**Overhead management**.</span></span> <span data-ttu-id="4b387-257">关闭加载或关闭 SBC，例如，更改某些参数，如启用或禁用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="4b387-257">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="4b387-258">更改端口需要运行 Set-CSOnlinePSTNGateway) 更改多个租户 (中的参数，但它实际上是相同的 SBC。</span><span class="sxs-lookup"><span data-stu-id="4b387-258">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="4b387-259">**开速处理**。</span><span class="sxs-lookup"><span data-stu-id="4b387-259">**Overhead processing**.</span></span> <span data-ttu-id="4b387-260">收集和监视中断运行状况数据 - SIP 选项是从相同的 SBC 和相同的物理中断收集的，降低路由数据处理速度。</span><span class="sxs-lookup"><span data-stu-id="4b387-260">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 
<span data-ttu-id="4b387-261">根据以下反馈，Microsoft 正提供新的逻辑来为客户租户预配置中文。</span><span class="sxs-lookup"><span data-stu-id="4b387-261">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="4b387-262">引入了以下两个新实体：</span><span class="sxs-lookup"><span data-stu-id="4b387-262">Two new entities were introduced:</span></span>
-    <span data-ttu-id="4b387-263">使用 Command New-CSOnlinePSTNGateway（例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true） 在运营商租户中注册的运营商截$true。</span><span class="sxs-lookup"><span data-stu-id="4b387-263">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.</span></span>

-    <span data-ttu-id="4b387-264">也有提示的 Trunk，该过程不需要注册。</span><span class="sxs-lookup"><span data-stu-id="4b387-264">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="4b387-265">这只是从承载商截断中添加的一个所需主机名。</span><span class="sxs-lookup"><span data-stu-id="4b387-265">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="4b387-266">它从交通线中发送其所有配置参数。</span><span class="sxs-lookup"><span data-stu-id="4b387-266">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="4b387-267">不需要在 PowerShell 中创建所传索的 Trunk，与运行商处插相关联基于 FQDN 名称 (请参阅下文) 。</span><span class="sxs-lookup"><span data-stu-id="4b387-267">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="4b387-268">**设置逻辑和示例**</span><span class="sxs-lookup"><span data-stu-id="4b387-268">**Provisioning logic and example**</span></span>

-    <span data-ttu-id="4b387-269">此参数条件仅需要使用 Set-CSOnlinePSTNGateway 命令设置和管理运行者将应用) 中等级 (数据转网) 部数据转网。</span><span class="sxs-lookup"><span data-stu-id="4b387-269">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="4b387-270">在上面的示例中，它adatum.biz;</span><span class="sxs-lookup"><span data-stu-id="4b387-270">In the example above it is adatum.biz;</span></span>
-    <span data-ttu-id="4b387-271">在客户租户中，该运行商只需向用户的语音路由策略添加已感过的中断中断，需要执行该操作。</span><span class="sxs-lookup"><span data-stu-id="4b387-271">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="4b387-272">无需为分类运行 New-CSOnlinePSTNGateway。</span><span class="sxs-lookup"><span data-stu-id="4b387-272">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="4b387-273">作为名称建议、收件或从承员 Trunk 的所有配置参数出来应答。</span><span class="sxs-lookup"><span data-stu-id="4b387-273">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="4b387-274">示例：</span><span class="sxs-lookup"><span data-stu-id="4b387-274">Examples:</span></span>
-    <span data-ttu-id="4b387-275">Customers.adatum.biz - 需要在参数租户中创建的具体中断。</span><span class="sxs-lookup"><span data-stu-id="4b387-275">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-    <span data-ttu-id="4b387-276">Sbc1.customers.adatum.biz， 在不需要在 PowerShell 中创建的客户租户中显示所得的中断。</span><span class="sxs-lookup"><span data-stu-id="4b387-276">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="4b387-277">只需在联机语音路由策略的客户租户策略中添加已分钟的中断的名称而不创建。</span><span class="sxs-lookup"><span data-stu-id="4b387-277">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="4b387-278">运营商需要设置 DNS 记录解析已被传送的 Trunk FQDN 到运营商 SBC IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4b387-278">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-    <span data-ttu-id="4b387-279">在运行者租户中 (应用) 于运行者应用的任何更改都将自动应用到该中断。</span><span class="sxs-lookup"><span data-stu-id="4b387-279">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="4b387-280">例如，运营商可以在运营商中更换 SIP 端口，此更改适用于所有 derive trunk。</span><span class="sxs-lookup"><span data-stu-id="4b387-280">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="4b387-281">配置中断的新逻辑简化了管理人员，因为无需转到每个租户，每台中线都更改参数。</span><span class="sxs-lookup"><span data-stu-id="4b387-281">New logic to configure the trunks simplifies the management as you don't need to go to every tenant and change the parameter on every trunk.</span></span>
-    <span data-ttu-id="4b387-282">这些选项仅发送到运行机器截断 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4b387-282">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="4b387-283">运行器中断的运行状况适用于所有已传输中断，可用于路由决策。</span><span class="sxs-lookup"><span data-stu-id="4b387-283">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="4b387-284">了解有关直接 [路由选项的详细信息](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。</span><span class="sxs-lookup"><span data-stu-id="4b387-284">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-    <span data-ttu-id="4b387-285">该运行商也可以截断运行运行器截断，所有已中断的中断也将失原。</span><span class="sxs-lookup"><span data-stu-id="4b387-285">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="4b387-286">**从以前的模型迁移到另一个运行器截断**</span><span class="sxs-lookup"><span data-stu-id="4b387-286">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="4b387-287">若要从实施从承载商托管模型的当前实现迁移到新模型，然后承家需要重新配置客户租户的中文。</span><span class="sxs-lookup"><span data-stu-id="4b387-287">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="4b387-288">使用 Remove-CSOnlinePSTNGateway (将 Trunk 保留在运行机租户的服务的中) -</span><span class="sxs-lookup"><span data-stu-id="4b387-288">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="4b387-289">强烈建议尽快迁移到新解决方案，以便我们将使用承员和密生的中断模型进行监视和配置。</span><span class="sxs-lookup"><span data-stu-id="4b387-289">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="4b387-290">请参阅 [有关配置在联系人头](#deploy-and-configure-the-sbc) 中发送子域的 FQDN 名称的 SBC 供应商的说明。</span><span class="sxs-lookup"><span data-stu-id="4b387-290">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

## <a name="considerations-for-setting-up-muti-tenant-failover"></a><span data-ttu-id="4b387-291">设置多租户故障转移的注意事项</span><span class="sxs-lookup"><span data-stu-id="4b387-291">Considerations for setting up muti-tenant failover</span></span> 

<span data-ttu-id="4b387-292">若要为多租户环境设置故障转移，需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b387-292">To set up failover for a multi-tenant environment, you'll need to do the following:</span></span>

- <span data-ttu-id="4b387-293">对于每个租户，为两个不同的 SBC 添加 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4b387-293">For each tenant, add the FQDNs for two different SBCs.</span></span>  <span data-ttu-id="4b387-294">例如：</span><span class="sxs-lookup"><span data-stu-id="4b387-294">For example:</span></span>

   <span data-ttu-id="4b387-295">customer1.sbc1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b387-295">customer1.sbc1.contoso.com</span></span> <br>
   <span data-ttu-id="4b387-296">customer1.sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b387-296">customer1.sbc2.contoso.com</span></span> <br>

- <span data-ttu-id="4b387-297">在在线语音路由策略中，指定这两个 SBC。</span><span class="sxs-lookup"><span data-stu-id="4b387-297">In the Online Voice Routing policies of the users, specify both SBCs.</span></span>  <span data-ttu-id="4b387-298">如果一个 SBC 失败，路由策略会将呼叫路由至第二个 SBC。</span><span class="sxs-lookup"><span data-stu-id="4b387-298">If one SBC fails, the routing policy will route calls to the second SBC.</span></span>


## <a name="see-also"></a><span data-ttu-id="4b387-299">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b387-299">See also</span></span>

[<span data-ttu-id="4b387-300">规划直接路由</span><span class="sxs-lookup"><span data-stu-id="4b387-300">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="4b387-301">配置直接路由</span><span class="sxs-lookup"><span data-stu-id="4b387-301">Configure Direct Routing</span></span>](direct-routing-configure.md)

