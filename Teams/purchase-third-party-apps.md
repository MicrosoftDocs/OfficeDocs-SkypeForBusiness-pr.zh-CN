---
title: 购买适用于 Teams 的第三方应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: 了解如何使用信用卡、借记卡或通过发票计费从 Teams 应用商店购买第三方应用。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 41882a241a911e7c482a2a9a16c9fa9cfd649e9d
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299191"
---
# <a name="purchase-third-party-apps-for-teams"></a>购买适用于 Teams 的第三方应用

Teams 应用可以免费安装，但有些应用可能需要购买服务订阅才能体验应用的完整功能和范围。 这些服务订阅称为软件即服务 (SaaS) 计划，可通过 [AppSource](https://appsource.microsoft.com/) 购买，现在可通过 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com) 购买。

在 Microsoft Teams 管理中心的“[管理应用](manage-apps.md)”页面上，可以查看并管理组织的所有 Teams 应用。 例如，可以看到应用的组织级别状态和属性、将新的自定义应用上传到组织的应用商店、在组织级别阻止或允许应用，以及管理组织范围的应用设置。

在这里，还可以为组织中用户的第三方应用所提供的服务购买许可证。 表中的“**许可证**”列指示应用是否提供 SaaS 订阅以供购买。

![购买许可证管理应用页面的屏幕截图。](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>在 Teams 管理中心购买应用

若要在 Teams 管理中心购买应用，请执行以下步骤： 

1. 在 Microsoft Teams 管理中心的左侧窗格中，转到“**Teams 应用**” > **“[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)”**。 必须是全局管理员或 Teams 服务管理员才能访问该页面。

1. 按应用名称搜索所需的应用。 要标识具有付费 SaaS 订阅的应用，请查看“**许可证**”列。 每个应用都有以下值之一：
    * **购买**：该应用提供 SaaS 订阅，并且可供购买。  
    * **购买**： 应用提供 SaaS 订阅，并且你已为其购买了许可证。
    * **- -**：应用不提供 SaaS 订阅。

1. 找到应用后，选择“**购买**”转到应用详细信息页面的“**套餐和定价**”选项卡。 查看应用的 SaaS 产品/服务的套餐和定价信息。 如需详细信息，请选择“**了解详细信息**”以转到 [AppSource](https://appsource.microsoft.com/) 上的应用页面。

   > [!NOTE]
   > 可能还会列出可供购买的专用套餐，其中包括组织可以单独与应用开发人员协商的特殊定价。 此类套餐的套餐名称下将会带有“**专用套餐**”标签。

1. 要订阅应用，请选择所需套餐，然后选择“**购买**”。 结帐流直接在 Teams 管理中心打开。

1. 选择要购买的用户许可证数量。

1. 验证计费帐户和买方地址是否正确。 如果还没有计费帐户，请选择“**添加**”。 有关计费帐户的详细信息，请参阅 [了解计费帐户](/microsoft-365/commerce/manage-billing-accounts)。

   > [!NOTE]
   > 只有全局管理员才能添加新的计费帐户。

1. 验证是否已选择正确的计费对象信息。 如果还没有，请选择“**新增**”。 可以选择使用信用卡、借记卡或通过 [发票计费](#invoice-billing) 付款。 使用计费对象信息，还可以添加采购订单号，以便稍后确定订单。 有关计费对象信息的详细信息，请参阅 [了解计费对象信息](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)。

1. 选择“**下单**”。

1. 选择“**设置**”以在应用开发人员的网站上激活订阅。 如果在购买后未设置订阅，可稍后通过选择“**管理许可证**”来进行设置。

购买与 Teams 应用关联的 SaaS 计划后，可以在应用详细信息页面的“**套餐和定价**”选项卡上查看以下购买详细信息。

* **许可证激活日期**：激活许可证的日期。 如果尚未设置帐户，则显示为“**订阅等待激活**”。
* **许可证**：已购买的许可证数量。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Teams 管理中心应用详细信息页上的“套餐和定价”选项卡的屏幕截图。":::

要查看和管理已购买的许可证，可选择“**管理许可证**”以访问 Microsoft 365 管理中心。

全局管理员可以添加更多许可证、移除许可证，以及取消组织中任何人购买的订阅。 Teams 服务管理员可以为自己进行的购买执行相同操作。 但是，如果 Teams 服务管理员也具有计费管理员角色，则他们可以管理组织中任何人进行的购买。

> [!NOTE]
> 如果全局管理员想要管理另一个全局管理员购买的订阅，则需要位于同一计费帐户中。 可以通过在 [Microsoft 365 管理中心](https://admin.microsoft.com) 中选择应用，向其他全局管理员授予对你所购买订阅的访问权限。 在管理中心，访问“**查看计费配置文件**” > “**选择计费帐户**” > “**分配角色**” > “**添加其他全局管理员**”。

> [!IMPORTANT]
> 启用应用购买时，还会启用应用内购买。 用户可能会看到应用内购买产品/服务，这些产品/服务由应用开发人员对其应用进行控制。 若要防止用户购买应用，必须阻止该应用。

### <a name="invoice-billing"></a>发票计费

* 发票计费可用作某些交易的付款选项。
* 首次使用发票计费时需要进行信用审核，这最多可能需要 24 到 48 小时才能完成审批。 在信用检查完成之前，发票计费将不可用。 你可以使用信用卡下达订单，或稍后在信用评审获得批准后重试。
* 发票计费仅适用于全局管理员或同时具有 Teams 服务管理员和计费管理员权限的管理员。
* 购买具有 30 天免费试用期的计划时，发票计费不可用。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>列出并销售 Teams 应用的 SaaS 计划

开发人员可以创建与其 Teams 应用关联的 SaaS 计划。 这些计划通过 [合作伙伴中心](https://partner.microsoft.com) 发布，并可供组织通过 [AppSource](https://appsource.microsoft.com/) 和 Microsoft Teams 管理中心进行购买。

有关第三方应用开发人员的详细信息，请参阅 [创建 SaaS 计划](/azure/marketplace/partner-center-portal/create-new-saas-offer)。

## <a name="related-articles"></a>相关文章

* [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
* [创建 SaaS 计划](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 内置角色](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)
