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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 了解如何配置一个会话边界控制器 (SBC) 来为多个租户提供服务。
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290466"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="fd5cb-103">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="fd5cb-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="fd5cb-104">直接路由支持配置一个会话边界控制器 (SBC) 来为多个租户提供服务。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="fd5cb-105">此方案专为 Microsoft 合作伙伴和/或 PSTN 运营商设计, 本文档后面称为运营商。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="fd5cb-106">运营商将向 Microsoft 团队提供的电话服务销售给客户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="fd5cb-107">运营商:</span><span class="sxs-lookup"><span data-stu-id="fd5cb-107">A carrier:</span></span>
- <span data-ttu-id="fd5cb-108">在其数据中心中部署和管理 SBC (客户无需实现 SBC, 并且它们从团队客户端的运营商处接收电话服务)。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="fd5cb-109">将 SBC 互连到多个租户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="fd5cb-110">向客户提供 PSTN 服务。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="fd5cb-111">管理端到端的通话质量。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="fd5cb-112">为 PSTN 服务单独收取费用。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="fd5cb-113">Microsoft 不管理运营商。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="fd5cb-114">Microsoft 提供了一个 PBX (Microsoft Phone System) 和一个团队客户端, 验证手机, 并验证可与 Microsoft Phone 系统配合使用的 SBCs。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="fd5cb-115">选择运营商之前, 请确保你的选择具有已认证的 SBC, 并且可以管理语音质量端到端。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="fd5cb-116">下面是配置方案的技术实现步骤。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="fd5cb-117">**仅限运营商:**</span><span class="sxs-lookup"><span data-stu-id="fd5cb-117">**Carrier only:**</span></span>
1. <span data-ttu-id="fd5cb-118">根据[认证的 SBC 供应商的说明](#deploy-and-configure-the-sbc), 为托管方案部署 SBC 并配置它。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="fd5cb-119">在运营商租户中注册一个基本域名, 并请求一个通配符证书。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="fd5cb-120">为每个客户注册子域, 这是基本域的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="fd5cb-121">**具有客户全局管理员的运营商:**</span><span class="sxs-lookup"><span data-stu-id="fd5cb-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="fd5cb-122">将子域名称添加到客户租户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="fd5cb-123">激活子域名。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="fd5cb-124">将运营商的主干配置为客户租户和预配用户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="fd5cb-125">*请确保了解 DNS 基础知识以及如何在 Office 365 中管理域名。在继续操作之前, 请查看[获取有关 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="fd5cb-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="fd5cb-126">部署和配置 SBC</span><span class="sxs-lookup"><span data-stu-id="fd5cb-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="fd5cb-127">有关如何针对 SBC 托管方案部署和配置 SBCs 的详细步骤, 请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="fd5cb-128">**AudioCodes:**[直接路由配置说明](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), 在 "将 AudioCodes SBC 连接到 Microsoft 团队直接路由托管模型配置说明" 中介绍的 SBC 托管方案的配置。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="fd5cb-129">**功能区通信:** 请参阅[功能区通信 SBC 核心 Microsoft 团队配置指南](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe), 了解有关如何配置功能区内核系列 SBCs 和此页面[功能区的文档最佳做法-配置 Microsoft 团队直接路由 SBC 的运营商边缘](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="fd5cb-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="fd5cb-130">请注意如何配置 "联系人" 标头。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="fd5cb-131">联系人页眉用于查找传入邀请消息上的客户租户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="fd5cb-132">注册基础域和子域</span><span class="sxs-lookup"><span data-stu-id="fd5cb-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="fd5cb-133">对于托管方案, 你需要创建:</span><span class="sxs-lookup"><span data-stu-id="fd5cb-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="fd5cb-134">运营商拥有的一个基本域名。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="fd5cb-135">作为每个客户租户中的基本域名的一部分的子域。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="fd5cb-136">在以下示例中:</span><span class="sxs-lookup"><span data-stu-id="fd5cb-136">In the following example:</span></span>
- <span data-ttu-id="fd5cb-137">Adatum 是通过提供 Internet 和电话服务来为多个客户提供服务的运营商。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="fd5cb-138">Woodgrove Bank、Contoso 和艾德公司都是具有 Office 365 域但接收来自 Adatum 的电话服务的三个客户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="fd5cb-139">在将邀请发送到 Office 365 时, 子域**必须**与将为客户配置的主干的 FQDN 名称匹配, 并将 Fqdn 与联系人标头中的 fqdn 相匹配。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="fd5cb-140">当呼叫到达 Office 365 直接路由接口时, 该接口使用联系人标题查找应在其中查找用户的租户。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="fd5cb-141">直接路由不会在邀请上使用电话号码查找, 因为某些客户可能具有在多个租户中可能会重叠的非号码。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="fd5cb-142">因此, 联系人标头中的 FQDN 名称是标识确切的租户以通过电话号码查找用户所必需的。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="fd5cb-143">*有关在 Office 365 租户中创建域名的详细信息, 请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="fd5cb-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="fd5cb-144">下图总结了基本域、子域和联系人标头的要求。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![基本域、子域和联系人标题的要求](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="fd5cb-146">SBC 需要证书才能对连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="fd5cb-147">对于 SBC 托管方案, 运营商需要使用\* \*base_domain (例如, \*customers.adatum.biz)\* 申请一个证书。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="fd5cb-148">此证书可用于对从单个 SBC 提供服务的多个租户的连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="fd5cb-149">下表是一个配置示例。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="fd5cb-150">新域名</span><span class="sxs-lookup"><span data-stu-id="fd5cb-150">New domain name</span></span> |<span data-ttu-id="fd5cb-151">类型</span><span class="sxs-lookup"><span data-stu-id="fd5cb-151">Type</span></span>|<span data-ttu-id="fd5cb-152">注册</span><span class="sxs-lookup"><span data-stu-id="fd5cb-152">Registered</span></span>  |<span data-ttu-id="fd5cb-153">适用于 SBC 的证书 SAN</span><span class="sxs-lookup"><span data-stu-id="fd5cb-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="fd5cb-154">示例中的租户默认域</span><span class="sxs-lookup"><span data-stu-id="fd5cb-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="fd5cb-155">当向用户发送呼叫时, SBC 必须在联系人标头中出现的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="fd5cb-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="fd5cb-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-156">customers.adatum.biz</span></span>|    <span data-ttu-id="fd5cb-157">Base64</span><span class="sxs-lookup"><span data-stu-id="fd5cb-157">Base</span></span>     |     <span data-ttu-id="fd5cb-158">在运营商租户中</span><span class="sxs-lookup"><span data-stu-id="fd5cb-158">In carrier tenant</span></span>  |    <span data-ttu-id="fd5cb-159">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="fd5cb-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-160">adatum.biz</span></span>      |<span data-ttu-id="fd5cb-161">NA, 这是一个服务租户, 没有用户</span><span class="sxs-lookup"><span data-stu-id="fd5cb-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="fd5cb-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="fd5cb-163">子域</span><span class="sxs-lookup"><span data-stu-id="fd5cb-163">Subdomain</span></span>  |    <span data-ttu-id="fd5cb-164">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="fd5cb-164">In a customer tenant</span></span>  |    <span data-ttu-id="fd5cb-165">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="fd5cb-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="fd5cb-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="fd5cb-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="fd5cb-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="fd5cb-169">子域</span><span class="sxs-lookup"><span data-stu-id="fd5cb-169">Subdomain</span></span> | <span data-ttu-id="fd5cb-170">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="fd5cb-170">In a customer tenant</span></span>   |   <span data-ttu-id="fd5cb-171">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="fd5cb-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="fd5cb-172">contoso.com</span></span>   |<span data-ttu-id="fd5cb-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="fd5cb-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="fd5cb-175">子域</span><span class="sxs-lookup"><span data-stu-id="fd5cb-175">Subdomain</span></span> | <span data-ttu-id="fd5cb-176">在客户租户中</span><span class="sxs-lookup"><span data-stu-id="fd5cb-176">In a customer tenant</span></span> |   <span data-ttu-id="fd5cb-177">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="fd5cb-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="fd5cb-178">adventureworks.com</span></span> | <span data-ttu-id="fd5cb-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="fd5cb-180">要配置基本和子域, 请按照下面所述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="fd5cb-181">在此示例中, 我们将为一个客户 (Woodgrove Bank 租户中的 sbc1.customers.adatum.biz) 配置一个基本域名 (customers.adatum.biz) 和一个子域。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="fd5cb-182">在运营商租户中注册基本域名</span><span class="sxs-lookup"><span data-stu-id="fd5cb-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="fd5cb-183">**这些操作在运营商租户中执行。**</span><span class="sxs-lookup"><span data-stu-id="fd5cb-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="fd5cb-184">确保您在运营商租户中具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="fd5cb-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="fd5cb-185">如果您作为全局管理员登录到 Microsoft 365 管理中心, 则只能添加新域。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-185">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="fd5cb-186">https://portal.office.com)若要验证你拥有的角色, 请登录到 Microsoft 365 管理中心 (请转到 "**用户** > **活动用户**", 然后验证你是否拥有全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="fd5cb-187">有关管理员角色以及如何在 Office 365 中分配角色的详细信息, 请参阅[关于 office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="fd5cb-188">将基础域添加到租户并验证它</span><span class="sxs-lookup"><span data-stu-id="fd5cb-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="fd5cb-189">在 Microsoft 365 管理中心中, 转到 "**设置** > **域** > **添加域**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="fd5cb-190">在 "**输入您拥有的域**" 框中, 键入基础域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="fd5cb-191">在以下示例中, 基本域为*customers.adatum.biz*。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![添加基础域](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="fd5cb-193">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-193">Click **Next**.</span></span>
4. <span data-ttu-id="fd5cb-194">在此示例中, 租户已将 adatum.biz 作为已验证的域名。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="fd5cb-195">由于 customers.adatum.biz 是已注册名称的子域, 该向导不会要求进行其他验证。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="fd5cb-196">但是, 如果你添加以前未验证的 FQDN, 你将需要完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="fd5cb-197">验证过程[如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![确认已验证的域名](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="fd5cb-199">单击 "**下一步**", 然后在 "**更新 DNS 设置**" 页面上, 选择**我将自己添加 DNS 记录**, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="fd5cb-200">在下一页上, 清除所有值 (除非要使用 Exchange、SharePoint 或团队/Skype for Business 的域名), 单击 "**下一步**", 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="fd5cb-201">请确保您的新域处于 "设置完成" 状态。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![显示 "设置" 状态的域已完成](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="fd5cb-203">激活域名</span><span class="sxs-lookup"><span data-stu-id="fd5cb-203">Activate the domain name</span></span>

<span data-ttu-id="fd5cb-204">注册域名后, 您需要通过至少添加一个 E1、E3 或 E5 许可用户来激活它, 并使用与创建的基础域匹配的 SIP 地址的 FQDN 部分分配 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="fd5cb-205">*有关在 Office 365 租户中添加用户的详细信息, 请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="fd5cb-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="fd5cb-206">例如: test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-206">For example: test@customers.adatum.biz</span></span>

![基础域激活页面](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="fd5cb-208">在客户租户中注册子域名称</span><span class="sxs-lookup"><span data-stu-id="fd5cb-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="fd5cb-209">你将需要为每个客户创建唯一的子域名称。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="fd5cb-210">在此示例中, 我们将在具有默认域名称的租户中创建一个子域 sbc1.customers.adatum.biz woodgrovebank.us。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="fd5cb-211">**以下所有操作均位于客户租户中。**</span><span class="sxs-lookup"><span data-stu-id="fd5cb-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="fd5cb-212">确保你在客户租户中具有适当的权限</span><span class="sxs-lookup"><span data-stu-id="fd5cb-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="fd5cb-213">如果您作为全局管理员登录到 Microsoft 365 管理中心, 则只能添加新域。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-213">You can only add new domains if you signed in to the Microsoft 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="fd5cb-214">https://portal.office.com)若要验证你拥有的角色, 请登录到 Microsoft 365 管理中心 (请转到 "**用户** > **活动用户**", 然后验证你是否拥有全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="fd5cb-215">有关管理员角色以及如何在 Office 365 中分配角色的详细信息, 请参阅[关于 office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="fd5cb-216">将子域添加到客户租户并验证它</span><span class="sxs-lookup"><span data-stu-id="fd5cb-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="fd5cb-217">在 Microsoft 365 管理中心中, 转到 "**设置** > **域** > **添加域**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="fd5cb-218">在 "**输入你拥有的域**" 框中, 键入此租户的子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="fd5cb-219">在下面的示例中, 子域是 sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![添加客户子域](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="fd5cb-221">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-221">Click **Next**.</span></span>
4. <span data-ttu-id="fd5cb-222">FQDN 从未在租户中注册。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="fd5cb-223">在下一步中, 你将需要验证域。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="fd5cb-224">选择 "**添加 TXT 记录**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-224">Select **Add a TXT record instead**.</span></span> 

    !["验证域" 页面上的选项](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="fd5cb-226">单击 "**下一步**", 记下生成的 TXT 值以验证域名。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    !["验证域" 页面上的文本记录](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="fd5cb-228">利用运营商的 DNS 托管提供商的上一步中的值创建 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![在运营商的 DNS 托管提供商中创建 TXT 记录](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="fd5cb-230">有关详细信息, 请参阅[在任何 dns 托管提供商处为 Office 365 创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="fd5cb-231">返回客户的 Microsoft 365 管理中心, 然后单击 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="fd5cb-232">在下一页上, 选择 "**我将自行添加 DNS 记录**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    !["更新 DNS 设置" 页面上的选项](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="fd5cb-234">在 "**选择联机服务**" 页面上, 清除 "所有选项", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    !["选择您的在线服务" 页面](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="fd5cb-236">在 "**更新 DNS 设置**" 页面上单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    !["更新 DNS 设置" 页面](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="fd5cb-238">确保状态为 "**设置完成**"。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![显示设置完成状态的页面](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="fd5cb-240">激活子域名</span><span class="sxs-lookup"><span data-stu-id="fd5cb-240">Activate the subdomain name</span></span>

<span data-ttu-id="fd5cb-241">注册域名后, 您需要通过至少添加一个用户并使用与客户租户中创建的子域相匹配的 SIP 地址的 FQDN 部分来激活该域名。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="fd5cb-242">*有关在 Office 365 租户中添加用户的详细信息, 请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="fd5cb-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="fd5cb-243">例如: test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="fd5cb-243">For example: test@sbc1.customers.adatum.biz</span></span>

!["子域" 页面的激活](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="fd5cb-245">创建主干和预配用户</span><span class="sxs-lookup"><span data-stu-id="fd5cb-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="fd5cb-246">根据我们在技术采纳计划中收到的反馈, Microsoft 可能会更改在客户租户中创建中继的过程以简化流程。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="fd5cb-247">请观看此页面上的文档更新, 并关注 Microsoft 技术社区博客, 了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="fd5cb-248">使用 "新建-CSonlinePSTNGateway" 命令在 customer 域中创建主干。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="fd5cb-249">主干 FQDN**必须**与为客户创建的子域匹配。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="fd5cb-250">例如：</span><span class="sxs-lookup"><span data-stu-id="fd5cb-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="fd5cb-251">创建主干时, 你可能会收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="fd5cb-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="fd5cb-252">请留出一些时间进行域注册和激活以进行复制, 然后重试。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="fd5cb-253">为用户预配电话号码和配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="fd5cb-254">有关新 CSOnlinePSTNGateway、预配用户和配置语音路由的详细信息, 请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="fd5cb-255">请参阅[SBC 供应商的说明](#deploy-and-configure-the-sbc), 了解如何在联系人标头中配置子域的 FQDN 名称。</span><span class="sxs-lookup"><span data-stu-id="fd5cb-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

