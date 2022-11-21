---
title: 用户对管理员的请求
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 09/20/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.reviewer: mhayrapetyan
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: 了解如何管理和配置最终用户请求，以批准组织中被阻止的应用。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 0be54f15391793ebc63172df05133bb173da426e
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131051"
---
# <a name="manage-user-requests"></a>管理用户请求

组织中被阻止的应用可能会影响最终用户的工作效率和协作。 最终用户无法使用被阻止的应用，但在 Teams 应用商店中查看此类应用及其信息，并请求管理员批准。 评估请求后，可以选择允许应用或关闭请求。

此功能提供有关组织内应用需求的信号。 可以轻松查看每个请求的应用的请求总数。 它可帮助你就评估哪些应用允许做出明智的决定。

你保留对用户允许或阻止的应用的完全控制。 如果选择允许应用，则用于管理应用的控件和 UI 保持不变。

* 默认选项将用户请求发送到 Teams 管理中心，你可以在其中 [查看用户请求并允许请求的应用](#view-and-act-on-user-requests-in-teams-admin-center)。

   :::image type="content" source="media/user-request-blocked-apps.png" alt-text="显示请求管理员批准被阻止应用的选项的屏幕截图。":::

* 通过自定义，可以配置最适合组织的 [最终用户体验](#modify-the-default-setting-to-receive-end-user-requests) 。 你可以提供在 Teams 应用商店中显示的说明或自定义消息，请求审批选项会将用户定向到组织特定的 URL 来收集其请求。

   :::image type="content" source="media/user-request-blocked-apps-redirected.png" alt-text="显示管理员将允许应用请求 URL 重定向到特定于组织的 URL 时，应用商店中应用的最终用户体验的屏幕截图。":::

## <a name="view-and-act-on-user-requests-in-teams-admin-center"></a>在 Teams 管理中心查看和处理用户请求

默认方法接收的最终用户请求显示在 Teams 管理中心。 可以轻松查看和管理请求。 建议定期会审以检查最终用户请求。 若要查看和允许应用，请执行以下步骤：

1. 登录到 Teams 管理中心，转到 **Teams 应用** > [**管理应用**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 选择显示“ **按用户请求”** 列。 也可以对列进行排序。

   :::image type="content" source="media/user-requests-tac.png" alt-text="显示 Teams 管理中心中用户请求列的屏幕截图，可以对其进行排序。" lightbox="media/user-requests-tac-expanded.png":::

1. 若要打开要允许的应用详细信息页，请选择应用的名称。

1. 选择“ **管理请求**”。

   :::image type="content" source="media/apps-manage-user-requests.png" alt-text="显示应用详细信息页上的“管理请求”选项的屏幕截图。" lightbox="media/apps-manage-user-requests-expanded.png":::

1. 按照弹出对话框中显示的以下一个或多个步骤进行操作。 批准应用的步骤因用于阻止应用的方法而异。

   * 如果使用权限策略阻止应用， [请修改权限策略](teams-app-permission-policies.md)。
   * 如果为所有用户阻止应用，请 [允许该应用](manage-apps.md#allow-and-block-apps)。
   * 如果阻止所有用户的所有应用， [请修改组织范围的设置](manage-apps.md#manage-org-wide-app-settings)。

最终用户可以在 Teams 应用商店中查看应用的 **“添加”** 选项，以检查是否允许该应用。 当你在 Teams 管理中心收到请求后允许应用时，Teams 不会通知最终用户他们的请求已得到处理。 允许应用时，请求计数器不会重置为零。

## <a name="modify-the-default-setting-to-receive-end-user-requests"></a>修改默认设置以接收最终用户请求

Teams 提供了一条默认消息，供用户请求对应用进行审批。 可以修改默认设置，以使用说明和/或组织特定的 URL 添加自定义消息。 Teams 应用商店中每个应用的修改都会显示。

若要配置自定义消息并将用户重定向到特定于组织 URL，请执行以下步骤：

1. 登录到 Teams 管理中心，转到 **Teams 应用** > [**管理应用**](https://admin.teams.microsoft.com/policies/manage-apps)。

1. 在右上角，选择 **“组织范围的应用设置**”。

1. 若要在 Teams 存储中显示自定义消息或说明，请在 **“用户请求配置”** 下的“文本”字段中输入文本消息。 字段限制为 300 个字符。

1. 若要提供组织特定的 URL 来收集用户请求，请执行以下步骤：

   1. 打开“ **将请求重定向到外部链接** ”开关。
   1. 提供特定于组织的 URL。

      :::image type="content" source="media/user-request-config-org-wide-setting.png" alt-text="在组织范围的设置 UI 中切换用户请求的 URL 自定义的屏幕截图。":::

1. 选择“**保存**”。

如果选择这样做，则评估第三方应用并允许请求的应用的方法保持不变。

## <a name="dismiss-user-requests"></a>消除用户请求

若要消除请求，请执行以下步骤：

1. 选择要为其消除用户请求的应用的名称。
1. 选择“ **管理请求**”。
1. 在“管理用户请求”对话框中，选择“ **消除所有请求**”。

   :::image type="content" source="media/dismiss-user-requests-apps.png" alt-text="管理员可以通过允许应用程序批准用户请求，也可以消除请求且不进行任何操作。":::

如果取消请求，它不会通知最终用户他们的请求已得到处理。 关闭允许应用的请求时，管理中心中的请求计数将重置为零。 此外，在关闭请求数小时后，最终用户可以再次请求允许同一应用。

## <a name="related-article"></a>相关文章

* [有关如何管理第三方应用的概述](manage-apps.md)。
