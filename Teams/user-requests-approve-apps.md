---
title: 管理员的用户请求
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何管理和配置最终用户请求，以允许在组织中阻止的应用。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 62d34aae25ef1ebff585ea430aeb3db20856669a
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657322"
---
# <a name="manage-user-requests"></a>管理用户请求

组织中阻止的应用可能会影响最终用户的工作效率和协作。 最终用户不能使用被阻止的应用，而是在 Teams 应用商店中查看此类应用及其信息，并请求管理员批准。 评估请求后，可以选择允许应用或关闭请求。

此功能提供有关组织内应用需求的信号。 可以轻松查看每个请求的应用的请求的聚合数。 它可帮助你做出有关要评估哪些应用以供允许的明智决策。

保留对用户允许或阻止的应用的完全控制。 如果选择允许应用，则用于管理应用的控件和 UI 保持不变。

* 默认选项将用户请求发送到 Teams 管理中心，你可以在其中 [查看用户请求并允许请求的应用](#view-user-requests-in-teams-admin-center)。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="显示请求管理员批准阻止应用的选项的屏幕截图。":::

* 通过自定义，可以配置最适合组织的 [最终用户体验](#modify-the-default-setting-to-receive-end-user-requests) 。 可以提供在 Teams 应用商店中显示的指令或自定义消息，请求审批选项会将用户定向到特定于组织的 URL 来收集其请求。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="屏幕截图显示了管理员将允许应用请求 URL 重定向到特定于组织 URL 的应用时应用的最终用户体验。":::

## <a name="view-user-requests-in-teams-admin-center"></a>在 Teams 管理中心查看用户请求

默认方法收到的最终用户请求显示在 Teams 管理中心。 可以轻松查看和管理请求。 建议定期会审以检查最终用户请求。 若要查看和允许应用，请执行以下步骤：

1. 登录 Teams 管理中心并转到 **Teams 应用** > [**管理应用**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 选择显示 **“用户请求** ”列。 也可以对列进行排序。

   :::image type="content" source="media/user-requests-tac.png" alt-text="屏幕截图显示了 Teams 管理中心中用户请求的列，并且可以对其进行排序。" lightbox="media/user-requests-tac-expanded.png":::

1. 若要打开要允许的应用详细信息页，请选择应用的名称。

1. 选择 **“管理请求**”。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="显示应用详细信息页上的“管理请求”选项的屏幕截图。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. 按照弹出对话框中显示的以下一个或多个步骤操作。 批准应用的步骤因用于阻止应用的方法而异。

   * 如果使用权限策略阻止应用， [请修改权限策略](teams-app-permission-policies.md)。
   * 如果为所有用户阻止应用，请 [允许该应用](manage-apps.md#allow-and-block-apps)。
   * 如果所有用户都阻止了所有应用， [请修改组织范围的设置](manage-apps.md#manage-org-wide-app-settings)。

最终用户可以查看 Teams 应用商店中应用的 **“添加** ”选项，以检查是否允许该应用。 在 Teams 管理中心接收请求后允许应用时，Teams 不会通知最终用户其请求已执行。 允许应用时，请求计数器不会重置为零。

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>修改默认设置以接收最终用户请求

Teams 提供了一条默认消息，供用户请求应用批准。 可以修改默认设置以添加包含说明、组织特定 URL 或两者兼有的自定义消息。 对 Teams 应用商店中的每个应用显示修改。

若要配置自定义消息并将用户重定向到特定于组织的 URL，请执行以下步骤：

1. 登录 Teams 管理中心并转到 **Teams 应用** > [**管理应用**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 在右上角，选择 **组织范围的应用设置**。

1. 若要在 Teams 应用商店中显示自定义消息或指令，请在“ **用户请求配置**”下的文本字段中输入一条短信。

1. 若要提供组织特定的 URL 来收集用户请求，请执行以下步骤：

   1. 打开向 **外部链接切换的重定向请求** 。
   1. 提供特定于组织的 URL。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="用于切换用户请求在组织范围设置 UI 中取消阻止应用的 URL 自定义的屏幕截图。":::

1. 选择“**保存**”。

用于评估和允许请求的应用的方法保持不变。

## <a name="dismiss-user-requests"></a>消除用户请求

若要消除对允许应用的请求，请执行以下步骤：

1. 选择要为其消除用户请求的应用的名称。
1. 选择 **“管理请求**”。
1. 在“管理用户请求”对话框中，选择 **“消除所有请求**”。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="管理员可以通过允许应用程序批准用户请求，也可以消除请求且不进行任何操作。":::

如果解除请求，则不会通知最终用户其请求已执行。 关闭允许应用的请求时，管理中心中的请求数将重置为零。 此外，在关闭请求几个小时后，最终用户可以再次请求允许相同的应用。

## <a name="related-article"></a>相关文章

* [有关如何管理第三方应用的概述](manage-apps.md)。
