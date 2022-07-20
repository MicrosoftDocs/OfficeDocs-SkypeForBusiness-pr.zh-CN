---
title: 为 Teams 购买第三方应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava, nsuter
search.appverid: MET150
f1keywords: ''
description: 了解如何使用信用卡、借记卡或发票计费从 Teams 商店购买第三方应用。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 8627d94fc384064b484019ecc17b2e4701e945e8
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880236"
---
# <a name="purchase-third-party-apps-for-teams"></a>为 Teams 购买第三方应用

Teams 应用可以免费安装，有些应用可能需要购买服务订阅才能体验应用的完整功能和范围。 这些服务订阅称为软件即服务 (SaaS) 产品/服务，可通过 [AppSource](https://appsource.microsoft.com/) 购买，现在通过 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)进行购买。

Microsoft Teams 管理中心中的 [“管理应用](manage-apps.md) ”页面是查看和管理组织的所有 Teams 应用的位置。 例如，可以看到应用的组织级状态和属性、将新的自定义应用上传到组织的应用商店、阻止或允许组织级别的应用，以及管理组织范围的应用设置。

在这里，还可以为组织中用户购买第三方应用提供的服务许可证。 表中的 **“许可证”** 列指示应用是否提供 SaaS 订阅进行购买。

![“购买许可证管理应用”页的屏幕截图。](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>在 Teams 管理中心购买应用

> [!IMPORTANT]
> 启用应用购买时，还会启用应用内购买。 用户可能会看到由其应用的 ISV 控制的应用内购买产品/服务。 如果要阻止用户购买应用，则必须阻止该应用。 有关如何阻止应用的详细信息，请参阅 [“管理应用策略](app-policies.md) ”或 [了解如何在组织级别阻止应用](manage-apps.md#allow-and-block-apps)。

1. 在 Microsoft Teams 管理中心的左窗格中，转到 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。 必须是全局管理员或 Teams 服务管理员才能访问该页面。

1. 搜索所需的应用名称。 若要标识具有付费 SaaS 订阅的应用，请查看 **“许可证** ”列。 每个应用都有以下值之一：
    * **购买**：应用提供 SaaS 订阅，可供购买。  
    * **已购买**：应用提供 SaaS 订阅，并且你已为此购买了许可证。
    * **- -**：应用不提供 SaaS 订阅。

1. 找到应用时，选择 **“购买** ”转到应用详细信息页的 **“计划”和“定价** ”选项卡。 查看应用的 SaaS 产品/服务的计划和定价信息。 如果需要更多信息，请选择 **“了解详细** 信息”，转到 [AppSource](https://appsource.microsoft.com/) 上的应用页面。

   > [!NOTE]
   > 也可以列出私人计划进行购买，其中包括组织以前与 ISV 协商过的特殊定价。 这些计划将具有计划名称下的 **“专用计划** ”标签。

1. 若要订阅应用，请选择所需的计划，然后选择 **“购买**”。 结帐流直接在 Teams 管理中心打开。

1. 选择要购买的用户许可证数。

1. 验证计费帐户和已售地址是否正确。 如果还没有，请选择 **“添加**”。 有关计费帐户的详细信息，请参 [阅“了解计费帐户](/microsoft-365/commerce/manage-billing-accounts)”。

   > [!NOTE]
   > 只有全局管理员可以添加新的计费帐户。

1. 验证是否选择了正确的计费配置文件。 如果还没有，请选择 **“添加新**”。 可以选择使用信用卡、借记卡或 [发票计费](#invoice-billing)付款。 通过计费配置文件，还可以添加采购订单号，以便稍后确定订单。 有关计费配置文件的详细信息，请参阅 [“了解计费配置文件](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)”。

1. 选择 **“位置”顺序**。

1. 选择 **“设置”** 以在发布者的网站上激活订阅。 如果购买后未设置订阅，可在以后选择 **“管理许可证**”来完成此操作。

购买与 Teams 应用关联的 SaaS 产品/服务后，可以在应用详细信息页的 **“计划”和“定价** ”选项卡上查看以下购买详细信息。

* **许可证激活日期**：激活许可证的日期。 如果帐户尚未设置，则显示为 **订阅挂起激活**。
* **许可证**：购买的许可证数。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="Teams 管理中心应用详细信息页上的“计划”和“定价”选项卡的屏幕截图。":::

若要查看和管理购买的许可证，请选择 **“管理许可证**”以访问Microsoft 365 管理中心。

全局管理员可以添加更多许可证、删除许可证，以及取消组织中任何人购买的订阅。 Teams 服务管理员可以为自己进行的购买执行相同的操作。 但是，如果 Teams 服务管理员也具有计费管理员角色，则他们可以管理组织中任何人的购买。

> [!NOTE]
> 如果全局管理员想要管理另一个全局管理员购买的订阅，则需要位于同一计费帐户中。 你可以通过在Microsoft 365 管理中心中选择应用，向你购买的订阅授予其他全局[管理员](https://admin.microsoft.com)访问权限。 在此处，转到 **“查看计费配置文件** > **选择计费帐户** > **分配角色** > **添加其他全局管理员**”。

### <a name="invoice-billing"></a>发票计费

* 发票计费可作为某些事务的付款选项。
* 首次使用发票计费时需要进行信用审查，这可能需要长达 24 到 48 小时才能获得批准。 在信用检查完成之前，发票计费将不可用。 可以使用信用卡下订单，也可以在信用审查获得批准后再试。
* 发票计费仅适用于全局管理员或具有 Teams 服务管理员和计费管理员权限的管理员。
* 购买具有 30 天免费试用版的计划时，发票计费不可用。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>列出并销售 Teams 应用的 SaaS 产品/服务

开发人员可以创建与其 Teams 应用关联的 SaaS 产品/服务。 这些产品/服务通过 [合作伙伴中心](https://partner.microsoft.com) 发布，可供组织通过 [AppSource](https://appsource.microsoft.com/) 和 Microsoft Teams 管理中心购买。

有关第三方应用开发人员的详细信息，请参阅 [创建 SaaS 产品/服务](/azure/marketplace/partner-center-portal/create-new-saas-offer)。

## <a name="related-articles"></a>相关文章

* [在 Microsoft Teams 管理中心管理应用](manage-apps.md)
* [创建 SaaS 产品/服务](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 内置角色](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)
