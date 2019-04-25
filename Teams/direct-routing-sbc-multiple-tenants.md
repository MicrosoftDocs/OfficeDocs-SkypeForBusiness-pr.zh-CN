---
title: 为多个租户配置会话边界控制器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 了解如何配置一个会话边界控制器 (SBC) 提供多个租户。
ms.openlocfilehash: 5338046724cc3768929b41dceb060aec1cee0bd6
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298545"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a><span data-ttu-id="5103b-103">为多个租户配置会话边界控制器</span><span class="sxs-lookup"><span data-stu-id="5103b-103">Configure a Session Border Controller for multiple tenants</span></span>

<span data-ttu-id="5103b-104">直接路由支持配置一个会话边界控制器 (SBC) 提供多个租户。</span><span class="sxs-lookup"><span data-stu-id="5103b-104">Direct Routing supports configuring one Session Border Controller (SBC) to serve multiple tenants.</span></span>

> [!NOTE]
> <span data-ttu-id="5103b-105">此方案适用于 Microsoft 合作伙伴和/或 PSTN 运营商，称为本文档后面的运营商。</span><span class="sxs-lookup"><span data-stu-id="5103b-105">This scenario is designed for Microsoft partners and/or PSTN carriers, referred to as carriers later in this document.</span></span> <span data-ttu-id="5103b-106">运营商销售向 Microsoft 工作组传递给他们的客户的电话服务。</span><span class="sxs-lookup"><span data-stu-id="5103b-106">A carrier sells telephony services delivered to Microsoft Teams to their customers.</span></span> 

<span data-ttu-id="5103b-107">运营商：</span><span class="sxs-lookup"><span data-stu-id="5103b-107">A carrier:</span></span>
- <span data-ttu-id="5103b-108">部署和管理其数据中心中的 SBC （客户不需要实现 SBC，和电话服务收到团队客户端中运营商）。</span><span class="sxs-lookup"><span data-stu-id="5103b-108">Deploys and manages an SBC in their datacenter (customers do not need to implement an SBC, and they receive telephony services from the carrier in the Teams client).</span></span>
- <span data-ttu-id="5103b-109">互连到多个租户 SBC。</span><span class="sxs-lookup"><span data-stu-id="5103b-109">Interconnects the SBC to multiple tenants.</span></span>
- <span data-ttu-id="5103b-110">为客户提供 PSTN 服务。</span><span class="sxs-lookup"><span data-stu-id="5103b-110">Provides PSTN services to customers.</span></span>
- <span data-ttu-id="5103b-111">管理呼叫质量端到端。</span><span class="sxs-lookup"><span data-stu-id="5103b-111">Manages call quality end to end.</span></span>
- <span data-ttu-id="5103b-112">PSTN 服务的单独的费用。</span><span class="sxs-lookup"><span data-stu-id="5103b-112">Charges separately for PSTN services.</span></span>

<span data-ttu-id="5103b-113">Microsoft 不管理运营商。</span><span class="sxs-lookup"><span data-stu-id="5103b-113">Microsoft does not manage carriers.</span></span> <span data-ttu-id="5103b-114">Microsoft 提供的 PBX （Microsoft 电话系统） 和团队客户端、 认证电话，并证实可用于 Microsoft 电话系统的 Sbc。</span><span class="sxs-lookup"><span data-stu-id="5103b-114">Microsoft offers a PBX (Microsoft Phone System) and a Teams client, certifies phones, and certifies SBCs that can be used with the Microsoft Phone System.</span></span> <span data-ttu-id="5103b-115">在选择之前运营商，请确保您选择已认证的 SBC 和可管理语音质量端到端。</span><span class="sxs-lookup"><span data-stu-id="5103b-115">Before choosing a carrier, please ensure that your choice has a certified SBC and can manage voice quality end to end.</span></span>

<span data-ttu-id="5103b-116">以下是配置方案的技术实现步骤。</span><span class="sxs-lookup"><span data-stu-id="5103b-116">The following are the technical implementation steps to configure the scenario.</span></span>

<span data-ttu-id="5103b-117">**仅运营商：**</span><span class="sxs-lookup"><span data-stu-id="5103b-117">**Carrier only:**</span></span>
1. <span data-ttu-id="5103b-118">部署的 SBC 并将其配置为承载方案根据[认证的 SBC 供应商提供的说明](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="5103b-118">Deploy the SBC and configure it for the hosting scenario according to the [instructions from the certified SBC vendors](#deploy-and-configure-the-sbc).</span></span>
2. <span data-ttu-id="5103b-119">在运营商租户中注册的基域名称并请求通配符证书。</span><span class="sxs-lookup"><span data-stu-id="5103b-119">Register a base domain name in the carrier tenant and request a wildcard certificate.</span></span>
3. <span data-ttu-id="5103b-120">为每个客户，是基本的域的一部分注册子域。</span><span class="sxs-lookup"><span data-stu-id="5103b-120">Register a subdomain for every customer, which is part of the base domain.</span></span>

<span data-ttu-id="5103b-121">**与客户全局管理员的运营商：**</span><span class="sxs-lookup"><span data-stu-id="5103b-121">**Carrier with a Customer Global Administrator:**</span></span>
1. <span data-ttu-id="5103b-122">添加到客户租户子域名称。</span><span class="sxs-lookup"><span data-stu-id="5103b-122">Add the subdomain name to the customer tenant.</span></span>
2. <span data-ttu-id="5103b-123">激活的子域名称。</span><span class="sxs-lookup"><span data-stu-id="5103b-123">Activate the subdomain name.</span></span>
3. <span data-ttu-id="5103b-124">配置中继到客户租户和设置用户从运营商。</span><span class="sxs-lookup"><span data-stu-id="5103b-124">Configure the trunk from the carrier to the customer tenant and provision users.</span></span>

<span data-ttu-id="5103b-125">*请确保您了解 DNS 基础知识和 Office 365 中管理的域名的方式。在进一步之前查看[获取 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="5103b-125">*Please make sure you understand DNS basics and how the domain name is managed in Office 365. Review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) before proceeding further.*</span></span>

## <a name="deploy-and-configure-the-sbc"></a><span data-ttu-id="5103b-126">部署并配置 SBC</span><span class="sxs-lookup"><span data-stu-id="5103b-126">Deploy and configure the SBC</span></span>

<span data-ttu-id="5103b-127">有关如何部署和配置 Sbc SBC 承载方案的详细步骤，请参阅 SBC 供应商的文档。</span><span class="sxs-lookup"><span data-stu-id="5103b-127">For the detailed steps on how to deploy and configure SBCs for an SBC hosting scenario, please refer to the SBC vendor's documentation.</span></span>

- <span data-ttu-id="5103b-128">**AudioCodes:**[直接路由配置说明](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，承载在"连接到 Microsoft 团队直接路由承载模型配置注释的 AudioCodes SBC"。 中所述情形 SBC 的配置</span><span class="sxs-lookup"><span data-stu-id="5103b-128">**AudioCodes:** [Direct Routing Configuration notes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), the configuration of the SBC hosting scenario described in “Connecting AudioCodes SBC to Microsoft Teams Direct Routing Hosting Model Configuration Note.”</span></span> 
- <span data-ttu-id="5103b-129">**功能区通信：** 请有关如何配置功能区核心系列 SBCs 文档的[功能区通信 SBC 核心 Microsoft 团队配置指南](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)和对此页[功能区最佳实践-配置的 Microsoft 团队直接路由 SBC 的运营商，参阅边缘](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span><span class="sxs-lookup"><span data-stu-id="5103b-129">**Ribbon Communications:**  Please refer to the [Ribbon Communications SBC Core Microsoft Teams Configuration Guide](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) for documentation on how to configure Ribbon Core Series SBCs and to this page [Ribbon Best Practice - Configuring Carriers for Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)</span></span>

> [!NOTE]
> <span data-ttu-id="5103b-130">请注意如何配置"联系人"标头。</span><span class="sxs-lookup"><span data-stu-id="5103b-130">Please pay attention to how to configure the “Contact” header.</span></span> <span data-ttu-id="5103b-131">联系人标头用于传入 invite 消息上查找客户租户。</span><span class="sxs-lookup"><span data-stu-id="5103b-131">The Contact header is used to find the customer tenant on the incoming invite message.</span></span> 

## <a name="register-a-base-domain-and-subdomains"></a><span data-ttu-id="5103b-132">注册基域和子域</span><span class="sxs-lookup"><span data-stu-id="5103b-132">Register a base domain and subdomains</span></span>

<span data-ttu-id="5103b-133">对于承载方案，您需要创建：</span><span class="sxs-lookup"><span data-stu-id="5103b-133">For the hosting scenario, you need to create:</span></span>
- <span data-ttu-id="5103b-134">一个归运营商的基域名称。</span><span class="sxs-lookup"><span data-stu-id="5103b-134">One base domain name owned by the carrier.</span></span>
- <span data-ttu-id="5103b-135">一部分中每个客户租户的基域名的子域。</span><span class="sxs-lookup"><span data-stu-id="5103b-135">A subdomain that is part of the base domain name in every customer tenant.</span></span>

<span data-ttu-id="5103b-136">在下面的示例：</span><span class="sxs-lookup"><span data-stu-id="5103b-136">In the following example:</span></span>
- <span data-ttu-id="5103b-137">Adatum 是通过提供 Internet 和电话服务提供若干个客户的运营商。</span><span class="sxs-lookup"><span data-stu-id="5103b-137">Adatum is a carrier that serves several customers by providing Internet and telephony services.</span></span>
- <span data-ttu-id="5103b-138">Woodgrove 银行、 Contoso 和 Adventure Works 是 Office 365 域但从 Adatum 接收的电话服务的三个客户。</span><span class="sxs-lookup"><span data-stu-id="5103b-138">Woodgrove Bank, Contoso, and Adventure Works are three customers that have Office 365 domains but receive the telephony services from Adatum.</span></span>

<span data-ttu-id="5103b-139">子域**必须**匹配发送到 Office 365 的邀请时将为客户和联系人标头中的 FQDN 配置中继的 FQDN 名称。</span><span class="sxs-lookup"><span data-stu-id="5103b-139">Subdomains **MUST** match the FQDN name of the trunk that will be configured for the customer and the FQDN in the Contact header when sending the Invite to Office 365.</span></span> 

<span data-ttu-id="5103b-140">当呼叫到达的 Office 365 直接路由接口时，接口将使用的联系人标头来查找租户其中应查找用户。</span><span class="sxs-lookup"><span data-stu-id="5103b-140">When a call arrives at the Office 365 Direct Routing interface, the interface uses the Contact header to find the tenant where the user should be looked up.</span></span> <span data-ttu-id="5103b-141">直接路由不使用电话号码查找上邀请，如某些客户可能具有非-DID 号码可以在多个租户中重叠。</span><span class="sxs-lookup"><span data-stu-id="5103b-141">Direct Routing does not use phone number lookup on the Invite, as some customers might have non-DID numbers that can overlap in several tenants.</span></span> <span data-ttu-id="5103b-142">因此，联系人标头中的 FQDN 名称都需要标识确切的租户，以查找用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="5103b-142">Therefore, the FQDN name in the Contact header is required to identify the exact tenant to look up the user by the phone number.</span></span>

<span data-ttu-id="5103b-143">*请查看有关在 Office 365 租户中创建域名[获取 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="5103b-143">*Please review  [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about creating domain names in Office 365 tenants.*</span></span>

<span data-ttu-id="5103b-144">下图汇总了对基域、 子域和联系人标头的要求。</span><span class="sxs-lookup"><span data-stu-id="5103b-144">The following diagram summarizes the requirements to base domain, subdomains, and Contact header.</span></span>

![基域、 子域，和联系人标头的要求](media/direct-routing-1-sbc-requirements.png)

<span data-ttu-id="5103b-146">SBC 需要证书进行身份验证连接。</span><span class="sxs-lookup"><span data-stu-id="5103b-146">The SBC requires a certificate to authenticate the connections.</span></span> <span data-ttu-id="5103b-147">运营商需要使用 SAN 中请求证书的 SBC 承载方案， \* \*.base_domain (例如， \*customers.adatum.biz)\*。</span><span class="sxs-lookup"><span data-stu-id="5103b-147">For the SBC hosting scenario, the carrier needs to request a certificate with SAN *\*.base_domain (for example, \*customers.adatum.biz)*.</span></span> <span data-ttu-id="5103b-148">此证书用于身份验证与单个 SBC 从提供的多个租户的连接。</span><span class="sxs-lookup"><span data-stu-id="5103b-148">This certificate can be used to authenticate connections to multiple tenants served from a single SBC.</span></span>

<span data-ttu-id="5103b-149">下表是一个配置的一个示例。</span><span class="sxs-lookup"><span data-stu-id="5103b-149">The following table is an example of one configuration.</span></span>


|<span data-ttu-id="5103b-150">新的域名</span><span class="sxs-lookup"><span data-stu-id="5103b-150">New domain name</span></span> |<span data-ttu-id="5103b-151">类型</span><span class="sxs-lookup"><span data-stu-id="5103b-151">Type</span></span>|<span data-ttu-id="5103b-152">注册</span><span class="sxs-lookup"><span data-stu-id="5103b-152">Registered</span></span>  |<span data-ttu-id="5103b-153">证书的 SBC SAN</span><span class="sxs-lookup"><span data-stu-id="5103b-153">Certificate SAN for SBC</span></span>  |<span data-ttu-id="5103b-154">在示例中的租户默认域</span><span class="sxs-lookup"><span data-stu-id="5103b-154">Tenant default domain in the example</span></span>  |<span data-ttu-id="5103b-155">SBC 必须提供联系人标头中发送给用户的呼叫时的 FQDN 名称</span><span class="sxs-lookup"><span data-stu-id="5103b-155">FQDN name that SBC must present in the Contact header when sending calls to users</span></span>|
|---------|---------|---------|---------|---------|---------|
|<span data-ttu-id="5103b-156">customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-156">customers.adatum.biz</span></span>|    <span data-ttu-id="5103b-157">基本</span><span class="sxs-lookup"><span data-stu-id="5103b-157">Base</span></span>     |     <span data-ttu-id="5103b-158">运营商租户中</span><span class="sxs-lookup"><span data-stu-id="5103b-158">In carrier tenant</span></span>  |    <span data-ttu-id="5103b-159">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-159">\*.customers.adatum.biz</span></span>  |   <span data-ttu-id="5103b-160">adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-160">adatum.biz</span></span>      |<span data-ttu-id="5103b-161">NA，这是服务租户，任何用户</span><span class="sxs-lookup"><span data-stu-id="5103b-161">NA, this is a service tenant, no users</span></span> |
|<span data-ttu-id="5103b-162">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-162">sbc1.customers.adatum.biz</span></span>|    <span data-ttu-id="5103b-163">子域</span><span class="sxs-lookup"><span data-stu-id="5103b-163">Subdomain</span></span>  |    <span data-ttu-id="5103b-164">客户租户中</span><span class="sxs-lookup"><span data-stu-id="5103b-164">In a customer tenant</span></span>  |    <span data-ttu-id="5103b-165">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-165">\*.customers.adatum.biz</span></span>  | <span data-ttu-id="5103b-166">woodgrovebank.us</span><span class="sxs-lookup"><span data-stu-id="5103b-166">woodgrovebank.us</span></span>  |  <span data-ttu-id="5103b-167">sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-167">sbc1.customers.adatum.biz</span></span>|
|<span data-ttu-id="5103b-168">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-168">sbc2.customers.adatum.biz</span></span>  |   <span data-ttu-id="5103b-169">子域</span><span class="sxs-lookup"><span data-stu-id="5103b-169">Subdomain</span></span> | <span data-ttu-id="5103b-170">客户租户中</span><span class="sxs-lookup"><span data-stu-id="5103b-170">In a customer tenant</span></span>   |   <span data-ttu-id="5103b-171">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-171">\*.customers.adatum.biz</span></span>   |<span data-ttu-id="5103b-172">contoso.com</span><span class="sxs-lookup"><span data-stu-id="5103b-172">contoso.com</span></span>   |<span data-ttu-id="5103b-173">sbc2.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-173">sbc2.customers.adatum.biz</span></span> |
|<span data-ttu-id="5103b-174">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-174">sbc3.customers.adatum.biz</span></span> |   <span data-ttu-id="5103b-175">子域</span><span class="sxs-lookup"><span data-stu-id="5103b-175">Subdomain</span></span> | <span data-ttu-id="5103b-176">客户租户中</span><span class="sxs-lookup"><span data-stu-id="5103b-176">In a customer tenant</span></span> |   <span data-ttu-id="5103b-177">\*。 customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-177">\*.customers.adatum.biz</span></span>  |  <span data-ttu-id="5103b-178">adventureworks.com</span><span class="sxs-lookup"><span data-stu-id="5103b-178">adventureworks.com</span></span> | <span data-ttu-id="5103b-179">sbc3.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-179">sbc3.customers.adatum.biz</span></span> |
||         |         |         |         |         |

<span data-ttu-id="5103b-180">若要配置的基本和子域，请按照如下所述的步骤。</span><span class="sxs-lookup"><span data-stu-id="5103b-180">To configure the base and subdomains, please follow the steps described below.</span></span> <span data-ttu-id="5103b-181">在示例中，我们将配置的基域名称 (customers.adatum.biz) 和一个客户 (sbc1.customers.adatum.biz Woodgrove 银行租户中) 的子域。</span><span class="sxs-lookup"><span data-stu-id="5103b-181">In the example, we will configure a base domain name (customers.adatum.biz) and a subdomain for one customer (sbc1.customers.adatum.biz in Woodgrove Bank tenant).</span></span>

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a><span data-ttu-id="5103b-182">在运营商租户中注册的基域名称</span><span class="sxs-lookup"><span data-stu-id="5103b-182">Register a base domain name in the carrier tenant</span></span>

<span data-ttu-id="5103b-183">**运营商租户中执行这些操作。**</span><span class="sxs-lookup"><span data-stu-id="5103b-183">**These actions are performed in the carrier tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a><span data-ttu-id="5103b-184">确保您的运营商租户中具有相应权限</span><span class="sxs-lookup"><span data-stu-id="5103b-184">Ensure that you have appropriate rights in the carrier tenant</span></span>

<span data-ttu-id="5103b-185">如果您登录到 Office 365 管理中心以全局管理员，您可以仅添加新域。</span><span class="sxs-lookup"><span data-stu-id="5103b-185">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="5103b-186">若要验证您具有的角色，请登录到 Microsoft 365 管理中心 (https://portal.office.com)，请转到**用户** > **活动用户**，然后验证是否已全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="5103b-186">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="5103b-187">有关管理角色和如何为 Office 365 中的一个角色分配的详细信息，请参阅[有关 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="5103b-187">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a><span data-ttu-id="5103b-188">向租户添加基域并验证其</span><span class="sxs-lookup"><span data-stu-id="5103b-188">Add a base domain to the tenant and verify it</span></span>

1.  <span data-ttu-id="5103b-189">在 Microsoft 365 管理中心，转到**安装程序** > **域** > **添加域**。</span><span class="sxs-lookup"><span data-stu-id="5103b-189">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2.  <span data-ttu-id="5103b-190">在**输入您拥有的域**框中，键入基域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5103b-190">In the **Enter a domain you own** box, type the FQDN of the base domain.</span></span> <span data-ttu-id="5103b-191">以下示例中，在基域名是*customers.adatum.biz*。</span><span class="sxs-lookup"><span data-stu-id="5103b-191">In the following example, the base domain is *customers.adatum.biz*.</span></span>

    ![添加基域名](media/direct-routing-2-sbc-add-domain.png)

3. <span data-ttu-id="5103b-193">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5103b-193">Click **Next**.</span></span>
4. <span data-ttu-id="5103b-194">在此示例中，租户已经有 adatum.biz 与已验证的域的名称。</span><span class="sxs-lookup"><span data-stu-id="5103b-194">In the example, the tenant already has adatum.biz as a verified domain name.</span></span> <span data-ttu-id="5103b-195">因为 customers.adatum.biz 是已注册名称子域，向导将不要求的其他验证。</span><span class="sxs-lookup"><span data-stu-id="5103b-195">The wizard will not ask for additional verification because customers.adatum.biz is a subdomain for the already registered name.</span></span> <span data-ttu-id="5103b-196">但是，如果您添加 FQDN 的尚未验证之前，您需要经过验证的过程。</span><span class="sxs-lookup"><span data-stu-id="5103b-196">However, if you add an FQDN that has not been verified before, you will need to go through the process of verification.</span></span> <span data-ttu-id="5103b-197">验证的过程是[如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。</span><span class="sxs-lookup"><span data-stu-id="5103b-197">The process of verification is [described below](#add-a-subdomain-to-the-customer-tenant-and-verify-it).</span></span>

    ![确认的已验证的域名](media/direct-routing-3-sbc-verify-domain.png)

5.  <span data-ttu-id="5103b-199">单击**下一步**，和在**更新 DNS 设置**页上，选择**将自己添加的 DNS 记录**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5103b-199">Click **Next**, and on the **Update DNS Settings** page, select **I’ll add the DNS records myself** and click **Next**.</span></span>
6.  <span data-ttu-id="5103b-200">在下一页上，清除所有值 （除非您想要用于业务 Exchange、 SharePoint、 或团队/Skype 的域名），单击**下一步**，，然后单击**完成时间**。</span><span class="sxs-lookup"><span data-stu-id="5103b-200">On the next page, clear all values (unless you want to use the domain name for Exchange, SharePoint, or Teams/Skype for Business), click **Next**, and then click **Finish**.</span></span> <span data-ttu-id="5103b-201">请确保您的新域中的安装程序完成状态。</span><span class="sxs-lookup"><span data-stu-id="5103b-201">Make sure your new domain is in the Setup complete status.</span></span>

    ![域显示状态的安装程序完成](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a><span data-ttu-id="5103b-203">激活的域名</span><span class="sxs-lookup"><span data-stu-id="5103b-203">Activate the domain name</span></span>

<span data-ttu-id="5103b-204">已注册的域名，您需要激活通过添加至少一个 E1，E3 或 E5 许可后用户和分配与 SIP 的 FQDN 部分的 SIP 地址的地址匹配创建的基域名。</span><span class="sxs-lookup"><span data-stu-id="5103b-204">After you have registered a domain name, you need to activate it by adding at least one E1, E3, or E5 licensed user and assigning a SIP address with the FQDN portion of the SIP address matching the created base domain.</span></span> 

<span data-ttu-id="5103b-205">*请查看有关将用户添加 Office 365 租户中[获取帮助与 Office 365 域](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="5103b-205">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="5103b-206">例如： test@customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-206">For example: test@customers.adatum.biz</span></span>

![基域名激活页](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a><span data-ttu-id="5103b-208">在客户租户中注册的子域名称</span><span class="sxs-lookup"><span data-stu-id="5103b-208">Register a subdomain name in a customer tenant</span></span>

<span data-ttu-id="5103b-209">您需要创建每个客户的唯一子域名称。</span><span class="sxs-lookup"><span data-stu-id="5103b-209">You will need to create a unique subdomain name for every customer.</span></span> <span data-ttu-id="5103b-210">本示例中，我们将使用默认域名称 woodgrovebank.us 创建子域 sbc1.customers.adatum.biz 租户中。</span><span class="sxs-lookup"><span data-stu-id="5103b-210">In this example, we will create a subdomain sbc1.customers.adatum.biz in a tenant with the default domain name woodgrovebank.us.</span></span>

<span data-ttu-id="5103b-211">**客户租户中是以下所有操作。**</span><span class="sxs-lookup"><span data-stu-id="5103b-211">**All actions below are in the customer tenant.**</span></span>

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a><span data-ttu-id="5103b-212">确保您客户租户中具有相应权限</span><span class="sxs-lookup"><span data-stu-id="5103b-212">Ensure that you have appropriate rights in the customer tenant</span></span>

<span data-ttu-id="5103b-213">如果您登录到 Office 365 管理中心以全局管理员，您可以仅添加新域。</span><span class="sxs-lookup"><span data-stu-id="5103b-213">You can only add new domains if you signed in to the Office 365 admin center as a Global Administrator.</span></span> 

<span data-ttu-id="5103b-214">若要验证您具有的角色，请登录到 Microsoft 365 管理中心 (https://portal.office.com)，请转到**用户** > **活动用户**，然后验证是否已全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="5103b-214">To validate the role you have, please sign in to the Microsoft 365 admin center (https://portal.office.com), go to **Users** > **Active Users**, and then verify that you have a Global Administrator role.</span></span> 

<span data-ttu-id="5103b-215">有关管理角色和如何为 Office 365 中的一个角色分配的详细信息，请参阅[有关 Office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="5103b-215">For more information about admin roles and how to assign a role in Office 365, see [About Office 365 admin roles](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a><span data-ttu-id="5103b-216">将子域添加到客户租户并确认它</span><span class="sxs-lookup"><span data-stu-id="5103b-216">Add a subdomain to the customer tenant and verify it</span></span>
1. <span data-ttu-id="5103b-217">在 Microsoft 365 管理中心，转到**安装程序** > **域** > **添加域**。</span><span class="sxs-lookup"><span data-stu-id="5103b-217">In the Microsoft 365 admin center, go to **Setup** > **Domains** > **Add domain**.</span></span>
2. <span data-ttu-id="5103b-218">在**输入您拥有的域**框中，键入此租户的子域的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5103b-218">In the **Enter a domain you own** box, type the FQDN of the subdomain for this tenant.</span></span> <span data-ttu-id="5103b-219">在下面的示例中，子域是 sbc1.customers.adatum.biz。</span><span class="sxs-lookup"><span data-stu-id="5103b-219">In the example below, the subdomain is sbc1.customers.adatum.biz.</span></span>

    ![添加客户子域](media/direct-routing-5-sbc-add-customer-domain.png)

3. <span data-ttu-id="5103b-221">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="5103b-221">Click **Next**.</span></span>
4. <span data-ttu-id="5103b-222">从不已在租户中注册的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5103b-222">The FQDN has never been registered in the tenant.</span></span> <span data-ttu-id="5103b-223">下一步，您需要验证域。</span><span class="sxs-lookup"><span data-stu-id="5103b-223">In the next step, you will need to verify the domain.</span></span> <span data-ttu-id="5103b-224">选择**添加 TXT 记录改为**。</span><span class="sxs-lookup"><span data-stu-id="5103b-224">Select **Add a TXT record instead**.</span></span> 

    ![在验证域页上的选项](media/direct-routing-6-sbc-verify-customer-domain.png)

5. <span data-ttu-id="5103b-226">单击**下一步**，并注意生成验证的域名的 TXT 值。</span><span class="sxs-lookup"><span data-stu-id="5103b-226">Click **Next**, and note the TXT value generated to verify the domain name.</span></span>

    ![在验证域页上的文本记录](media/direct-routing-7-sbc-verify-domain-txt.png)

6. <span data-ttu-id="5103b-228">值从运营商的 DNS 宿主提供商的上一步中创建的 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="5103b-228">Create the TXT record with the value from the previous step in carrier’s DNS hosting provider.</span></span>

    ![在运营商的 DNS 宿主提供商中创建的 TXT 记录](media/direct-routing-8-sbc-txt-record.png)

    <span data-ttu-id="5103b-230">有关详细信息，请参阅[Office 365 任何 DNS 宿主提供商处创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。</span><span class="sxs-lookup"><span data-stu-id="5103b-230">For more information, refer to [Create DNS records at any DNS hosting provider for Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).</span></span>

7. <span data-ttu-id="5103b-231">返回到客户的 Microsoft 365 管理中心，并单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="5103b-231">Go back to the customer's Microsoft 365 admin center and click **Verify**.</span></span> 
8. <span data-ttu-id="5103b-232">在下一页上，选择**将自己添加的 DNS 记录**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5103b-232">On the next page, select **I’ll add the DNS records myself** and click **Next**.</span></span>

    ![在更新 DNS 设置页上的选项](media/direct-routing-9-sbc-update-dns.png)

9. <span data-ttu-id="5103b-234">在**选择联机服务**页上，清除所有选项，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="5103b-234">On the **Choose your online services** page, clear all options and click **Next**.</span></span>

    ![选择您联机服务页](media/direct-routing-10-sbc-choose-services.png)

10. <span data-ttu-id="5103b-236">在**更新 DNS 设置**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="5103b-236">Click **Finish** on the **Update DNS settings** page.</span></span>

    ![更新 DNS 设置页](media/direct-routing-11-sbc-update-dns-finish.png)

11. <span data-ttu-id="5103b-238">确保状态为**安装程序完成**。</span><span class="sxs-lookup"><span data-stu-id="5103b-238">Ensure that the status is **Setup complete**.</span></span> 
    
    ![显示状态的安装程序完成页](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a><span data-ttu-id="5103b-240">激活子域名</span><span class="sxs-lookup"><span data-stu-id="5103b-240">Activate the subdomain name</span></span>

<span data-ttu-id="5103b-241">注册域名后，您需要激活通过添加至少一个用户和分配匹配客户租户中创建的子域的 SIP 地址的 FQDN 部分的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="5103b-241">After you register a domain name, you need to activate it by adding at least one user and assign a SIP address with the FQDN portion of the SIP address matching the created subdomain in the customer tenant.</span></span>

<span data-ttu-id="5103b-242">*请查看有关将用户添加 Office 365 租户中[获取帮助与 Office 365 域](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*</span><span class="sxs-lookup"><span data-stu-id="5103b-242">*Please review [Get help with Office 365 domains](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) for more information about adding users in Office 365 tenants.*</span></span>

<span data-ttu-id="5103b-243">例如： test@sbc1.customers.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="5103b-243">For example: test@sbc1.customers.adatum.biz</span></span>

![子域页上的激活](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a><span data-ttu-id="5103b-245">创建中继和设置用户</span><span class="sxs-lookup"><span data-stu-id="5103b-245">Create a trunk and provision users</span></span>

> [!NOTE]
> <span data-ttu-id="5103b-246">根据我们在技术的应用程序中收到的反馈，Microsoft 可能会更改简化过程客户租户中创建中继的过程。</span><span class="sxs-lookup"><span data-stu-id="5103b-246">Based on feedback we received in the Technical Adoption Program, Microsoft might change the process of creating trunks in the customer tenants to simplify the process.</span></span> <span data-ttu-id="5103b-247">请观看此页上的文档更新，并按照 Microsoft 技术社区博客 （英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5103b-247">Please watch the documentation updates on this page and follow the Microsoft Technical Community blogs for further information.</span></span> 

<span data-ttu-id="5103b-248">使用新建 CSonlinePSTNGateway 命令的客户域中创建中继。</span><span class="sxs-lookup"><span data-stu-id="5103b-248">Create a trunk in the customer domain using the New-CSonlinePSTNGateway command.</span></span> <span data-ttu-id="5103b-249">中继 FQDN**必须**匹配子域为客户创建。</span><span class="sxs-lookup"><span data-stu-id="5103b-249">The trunk FQDN **MUST** match the subdomain created for the customer.</span></span>

<span data-ttu-id="5103b-250">例如：</span><span class="sxs-lookup"><span data-stu-id="5103b-250">For example:</span></span>

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

<span data-ttu-id="5103b-251">创建中继时, 可能会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="5103b-251">When creating the trunk, you may receive the following error message:</span></span>

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

<span data-ttu-id="5103b-252">请允许域注册和激活以复制，然后重试一些的时间。</span><span class="sxs-lookup"><span data-stu-id="5103b-252">Please allow some time for domain registration and activation to replicate and try again.</span></span>

<span data-ttu-id="5103b-253">为用户提供的电话号码和配置语音路由。</span><span class="sxs-lookup"><span data-stu-id="5103b-253">Provision users with the phone numbers and configure voice routing.</span></span>

<span data-ttu-id="5103b-254">新建 CSOnlinePSTNGateway 的详细信息，设置用户和配置语音路由，请参阅[配置直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="5103b-254">For more information on the New-CSOnlinePSTNGateway, provisioning users, and configuring voice routing, please refer to [Configure Direct Routing](direct-routing-configure.md).</span></span>


<span data-ttu-id="5103b-255">请参阅上配置联系人标头中发送子域的 FQDN 名称的[SBC 供应商的说明](#deploy-and-configure-the-sbc)。</span><span class="sxs-lookup"><span data-stu-id="5103b-255">Please refer to the [SBC vendor instructions](#deploy-and-configure-the-sbc) on configuring sending the FQDN name of subdomains in the Contact header.</span></span>

