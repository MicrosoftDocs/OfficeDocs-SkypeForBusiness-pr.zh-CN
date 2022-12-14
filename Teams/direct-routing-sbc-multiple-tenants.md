---
title: 配置会话边界控制器 - 多个租户
ms.reviewer: filippse
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
description: 了解如何配置一个会话边界控制器 (SBC) ，以便为Microsoft合作伙伴和/或 PSTN 运营商提供多个租户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 570709730f7563b30b98626395f6b0a72fc1ac48
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392292"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>为多个租户配置会话边界控制器

直接路由支持配置一个会话边界控制器 (SBC) ，以便为多个租户提供服务。

> [!NOTE]
> 此方案专为Microsoft合作伙伴和/或 PSTN 运营商设计，本文档稍后称为运营商。 运营商向客户销售交付给Microsoft Teams 的电话服务。 

运营商：
- 在其数据中心部署和管理 SBC， (客户不需要实现 SBC，并且他们从 Teams 客户端) 中接收运营商的电话服务。
- 将 SBC 互连到多个租户。
- 为客户提供公用电话交换网 (PSTN) 服务。
- 端到端管理通话质量。
- PSTN 服务单独收费。

Microsoft不管理运营商。 Microsoft提供电话系统（专用交换机 (PBX) ）和 Teams 客户端。 Microsoft还认证电话，并认证可与电话系统一起使用的 SBC。 在选择运营商之前，请确保所选内容具有经过认证的 SBC，并且可以端到端管理语音质量。

下面是配置方案的技术实现步骤。

**仅限运营商：**
1. 部署 SBC，并根据 [经认证的 SBC 供应商的说明](#deploy-and-configure-the-sbc)为托管方案配置它。
2. 在运营商租户中注册基本域名并请求通配符证书。
3. 为每个客户注册一个子域，该子域是基域的一部分。

**具有客户全局管理员的运营商：**
1. 将子域名称添加到客户租户。
2. 激活子域名称。
3. 配置从运营商到客户租户的中继并预配用户。

*请确保了解 DNS 基础知识以及如何在 Microsoft 365 中管理域名。在继续操作之前，请参阅 [获取Microsoft 365 个域的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。*

## <a name="deploy-and-configure-the-sbc"></a>部署和配置 SBC

有关如何为 SBC 托管方案部署和配置 SBC 的详细步骤，请参阅 SBC 供应商的文档。

- **AudioCodes：** 请参阅 [直接路由配置说明](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，了解 SBC 托管方案的配置，如“将 AudioCodes SBC 连接到 Microsoft Teams 直接路由托管模型配置说明”中所述。 
- **甲骨文：** 请参阅 [直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)，了解 SBC 托管方案的配置，如“Microsoft”部分中所述。 
- **功能区通信：** 有关如何配置 [功能区核心系列 SBC SBC Microsoft SBC 系列](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide) SBC 的文档，请参阅 Teams 配置指南。 另请参阅[功能区最佳做法 - 为 Microsoft Teams 直接路由 SBC Edge 配置运营商](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode) ：** 在 [TE-Systems 社区页面](https://community.te-systems.de/) 网站上注册，获取有关如何为多个租户配置任意节点 SBC 的文档和示例。
- **Metaswitch：** 在 [Metaswitch Community 页面](https://manuals.metaswitch.com/MAN39555) 网站上注册，获取有关如何为多个租户启用 Perimeta SBC 的文档。

> [!NOTE]
> 确保知道如何配置“联系人”标头。 联系人标头用于在传入邀请消息上查找客户租户。 

## <a name="register-a-base-domain-and-subdomains"></a>注册基域和子域

对于托管方案，需要创建：

- 运营商拥有的一个基本域名。
- 作为每个客户租户中基域名的一部分的子域。

在以下示例中：

- Adatum 是一家运营商，通过提供 Internet 和电话服务为多个客户提供服务。
- Woodgrove Bank、Contoso 和 Adventure Works 是三个客户，Microsoft 365 个域，但接收来自 Adatum 的电话服务。

子域 **必须与** 将为客户配置的中继的 FQDN 名称与发送邀请Microsoft 365 时联系人标头中的 FQDN 相匹配。 

当呼叫到达 Microsoft 365 直接路由接口时，该接口使用联系人标头查找应在其中查找用户的租户。 直接路由不会在“邀请”上使用电话号码查找，因为某些客户可能具有可在多个租户中重叠的非 DID 号码。 因此，需要“联系人”标头中的 FQDN 名称来标识确切的租户，以便按电话号码查找用户。

*有关在 Microsoft 365 组织中创建域名的详细信息，请参阅 [获取有关 Microsoft 365 域的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。*

下图总结了基域、子域和联系人标头的要求。

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="显示域和联系人标头要求的关系图。" lightbox="media/direct-routing-1-sbc-requirements.png":::

SBC 需要证书才能对连接进行身份验证。 对于 SBC 托管方案，运营商需要使用 CN 和/或 SAN *\*.base_domain (请求证书， \*例如 .customers.adatum.biz)*。 此证书可用于对从单个 SBC 提供的多个租户的连接进行身份验证。

下表是一个配置的示例。


|新域名 |类型|注册  |证书 CN/SAN for SBC  |示例中的租户默认域  |向用户发送呼叫时，SBC 必须出现在联系人标头中的 FQDN 名称|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    基地     |     在运营商租户中  |    \*.customers.adatum.biz  |   adatum.biz      |NA，这是一个服务租户，没有用户 |
|sbc1.customers.adatum.biz|    子域  |    在客户租户中  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客户租户中   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客户租户中 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

若要配置基域和子域，请按照以下步骤操作。 此示例为 Woodgrove Bank 租户) 中的一个客户 (sbc1.customers.adatum.biz 配置基本域名 (customers.adatum.biz) 和子域。

> [!NOTE]
> 使用 sbcX.customers.adatum.biz 在运营商租户中启用语音;sbcX 可以是任何唯一且有效的字母数字主机名。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在运营商租户中注册基本域名

**这些操作在运营商租户中执行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>确保你在运营商租户中拥有适当的权限

仅当以全局管理员身份登录到Microsoft 365 管理中心时，才能添加新域。 

若要验证你拥有的角色，请登录到 Microsoft 365 管理中心 (https://portal.office.com)，转到 **“用户** > **活动用户”**，然后验证你是否具有全局管理员角色。 

有关管理员角色以及如何在 Microsoft 365 中分配角色的详细信息，请参阅[关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>将基域添加到租户并对其进行验证

1. 在Microsoft 365 管理中心中，转到 **“设置** > **域** > **”“添加域**”。

2. 在 **“输入你拥有的域** ”框中，键入基域的 FQDN。 在以下示例中，基域 *customers.adatum.biz*。

3. 单击" **下一步**"。

4. 在此示例中，租户已将 adatum.biz 作为已验证域名。 向导不会要求进行其他验证，因为 customers.adatum.biz 是已注册名称的子域。 但是，如果添加之前未验证的 FQDN，则需要完成验证过程。 下面 [介绍了](#add-a-subdomain-to-the-customer-tenant-and-verify-it)验证过程。

5. 选择“ **下一步**”，然后在 **“更新 DNS 设置”** 页上，选择“ **我将自行添加 DNS 记录** ”，然后选择“ **下一步**”。

6. 在下一页上，清除所有值 (，除非要使用 Exchange、SharePoint、Teams 或Skype for Business) 的域名，选择“**下一步**”，然后选择“**完成**”。 确保新域处于“安装完成”状态。

### <a name="activate-the-domain-name"></a>激活域名

注册域名后，需要通过添加至少一个 Teams 许可用户或资源帐户来激活它。 可接受的帐户将获得以下任一 SKU 的许可：

- 具有 Office 365 E1/E3/E5 或 Microsoft 365 E3/E5 的用户帐户。
- 具有 Office 365 A1/A3/A5 或 Microsoft 365 A1/A3/A5 的用户帐户。
- 具有 Office 365 F3 或 Microsoft 365 F1/F3 的用户帐户。
- Office 365 G1/G3/G5 或 Microsoft 365 G3/G5 的用户帐户。
- 具有 Microsoft 365 商业基础版/标准/高级的用户帐户。
- 具有 **Microsoft Teams 共享设备许可证的** 用户帐户。
- 具有 **Microsoft Teams 电话资源帐户许可证的资源帐户**。

此外，帐户的 UPN (用户主体名称) 或Skype for Business本地 SIP 地址必须使用与新创建的域相同的 FQDN。

有关在 Microsoft 365 组织中添加用户的详细信息，请参阅[获取有关 Microsoft 365 域的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

例如：test@customers.adatum.biz

![基本域激活页的屏幕截图。](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客户租户中注册子域名称

需要为每个客户创建唯一的子域名称。 在此示例中，我们将在具有默认域名 woodgrovebank.us 的租户中创建子域 sbc1.customers.adatum.biz。

**以下所有操作都在客户租户中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>确保你在客户租户中具有适当的权限

仅当以全局管理员身份登录到Microsoft 365 管理中心时，才能添加新域。 

若要验证你拥有的角色，请登录到 Microsoft 365 管理中心 (https://portal.office.com)，转到 **“用户** > **活动用户”**，然后验证你是否具有全局管理员角色。 

有关管理员角色以及如何在 Microsoft 365 中分配角色的详细信息，请参阅[关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>将子域添加到客户租户并对其进行验证

1. 在Microsoft 365 管理中心中，转到 **“设置** > **域** > **”“添加域**”。

2. 在 **“输入你拥有的域** ”框中，键入此租户的子域的 FQDN。 在下面的示例中，子域 sbc1.customers.adatum.biz。

3. 选择“ **下一步**”。

4. 从未在租户中注册 FQDN。 在下一步中，需要验证域。 **改为选择“添加 TXT 记录**”。 

5. 选择“ **下一步**”，并记下为验证域名而生成的 TXT 值。

    ![“验证域”页上文本记录的屏幕截图。](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 使用运营商的 DNS 托管提供商中上一步的值创建 TXT 记录。

    有关详细信息，请参阅 [在任何 DNS 托管提供商处创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 转到客户的Microsoft 365 管理中心并选择“**验证**”。 

8. 在下一页上，选择“ **我将自己添加 DNS 记录”** ，然后选择“ **下一步**”。

9. 在 **“选择联机服务**”页上，清除所有选项，然后选择“**下一步**”。

10. 在 **“更新 DNS 设置**”页上选择“**完成**”。

11. 确保状态为 **“安装完成**”。

    ![显示“安装完成”状态的页面的屏幕截图。](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> 单个客户端的基 URL 和子域必须位于同一租户上，才能添加 _直接路由_ 中继。

### <a name="activate-the-subdomain-name"></a>激活子域名称

注册子域名称后，需要通过添加至少一个 Teams 许可的用户或资源帐户来激活它。 可接受的帐户将获得以下任一 SKU 的许可：

-   具有 Office 365 E1/E3/E5/A3/A5 或 Microsoft 365 E3/E5/A3/A5 的用户帐户
-   具有 Office 365 F1/F3 或 Microsoft 365 F1/F3 的用户帐户
-   具有Microsoft 365 商业基础版/标准/高级版和 G3/G5 计划的用户帐户
-   具有 **Microsoft Teams 共享设备许可证的** 用户帐户
-   具有 **Microsoft Teams 电话资源帐户许可证的资源帐户**

此外，帐户的 UPN (用户主体名称) 或Skype for Business本地 SIP 地址必须使用与新创建的子域相同的 FQDN。

有关在 Microsoft 365 组织中添加用户的详细信息，请参阅[获取有关 Microsoft 365 的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。

例如：test@sbc1.customers.adatum.biz

![“激活子域”页的屏幕截图。](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>创建中继并预配用户

在直接路由的初始版本中，Microsoft需要使用 New-CSOnlinePSTNGateway cmdlet 将中继添加到每个服务租户 (客户租户) 。

但是，由于以下两个原因，此方法并非最佳：
 
- **开销管理**。 例如，卸载或排出 SBC 会更改某些参数，例如启用或禁用媒体旁路。 更改端口需要通过运行 Set-CSOnlinePSTNGateway) 来更改多个租户中的参数 (，但它实际上是相同的 SBC。 

-  **开销处理**。 收集和监视中继运行状况数据 - 从多个逻辑中继收集的 SIP 选项（实际上，同一 SBC 和同一物理中继）会减慢路由数据的处理速度。
 
根据此反馈，Microsoft引入一个新的逻辑来为客户租户预配中继。

引入了两个新实体：

- 使用命令 New-CSOnlinePSTNGateway 在运营商租户中注册的运营商中继。 例如： 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- 不需要注册的派生中继。 它只是从运营商中继中添加的所需主机名。 它从运营商中继派生其所有配置参数。 与运营商中继的关联基于 FQDN 名称 (请参阅下面的详细信息) 。

**预配逻辑和示例**

- 运营商只需使用 Set-CSOnlinePSTNGateway 命令 (运营商域中的运营商中继) 设置和管理单个中继。 在上面的示例中，它是 adatum.biz。

- 在客户租户中，运营商需要将派生的中继 FQDN 添加到语音路由。 无需为中继运行New-CSOnlinePSTNGateway。

- 顾名思义，派生的中继继承或派生来自运营商中继的所有配置参数。 

例子：
- Customers.adatum.biz – 需要在运营商租户中创建的运营商中继。

- Sbc1.customers.adatum.biz – 客户租户中的派生中继。 可以在语音路由的客户租户中添加派生中继的名称，而无需创建它。

- 运营商需要设置 DNS 记录，将派生的中继 FQDN 解析为运营商 SBC IP 地址。

- 对运营商中继 (对运营商租户) 所做的任何更改都会自动应用于派生中继。 例如，运营商可以更改运营商中继上的 SIP 端口，此更改适用于所有派生的中继。 配置中继的新逻辑简化了管理，因为无需转到每个租户并更改每个中继上的参数。

- 选项仅发送到运营商中继 FQDN。 运营商中继的运行状况将应用于所有派生中继，并用于路由决策。 详细了解 [直接路由选项](./direct-routing-monitor-and-troubleshoot.md)。

- 载体可以排出载波中继，并且所有派生的中继也会被排出。 
 
> [!NOTE]
> 应用于运营商中继的数字转换规则不适用于派生中继。 这是一个已知问题。 作为替代解决方案，必须为每个客户的租户创建数字转换规则。

**从以前的模型迁移到运营商干线**
 
若要从当前实现的运营商托管模型迁移到新模型，运营商需要重新配置客户租户的中继。 使用将中继保留在运营商租户中的Remove-CSOnlinePSTNGateway (从客户租户中删除中继) -

我们强烈建议尽快迁移到新解决方案，因为我们将使用运营商和派生中继模型来增强监视和预配。
 
有关在联系人标头中配置发送子域的 FQDN 名称的详细信息，请参阅 [SBC 供应商说明](#deploy-and-configure-the-sbc)。

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>设置多租户故障转移的注意事项 

若要为多租户环境设置故障转移，需要执行以下操作：

- 对于每个租户，为两个不同的 SBC 添加 FQDN。 例如：

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 在“联机语音路由”中，指定这两个 SBC。 如果一个 SBC 失败，路由策略会将呼叫路由到第二个 SBC。


## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
