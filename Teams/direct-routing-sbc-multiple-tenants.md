---
title: 配置会话边界控制器 - 多个租户
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何在 SBC (配置一) 边界控制器，为 Microsoft 合作伙伴和/或 PSTN 运营商提供多个租户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 824b550200fcb04ecf26ec6f939515586ec64544
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619488"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>为多个租户配置会话边界控制器

直接路由支持在 SBC (配置一) 边界控制器，为多个租户提供服务。

> [!NOTE]
> 此方案专为 Microsoft 合作伙伴和/或 PSTN 运营商（本文档稍后称为运营商）设计。 运营商销售交付给客户的Microsoft Teams服务。 

运营商：
- 在客户的数据中心部署和管理 SBC (客户无需实现 SBC，他们会收到来自运营商的电话服务，Teams客户端) 。
- 将 SBC 互连到多个租户。
- 为客户提供 PSTN 服务。
- 管理端到端呼叫质量。
- PSTN 服务单独收费。

Microsoft 不管理运营商。 Microsoft 提供 PBX (Microsoft 电话 System) 和 Teams 客户端。 Microsoft 还认证手机，并认证可以与 Microsoft 电话 System 一Microsoft 电话的 SDC。 在选择运营商之前，请确保你的选择具有经过认证的 SBC，并可以端到端地管理语音质量。

下面是配置方案的技术实现步骤。

**仅运营商：**
1. 根据经过认证的 SBC 供应商的说明部署 SBC 并针对托管 [方案配置它](#deploy-and-configure-the-sbc)。
2. 在运营商租户中注册基本域名，并请求通配符证书。
3. 注册每个客户的子域，该子域是基本域的一部分。

**具有客户全局管理员的运营商：**
1. 将子域名称添加到客户租户。
2. 激活子域名称。
3. 配置从运营商到客户租户的中继并预配用户。

*请确保你了解 DNS 基础知识以及如何在 Microsoft 365 或 Office 365 中管理域名。在 [继续下一Microsoft 365之前，请查看Office 365获取](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)域或域的帮助。*

## <a name="deploy-and-configure-the-sbc"></a>部署和配置 SBC

若要详细了解如何为 SBC 托管方案部署和配置 SBC，请参阅 SBC 供应商的文档。

- **AudioCodes：**[直接路由](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)配置说明，"将 AudioCodes SBC 连接到 Microsoft Teams路由托管模型配置说明"中所述的 SBC 托管方案的配置。 
- **Oracle：**[直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，"Microsoft"部分介绍了 SBC 托管方案的配置。 
- **功能区通信：** 请参阅功能区 [通信 SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)配置指南，了解如何配置功能区核心系列 SBC 的文档，并参阅本页功能区最佳实践 - 为 Microsoft Teams Direct Routing [SBC Edge 配置](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)运营商
- **TE-Systems (anynode) ：** 请在 [TE-Systems](https://community.te-systems.de/) Community页上注册，了解如何为多个租户配置 anynode SBC 的文档和示例。
- **Metaswitch：** 有关如何为多个租户启用 Perimeta SBC 的文档，[请在 Metaswitch](https://manuals.metaswitch.com/MAN39555) Community 页上注册。

> [!NOTE]
> 请注意如何配置"联系人"标头。 联系人标头用于在传入邀请消息上查找客户租户。 

## <a name="register-a-base-domain-and-subdomains"></a>注册基本域和子域

对于托管方案，需要创建：
- 运营商拥有的一个基域名。
- 一个子域，它是每个客户租户中基本域名的一部分。

在下面的示例中：
- Adatum 是一家运营商，通过提供 Internet 和电话服务为多个客户提供服务。
- Woodgrove Bank、Contoso 和 Adventure Works 是三个拥有Microsoft 365或Office 365但从 Adatum 接收电话服务的客户。

子域 **必须与** 在将邀请发送到客户或联系人时为客户配置的中继的 FQDN 名称与联系人标头中的 FQDN Microsoft 365 Office 365。 

当呼叫到达 Microsoft 365 Office 365直接路由接口时，该接口使用 Contact 标头查找应查找用户的租户。 直接路由不使用"邀请"上的电话号码查找，因为某些客户可能拥有非 DID 号码，这些号码可能与多个租户重叠。 因此，需要 Contact 标头中的 FQDN 名称来标识要按电话号码查找用户的确切租户。

*有关 [在组织或Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) Microsoft 365创建域名的信息，请查看获取有关 Office 365 Office 365 域的帮助。*

下图总结了基本域、子域和 Contact 标头的要求。

![显示域和联系人头的要求的示意图](media/direct-routing-1-sbc-requirements.png)

SBC 需要证书来验证连接。 对于 SBC 托管方案，运营商需要使用 CN 和/或 SAN .base_domain (请求证书，*\* 例如 \* .customers.adatum.biz) 。* 此证书可用于对从单个 SBC 提供的多个租户的连接进行身份验证。


下表是一个配置示例。


|新域名 |类型|已注册  |适用于 SBC 的证书 CN/SAN  |示例中的租户默认域  |向用户发送呼叫时 SBC 必须存在于 Contact 标头中的 FQDN 名称|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    基本     |     在运营商租户中  |    \*.customers.adatum.biz  |   adatum.biz      |NA，这是一个服务租户，没有用户 |
|sbc1.customers.adatum.biz|    子域  |    在客户租户中  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客户租户中   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客户租户中 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

若要配置基域和子域，请执行下面所述的步骤。 在示例中，我们将在 Woodgrove Bank 租户 (customers.adatum.biz) 中为一个 (sbc1.customers.adatum.biz 配置基本域名) 。

> [!NOTE]
> 使用 sbcX.customers.adatum.biz 在运营商租户中启用语音。 sbcX 可以是任何唯一且有效的字母数字主机名。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在运营商租户中注册基本域名

**这些操作在运营商租户中执行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>确保在运营商租户中拥有适当的权限

只有以全局管理员Microsoft 365 管理中心才能添加新域。 

若要验证你拥有的角色，请登录到 Microsoft 365 管理中心 (，转到"用户活动用户"，然后 https://portal.office.com)   >  验证你具有全局管理员角色。 

有关管理员角色以及如何在管理员角色中分配角色Microsoft 365 Office 365，请参阅[关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>将基本域添加到租户并验证

1. 在Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **添加域"。**
2. 在 **"输入你拥有域"框中** ，键入基本域的 FQDN。 在下面的示例中，基本域 *customers.adatum.biz。*

    ![显示"添加域"页面的屏幕截图](media/direct-routing-2-sbc-add-domain.png)

3. 单击" **下一步**"。
4. 在示例中，租户已 adatum.biz 已验证的域名。 向导不会要求进行其他验证，customers.adatum.biz 已注册名称的子域。 但是，如果添加以前尚未验证的 FQDN，则需要完成验证过程。 验证过程 [如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![显示已验证域名确认的屏幕截图](media/direct-routing-3-sbc-verify-domain.png)

5. 单击 **"下** 一步 **"，在**"更新 DNS 设置"页上，选择"我将自己 **添加 DNS 记录**"，然后单击"下一 **步"。**
6. 在下一页上，清除所有值 (，除非要使用 Exchange、SharePoint 或 Teams/Skype for Business) 的域名，请单击"下一步"，然后单击 **"完成**"。  确保新域位于"设置完成"状态。

    ![显示状态为"设置已完成"的域的屏幕截图](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>激活域名

注册域名后，需要通过添加至少一个具有 电话系统 许可证的用户，并分配 SIP 地址与所创建基域匹配的 SIP 地址的 FQDN 部分来激活它。

> [!NOTE]
> 运营商租户必须至少保留一个电话系统分配给租户的许可证，以避免删除Skype for Business配置。 

*有关 [在组织或Microsoft 365 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)添加用户的信息，请查看获取有关Microsoft 365或Office 365的帮助。*

例如：test@customers.adatum.biz

![基本域激活页面的屏幕截图](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客户租户中注册子域名称

需要为每个客户创建唯一的子域名称。 本示例在租户中创建一个子 sbc1.customers.adatum.biz，该租户的默认域名为 woodgrovebank.us。

**以下所有操作均在客户租户中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>确保在客户租户中拥有适当的权限

只有以全局管理员Microsoft 365 管理中心才能添加新域。 

若要验证你拥有的角色，请登录到 Microsoft 365 管理中心 (，转到"用户活动用户"，然后 https://portal.office.com)   >  验证你具有全局管理员角色。 

有关管理员角色以及如何在用户或 Microsoft 365 中分配Office 365，请参阅[关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>将子域添加到客户租户并验证
1. 在Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **添加域"。**
2. 在 **"输入你拥有域"框中** ，键入此租户的子域的 FQDN。 在下面的示例中，子域 sbc1.customers.adatum.biz。

    !["添加域"页的屏幕截图](media/direct-routing-5-sbc-add-customer-domain.png)

3. 单击" **下一步**"。
4. FQDN 从未在租户中注册过。 下一步需要验证域。 改为 **选择"添加 TXT 记录"。** 

    !["验证域"页的屏幕截图](media/direct-routing-6-sbc-verify-customer-domain.png)

5. 单击 **"** 下一步"，并记下生成的 TXT 值以验证域名。

    !["验证域"页面上的文本记录的屏幕截图](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 在运营商的 DNS 托管提供商中，使用上一步骤中的值创建 TXT 记录。

    ![显示创建 TXT 记录的屏幕截图](media/direct-routing-8-sbc-txt-record.png)

    有关详细信息，请参阅在任何 DNS 托管提供商 上 [创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 返回到客户的帐户，Microsoft 365 管理中心"验证 **"。** 
8. 下一页上，选择 **"我将自己添加 DNS 记录**"，然后单击"下一 **步"。**

    !["更新 DNS 设置"页上的选项的屏幕截图](media/direct-routing-9-sbc-update-dns.png)

9. 在"**选择联机服务"页面上**，清除所有选项，然后单击"下一 **步"。**

    !["选择联机服务"页面的屏幕截图](media/direct-routing-10-sbc-choose-services.png)

10. 在 **"更新** **DNS 设置"页上单击"完成** "。

    !["更新 DNS 设置"页的屏幕截图](media/direct-routing-11-sbc-update-dns-finish.png)

11. 确保状态为"设置 **完成"。** 
    
    ![显示安装完成状态的页面的屏幕截图](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> 单个客户端的基本 URL 和子域必须位于同一租户上，才能添加 _直接路由_ 中继。

### <a name="activate-the-subdomain-name"></a>激活子域名称

注册域名后，需要通过添加至少一个用户并分配 SIP 地址（包含与客户租户中创建的子域匹配的 SIP 地址的 FQDN 部分）来激活它。 

*有关 [在组织或Microsoft 365 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)添加用户的信息，请查看获取有关Microsoft 365或Office 365的帮助。*

例如：test@sbc1.customers.adatum.biz

![激活子域页面的屏幕截图](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>创建中继并预配用户

在直接路由的初始版本中，Microsoft 要求使用 New-CSOnlinePSTNGateway 将中继添加到 (租户) 租户。

但是，由于两个原因，这一点未证明最佳：
 
- **开销管理**。 例如，卸载或清空 SBC 会更改某些参数，例如启用或禁用媒体旁路。 更改端口需要通过运行 Set-CSOnlinePSTNGateway (更改多个租户中的参数) ，但实际上是相同的 SBC。 

-  **开销处理**。 收集和监视中继运行状况数据 - 从多个逻辑中继收集的 SIP 选项，实际上，相同的 SBC 和相同的物理中继会减慢路由数据的处理速度。
 
基于此反馈，Microsoft 将引入一个新逻辑来为客户租户预配中继。

引入了两个新实体：
-    使用命令 New-CSOnlinePSTNGateway 在运营商租户中注册的运营商中继，例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true。

-    派生的中继，不需要注册。 它只是从运营商中继中添加的所需主机名。 它从运营商中继派生其所有配置参数。 无需在 PowerShell 中创建派生的中继，并且与运营商中继的关联基于 FQDN 名称 (请参阅下面) 。

**预配逻辑和示例**

-    运营商只需使用 Set-CSOnlinePSTNGateway) 命令在运营商域 (中继中设置和管理单个Set-CSOnlinePSTNGateway中继。 在以上示例中，它是 adatum.biz;
-    在客户租户中，运营商只需将派生的中继 FQDN 添加到用户的语音路由策略。 无需为中继New-CSOnlinePSTNGateway应用程序。
-    如名称所示，派生的中继从运营商中继继承或派生所有配置参数。 示例：
-    Customers.adatum.biz – 需要在运营商租户中创建的运营商中继。
-    Sbc1.customers.adatum.biz – 客户租户中的派生中继，无需在 PowerShell 中创建。  只需在联机语音路由策略中将派生的中继的名称添加到客户租户中，而无需创建它。
-   运营商需要设置 DNS 记录，将派生的中继 FQDN 解析为运营商 SBC IP 地址。

-    对运营商租户上的运营商中继 (所做的更改) 自动应用到派生的中继。 例如，运营商可以更改运营商中继上的 SIP 端口，此更改适用于所有派生的中继。 配置中继的新逻辑简化了管理，因为无需转到每个租户并更改每个中继上的 参数。
-    选项仅发送到运营商中继 FQDN。 运营商中继的运行状况状态将应用到所有派生的中继，并用于路由决策。 了解有关直接路由 [选项的详细信息](./direct-routing-monitor-and-troubleshoot.md)。
-    运营商可以排出运营商中继，所有派生的中继也将排出。 
 
> [!NOTE]
> 在运营商中继上应用的号码转换规则不适用于派生的中继。 这是一个已知问题。 作为替代方法，必须针对每个客户的租户创建数字转换规则。

**从以前的模型迁移到运营商中继**
 
若要从运营商托管模型的当前实现迁移到新模型，运营商需要为客户租户重新配置中继。 使用将中继留在运营商租户中Remove-CSOnlinePSTNGateway (从客户租户中删除) -

我们强烈建议尽快迁移到新解决方案，因为我们将使用运营商和派生的中继模型增强监视和预配。
 

请参阅 [SBC 供应商有关](#deploy-and-configure-the-sbc) 配置在 Contact 标头中发送子域的 FQDN 名称的说明。

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>设置多租户故障转移的注意事项 

若要为多租户环境设置故障转移，需要执行以下操作：

- 对于每个租户，为两个不同的 SDC 添加 FQDN。  例如：

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 在用户的联机语音路由策略中，指定这两个 SDC。  如果一个 SBC 失败，路由策略将调用路由到第二个 SBC。


## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
