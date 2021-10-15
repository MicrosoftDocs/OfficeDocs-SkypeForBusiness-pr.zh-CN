---
title: 购买第三方应用Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: chhavib, vaibhava
search.appverid: MET150
f1keywords: ''
description: 了解如何在 Microsoft Teams 管理中心Teams第三方应用。
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 6d7a6e1a38327cef327a9de119321127b58909fb
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367530"
---
# <a name="purchase-third-party-apps-for-teams"></a>购买第三方应用Teams

Teams应用可免费安装，某些应用可能需要购买服务订阅，以体验应用的完整功能和范围。 这些服务订阅称为软件即服务 (SaaS) 产品/服务，现在可以通过[AppSource](https://appsource.microsoft.com/)购买，现在Microsoft Teams中心购买。

管理[中心](manage-apps.md)中的"Microsoft Teams"页面是查看和管理组织Teams应用的地方。 例如，可以看到应用的组织级状态和属性、将新的自定义应用上载到组织的应用商店、在组织级别阻止或允许应用，以及管理组织范围内的应用设置。

在此处，还可以购买第三方应用为组织用户提供的服务的许可证。 表中的 **"** 许可证"列指示应用是否提供 SaaS 订阅进行购买。

![购买许可证管理应用页面的屏幕截图。](media/manage-apps-new-page.png)

## <a name="purchase-apps-in-the-teams-admin-center"></a>在管理中心Teams应用

> [!IMPORTANT]
> 如果你希望阻止你的用户通过应用商店购买Teams，你必须阻止该应用。 若要详细了解如何阻止应用，请参阅 [管理](app-policies.md) 应用策略或了解如何在组织 [级别阻止应用](manage-apps.md#allow-and-block-apps)。

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。 必须是全局管理员或Teams管理员才能访问页面。
2. 搜索你需要的应用。 若要识别具有付费 SaaS 订阅的应用，请查找"许可证 **"** 列。 每个应用将具有以下值之一：
    - **购买**：该应用提供 SaaS 订阅，可供购买。  
    - **已** 购买：该应用提供 SaaS 订阅，并且你已购买其许可证。
    - **- -**：应用未提供 SaaS 订阅。
3. 找到应用时，单击" **购买** "转到应用详细信息 **页的** "计划和定价"选项卡。 查看应用的 SaaS 套餐的计划和定价信息。 如果你需要更多信息，请选择" **了解详细信息** "以转到 [AppSource 上的应用页面](https://appsource.microsoft.com/)。

> [!NOTE]
> 还可以列出专用计划进行购买，其中包括组织以前与 ISV 协商的特殊定价。 这些计划在计划 **名称下带有** "专用计划"标签。

4. 若要订阅应用，请选择想要的计划，然后选择"购买 **"。** 结帐流将在管理中心Teams打开。
5. 选择要购买的用户许可证数。
6. 检查计费帐户和售达地址是否正确。 如果还没有，请通过选择"添加"来添加新 **的 。** 有关计费帐户的信息，请参阅 [了解计费帐户](/microsoft-365/commerce/manage-billing-accounts)。

> [!NOTE]
> 只有全局管理员才能添加新的计费帐户。

7. 检查是否选择了正确的计费配置文件。 如果还没有，请通过选择"添加新" **来添加新的**。 可以选择使用信用卡、借记卡或发票计费付款。 计费配置文件还允许您添加采购订单编号，以便以后标识订单。 有关计费配置文件详细信息，请参阅 [了解计费配置文件](/microsoft-365/commerce/billing-and-payments/manage-billing-profiles)。

> [!NOTE]
> 发票计费仅适用于超过 500 美元的交易。

8. 选择 **"下单"。**
9. 选择 **"设置** "以在发布者的网站上激活订阅。 如果在购买后没有设置订阅，可以在以后选择"管理许可证 **"来设置订阅**。

购买与 Teams 应用关联的 SaaS 产品/服务后，可以在应用详细信息页的"计划和定价"选项卡上查看以下购买详细信息。

- **许可证激活日期**：激活许可证的日期。 如果你的帐户尚未设置，这将显示为"订阅挂起 **激活"。**
- **许可证**：购买的许可证数。

:::image type="content" source="media/purchase-third-party-apps-details-page.png" alt-text="应用详细信息页的计划和定价选项卡的屏幕截图。":::

选择 **"管理** 许可证"，转到Microsoft 365 管理中心以查看和管理购买的许可证。

全局管理员可以添加更多许可证、删除许可证以及取消组织中任何人购买的订阅。 Teams管理员可以对自己购买的购买执行相同的操作。 但是，如果Teams管理员也具有计费管理员角色，他们可以管理组织中任何人的购买。

> [!NOTE]
> 如果全局管理员想要管理由另一个全局管理员购买的订阅，则需要在同一计费帐户中。 可以通过选择订阅中的应用，为另一个全局管理员授予对所购买的订阅Microsoft 365 管理中心。 从该页转到"**查看计费配置文件"**  >  **选择计费帐户**  >  **""分配角色**  >  **""添加其他全局管理员"。**

## <a name="have-a-saas-offer-for-a-teams-app-that-you-want-to-list-and-sell-in-the-microsoft-teams-admin-center-and-appsource"></a>在管理中心和 AppSource 中Teams销售的 SaaS 产品/Microsoft Teams SaaS 产品/服务？

开发人员可以创建与其应用应用关联的 SaaS Teams产品/服务。 这些产品/服务通过[合作伙伴中心发布](https://partner.microsoft.com)，可供组织通过[AppSource](https://appsource.microsoft.com/)和 Microsoft Teams购买。

第三方应用开发人员可以转到 [创建 SaaS 产品/](/azure/marketplace/partner-center-portal/create-new-saas-offer) 服务了解详细信息。

## <a name="related-topics"></a>相关主题

- [在管理中心内Microsoft Teams应用](manage-apps.md)
- [创建 SaaS 产品/服务](/azure/marketplace/partner-center-portal/create-new-saas-offer)
- [Azure AD内置角色](/azure/active-directory/roles/permissions-reference)
- [Microsoft 365管理员角色](/microsoft-365/admin/add-users/about-admin-roles)