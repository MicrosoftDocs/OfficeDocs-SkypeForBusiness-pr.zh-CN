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
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>为多个租户配置会话边界控制器

直接路由支持将一个会话边界 (SBC 控制器配置为 (SBC 和) 租户。

> [!NOTE]
> 此方案适用于 Microsoft 合作伙伴和/或 PSTN 转网商，即称为 Carrier。本文档后面部分称为商。 一位教师会将电信服务发送给 Microsoft Teams 给客户。 

在执行以下操作时：
- 在其数据中心中部署和管理 SBC (客户无需实施 SBC，他们会从 Teams 客户端客户端服务购买商的电话服务) 。
- 将 SBC 与多个租户连接。
- 向客户提供 PSTN 服务。
- 管理通话质量端到端。
- 为 PSTN 服务单独收费。

Microsoft 不管理商。 Microsoft 提供了一个 PBX (Microsoft Phone System) 客户端。 Microsoft 还会认证手机和可与 Microsoft Phone 系统一起使用的证书 SBC。 在选择运行机构之前，请确保您的选择有认证的 SBC 并且可以将语音质量端管理到结束。

以下是配置方案的技术实现步骤。

**仅执行以下操作：**
1. 部署 SBC 并根据已认证的 SBC 供应商的说明对 [托管方案进行配置](#deploy-and-configure-the-sbc)。
2. 在条件租户中注册一个基域名，并请求通配符证书。
3. 为每个客户注册一个子域，这是基域的一部分。

**具有客户全局管理员的机会：**
1. 将子域名添加到客户租户。
2. 激活子域名。
3. 配置从承告商到客户租户的中断，并设置用户。

*请确保了解 DNS 基础知识以及在 Microsoft 365 或 Office 365 中管理域名的方式。进 [一步继续尝试之前，请先查看有关 Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 域的帮助。*

## <a name="deploy-and-configure-the-sbc"></a>部署和配置 SBC

有关如何为 SBC 托管方案部署和配置 SBC 的详细步骤，请参阅 SBC 供应商的文档。

- **AudioCodes：**[直接路由配置备注](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，将"AudioCodes SBC 连接到 Microsoft Teams 直接路由托管模型配置笔记"中所述的 SBC 托管方案配置。 
- **Oracle：**[直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，SBC 托管方案的配置将在"Microsoft"部分中进行介绍。 
- **功能区通信：**  有关如何配置功能区内部 SBC 和此页面功能区的最佳实践的文档，请参阅"关于 CBC [Core Microsoft Teams"](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) 的文档的参考指南 - 为 Microsoft Teams 直接路由 [SBC 边缘配置 Corts](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems 字段 (任何节) ：**  请在 [TE-Systems"社区](https://community.te-systems.de/) "页面上注册文档，以及如何为多个租户配置任何节点 SBC 的示例。
- **Metaswitch：**  请登记 ["Metaswitch 社区"](https://sso.metaswitch.com/UI/Login) 页，以获取有关如何为多个租户启用 Perimeta SBC 的文档。

> [!NOTE]
> 请注意如何配置"联系人"标题。 联系人头用于在传入邀请邮件中查找客户租户。 

## <a name="register-a-base-domain-and-subdomains"></a>注册基域和子域

对于托管方案，你需要创建：
- 一个由管理器拥有的基域名。
- 每个客户租户中作为基域名的一个子域。

在以下示例中：
- Adatum 是通过提供 Internet 和电话服务来商为多名客户提供服务。
- Woodgrove Bank、Contoso 和 Adventure Works 是三名有 Microsoft 365 或 Office 365 域但从 Adatum 接收电话服务的三名客户。

子域 **名必须** 与将要为客户配置的中断的 FQDN 名称和联系人标题中的 FQDN 匹配，才能在将邀请发送给 Microsoft 365 或 Office 365 时，搜索结果中。 

当呼叫到达 Microsoft 365 或 Office 365 直接路由接口时，接口使用联系人标题查找应该在其中查找用户的租户。 直接路由不在邀请上使用电话号码查找，因此某些客户可能在多个租户中有可以重叠的非 DID 号码。 因此，需要在联系人头中的 FQDN 名称来确定确切的租户，以通过电话号码查找该用户。

*请查看  [有关在 Microsoft 365 或 Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) 组织中创建域名的详细信息，查看有关 Office 365 域的帮助。*

下图汇总了基域、子域和联系人头的要求。

![显示对域和联系人头的要求的图表](media/direct-routing-1-sbc-requirements.png)

SBC 需要证书才能对连接进行身份验证。 对于 SBC 托管方案，运行商需使用 SAN * \* .base_domain (（例如 \* .customers.adatum.biz) ）请求证customers.adatum.biz) 。 * 此证书可用于验证从单个 SBC 提供的多个租户的连接。


下表是了一个配置的示例。


|新域名 |类型|已注册  |SAN for SBC 证书  |示例中的租户默认域  |向用户发送呼叫时，SBC 必须出现在联系人头眉中|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    基数     |     在任意租户中  |    \*.customers.adatum.biz  |   adatum.biz      |NA，这是一个服务租户，没有用户 |
|sbc1.customers.adatum.biz|    子域  |    在客户租户中  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客户租户中   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客户租户中 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

若要配置基值和子域，请按照下述步骤进行操作。 在此示例中，我们将在 Woodgrove Bank 租 (customers.adatum.biz) 户) 客户配置一个域名和一个 (sbc1.customers.adatum.biz子。

> [!NOTE]
> 使用 sbcX.customers.adatum.biz在任意租户中启用语音。 sbcX 可以是任何唯一的有效字母数字主机名。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在任命者租户中注册基域名

**这些操作在任意租户中执行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>确保一位运行者租户具有适当的权利

只有在你以全局管理员的形式登录到 Microsoft 365 管理中心时，才能添加新的域。 

若要验证所拥有的角色，请登录到 Microsoft 365 管理中心 (， https://portal.office.com) 转到 **"用户**  >  **活动**用户"，然后验证你是否具有全局管理员角色。 

若要详细了解管理员角色以及如何在 Microsoft 365 或 Office 365 中分配角色，请参阅 ["关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)"。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>将基域添加到租户并验证

1. 在 Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **"添加域**。
2. 在" **输入自行输入的域** "框中，键入基域的 FQDN。 在以下示例中，基域*是customers.adatum.biz。*

    ![显示"添加域"页面的屏幕截图](media/direct-routing-2-sbc-add-domain.png)

3. 单击" **下一步**"。
4. 在示例中，租户已经adatum.biz为经过验证的域名。 向导不要求您进行额外验证，因为customers.adatum.biz是已经注册的名称的子域。 但是，如果添加之前尚未验证的 FQDN，则需要完成验证过程。 验证过程将在下 [面进行介绍](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

    ![显示已验证的域名确认的屏幕截图](media/direct-routing-3-sbc-verify-domain.png)

5. 单击 **"下**一步 **"，在"更新 DNS 设置"** 页面上， **选择"自己添加 DNS 记录"并** 单击"下 **一步**"。
6. 在下一页上，除非 (想要对 Exchange、SharePoint 或 Skype for Business) 使用域名，否则清除所有值，单击**Finish****"完成**"。 请确保新域处于设置完整状态。

    ![屏幕截图显示域和设置状态为完成的域](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>激活域名

注册域名后，需要通过添加至少一个 E1、E3 或 E5 许可用户并向 SIP 地址的 FQDN 部分分配 SIP 地址，并分配与所创建基域匹配的 FQDN 部分的 SIP 地址。 许可证在域激活后可能会 (最长可能需要 24 小时) 。

*请查看有关 [Microsoft 365 或 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) ，了解有关在 Microsoft 365 或 Office 365 组织中添加用户的详细信息。*

例如：test@customers.adatum.biz

![基域激活页面的屏幕截图](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客户租户中注册子域名

需要为每位客户创建唯一的子域名。 在此示例中，将在具有默认sbc1.customers.adatum.biz域名的租户中创建一个woodgrovebank.us。

**以下所有操作都位于客户租户中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>确保客户租户中具有适当的权限

只有在你以全局管理员的形式登录到 Microsoft 365 管理中心时，才能添加新的域。 

若要验证所拥有的角色，请登录到 Microsoft 365 管理中心 (， https://portal.office.com) 转到 **"用户**  >  **活动**用户"，然后验证你是否具有全局管理员角色。 

若要详细了解管理员角色以及如何在 Microsoft 365 或 Office 365 中分配角色，请参阅 ["关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)"。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>将子域添加到客户租户并验证
1. 在 Microsoft 365 管理中心，转到"**设置**  >  **域**  >  **"添加域**。
2. 在" **输入您拥有的域"** 框中，键入此租户子域的 FQDN。 在下面的示例中，子域sbc1.customers.adatum.biz。

    !["添加域"页面的屏幕截图](media/direct-routing-5-sbc-add-customer-domain.png)

3. 单击" **下一步**"。
4. FQDN 从未在租户中注册过。 在下一步中，你需要验证域。 则 **改为选择"添加 TXT 记录**"。 

    !["验证域"页的屏幕截图](media/direct-routing-6-sbc-verify-customer-domain.png)

5. 单击 **"** 下一步"，并注意生成的用于验证域名的 TXT 值。

    !["验证域"页面上文本记录的屏幕截图](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 使用注册机号的 DNS 托管提供商步骤中的值创建 TXT 记录。

    ![屏幕截图显示如何创建 TXT 记录](media/direct-routing-8-sbc-txt-record.png)

    有关详细信息，请参阅在任何 [DNS 托管提供商处创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 返回到客户的 Microsoft 365 管理中心，然后单击 **"验证**"。 
8. 在下一页上，**选择我将自己添加 DNS 记录，然后单击"下****一步**"。

    !["更新 DNS 设置"页面上选项的屏幕截图](media/direct-routing-9-sbc-update-dns.png)

9. 在"选择 **你的联机服务"页面上** ，清除所有选项，然后单击"下 **一步**"。

    !["选择联机服务"页面的屏幕截图](media/direct-routing-10-sbc-choose-services.png)

10. 在 **"更新 DNS 设置** "页 **上单击"完成** "。

    !["更新 DNS 设置"页面的屏幕截图](media/direct-routing-11-sbc-update-dns-finish.png)

11. 确保状态为**完成。** 
    
    ![显示设置完成状态的页面的屏幕截图](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>激活子域名

注册域名后，需要通过添加至少一个用户并向 SIP 地址的 FQDN 部分分配一个 SIP 地址，该地址与客户租户中创建的子域相匹配。 在子域激活后，可以从用户中撤销许可证 (最长可能需要 24 小时) 。

*请查看有关 [Microsoft 365 或 Office 365 域的帮助](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) ，了解有关在 Microsoft 365 或 Office 365 组织中添加用户的详细信息。*

例如：test@sbc1.customers.adatum.biz

![子域页面的激活屏幕截图](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>创建中断和预订用户

在初始版本的直接路由中，Microsoft 需要将中断添加到使用 New-CSOnlinePSTNGateway 开发 () 中，前者才能使用该延时运行中。

但是，这未获得过于以下两个原因的原因：
 
- **开展管理**。 关闭加载或关闭 SBC，例如，更改某些参数，如启用或禁用媒体旁路。 更改端口需要运行 Set-CSOnlinePSTNGateway) 更改多个租户 (中的参数，但它实际上是相同的 SBC。 

-  **开速处理**。 收集和监视中断运行状况数据 - SIP 选项是从相同的 SBC 和相同的物理中断收集的，降低路由数据处理速度。
 
根据以下反馈，Microsoft 正提供新的逻辑来为客户租户预配置中文。

引入了以下两个新实体：
-    使用 Command New-CSOnlinePSTNGateway（例如 New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true） 在运营商租户中注册的运营商截$true。

-    也有提示的 Trunk，该过程不需要注册。 这只是从承载商截断中添加的一个所需主机名。 它从交通线中发送其所有配置参数。 不需要在 PowerShell 中创建所传索的 Trunk，与运行商处插相关联基于 FQDN 名称 (请参阅下文) 。

**设置逻辑和示例**

-    此参数条件仅需要使用 Set-CSOnlinePSTNGateway 命令设置和管理运行者将应用) 中等级 (数据转网) 部数据转网。 在上面的示例中，它adatum.biz;
-    在客户租户中，该运行商只需向用户的语音路由策略添加已感过的中断中断，需要执行该操作。 无需为分类运行 New-CSOnlinePSTNGateway。
-    作为名称建议、收件或从承员 Trunk 的所有配置参数出来应答。 示例：
-    Customers.adatum.biz - 需要在参数租户中创建的具体中断。
-    Sbc1.customers.adatum.biz， 在不需要在 PowerShell 中创建的客户租户中显示所得的中断。  只需在联机语音路由策略的客户租户策略中添加已分钟的中断的名称而不创建。
-   运营商需要设置 DNS 记录解析已被传送的 Trunk FQDN 到运营商 SBC IP 地址。

-    在运行者租户中 (应用) 于运行者应用的任何更改都将自动应用到该中断。 例如，运营商可以在运营商中更换 SIP 端口，此更改适用于所有 derive trunk。 配置中断的新逻辑简化了管理人员，因为无需转到每个租户，每台中线都更改参数。
-    这些选项仅发送到运行机器截断 FQDN。 运行器中断的运行状况适用于所有已传输中断，可用于路由决策。 了解有关直接 [路由选项的详细信息](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)。
-    该运行商也可以截断运行运行器截断，所有已中断的中断也将失原。 
 

**从以前的模型迁移到另一个运行器截断**
 
若要从实施从承载商托管模型的当前实现迁移到新模型，然后承家需要重新配置客户租户的中文。 使用 Remove-CSOnlinePSTNGateway (将 Trunk 保留在运行机租户的服务的中) -

强烈建议尽快迁移到新解决方案，以便我们将使用承员和密生的中断模型进行监视和配置。
 

请参阅 [有关配置在联系人头](#deploy-and-configure-the-sbc) 中发送子域的 FQDN 名称的 SBC 供应商的说明。

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>设置多租户故障转移的注意事项 

若要为多租户环境设置故障转移，需要执行以下操作：

- 对于每个租户，为两个不同的 SBC 添加 FQDN。  例如：

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 在在线语音路由策略中，指定这两个 SBC。  如果一个 SBC 失败，路由策略会将呼叫路由至第二个 SBC。


## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)

