---
title: 配置会话边框控制器 - 多个租户
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
description: 了解如何配置一个会话边界控制器 (SBC) ，为 Microsoft 合作伙伴和/或 PSTN 运营商提供多个租户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: be75743752f34024baf7b2fd017557c2f0044ba6
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823683"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>为多个租户配置会话边界控制器

直接路由支持将一个会话边界控制器 (SBC) 配置为为多个租户提供服务。

> [!NOTE]
> 此方案专为 Microsoft 合作伙伴和/或 PSTN 运营商设计，在本文档后面称为运营商。 一家运营商销售提供给Microsoft Teams的客户的电话服务。 

承运人：
- 在数据中心部署和管理 SBC (客户无需实现 SBC，并且他们从Teams客户端) 中从运营商接收电话服务。
- 将 SBC 连接到多个租户。
- 向客户提供公共交换电话网络 (PSTN) 服务。
- 端到端管理调用质量。
- PSTN 服务单独收费。

Microsoft 不管理运营商。 Microsoft 提供电话系统（专用分支Exchange (PBX) ）和Teams客户端。 Microsoft 还会认证手机，并认证可用于电话系统的 SBC。 在选择运营商之前，请确保所选内容具有经过认证的 SBC，并且可以端到端管理语音质量。

下面是用于配置方案的技术实现步骤。

**仅限承运人：**
1. 根据 [经认证的 SBC 供应商的说明部署 SBC](#deploy-and-configure-the-sbc) 并将其配置为托管方案。
2. 在承运人租户中注册基本域名并请求通配符证书。
3. 为每个客户注册子域，这是基本域的一部分。

**具有客户全局管理员的运营商：**
1. 将子域名称添加到客户租户。
2. 激活子域名称。
3. 将中继从运营商配置为客户租户并预配用户。

*请确保了解 DNS 基础知识以及如何在Microsoft 365中管理域名。请参阅 [有关Microsoft 365域的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)，然后再继续。*

## <a name="deploy-and-configure-the-sbc"></a>部署和配置 SBC

有关如何部署和配置 SBC 托管方案的 SBC 的详细步骤，请参阅 SBC 供应商的文档。

- **AudioCodes：** 请参阅有关 SBC 托管方案配置 [的直接路由配置说明](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)，如“将 AudioCodes SBC 连接到Microsoft Teams直接路由托管模型配置说明”中所述。 
- **甲骨文：** 请参阅“Microsoft”部分中所述的 SBC 托管方案配置 [的直接路由配置说明](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) 。 
- **功能区通信：** 有关如何配置功能区核心系列 SBC 的文档，请参阅 [功能区通信 SBC Core Microsoft Teams配置指南](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe)。 另请参阅[功能区最佳做法 - 为Microsoft Teams直接路由 SBC Edge 配置承运人](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (任何节点) ：** 在 [TE-Systems Community 页面](https://community.te-systems.de/)站点上注册，以获取有关如何为多个租户配置任何节点 SBC 的文档和示例。
- **Metaswitch：** 在 [Metaswitch Community 页面](https://manuals.metaswitch.com/MAN39555)站点上注册，以获取有关如何为多个租户启用 Perimeta SBC 的文档。

> [!NOTE]
> 请确保了解如何配置“联系人”标头。 联系人标头用于在传入邀请消息上查找客户租户。 

## <a name="register-a-base-domain-and-subdomains"></a>注册基域和子域

对于托管方案，需要创建：

- 运营商拥有的一个基本域名。
- 作为每个客户租户中基本域名的一部分的子域。

在以下示例中：

- Adatum 是一家通过提供 Internet 和电话服务为多个客户提供服务的运营商。
- Woodgrove Bank、Contoso 和 Adventure Works 是三个拥有Microsoft 365域但从 Adatum 接收电话服务的客户。

子域 **必须** 与将客户配置的中继的 FQDN 名称匹配，并将邀请发送到Microsoft 365时，在联系人标头中配置 FQDN。 

当呼叫到达Microsoft 365直接路由接口时，该接口使用联系人标头查找应查找用户的租户。 直接路由不会在“邀请”上使用电话号码查找，因为某些客户的非 DID 号码可能在多个租户中重叠。 因此，联系人标头中的 FQDN 名称需要标识确切的租户才能按电话号码查找用户。

*有关在Microsoft 365组织中创建域名的详细信息，[请参阅有关Microsoft 365域的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。*

下图汇总了对基本域、子域和联系人标头的要求。

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="显示域和联系人标头要求的示意图。" lightbox="media/direct-routing-1-sbc-requirements.png":::

SBC 需要证书才能对连接进行身份验证。 对于 SBC 托管方案，承运人需要请求具有 CN 和/或 SAN *\*.base_domain (的证书， \*例如 .customers.adatum.biz)*。 此证书可用于对从单个 SBC 提供的多个租户的连接进行身份验证。

下表是一个配置的示例。


|新域名 |类型|注册  |SBC 的证书 CN/SAN  |示例中的租户默认域  |向用户发送呼叫时 SBC 必须在联系人标头中显示的 FQDN 名称|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    基地     |     在承运人租户中  |    \*.customers.adatum.biz  |   adatum.biz      |NA，这是一个服务租户，没有用户 |
|sbc1.customers.adatum.biz|    子域  |    在客户租户中  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   子域 | 在客户租户中   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   子域 | 在客户租户中 |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

若要配置基域和子域，请执行以下步骤。 本示例为 Woodgrove Bank 租户) 中的一个客户 (sbc1.customers.adatum.biz 配置基本域名 (customers.adatum.biz) 和子域。

> [!NOTE]
> 使用 sbcX.customers.adatum.biz 在承运人租户中启用语音;sbcX 可以是任何唯一且有效的字母数字主机名。

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>在承运人租户中注册基本域名

**这些操作在承运人租户中执行。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>确保在承运人租户中拥有适当的权限

只有以全局管理员身份登录到Microsoft 365 管理中心，才能添加新域。 

若要验证你拥有的角色，请登录到Microsoft 365 管理中心 (https://portal.office.com)，转到 **“用户** > **活动用户**”，然后验证你是否具有全局管理员角色。 

有关管理员角色以及如何在Microsoft 365中分配角色的详细信息，[请参阅“关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)”。

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>将基域添加到租户并对其进行验证

1. 在Microsoft 365 管理中心中，转到 **“设置** > **域** > **添加域**”。

2. 在 **“输入你拥有的域** ”框中，键入基域的 FQDN。 在下面的示例中，基本域 *customers.adatum.biz*。

3. 单击" **下一步**"。

4. 在此示例中，租户已 adatum.biz 为已验证的域名。 向导不会要求其他验证，因为 customers.adatum.biz 是已注册名称的子域。 但是，如果添加了之前尚未验证的 FQDN，则需要完成验证过程。 [验证过程如下所述](#add-a-subdomain-to-the-customer-tenant-and-verify-it)。

5. 选择 **“下一步**”，然后在 **“更新 DNS 设置**”页上，选择 **“我自己添加 DNS 记录**”，然后选择 **“下一步**”。

6. 在下一页上，清除 (的所有值，除非你要将域名用于Exchange、SharePoint、Teams或Skype for Business) ，选择 **“下一步**”，然后选择 **“完成**”。 确保新域处于安装程序完整状态。

### <a name="activate-the-domain-name"></a>激活域名

注册域名后，需要通过添加至少一个具有电话系统许可证的用户并使用与创建的基域匹配的 SIP 地址的 FQDN 部分分配 SIP 地址来激活它。

> [!NOTE]
> 承运商租户必须保留至少一个分配给租户的电话系统许可证，以避免删除Skype for Business配置。 

*有关在Microsoft 365组织中添加用户的详细信息，[请参阅有关Microsoft 365域的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。*

例如：test@customers.adatum.biz

![基本域激活页的屏幕截图。](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>在客户租户中注册子域名称

需要为每个客户创建唯一的子域名称。 在此示例中，我们将在具有默认域名 woodgrovebank.us 的租户中创建子域 sbc1.customers.adatum.biz。

**以下所有操作都在客户租户中。**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>确保你在客户租户中拥有适当的权限

只有以全局管理员身份登录到Microsoft 365 管理中心，才能添加新域。 

若要验证你拥有的角色，请登录到Microsoft 365 管理中心 (https://portal.office.com)，转到 **“用户** > **活动用户**”，然后验证你是否具有全局管理员角色。 

有关管理员角色以及如何在Microsoft 365中分配角色的详细信息，[请参阅“关于管理员角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)”。

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>将子域添加到客户租户并对其进行验证

1. 在Microsoft 365 管理中心中，转到 **“设置** > **域** > **添加域**”。

2. 在 **“输入你拥有的域** ”框中，键入此租户的子域的 FQDN。 在下面的示例中，子域 sbc1.customers.adatum.biz。

3. 选择 **“下一步**”。

4. FQDN 从未在租户中注册过。 在下一步中，需要验证域。 请改为选择 **“添加 TXT 记录**”。 

5. 选择 **“下一步**”，并记下为验证域名而生成的 TXT 值。

    ![“验证域”页上的文本记录的屏幕截图。](media/direct-routing-7-sbc-verify-domain-txt.png)

6. 在运营商的 DNS 托管提供程序中使用上一步中的值创建 TXT 记录。

    有关详细信息，请参阅 [在任何 DNS 托管提供程序处创建 DNS 记录](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)。

7. 转到客户的Microsoft 365 管理中心，然后选择 **“验证**”。 

8. 在下一页上，选择 **“我将自己添加 DNS 记录** ”，然后选择 **“下一步**”。

9. 在 **“选择联机服务** 页上，清除所有选项，然后选择 **”下一步**”。

10. 在 **“更新 DNS 设置**”页上选择 **“完成**”。

11. 确保状态 **设置已完成**。 
    
    ![显示安装程序完成状态的页面的屏幕截图。](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> 单个客户端的基 URL 和子域必须位于同一租户上，才能添加 _直接路由_ 中继。

### <a name="activate-the-subdomain-name"></a>激活子域名称

注册域名后，需要通过添加至少一个用户并分配 SIP 地址的 FQDN 部分（与客户租户中创建的子域匹配）来激活该域名。 

*有关在Microsoft 365组织中添加用户的详细信息，[请参阅有关Microsoft 365的帮助](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)。*

例如：test@sbc1.customers.adatum.biz

![“激活子域”页的屏幕截图。](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>创建中继并预配用户

随着直接路由的初始发布，Microsoft 需要使用 New-CSOnlinePSTNGateway cmdlet 将一个中继添加到每个服务租户 (客户租户) 。

但是，由于以下两个原因，此方法未被证明是最佳方法：
 
- **开销管理**。 例如，卸载或排出 SBC 会更改某些参数，例如启用或禁用媒体旁路。 更改端口需要通过运行 Set-CSOnlinePSTNGateway)  (更改多个租户中的参数，但实际上它与 SBC 相同。 

-  **开销处理**。 收集和监视中继运行状况数据 - 从多个逻辑中继收集的 SIP 选项（实际上是相同的 SBC 和相同的物理中继）会减慢路由数据的处理速度。
 
根据此反馈，Microsoft 引入了一个新的逻辑来预配客户租户的中继。

引入了两个新实体：

- 使用命令 New-CSOnlinePSTNGateway 在承运人租户中注册的承运人中继。 例如： 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- 不需要注册的派生中继。 它只是从承运人中继添加的所需主机名。 它从承运人中继派生其所有配置参数。 派生中继无需在 PowerShell 中创建，并且与承运人中继的关联基于 FQDN 名称 (请参阅下面) 的详细信息。

**预配逻辑和示例**

- 承运商只需使用Set-CSOnlinePSTNGateway命令设置和管理承运商域)  (单个中继。 在上面的示例中，它 adatum.biz。

- 在客户租户中，运营商需要将派生中继 FQDN 添加到语音路由。 无需为中继运行New-CSOnlinePSTNGateway。

- 派生中继（顾名思义）继承或派生从承运人中继的所有配置参数。 

例子：
- Customers.adatum.biz - 需要在承运人租户中创建的承运人中继。

- Sbc1.customers.adatum.biz - 无需在 PowerShell 中创建的客户租户中的派生中继。 可以在联机语音路由策略中添加客户租户中派生中继的名称，而无需创建它 (在注册) Routing-Voice的路由字段 SBC Teams 下在 TAC 中设置语音路由策略时使用派生中继 FQDN。

- 承运商需要设置 DNS 记录解析派生中继 FQDN 到运营商 SBC IP 地址。

- 对承运人租户) 上的承运人中继 (所做的任何更改都将自动应用于派生中继。 例如，承运人可以更改承运人中继上的 SIP 端口，此更改适用于所有派生中继。 配置中继的新逻辑简化了管理，因为无需转到每个租户并更改每个中继上的参数。

- 这些选项仅发送到运营商中继 FQDN。 承运人中继的运行状况应用于所有派生中继，用于路由决策。 详细了解 [直接路由选项](./direct-routing-monitor-and-troubleshoot.md)。

- 承运人可以排干承运人中继，所有派生中继也会被排干。 
 
> [!NOTE]
> 对承运人中继应用的数字转换规则不适用于派生中继。 这是一个已知问题。 作为替代解决方案，必须为每个客户的租户创建数字转换规则。

**从上一个模型迁移到承运人中继**
 
若要从运营商托管模型的当前实现迁移到新模型，承运商需要重新配置客户租户的中继。 使用将中继留在承运商租户) Remove-CSOnlinePSTNGateway (从客户租户中删除中继-

我们强烈建议尽快迁移到新解决方案，因为我们将使用运营商和派生中继模型加强监视和预配。
 
有关在联系人标头中配置发送子域的 FQDN 名称的详细信息，请参阅 [SBC 供应商说明](#deploy-and-configure-the-sbc)。

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>设置多租户故障转移的注意事项 

若要为多租户环境设置故障转移，需要执行以下操作：

- 对于每个租户，为两个不同的 SBC 添加 FQDN。 例如：

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- 在联机语音路由中，指定两个 SBC。 如果一个 SBC 失败，则路由策略会将调用路由到第二个 SBC。


## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
