---
title: 购买第三方应用和管理订阅
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 10/04/2022
ms.collection:
- M365-collaboration
ms.reviewer: chhavib, nsuter
search.appverid: MET150
f1keywords: ''
description: 了解如何使用信用卡、借记卡或通过发票计费在 Teams 应用商店中购买付费应用许可证。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 82364d5659009e067a6884551266c6fabf93dc04
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912421"
---
# <a name="purchase-third-party-teams-apps-and-manage-subscriptions"></a>购买第三方 Teams 应用和管理订阅

某些 Teams 应用可能需要购买服务订阅才能体验应用的完整功能和范围。 这些服务订阅称为软件即服务 (SaaS) 套餐。 可以通过 [AppSource](https://appsource.microsoft.com/) 和 [Microsoft Teams 管理中心](https://admin.teams.microsoft.com)购买许可证。

使用与任何其他应用相同的治理控制来管理付费应用。 可以从 Teams 管理中心的“ [管理应用](manage-apps.md) ”页查看和管理所有 Teams 应用。

在“管理应用”页上，还可以为组织中的用户购买第三方应用提供的服务许可证。 表中 **的“许可证** ”列指示应用是否提供 SaaS 订阅以供购买。 最终用户可以使用信用卡、借记卡或发票计费来购买应用。

:::image type="content" source="media/manage-apps-new-page.png" alt-text="显示 Teams 管理中心“管理应用”页上的“购买许可证”选项的屏幕截图。" lightbox="media/manage-apps-new-page-large.png":::

## <a name="purchase-apps-in-the-teams-admin-center"></a>在 Teams 管理中心购买应用

若要在 Teams 管理中心购买应用，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**。 必须是全局管理员或 Teams 服务管理员才能访问该页面。

1. 按应用名称搜索所需的应用。 若要检查应用是否提供付费 SaaS 订阅，请参阅 **“许可证”** 列。 每个应用都有以下值之一：
    * **购买**：该应用提供 SaaS 订阅，并且可供购买。
    * **购买**： 应用提供 SaaS 订阅，并且你已为其购买了许可证。
    * **- -**：应用不提供 SaaS 订阅。

1. 选择“ **购买** ”，转到应用详细信息页的“ **计划和定价** ”选项卡。 可以查看管理中心提供的计划和定价信息。 可以选择“ **了解详细信息** ”链接，转到 [AppSource](https://appsource.microsoft.com/) 上的应用页面。

1. 要订阅应用，请选择所需套餐，然后选择“**购买**”。 结帐流直接在 Teams 管理中心打开。

> [!NOTE]
> 可能还会列出可供购买的专用套餐，其中包括组织可以单独与应用开发人员协商的特殊定价。 此类套餐的套餐名称下将会带有“**专用套餐**”标签。

1. 选择要购买的用户许可证数量。

1. 验证计费帐户和买方地址是否正确。 如果还没有计费帐户，请选择“**添加**”。 有关计费帐户的详细信息，请参阅 [了解计费帐户](/microsoft-365/commerce/manage-billing-accounts)。 只有全局管理员才能添加新的计费帐户。

1. 验证是否已选择正确的计费对象信息。 如果还没有，请选择“**新增**”。 可以使用信用卡、借记卡或 [发票计费进行付款](#invoice-billing)。 使用计费对象信息，还可以添加采购订单号，以便稍后确定订单。 有关计费对象信息的详细信息，请参阅 [了解计费对象信息](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)。

1. 选择“**下单**”。

1. 选择“**设置**”以在应用开发人员的网站上激活订阅。 如果在购买后未设置订阅，可以稍后通过选择“ **管理订阅**”来设置订阅。

购买与 Teams 应用关联的 SaaS 产品/服务后，可以在应用详细信息页的“ **计划和订阅** ”选项卡上查看以下购买详细信息。

* **许可证激活日期**：激活许可证的日期。
* **许可证**：购买的许可证数。

  :::image type="content" source="media/manage-apps-plans-and-subscription.png" alt-text="Teams 管理中心应用详细信息页上的“套餐和定价”选项卡的屏幕截图。" lightbox="media/purchase-third-party-apps-details-page.png":::

选择“ **管理订阅** ”以查看和管理你购买的许可证。

全局管理员可以查看组织中任何人购买的订阅，但他们只能添加更多许可证、删除许可证以及取消其计费帐户中任何人购买的订阅。 Teams 服务管理员可以为自己进行的购买执行相同操作。

> [!NOTE]
> 如果全局管理员想要管理另一个全局管理员购买的订阅，则需要位于同一计费帐户中。 可以通过在 [Microsoft 365 管理中心](https://admin.microsoft.com) 中选择应用，向其他全局管理员授予对你所购买订阅的访问权限。 在管理中心，访问“**查看计费配置文件**” > “**选择计费帐户**” > “**分配角色**” > “**添加其他全局管理员**”。

> [!IMPORTANT]
> 启用应用购买时，还会启用应用内购买。 用户可能会看到应用内购买产品/服务，这些产品/服务由应用开发人员对其应用进行控制。 若要防止用户购买应用，必须阻止该应用。

### <a name="invoice-billing"></a>发票计费

* 发票计费可用作某些交易的付款选项。
* 首次使用发票计费时需要进行信用审核，这最多可能需要 24 到 48 小时才能完成审批。 在信用检查完成之前，发票计费将不可用。 你可以使用信用卡下达订单，或稍后在信用评审获得批准后重试。
* 发票计费仅适用于全局管理员或同时具有 Teams 服务管理员和计费管理员权限的管理员。
* 购买具有 30 天免费试用期的计划时，发票计费不可用。

## <a name="manage-subscriptions-in-teams-admin-center"></a>在 Teams 管理中心管理订阅

在 Teams 管理中心中，可以管理购买的应用订阅和许可证。 可以查看应用订阅列表及其详细信息，并执行以下操作：

* 更改计划
* 购买或删除许可证
* 更新付款方式
* 取消订阅
* 查看发票

  :::image type="content" source="media/manage-existing-subscriptions-actions.png" alt-text="应用的订阅详细信息的屏幕截图。" lightbox="media/manage-existing-subscriptions-all.png":::

若要管理订阅，请执行以下步骤：

1. 登录到 Teams 管理中心并访问 **Teams 应用** > [**管理应用**](https://admin.teams.microsoft.com/policies/manage-apps) 。

1. 选择“ **订阅** ”选项卡以查看购买的订阅。

   :::image type="content" source="media/subscription-options-in-manage-apps.png" alt-text="“管理应用”页中应用的订阅选项的屏幕截图。" lightbox="media/manage-app-subscriptions-manage-apps.png":::

> [!NOTE]
> 在 Teams 管理中心中，可以管理你或属于同一计费帐户的其他管理员购买的应用订阅。 若要查看其他管理员为同一租户购买或使用不同计费帐户购买的所有应用订阅，请访问[Microsoft 365 管理中心](https://admin.microsoft.com/adminportal/home#/homepage)。

## <a name="list-and-sell-a-saas-offer-for-a-teams-app"></a>列出并销售 Teams 应用的 SaaS 计划

开发人员可以创建与其 Teams 应用关联的 SaaS 计划。 这些计划通过 [合作伙伴中心](https://partner.microsoft.com) 发布，并可供组织通过 [AppSource](https://appsource.microsoft.com/) 和 Microsoft Teams 管理中心进行购买。

有关第三方应用开发人员的详细信息，请参阅 [创建 SaaS 计划](/azure/marketplace/partner-center-portal/create-new-saas-offer)。

## <a name="related-articles"></a>相关文章

* [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
* [创建 SaaS 计划](/azure/marketplace/partner-center-portal/create-new-saas-offer)
* [Azure Active Directory 内置角色](/azure/active-directory/roles/permissions-reference)
* [Microsoft 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)
