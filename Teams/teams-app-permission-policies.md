---
title: 在 Microsoft Teams 中管理应用权限策略
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 了解 Microsoft Teams 中的应用权限策略，以及如何控制最终用户的应用可用性。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aac7024730c3f18e1c0f38a2e041dea840a6b869
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912401"
---
# <a name="use-app-permission-policies-to-control-user-access-to-apps"></a>使用应用权限策略控制用户对应用的访问

作为管理员，你可以使用应用权限策略来控制组织中每个用户可用的应用。 你设置为允许或阻止所有应用或特定应用的权限适用于 [Teams 中的所有类型的应用](deploy-apps-microsoft-teams-landing-page.md)。 必须是全局管理员或 Teams 服务管理员才能管理这些策略。

若要允许应用，必须在 [组织范围的应用设置](manage-apps.md#manage-org-wide-app-settings)、 [单个应用的](manage-apps.md#allow-and-block-apps)设置和应用权限策略中允许应用。 虽然其他两种方法只允许在组织中使用应用，但权限策略允许你控制哪些用户可以使用特定应用。 通过创建策略并将其应用于特定用户，可以控制每个用户和每个应用的访问权限。

Teams 管理中心允许创建两种类型的权限策略：

* `Global (Org-wide default)` 策略默认存在，适用于所有用户。 对此策略所做的任何更改都会影响所有用户，因为默认情况下，此策略将应用于所有用户。
* 管理员创建的策略仅适用于应用该策略的用户。 创建新策略以允许特定用户或用户组应用。

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="显示正在创建新的应用权限策略的屏幕截图。" lightbox="media/app-permission-policy.png":::

如果组织已在 Teams 中，在 Microsoft 365 管理中心的 **租户范围设置** 中配置的应用设置将反映在 Teams 管理中心 [“管理应用](https://admin.teams.microsoft.com/policies/manage-apps)”页上的组织范围应用设置中。 如果你不熟悉 Teams 并且刚刚入门，则默认情况下，组织范围的全局设置允许所有应用。 它包括 Microsoft、第三方软件提供商和组织发布的应用。

> [!NOTE]
> 若要了解 Microsoft 365 政府版社区云高 (GCCH) 和国防部 (DoD) 环境中的第三方 [应用设置，请参阅管理 Microsoft 365 政府版组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government)。

## <a name="create-an-app-permission-policy"></a>创建应用权限策略

如果要控制可用于不同用户组的应用，请使用一个或多个自定义应用权限策略。 根据应用是由 Microsoft、第三方还是由你的组织发布，你可以创建并分配单独的自定义策略。 创建自定义策略后，如果在组织范围的应用设置中禁用了第三方应用，则无法对其进行更改。

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[权限策略](https://admin.teams.microsoft.com/policies/app-permission)**。
1. 选择“**添加**”。
1. 提供策略的名称和说明。
1. 在 **“Microsoft 应用**”、“ **第三方应用**”和“ **自定义应用**”下，选择以下选项之一：

    * 允许所有应用
    * 允许特定的应用并阻止其他所有应用
    * 阻止特定的应用并允许其他所有应用
    * 阻止所有应用

1. 如果选择“**允许特定的应用并阻止其他所有应用**”，请添加要允许的应用：

    1. 选择“**允许应用**”。
    1. 搜索要允许的应用，然后选择“**添加**”。 搜索结果将筛选为应用开发人员（**Microsoft 应用**、**第三方应用** 或 **自定义应用**）。
    1. 选择一个或多个应用后，选择“ **允许**”。

1. 如果选择了 **“阻止特定应用并允许所有其他应用**”，同样，请搜索并选择要阻止的应用，然后选择“ **阻止**”。

1. 选择“**保存**”。

## <a name="edit-an-app-permission-policy"></a>编辑应用权限策略

可以使用 Teams 管理中心编辑全局策略或已创建的任何自定义策略。

1. 登录到 Teams 管理中心并访问 **Teams 应用** > **[权限策略](https://admin.teams.microsoft.com/policies/app-permission)**。
1. 通过单击策略名称的左侧选择策略，然后选择 **“编辑”**。
1. 进行更改以允许或阻止这三个类别中的每一个特定应用。
1. 选择“**保存**”。

## <a name="assign-a-custom-policy-for-app-permissions-to-users"></a>向用户分配应用权限的自定义策略

仅当你将策略应用于一个或多个用户时，应用权限策略才会生效。 查看向用户 [分配策略](policy-assignment-overview.md#ways-to-assign-policies)的不同方法。

## <a name="considerations-when-using-app-permission-policies"></a>使用应用权限策略时的注意事项

下面是使用应用权限策略授予访问权限或禁止对应用的访问权限时的一些注意事项：

* 仅当你将策略应用于一个或多个用户时，应用权限策略才会生效。

* 编辑或分配策略后，更改可能需要几个小时才能生效。

* 最终用户无法与不允许用户使用的应用的任何功能进行交互。

* 用户可以搜索阻止的应用并请求管理员批准。 管理员保留完全控制权，以 [批准或忽略用户请求](user-requests-approve-apps.md)。

* 应用设置策略与应用权限策略协同工作。 从一组允许的应用中选择要固定设置策略的应用。 但是，如果用户具有阻止使用固定应用的应用权限策略，则该用户不能使用该应用。

* 应用策略适用于在 Web、移动或桌面上使用任何 Teams 的用户。

## <a name="related-articles"></a>相关文章

* [Teams 中应用的管理设置](admin-settings.md)
* [向 Teams 中的用户分配策略](policy-assignment-overview.md)
* [Teams 功能可用性比较](/office365/servicedescriptions/teams-service-description#feature-availability)
