---
title: 在 Microsoft Teams 管理中心管理应用
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何管理 Teams 应用。 了解如何允许或阻止应用、检查组织级别状态和应用属性、上传自定义应用和管理应用设置。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 3278d7cdbc144f839bbb6a675ff8f3e5168c80ed
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705821"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心管理 Teams 应用

可在 Microsoft Teams 管理中心内的 **“Teams 应用”** 中管理你组织的应用。 使用“管理应用”页面可以查看和管理组织应用目录中的所有 Teams 应用、满足应用管理的突出用例、使用策略定义对应用的访问权限等。

:::image type="content" source="media/manage-apps.png" alt-text="“管理应用”页的屏幕截图。" lightbox="media/manage-apps.png":::

若要管理应用，可以使用策略来控制用户的权限、应用的安装以及在组织中创建的自定义应用的上传。 若要了解策略，请参阅 [应用策略概述](app-policies.md)。

若要使用 Teams 管理中心，必须具有全局管理员或 Teams 管理员角色。 有关详细信息，请参阅 [Teams 管理员角色](./using-admin-roles.md) 和 [Microsoft 365管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

> [!NOTE]
> “管理应用”页面在 Teams 的 Microsoft 365 政府社区云 High （GCCH） 或国防部 （DoD） 部署中不可用。

在创建应用期间，开发人员会创建应用 ID 并将其添加到清单文件。 从列设置中启用列后，可以在“管理应用”`External app ID`页上查看此外部应用 ID。 还可以在自定义应用的应用详细信息页上查看它。 该 ID 仅适用于自定义应用。

## <a name="app-management-use-cases-and-the-available-interfaces"></a>应用管理用例和可用接口

Teams 管理中心提供用于完成大多数应用管理用例的选项。 此外，其他门户或 Teams 管理中心的不同页面中也提供了一些选项。

管理中心支持的应用管理任务位于下表中。

| 应用管理用例 | 添加到接口 | 文档 |
|:----|:----|:----|
| 通过允许和阻止应用来控制组织中的用户可用的应用。 还可以上传和批准自定义应用。 在此页面上管理应用后，可以使用应用权限和应用设置策略来配置组织应用商店中特定用户可用的应用。 | [在 Teams 管理中心管理应用](https://admin.teams.microsoft.com/policies/manage-apps) | 当前文章 |
| 应用权限策略控制要向组织中的 Teams 用户提供哪些应用。 可使用全局 (组织范围) 默认策略并对其进行自定义，也可创建一个或多个策略来满足组织的需求。 | [权限策略](https://admin.teams.microsoft.com/policies/app-permission) | [管理应用权限策略](teams-app-permission-policies.md) |
| 应用设置策略控制如何通过 Teams 应用向用户提供应用。 可使用全局 (默认为组织范围) 策略并对其进行自定义，也可创建自定义策略并将其分配给一组用户。 | [设置策略](https://admin.teams.microsoft.com/policies/app-setup) | [管理应用设置策略](teams-app-setup-policies.md) |
| 可以开发和上传自定义应用作为应用包，并使其在组织的应用商店中可用。 | 管理应用中的组织范围 [应用](https://admin.teams.microsoft.com/policies/manage-apps)设置 | [管理自定义应用策略](teams-custom-app-policies-and-settings.md) |
| 可以使用组织的徽标、自定义背景或颜色自定义 Teams 应用商店。 | [自定义存储](https://admin.teams.microsoft.com/policies/customize-appstore) | [自定义组织的应用商店](customize-your-app-store.md) |
| Teams 应用使用情况报表提供有关正在使用的应用、活动用户和其他应用使用情况信息的信息。 | [使用率报告](https://admin.teams.microsoft.com/analytics/reports) | [Teams 应用使用情况报告](teams-analytics-and-reports/app-usage-report.md) |
| 用户可以在主持会议或与来宾聊天时添加应用。 他们还可以使用来宾在加入外部托管的会议或聊天时共享的应用。 将应用托管用户组织的数据策略，以及该用户组织共享的任何第三方应用的数据共享做法。 | [外部访问](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [应用行为，具体取决于用户类型](non-standard-users.md) |
| 通过来宾访问，你可以向组织外部的人员提供对应用程序和其他 Teams 功能的访问权限，同时保持对公司数据的控制。 | [来宾访问](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Teams 中的来宾访问](guest-access.md) |
| Teams 更新策略用于管理 Teams 和 Office 预览版用户，这些用户可以在 Teams 应用中查看预发布或预览功能。 | [Teams 更新策略](https://admin.teams.microsoft.com/policies/updatemanagement) | [Teams 公共预览版](public-preview-doc-updates.md) |

下表列出了其他门户上支持的应用管理任务。

| 应用管理用例 | 添加到接口 | 文档 |
|:----|:----|:----|
| 在 Microsoft 365 管理中心 中管理第三方应用的许可证和订阅 | [Microsoft 365 管理中心](https://admin.microsoft.com/#/licenses) | [管理第三方应用订阅](/microsoft-365/commerce/manage-saas-apps) |
| 审核 Microsoft Purview 合规性门户上的 Teams 应用事件。 | [审核](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Teams 活动](audit-app-management-activities.md) |
| 可以通过三种方法向应用程序授予对组织及其数据的权限：管理员同意所有用户使用应用程序、用户向应用程序授予许可，或者管理员集成应用程序并启用自助访问权限或将用户直接分配到应用程序。 验证应用的 Graph 权限。 验证用户提供的权限或管理员委派的权限。 | [Azure AD门户](https://aad.portal.azure.com/) | [查看授予应用程序的权限](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>允许和阻止应用

“管理应用”页允许或阻止组织级别的单个应用。 该页面显示所有可用应用及其当前组织级别的应用状态。 应用列表包括 Microsoft、第三方开发人员和组织内开发人员提供的应用。

若要允许或阻止应用，请执行以下操作：

1. 登录 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)**
1. 从应用列表中选择应用。 可以按应用的名称进行搜索。
1. 选择 **“允许** ”或 **“阻止”** 选项。

在 Teams 管理中心的“ [管理应用](https://admin.teams.microsoft.com/policies/manage-apps) ”页上允许（或阻止）应用时，组织中的所有用户均允许（或阻止）特定应用。 此方法与上下文中的应用权限策略不同，因为允许（或阻止）应用通过权限策略，只会影响分配了策略的特定用户。

仅当通过租户范围的设置允许应用并通过权限策略允许用户使用时，用户才能安装和使用应用。

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>允许开发人员阻止的应用

当开发人员将应用发布到 Teams 应用商店时，某些应用可能需要管理员来配置应用。 设置完应用程序后，管理员向最终用户提供应用程序。

例如，Contoso Electronics 是为 Microsoft Teams 创建技术支持应用的应用开发人员。 Contoso Electronics 希望其客户设置应用的某些属性，以便当用户与应用交互时，它按预期运行。 在管理员允许应用程序之前，它将在 Teams 管理中心显示为“**被发布者阻止**”，默认情况下对最终用户隐藏。 按照发布者的指南设置应用后，可以通过将状态更改为“ **允许**”，使其可供用户使用。

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Teams 管理中心中被发布者状态阻止的屏幕截图。":::

有关开发人员默认情况下如何阻止应用的信息，请参阅 [启用阻止应用，直到管理员允许应用](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves)。

## <a name="manage-org-wide-app-settings"></a>管理组织范围的应用设置

使用组织范围的应用设置来控制具有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) 的用户是否获得定制的一线应用体验、用户是否可以安装第三方应用，以及用户是否可以上传或与组织中的自定义应用交互。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。

> [!NOTE]
> 若要了解如何在 Microsoft 365 Government 中使用组织范围的应用设置 - 政府社区云 Teams 的高 GCCH 和国防部 （DoD） 部署，请参阅 [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

1. 在 **[“管理应用](https://admin.teams.microsoft.com/policies/manage-apps)** ”页上，选择 **组织范围的应用设置**。 然后，你可以在面板中配置所需的设置。

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="“管理应用”页上“组织范围的应用设置”窗格的屏幕截图":::

1. 在“**定制应用**”下，关闭或打开“**显示定制应用**”。 启用此设置后，具有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户可获得定制的一线应用体验。 此体验会为一线工作人员固定 Teams 中最相关的应用。 若要了解详细信息，请参阅 [为一线员工定制 Teams 应用](pin-teams-apps-based-on-license.md)。

    此功能适用于 F 许可证。 将来将支持其他许可证类型。
1. 在“**第三方应用**”下，关闭或打开这些设置以控制对第三方应用的访问权限：

    * **允许第三方应用**：控制用户是否可以使用第三方应用。 如果关闭此设置，则用户将无法安装或使用任何第三方应用，并且这些应用的应用状态在表中显示为 **“已阻止的组织范围** ”。

        > [!NOTE]
        > **当“允许第三方应用** ”关闭时，仍会为所有用户启用 [传出 Webhook](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ，但你可以通过应用权 [限策略](teams-app-permission-policies.md)允许或阻止传出 Webhook 应用在用户级别控制它们。 请注意，如果现有 **Microsoft 应用** 的 [应用权限策略](teams-app-permission-policies.md) 使用“ **允许特定应用”并阻止所有其他** 设置，并且你希望为用户启用传出 Webhook，请将传出 Webhook 应用添加到列表中。

        > [!NOTE]
        > 主持会议或与来自其他组织的人员聊天时，Teams 用户可以添加应用。 当他们加入由其他组织主持的会议或聊天时，也可以使用由这些组织的人共享的应用。 将应用主持用户组织的数据策略，以及该用户组织共享的任何第三方应用的数据共享实践。

    * **默认情况下，允许发布到应用商店的所有新的第三方应用**：控制发布到 Teams 应用商店的新第三方应用是否在 Teams 中自动可用。 仅在允许第三方应用时才能设置此选项。

1. 在 **自定义应用** 下，关闭或打开 **允许与自定义应用交互**。 此设置控制用户是否可以与自定义应用交互。 要了解详细信息，请参阅[在 Teams 中管理自定义应用策略和设置](teams-custom-app-policies-and-settings.md)。
1. 单击“**保存**”以使组织范围的应用设置生效。

## <a name="related-article"></a>相关文章

* [从 Skype for Business 管理中心过渡期间管理 Teams](manage-teams-skypeforbusiness-admin-center.md)
* [管理用户请求以允许应用](user-requests-approve-apps.md)。
