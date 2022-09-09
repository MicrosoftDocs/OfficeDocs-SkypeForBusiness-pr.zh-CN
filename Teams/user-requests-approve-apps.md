---
title: 用户请求管理员允许应用
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
ms.openlocfilehash: c47578184aa97f9c6cc366e186c1590ef1e3fba4
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637306"
---
# <a name="manage-user-requests-to-allow-apps-that-are-blocked-by-admins"></a>管理用户请求以允许管理员阻止的应用

组织中阻止的应用可能会降低最终用户的工作效率和协作。 最终用户无法使用 Teams 应用商店中可用但组织中受阻止的应用。 但是，为了随时了解情况，最终用户可以查看被阻止的应用、查看应用的信息及其服务器的用例。 选择允许应用后，用户可以请求管理员批准，以便他们可以在 Teams 中使用这些应用。

此功能提供有关组织内应用需求的信号。 可以轻松查看应用请求的聚合数，并就组织中要考虑允许的应用做出明智的决策。

保留对用户允许或阻止的应用的完全控制。 如果选择允许应用，则用于管理应用的控件和 UI 保持不变。

* 默认选项在 Teams 管理中心发送用户请求，你可以在其中 [查看用户请求并允许请求的应用](#view-user-requests-and-allow-the-requested-apps)。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="显示请求管理员批准阻止应用的选项的屏幕截图。":::

* 通过自定义，可以通过将用户重定向到自定义应用请求方法来 [配置最终用户体验](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app) 。 可以提供自定义短信来通知用户，并将用户定向到组织的内部 URL 以收集允许应用的请求。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="屏幕截图显示了管理员将允许应用请求 URL 重定向到自定义 URL 时应用在应用商店中的最终用户体验。":::

## <a name="modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app"></a>修改默认设置以接收最终用户请求以允许应用

若要配置自定义消息并将用户重定向到特定于组织的 URL 以请求应用审批，请执行以下步骤：

1. 登录 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)** 页面。

1. 选择组织范围的应用设置。

1. 若要在 Teams 客户端存储中显示自定义消息或指令，请在用户请求配置中提供一条短信。

1. 若要提供组织特定的 URL 来收集用户请求，请执行以下操作：

   1. 将“将请求重定向到外部工具”选项更改为“打开”。
   1. 提供组织特定的自定义 URL。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="用于切换用户请求在组织范围设置 UI 中取消阻止应用的 URL 自定义的屏幕截图。":::

1. 选择“**保存**”。

## <a name="view-user-requests-and-allow-the-requested-apps"></a>查看用户请求并允许请求的应用

默认方法收到的最终用户请求显示在 Teams 管理中心。 可以轻松查看和管理请求。 强烈建议定期对最终用户请求进行会审检查。 若要查看和允许应用，请执行以下步骤：

1. 登录 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)** 页面。

1. 选择显示 **“用户请求** ”列。 也可以对列进行排序。

   :::image type="content" source="media/user-requests-tac.png" alt-text="屏幕截图显示了 Teams 管理中心中用户请求的列，并且可以对其进行排序。" lightbox="media/user-requests-tac-expanded.png":::

1. 若要打开要允许的应用详细信息页，请选择应用的名称。

1. 选择 **“管理请求**”。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="显示应用详细信息页上的“管理请求”选项的屏幕截图。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. 按照弹出对话框中显示的以下一个或多个步骤操作。 批准应用的步骤因用于阻止应用的方法而异。

   * 如果使用权限策略阻止应用， [请修改权限策略](teams-app-permission-policies.md)。
   * 如果为所有用户阻止应用，请 [允许该应用](manage-apps.md#allow-and-block-apps)。
   * 如果所有用户都阻止了所有应用， [请修改组织范围的设置](manage-apps.md#manage-org-wide-app-settings)。

1. （可选）若要切换到特定于组织 URL 的自定义配置，请在“管理用户请求”对话框中选择“配置用户请求”链接。 它将打开组织范围的应用设置窗格，可在其中 [配置最终用户请求体验](#modify-the-default-setting-to-receive-end-user-requests-to-allow-an-app)。

如果在 Teams 管理中心收到请求后允许应用，则 Teams 不会通知最终用户其请求已执行。 用户可以在 Teams 应用商店中检查应用，以检查是否允许应用。 允许后，用户可以使用“添加应用”选项。 如果在通过组织特定的方法接收请求后允许应用，则将应用内部机制来向最终用户提供状态更新。

若要将应用请求数重置为零，请消除请求。 仅允许应用不会将其请求计数器重置为零。

## <a name="dismiss-user-requests"></a>消除用户请求

若要消除允许应用的请求，请执行以下步骤：

1. 选择要为其消除用户请求的应用的名称。
1. 选择 **“管理请求** ”，然后选择“消除对话框上 **的所有请求** ”。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="管理员可以通过允许应用程序批准用户请求，也可以消除请求且不进行任何操作。":::

如果解除请求，则不会通知最终用户其请求已执行。 关闭允许应用的请求时，管理中心中的请求数将重置为零。 此外，在你关闭请求几个小时后，最终用户可以再次请求允许相同的应用。

## <a name="related-article"></a>相关文章

* [有关如何管理第三方应用的概述](manage-apps.md)。
