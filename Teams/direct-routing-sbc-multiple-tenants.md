---
title: 为多个租户配置会话边界控制器
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
description: 了解如何配置一个会话边界控制器（SBC）来为多个租户提供服务。
ms.openlocfilehash: 5009f600af0d9632ed94b544e75f791d9ecead85
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572131"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="ebde8-103">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="ebde8-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="ebde8-104">直接路由支持配置一个会话边界控制器（SBC）来为多个租户提供服务。</span><span class="sxs-lookup"><span data-stu-id="ebde8-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="ebde8-105">此方案专为 Microsoft 合作伙伴和/或 PSTN 运营商设计，本文档后面称为运营商。</span><span class="sxs-lookup"><span data-stu-id="ebde8-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="ebde8-106">运营商将向 Microsoft 团队提供的电话服务销售给客户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="ebde8-107">运营商：</span><span class="sxs-lookup"><span data-stu-id="ebde8-107">A carrier:</span></span>
- <span data-ttu-id="ebde8-108">在其数据中心中部署和管理 SBC （客户无需实现 SBC，并且它们从团队客户端的运营商处接收电话服务）。</span><span class="sxs-lookup"><span data-stu-id="ebde8-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="ebde8-109">将 SBC 互连到多个租户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="ebde8-110">向客户提供 PSTN 服务。</span><span class="sxs-lookup"><span data-stu-id="ebde8-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="ebde8-111">管理端到端的通话质量。</span><span class="sxs-lookup"><span data-stu-id="ebde8-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="ebde8-112">为 PSTN 服务单独收取费用。</span><span class="sxs-lookup"><span data-stu-id="ebde8-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="ebde8-113">Microsoft 不管理运营商。</span><span class="sxs-lookup"><span data-stu-id="ebde8-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="ebde8-114">Microsoft 提供了一个 PBX （Microsoft Phone System）和一个团队客户端，验证手机，并验证可与 Microsoft Phone 系统配合使用的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="ebde8-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="ebde8-115">选择运营商之前，请确保你的选择具有已认证的 SBC，并且可以管理语音质量端到端。</span><span class="sxs-lookup"><span data-stu-id="ebde8-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="ebde8-116">下面是配置方案的技术实现步骤。</span><span class="sxs-lookup"><span data-stu-id="ebde8-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="ebde8-117">**仅限运营商：**</span><span class="sxs-lookup"><span data-stu-id="ebde8-117">**Carrier only:**</span></span>
1. <span data-ttu-id="ebde8-118">根据[认证的 SBC 供应商的说明](#deploy-and-configure-the-sbc)，为托管方案部署 SBC 并配置它。</span><span class="sxs-lookup"><span data-stu-id="ebde8-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="ebde8-119">在运营商租户中注册一个基本域名，并请求一个通配符证书。</span><span class="sxs-lookup"><span data-stu-id="ebde8-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="ebde8-120">为每个客户注册子域，这是基本域的一部分。</span><span class="sxs-lookup"><span data-stu-id="ebde8-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="ebde8-121">**具有客户全局管理员的运营商：**</span><span class="sxs-lookup"><span data-stu-id="ebde8-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="ebde8-122">将子域名称添加到客户租户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="ebde8-123">激活子域名。</span><span class="sxs-lookup"><span data-stu-id="ebde8-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="ebde8-124">将运营商的主干配置为客户租户和预配用户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="ebde8-125">*请确保了解 DNS 基础知识以及如何在 Office 365 中管理域名。在继续操作之前，请查看[获取有关 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="ebde8-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="ebde8-126">部署和配置 SBC</span><span class="sxs-lookup"><span data-stu-id="ebde8-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="ebde8-127">有关如何针对 SBC 托管方案部署和配置 SBCs 的详细步骤，请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="ebde8-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="ebde8-128">**AudioCodes：** [直接路由配置说明](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，在 "将 AudioCodes SBC 连接到 Microsoft 团队直接路由托管模型配置说明" 中所述的 SBC 托管方案的配置。</span><span class="sxs-lookup"><span data-stu-id="ebde8-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="ebde8-129">**Oracle：** [直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，在 "Microsoft" 部分中介绍了 SBC 托管方案的配置。</span><span class="sxs-lookup"><span data-stu-id="ebde8-129">**Oracle:** [Direct Routing Configuration notes](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), the configuration of the SBC hosting scenario is described in the "Microsoft" section.</span></span> 
- <span data-ttu-id="ebde8-130">**功能区通信：** 请参阅[功能区通信 SBC 核心 Microsoft 团队配置指南](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)，了解有关如何配置功能区内核系列 SBCs 和此页面[功能区的文档最佳做法-配置 Microsoft 团队直接路由 SBC 的运营商边缘](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="ebde8-130">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>
- <span data-ttu-id="ebde8-131">**TE-系统（anynode）：** 请在[TE 系统社区页面](https://community.te-systems.de/)上注册，了解有关如何为多个租户配置 anynode SBC 的文档和示例。</span><span class="sxs-lookup"><span data-stu-id="ebde8-131">**TE-Systems (anynode):**  Please register on the [TE-Systems Community page](https://community.te-systems.de/) for documentation and examples on how to configure anynode SBC for multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="ebde8-132">请注意如何配置 "联系人" 标头。</span><span class="sxs-lookup"><span data-stu-id="ebde8-132">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="ebde8-133">联系人页眉用于查找传入邀请消息上的客户租户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-133">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="ebde8-134">注册基础域和子域</span><span class="sxs-lookup"><span data-stu-id="ebde8-134">Register a base domain and subdomains</span></span>

<span data-ttu-id="ebde8-135">对于托管方案，你需要创建：</span><span class="sxs-lookup"><span data-stu-id="ebde8-135">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="ebde8-136">运营商拥有的一个基本域名。</span><span class="sxs-lookup"><span data-stu-id="ebde8-136">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="ebde8-137">作为每个客户租户中的基本域名的一部分的子域。</span><span class="sxs-lookup"><span data-stu-id="ebde8-137">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="ebde8-138">在以下示例中：</span><span class="sxs-lookup"><span data-stu-id="ebde8-138">In the following example:</span></span>
- <span data-ttu-id="ebde8-139">Adatum 是通过提供 Internet 和电话服务来为多个客户提供服务的运营商。</span><span class="sxs-lookup"><span data-stu-id="ebde8-139">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="ebde8-140">Woodgrove Bank、Contoso 和艾德公司都是具有 Office 365 域但接收来自 Adatum 的电话服务的三个客户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-140">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="ebde8-141">在将邀请发送到 Office 365 时，子域**必须**与将为客户配置的主干的 FQDN 名称匹配，并将 Fqdn 与联系人标头中的 fqdn 相匹配。</span><span class="sxs-lookup"><span data-stu-id="ebde8-141">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="ebde8-142">当呼叫到达 Office 365 直接路由接口时，该接口使用联系人标题查找应在其中查找用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ebde8-142">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="ebde8-143">直接路由不会在邀请上使用电话号码查找，因为某些客户可能具有在多个租户中可能会重叠的非号码。</span><span class="sxs-lookup"><span data-stu-id="ebde8-143">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="ebde8-144">因此，联系人标头中的 FQDN 名称是标识确切的租户以通过电话号码查找用户所必需的。</span><span class="sxs-lookup"><span data-stu-id="ebde8-144">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="ebde8-145">*有关在 Office 365 租户中创建域名的详细信息，请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="ebde8-145">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="ebde8-146">下图总结了基本域、子域和联系人标头的要求。</span><span class="sxs-lookup"><span data-stu-id="ebde8-146">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![显示域和联系人标题要求的图表](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="ebde8-148">SBC 需要证书才能对连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ebde8-148">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="ebde8-149">对于 SBC 托管方案，运营商需要使用\* \*base_domain （例如\*customers.adatum.biz）\* 申请一个证书。</span><span class="sxs-lookup"><span data-stu-id="ebde8-149">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*.customers.adatum.biz)*.</span></span> <span data-ttu-id="ebde8-150">此证书可用于对从单个 SBC 提供服务的多个租户的连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ebde8-150">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>


<span data-ttu-id="ebde8-151">下表是一个配置示例。</span><span class="sxs-lookup"><span data-stu-id="ebde8-151">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="ebde8-152">新域名</span><span class="sxs-lookup"><span data-stu-id="ebde8-152">New domain name</span></span> |<span data-ttu-id="ebde8-153">类型</span><span class="sxs-lookup"><span data-stu-id="ebde8-153">Type</span></span>|<span data-ttu-id="ebde8-154">注册</span><span class="sxs-lookup"><span data-stu-id="ebde8-154">Registered</span></span>  |<span data-ttu-id="ebde8-155">适用于 SBC 的证书 SAN</span><span class="sxs-lookup"><span data-stu-id="ebde8-155">Certificate SAN for SBC</span></span>  |<span data-ttu-id="ebde8-156">示例中的租户默认域</span><span class="sxs-lookup"><span data-stu-id="ebde8-156">Tenant default domain in the example</span></span>  |<span data-ttu-id="ebde8-157">当向用户发送呼叫时，SBC 必须在联系人标头中出现的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="ebde8-157">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="ebde8-158">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-158">customers.adatum.biz</span></span>|    <span data-ttu-id="ebde8-159">Base64</span><span class="sxs-lookup"><span data-stu-id="ebde8-159">Base</span></span>     |     <span data-ttu-id="ebde8-160">在运营商租户中</span><span class="sxs-lookup"><span data-stu-id="ebde8-160">In carrier tenant</span></span>  |    <span data-ttu-id="ebde8-161">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-161">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="ebde8-162">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-162">adatum.biz</span></span>      |<span data-ttu-id="ebde8-163">NA，这是一个服务租户，没有用户</span><span class="sxs-lookup"><span data-stu-id="ebde8-163">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="ebde8-164">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-164">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="ebde8-165">子域</span><span class="sxs-lookup"><span data-stu-id="ebde8-165">Subdomain</span></span>  |    <span data-ttu-id="ebde8-166">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="ebde8-166">In a customer tenant</span></span>  |    <span data-ttu-id="ebde8-167">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-167">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="ebde8-168">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="ebde8-168">woodgrovebank.us</span></span>  |  <span data-ttu-id="ebde8-169">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-169">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="ebde8-170">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-170">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="ebde8-171">子域</span><span class="sxs-lookup"><span data-stu-id="ebde8-171">Subdomain</span></span> | <span data-ttu-id="ebde8-172">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="ebde8-172">In a customer tenant</span></span>   |   <span data-ttu-id="ebde8-173">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-173">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="ebde8-174">contoso.com</span><span class="sxs-lookup"><span data-stu-id="ebde8-174">contoso.com</span></span>   |<span data-ttu-id="ebde8-175">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-175">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="ebde8-176">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-176">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="ebde8-177">子域</span><span class="sxs-lookup"><span data-stu-id="ebde8-177">Subdomain</span></span> | <span data-ttu-id="ebde8-178">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="ebde8-178">In a customer tenant</span></span> |   <span data-ttu-id="ebde8-179">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-179">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="ebde8-180">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="ebde8-180">adventureworks.com</span></span> | <span data-ttu-id="ebde8-181">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-181">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="ebde8-182">要配置基本和子域，请按照下面所述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="ebde8-182">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="ebde8-183">在此示例中，我们将为一个客户（Woodgrove Bank 租户中的 sbc1.customers.adatum.biz）配置一个基本域名（customers.adatum.biz）和一个子域。</span><span class="sxs-lookup"><span data-stu-id="ebde8-183">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

> [!NOTE]
> <span data-ttu-id="ebde8-184">使用 sbcX.customers.adatum.biz 启用运营商租户中的语音。</span><span class="sxs-lookup"><span data-stu-id="ebde8-184">Use sbcX.customers.adatum.biz to enable voice in the carrier tenant.</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="ebde8-185">在运营商租户中注册基本域名</span><span class="sxs-lookup"><span data-stu-id="ebde8-185">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="ebde8-186">**这些操作在运营商租户中执行。**</span><span class="sxs-lookup"><span data-stu-id="ebde8-186">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="ebde8-187">确保您在运营商租户中具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="ebde8-187">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="ebde8-188">如果您作为全局管理员登录到 Microsoft 365 管理中心，则只能添加新域。</span><span class="sxs-lookup"><span data-stu-id="ebde8-188">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="ebde8-189">https://portal.office.com)若要验证你拥有的角色，请登录到 Microsoft 365 管理中心（请转到 "**用户** > **活动用户**"，然后验证你是否拥有全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ebde8-189">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="ebde8-190">有关管理员角色以及如何在 Office 365 中分配角色的详细信息，请参阅[关于 office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="ebde8-190">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="ebde8-191">将基础域添加到租户并验证它</span><span class="sxs-lookup"><span data-stu-id="ebde8-191">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="ebde8-192">在 Microsoft 365 管理中心中，转到 "**设置** > **域** > **添加域**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-192">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="ebde8-193">在 "**输入您拥有的域**" 框中，键入基础域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ebde8-193">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="ebde8-194">在以下示例中，基本域为*customers.adatum.biz*。</span><span class="sxs-lookup"><span data-stu-id="ebde8-194">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![显示 "添加域" 页面的屏幕截图](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="ebde8-196">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-196">Click **Next**.</span></span>
4. <span data-ttu-id="ebde8-197">在此示例中，租户已将 adatum.biz 作为已验证的域名。</span><span class="sxs-lookup"><span data-stu-id="ebde8-197">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="ebde8-198">由于 customers.adatum.biz 是已注册名称的子域，该向导不会要求进行其他验证。</span><span class="sxs-lookup"><span data-stu-id="ebde8-198">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="ebde8-199">但是，如果你添加以前未验证的 FQDN，你将需要完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="ebde8-199">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="ebde8-200">验证过程[如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="ebde8-200">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![显示验证的域名确认的屏幕截图](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="ebde8-202">单击 "**下一步**"，然后在 "**更新 DNS 设置**" 页面上，选择**我将自己添加 DNS 记录**，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-202">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="ebde8-203">在下一页上，清除所有值（除非要使用 Exchange、SharePoint 或团队/Skype for Business 的域名），单击 "**下一步**"，然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-203">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="ebde8-204">请确保您的新域处于 "设置完成" 状态。</span><span class="sxs-lookup"><span data-stu-id="ebde8-204">Make sure your new domain is in the Setup complete status.</span></span>

    ![显示 "设置" 状态为 "完成" 的域的屏幕截图](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="ebde8-206">激活域名</span><span class="sxs-lookup"><span data-stu-id="ebde8-206">Activate the domain name</span></span>

<span data-ttu-id="ebde8-207">注册域名后，您需要通过至少添加一个 E1、E3 或 E5 许可用户来激活它，并使用与创建的基础域匹配的 SIP 地址的 FQDN 部分分配 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="ebde8-207">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="ebde8-208">*有关在 Office 365 租户中添加用户的详细信息，请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="ebde8-208">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="ebde8-209">例如： test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-209">For example: test@customers.adatum.biz</span></span>

![基本域激活页面的屏幕截图](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="ebde8-211">在客户租户中注册子域名称</span><span class="sxs-lookup"><span data-stu-id="ebde8-211">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="ebde8-212">你将需要为每个客户创建唯一的子域名称。</span><span class="sxs-lookup"><span data-stu-id="ebde8-212">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="ebde8-213">在此示例中，我们将在具有默认域名称的租户中创建一个子域 sbc1.customers.adatum.biz woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="ebde8-213">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="ebde8-214">**以下所有操作均位于客户租户中。**</span><span class="sxs-lookup"><span data-stu-id="ebde8-214">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="ebde8-215">确保你在客户租户中具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="ebde8-215">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="ebde8-216">如果您作为全局管理员登录到 Microsoft 365 管理中心，则只能添加新域。</span><span class="sxs-lookup"><span data-stu-id="ebde8-216">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="ebde8-217">https://portal.office.com)若要验证你拥有的角色，请登录到 Microsoft 365 管理中心（请转到 "**用户** > **活动用户**"，然后验证你是否拥有全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ebde8-217">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="ebde8-218">有关管理员角色以及如何在 Office 365 中分配角色的详细信息，请参阅[关于 office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="ebde8-218">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="ebde8-219">将子域添加到客户租户并验证它</span><span class="sxs-lookup"><span data-stu-id="ebde8-219">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="ebde8-220">在 Microsoft 365 管理中心中，转到 "**设置** > **域** > **添加域**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-220">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="ebde8-221">在 "**输入你拥有的域**" 框中，键入此租户的子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ebde8-221">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="ebde8-222">在下面的示例中，子域是 sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="ebde8-222">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    !["添加域" 页面的屏幕截图](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="ebde8-224">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-224">Click **Next**.</span></span>
4. <span data-ttu-id="ebde8-225">FQDN 从未在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="ebde8-225">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="ebde8-226">在下一步中，你将需要验证域。</span><span class="sxs-lookup"><span data-stu-id="ebde8-226">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="ebde8-227">选择 "**添加 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-227">Select **Add a TXT record instead**.</span></span> 

    !["验证域" 页面的屏幕截图](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="ebde8-229">单击 "**下一步**"，记下生成的 TXT 值以验证域名。</span><span class="sxs-lookup"><span data-stu-id="ebde8-229">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    !["验证域" 页面上的文本记录的屏幕截图](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="ebde8-231">利用运营商的 DNS 托管提供商的上一步中的值创建 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="ebde8-231">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![显示创建 TXT 记录的屏幕截图](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="ebde8-233">有关详细信息，请参阅[在任何 dns 托管提供商处为 Office 365 创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="ebde8-233">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="ebde8-234">返回客户的 Microsoft 365 管理中心，然后单击 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-234">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="ebde8-235">在下一页上，选择 "**我将自行添加 DNS 记录**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-235">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    !["更新 DNS 设置" 页面上的选项的屏幕截图](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="ebde8-237">在 "**选择联机服务**" 页面上，清除 "所有选项"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-237">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    !["选择您的在线服务" 页面的屏幕截图](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="ebde8-239">在 "**更新 DNS 设置**" 页面上单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-239">Click **Finish** on the **Update DNS settings** page.</span></span>

    !["更新 DNS 设置" 页面的屏幕截图](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="ebde8-241">确保状态为 "**设置完成**"。</span><span class="sxs-lookup"><span data-stu-id="ebde8-241">Ensure that the status is **Setup complete**.</span></span> 
    
    ![显示设置完成状态的页面的屏幕截图](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="ebde8-243">激活子域名</span><span class="sxs-lookup"><span data-stu-id="ebde8-243">Activate the subdomain name</span></span>

<span data-ttu-id="ebde8-244">注册域名后，您需要通过至少添加一个用户并使用与客户租户中创建的子域相匹配的 SIP 地址的 FQDN 部分来激活该域名。</span><span class="sxs-lookup"><span data-stu-id="ebde8-244">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="ebde8-245">*有关在 Office 365 租户中添加用户的详细信息，请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="ebde8-245">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="ebde8-246">例如： test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="ebde8-246">For example: test@sbc1.customers.adatum.biz</span></span>

!["子域" 页面的激活屏幕截图](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="ebde8-248">创建主干和预配用户</span><span class="sxs-lookup"><span data-stu-id="ebde8-248">Create a trunk and provision users</span></span>

<span data-ttu-id="ebde8-249">通过直接路由的初始发布，Microsoft 需要使用新的 CSOnlinePSTNGateway 将主干添加到每个服务的租户（客户租户）。</span><span class="sxs-lookup"><span data-stu-id="ebde8-249">With the initial release of Direct Routing, Microsoft required a trunk to be added to each served tenant (customer tenant) using New-CSOnlinePSTNGateway.</span></span>

<span data-ttu-id="ebde8-250">但是，这种情况尚未证明最佳原因：</span><span class="sxs-lookup"><span data-stu-id="ebde8-250">However, this has not proved optimal for two reasons:</span></span>
 
- <span data-ttu-id="ebde8-251">**开销管理**。</span><span class="sxs-lookup"><span data-stu-id="ebde8-251">**Overhead management**.</span></span> <span data-ttu-id="ebde8-252">例如，卸载或排出 SBC 将更改某些参数，例如启用或禁用媒体绕过。</span><span class="sxs-lookup"><span data-stu-id="ebde8-252">Offloading or draining an SBC, for example, changes some parameters, like enabling or disabling media bypass.</span></span> <span data-ttu-id="ebde8-253">更改端口需要更改多个租户中的参数（通过运行 Set-CSOnlinePSTNGateway），但实际上是同一个 SBC。</span><span class="sxs-lookup"><span data-stu-id="ebde8-253">Changing the port requires changing parameters in multiple tenants (by running Set-CSOnlinePSTNGateway), but it is in fact the same SBC.</span></span> 

-  <span data-ttu-id="ebde8-254">**开销处理**。</span><span class="sxs-lookup"><span data-stu-id="ebde8-254">**Overhead processing**.</span></span> <span data-ttu-id="ebde8-255">收集和监视从多个逻辑中继收集的干线运行状况数据 SIP 选项，实际上，同一 SBC 和相同的物理干线会减缓路由数据的处理。</span><span class="sxs-lookup"><span data-stu-id="ebde8-255">Gathering and monitoring trunk health data - SIP options collected from multiple logical trunks that are, in reality, the same SBC and the same physical trunk, slows down processing of the routing data.</span></span>
 

<span data-ttu-id="ebde8-256">根据此反馈，Microsoft 将引入新的逻辑来为客户租户设置中继。</span><span class="sxs-lookup"><span data-stu-id="ebde8-256">Based on this feedback, Microsoft is bringing in a new logic to provision the trunks for the customer tenants.</span></span>

<span data-ttu-id="ebde8-257">引入了两个新实体：</span><span class="sxs-lookup"><span data-stu-id="ebde8-257">Two new entities were introduced:</span></span>
-   <span data-ttu-id="ebde8-258">使用命令 New-CSOnlinePSTNGateway 在运营商租户中注册的运营商中继，例如，CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignallingport 5068-ForwardPAI $true。</span><span class="sxs-lookup"><span data-stu-id="ebde8-258">A carrier trunk registered in the carrier tenant using the command New-CSOnlinePSTNGateway, for example New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignallingport 5068 -ForwardPAI $true.</span></span>

-   <span data-ttu-id="ebde8-259">派生的主干，不需要注册。</span><span class="sxs-lookup"><span data-stu-id="ebde8-259">A derived trunk, that does not require registration.</span></span> <span data-ttu-id="ebde8-260">它只是从运营商主干中添加的所需主机名。</span><span class="sxs-lookup"><span data-stu-id="ebde8-260">It is simply a desired host name added in from of the carrier trunk.</span></span> <span data-ttu-id="ebde8-261">它从载波主干派生其所有配置参数。</span><span class="sxs-lookup"><span data-stu-id="ebde8-261">It derives all of its configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="ebde8-262">派生的主干不需要在 PowerShell 中创建，并且与运营商主干的关联基于 FQDN 名称（请参阅下面的详细信息）。</span><span class="sxs-lookup"><span data-stu-id="ebde8-262">The derived trunk doesn't need to be created in PowerShell, and the association with the carrier trunk is based on the FQDN name (see details below).</span></span>

<span data-ttu-id="ebde8-263">**预配逻辑和示例**</span><span class="sxs-lookup"><span data-stu-id="ebde8-263">**Provisioning logic and example**</span></span>

-   <span data-ttu-id="ebde8-264">运营商仅需要使用 Set-CSOnlinePSTNGateway 命令设置和管理单个中继（运营公司域中的载波干线）。</span><span class="sxs-lookup"><span data-stu-id="ebde8-264">Carriers only need to set up and manage a single trunk  (carrier trunk in the carrier domain), using the Set-CSOnlinePSTNGateway command.</span></span> <span data-ttu-id="ebde8-265">在上面的示例中，它是 adatum.biz;</span><span class="sxs-lookup"><span data-stu-id="ebde8-265">In the example above it is adatum.biz;</span></span>
-   <span data-ttu-id="ebde8-266">在客户租户中，运营商只需将派生的干线 FQDN 添加到用户的语音路由策略。</span><span class="sxs-lookup"><span data-stu-id="ebde8-266">In the customer tenant, the carrier need only to add the derived trunk FQDN to the voice routing policies of the users.</span></span> <span data-ttu-id="ebde8-267">无需为主干运行新的 CSOnlinePSTNGateway。</span><span class="sxs-lookup"><span data-stu-id="ebde8-267">There is no need to run New-CSOnlinePSTNGateway for a trunk.</span></span>
-    <span data-ttu-id="ebde8-268">顾名思义，派生的主干会继承或派生载波主干中的所有配置参数。</span><span class="sxs-lookup"><span data-stu-id="ebde8-268">The derived trunk, as the name suggests, inherits or derives all the configuration parameters from the carrier trunk.</span></span> <span data-ttu-id="ebde8-269">说明</span><span class="sxs-lookup"><span data-stu-id="ebde8-269">Examples:</span></span>
-   <span data-ttu-id="ebde8-270">Customers.adatum.biz-需要在运营商租户中创建的运营商主干。</span><span class="sxs-lookup"><span data-stu-id="ebde8-270">Customers.adatum.biz – the carrier trunk which needs to be created in the carrier tenant.</span></span>
-   <span data-ttu-id="ebde8-271">Sbc1.customers.adatum.biz-不需要在 PowerShell 中创建的客户租户中的派生主干。</span><span class="sxs-lookup"><span data-stu-id="ebde8-271">Sbc1.customers.adatum.biz – the derived trunk in a customer tenant that does not need to be created in PowerShell.</span></span>  <span data-ttu-id="ebde8-272">您只需在 "联机语音路由策略" 中添加派生的主干的名称，而无需创建它。</span><span class="sxs-lookup"><span data-stu-id="ebde8-272">You can simply add the name of the derived trunk in the customer tenant in the online voice routing policy without creating it.</span></span>
-   <span data-ttu-id="ebde8-273">运营商将需要将派生的干线 FQDN 的 DNS 记录设置为载波 SBC ip 地址。</span><span class="sxs-lookup"><span data-stu-id="ebde8-273">Carrier will need to setup DNS record resolving derived trunk FQDN to carrier SBC ip address.</span></span>

-   <span data-ttu-id="ebde8-274">对载体主干（在运营商租户上）所做的任何更改都将自动应用于派生的中继。</span><span class="sxs-lookup"><span data-stu-id="ebde8-274">Any changes made on a carrier trunk (on carrier tenant) is automatically applied to derived trunks.</span></span> <span data-ttu-id="ebde8-275">例如，运营商可以更改载波主干上的 SIP 端口，此更改将应用于所有派生的中继。</span><span class="sxs-lookup"><span data-stu-id="ebde8-275">For example, carriers can change an SIP port on the carrier trunk, and this change applies to all derived trunks.</span></span> <span data-ttu-id="ebde8-276">用于配置中继的新逻辑可简化管理，因为无需转到每个租户并在每个主干上更改参数。</span><span class="sxs-lookup"><span data-stu-id="ebde8-276">New logic to configure the trunks simplifies the management as you don’t need to go to every tenant and change the parameter on every trunk.</span></span>
-   <span data-ttu-id="ebde8-277">选项仅发送给载波中继 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ebde8-277">The options are sent only to the carrier trunk FQDN.</span></span> <span data-ttu-id="ebde8-278">载波干线的运行状况将应用于所有派生的中继，并用于路由决策。</span><span class="sxs-lookup"><span data-stu-id="ebde8-278">The health status of the carrier trunk is applied to all derived trunks and is used for routing decisions.</span></span> <span data-ttu-id="ebde8-279">了解有关[直接路由选项](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebde8-279">Find out more about [Direct Routing options](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).</span></span>
-   <span data-ttu-id="ebde8-280">运营商可以排出载波主干，所有衍生的中继也将排出。</span><span class="sxs-lookup"><span data-stu-id="ebde8-280">The carrier can drain the carrier trunk, and all derived trunks will be drained as well.</span></span> 
 

<span data-ttu-id="ebde8-281">**从以前的模型迁移到运营商主干**</span><span class="sxs-lookup"><span data-stu-id="ebde8-281">**Migration from the previous model to the carrier trunk**</span></span>
 
<span data-ttu-id="ebde8-282">对于从运营商托管模型的当前实现迁移到新模型，运营商将需要为客户租户重新配置中继。</span><span class="sxs-lookup"><span data-stu-id="ebde8-282">For migration from the current implementation of the carrier hosted model to the new model, the carriers will need to reconfigure the trunks for customer tenants.</span></span> <span data-ttu-id="ebde8-283">使用 Remove-CSOnlinePSTNGateway （离开运营商租户中的主干）从客户租户中删除中继</span><span class="sxs-lookup"><span data-stu-id="ebde8-283">Remove the trunks from the customer tenants using Remove-CSOnlinePSTNGateway (leaving the trunk in the carrier tenant)-</span></span>

<span data-ttu-id="ebde8-284">我们强烈建议您尽快迁移到新的解决方案，因为我们将使用运营商和衍生中继模型增强监控和资源调配。</span><span class="sxs-lookup"><span data-stu-id="ebde8-284">We highly encourage migrating to the new solution as soon as possible as we will be enhancing monitoring and provisioning using the carrier and derived trunk model.</span></span>
 

<span data-ttu-id="ebde8-285">请参阅[SBC 供应商的说明](#deploy-and-configure-the-sbc)，了解如何在联系人标头中配置子域的 FQDN 名称。</span><span class="sxs-lookup"><span data-stu-id="ebde8-285">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

