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
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>为多个租户配置会话边界控制器

直接路由支持配置一个会话边界控制器 (SBC) 来为多个租户提供服务。

> [!NOTE]
> 此方案专为 Microsoft 合作伙伴和/或 PSTN 运营商设计, 本文档后面称为运营商。 运营商将向 Microsoft 团队提供的电话服务销售给客户。 

运营商:
- 在其数据中心中部署和管理 SBC (客户无需实现 SBC, 并且它们从团队客户端的运营商处接收电话服务)。
- 将 SBC 互连到多个租户。
- 向客户提供 PSTN 服务。
- 管理端到端的通话质量。
- 为 PSTN 服务单独收取费用。

Microsoft 不管理运营商。 Microsoft 提供了一个 PBX (Microsoft Phone System) 和一个团队客户端, 验证手机, 并验证可与 Microsoft Phone 系统配合使用的 SBCs。 选择运营商之前, 请确保你的选择具有已认证的 SBC, 并且可以管理语音质量端到端。

下面是配置方案的技术实现步骤。

**仅限运营商:**
1. 根据[认证的 SBC 供应商的说明](#deploy-and-configure-the-sbc), 为托管方案部署 SBC 并配置它。
2. 在运营商租户中注册一个基本域名, 并请求一个通配符证书。
3. 为每个客户注册子域, 这是基本域的一部分。

**具有客户全局管理员的运营商:**
1. 将子域名称添加到客户租户。
2. 激活子域名。
3. 将运营商的主干配置为客户租户和预配用户。

*请确保了解 DNS 基础知识以及如何在 Office 365 中管理域名。在继续操作之前, 请查看[获取有关 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*

## <a name="deploy-and-configure-the-sbc"></a>部署和配置 SBC

有关如何针对 SBC 托管方案部署和配置 SBCs 的详细步骤, 请参阅 SBC 供应商的文档。

- **AudioCodes:**[直接路由配置说明](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), 在 "将 AudioCodes SBC 连接到 Microsoft 团队直接路由托管模型配置说明" 中介绍的 SBC 托管方案的配置。 
- **功能区通信:** 请参阅[功能区通信 SBC 核心 Microsoft 团队配置指南](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe), 了解有关如何配置功能区内核系列 SBCs 和此页面[功能区的文档最佳做法-配置 Microsoft 团队直接路由 SBC 的运营商边缘](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)

> [!NOTE]
> 请注意如何配置 "联系人" 标头。 联系人页眉用于查找传入邀请消息上的客户租户。 

## <a name="register-a-base-domain-and-subdomains"></a>注册基础域和子域

对于托管方案, 你需要创建:
- 运营商拥有的一个基本域名。
- 作为每个客户租户中的基本域名的一部分的子域。

在以下示例中:
- Adatum 是通过提供 Internet 和电话服务来为多个客户提供服务的运营商。
- Woodgrove Bank、Contoso 和艾德公司都是具有 Office 365 域但接收来自 Adatum 的电话服务的三个客户。

在将邀请发送到 Office 365 时, 子域**必须**与将为客户配置的主干的 FQDN 名称匹配, 并将 Fqdn 与联系人标头中的 fqdn 相匹配。 

当呼叫到达 Office 365 直接路由接口时, 该接口使用联系人标题查找应在其中查找用户的租户。 直接路由不会在邀请上使用电话号码查找, 因为某些客户可能具有在多个租户中可能会重叠的非号码。 因此, 联系人标头中的 FQDN 名称是标识确切的租户以通过电话号码查找用户所必需的。

*有关在 Office 365 租户中创建域名的详细信息, 请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*

下图总结了基本域、子域和联系人标头的要求。

![基本域、子域和联系人标题的要求](media/direct-routing-1-sbc-requirements.png)

SBC 需要证书才能对连接进行身份验证。 对于 SBC 托管方案, 运营商需要使用* \*base_domain (例如, \*customers.adatum.biz)* 申请一个证书。 此证书可用于对从单个 SBC 提供服务的多个租户的连接进行身份验证。

下表是一个配置示例。


|新域名 |类型|注册  |适用于 SBC 的证书 SAN  |示例中的租户默认域  |当向用户发送呼叫时, SBC 必须在联系人标头中出现的 FQDN 名称|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base64     |     在运营商租户中  |    \*。 customers.adatum.biz  |   adatum.biz      |NA, 这是一个服务租户, 没有用户 |
|sbc1.customers.adatum.biz|    子域  |    在客户租户中  |    \*。 customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客户租户中   |   \*。 customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客户租户中 |   \*。 customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

要配置基本和子域, 请按照下面所述的步骤进行操作。 在此示例中, 我们将为一个客户 (Woodgrove Bank 租户中的 sbc1.customers.adatum.biz) 配置一个基本域名 (customers.adatum.biz) 和一个子域。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在运营商租户中注册基本域名

**这些操作在运营商租户中执行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>确保您在运营商租户中具有适当的权限

如果您作为全局管理员登录到 Microsoft 365 管理中心, 则只能添加新域。 

https://portal.office.com)若要验证你拥有的角色, 请登录到 Microsoft 365 管理中心 (请转到 "**用户** > **活动用户**", 然后验证你是否拥有全局管理员角色。 

有关管理员角色以及如何在 Office 365 中分配角色的详细信息, 请参阅[关于 office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>将基础域添加到租户并验证它

1.  在 Microsoft 365 管理中心中, 转到 "**设置** > **域** > **添加域**"。
2.  在 "**输入您拥有的域**" 框中, 键入基础域的 FQDN。 在以下示例中, 基本域为*customers.adatum.biz*。

    ![添加基础域](media/direct-routing-2-sbc-add-domain.png)

3. 单击" **下一步**"。
4. 在此示例中, 租户已将 adatum.biz 作为已验证的域名。 由于 customers.adatum.biz 是已注册名称的子域, 该向导不会要求进行其他验证。 但是, 如果你添加以前未验证的 FQDN, 你将需要完成验证过程。 验证过程[如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![确认已验证的域名](media/direct-routing-3-sbc-verify-domain.png)

5.  单击 "**下一步**", 然后在 "**更新 DNS 设置**" 页面上, 选择**我将自己添加 DNS 记录**, 然后单击 "**下一步**"。
6.  在下一页上, 清除所有值 (除非要使用 Exchange、SharePoint 或团队/Skype for Business 的域名), 单击 "**下一步**", 然后单击 "**完成**"。 请确保您的新域处于 "设置完成" 状态。

    ![显示 "设置" 状态的域已完成](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>激活域名

注册域名后, 您需要通过至少添加一个 E1、E3 或 E5 许可用户来激活它, 并使用与创建的基础域匹配的 SIP 地址的 FQDN 部分分配 SIP 地址。 

*有关在 Office 365 租户中添加用户的详细信息, 请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*

例如: test@customers.adatum.biz

![基础域激活页面](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客户租户中注册子域名称

你将需要为每个客户创建唯一的子域名称。 在此示例中, 我们将在具有默认域名称的租户中创建一个子域 sbc1.customers.adatum.biz woodgrovebank.us。

**以下所有操作均位于客户租户中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>确保你在客户租户中具有适当的权限

如果您作为全局管理员登录到 Microsoft 365 管理中心, 则只能添加新域。 

https://portal.office.com)若要验证你拥有的角色, 请登录到 Microsoft 365 管理中心 (请转到 "**用户** > **活动用户**", 然后验证你是否拥有全局管理员角色。 

有关管理员角色以及如何在 Office 365 中分配角色的详细信息, 请参阅[关于 office 365 管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>将子域添加到客户租户并验证它
1. 在 Microsoft 365 管理中心中, 转到 "**设置** > **域** > **添加域**"。
2. 在 "**输入你拥有的域**" 框中, 键入此租户的子域的 FQDN。 在下面的示例中, 子域是 sbc1.customers.adatum.biz。

    ![添加客户子域](media/direct-routing-5-sbc-add-customer-domain.png)

3. 单击" **下一步**"。
4. FQDN 从未在租户中注册。 在下一步中, 你将需要验证域。 选择 "**添加 TXT 记录**"。 

    !["验证域" 页面上的选项](media/direct-routing-6-sbc-verify-customer-domain.png)

5. 单击 "**下一步**", 记下生成的 TXT 值以验证域名。

    !["验证域" 页面上的文本记录](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 利用运营商的 DNS 托管提供商的上一步中的值创建 TXT 记录。

    ![在运营商的 DNS 托管提供商中创建 TXT 记录](media/direct-routing-8-sbc-txt-record.png)

    有关详细信息, 请参阅[在任何 dns 托管提供商处为 Office 365 创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 返回客户的 Microsoft 365 管理中心, 然后单击 "**验证**"。 
8. 在下一页上, 选择 "**我将自行添加 DNS 记录**", 然后单击 "**下一步**"。

    !["更新 DNS 设置" 页面上的选项](media/direct-routing-9-sbc-update-dns.png)

9. 在 "**选择联机服务**" 页面上, 清除 "所有选项", 然后单击 "**下一步**"。

    !["选择您的在线服务" 页面](media/direct-routing-10-sbc-choose-services.png)

10. 在 "**更新 DNS 设置**" 页面上单击 "**完成**"。

    !["更新 DNS 设置" 页面](media/direct-routing-11-sbc-update-dns-finish.png)

11. 确保状态为 "**设置完成**"。 
    
    ![显示设置完成状态的页面](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>激活子域名

注册域名后, 您需要通过至少添加一个用户并使用与客户租户中创建的子域相匹配的 SIP 地址的 FQDN 部分来激活该域名。

*有关在 Office 365 租户中添加用户的详细信息, 请参阅[获取有关 office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)。*

例如: test@sbc1.customers.adatum.biz

!["子域" 页面的激活](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>创建主干和预配用户

> [!NOTE]
> 根据我们在技术采纳计划中收到的反馈, Microsoft 可能会更改在客户租户中创建中继的过程以简化流程。 请观看此页面上的文档更新, 并关注 Microsoft 技术社区博客, 了解详细信息。 

使用 "新建-CSonlinePSTNGateway" 命令在 customer 域中创建主干。 主干 FQDN**必须**与为客户创建的子域匹配。

例如：

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

创建主干时, 你可能会收到以下错误消息:

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

请留出一些时间进行域注册和激活以进行复制, 然后重试。

为用户预配电话号码和配置语音路由。

有关新 CSOnlinePSTNGateway、预配用户和配置语音路由的详细信息, 请参阅[配置直接路由](direct-routing-configure.md)。


请参阅[SBC 供应商的说明](#deploy-and-configure-the-sbc), 了解如何在联系人标头中配置子域的 FQDN 名称。

