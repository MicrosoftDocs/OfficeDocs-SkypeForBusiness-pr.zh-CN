---
title: 在 Microsoft 团队管理中心中管理 Power Platform 应用
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队管理中心中管理对 Power Platform 应用的访问权限。
ms.openlocfilehash: 687d8df929150cdc38795a13ba06687ed7e42b2b
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650955"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中管理 Power Platform 应用

## <a name="power-platform-apps-in-teams"></a>团队中的 Power Platform 应用

本文概述了如何管理添加到 Microsoft 团队管理中心中的团队的 [Power Platform](https://powerplatform.microsoft.com/) 应用。

[Power Apps](https://powerapps.microsoft.com) 是低代码/无代码应用程序开发环境，你的组织中的开发者可以使用它来生成连接到你的业务数据的自定义应用。 [Power Virtual agent](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一个无代码 bot 构建环境，用于创建功能强大的 bot。 通过将 Power Platform 应用集成到团队中，组织可以优化业务流程、更快地响应不断变化的业务需求，以提高协作能力，并创建和共享自定义解决方案以提高工作效率。  

由你的组织中的由决策者创建的 Power Platform 应用将自动添加到团队。 通过使用 power [Apps 中的共享功能](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 和 [power Virtual agent 中的共享功能](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)，制造商可以控制哪些人可以访问其应用。

当创建或共享 Power Platform 应用时，用户可以通过面向你的同事构建的***组织名称***，在 "应用" 页面上查看和安装该应用  >  **Built by your colleagues**。  (在创建或共享应用后，可能需要几分钟的时间才能在此处显示。 ) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text=""应用程序" 页面的屏幕截图，显示由同事构建的 Power Platform 应用":::

如果应用满足以下条件之一，用户将看到 **由同事构建** 的 Power Platform 应用。

|Power Apps |Power Virtual Agent  |
|---------|---------|
|<ul><li>用户创建了该应用。</li><li>该应用直接与用户共享。</li><li>用户最近使用过该应用。 </li></ul>| <ul><li>用户创建了机器人。</li><li>机器人由用户所属的团队拥有。 </li></ul>        |

用户安装 Power Platform 应用的方式与安装任何其他团队应用的方式相同。 请记住，用户只能将应用安装到他们拥有权限的上下文中，例如，团队拥有的团队、其所属的聊天或其个人范围。

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中管理对 Power Platform 应用的访问

作为管理员，你可以控制 Power Platform 应用是否在团队中的 "应用" 页面上的 **同事构建** 中列出。 你可以在 "管理应用" 页面上的 "管理应用" 页面上的 "管理应用" 页面上的 "管理应用" 页面上的 "管理应用[app permission policies](teams-app-permission-policies.md)" 页面或特定用户的 "[管理应用](manage-apps.md)" 页面上创建的所有应用中，

你组织的应用商店中的 **共享 Power Apps** 和 **Shared Power Virtual Agent 应用** 应用代表在该特定平台上创建的所有应用。 如果在组织级别或针对特定用户阻止其中一个或两个应用，这些用户将无法看到 **由同事构建** 的平台中的任何应用，并且无法在团队中安装它们。  

请记住，你可以控制对在 Power Apps 和 Power Virtual Agent 中创建的所有应用的访问权限，但不能允许或阻止单个应用。 通过 "Power Apps" 和 "Power Virtual Agent" 中的 "共享" 功能，制造商决定哪些人可以访问他们创建的应用。 如果某个 maker 在与用户的 Power Virtual 代理中创建了一个应用，并且已阻止该用户的 **共享 Power Virtual Agent 应用** ，则该用户将无法在团队中看到或安装该平台中的任何应用。

如果允许用户从 Power Apps 或 Power Virtual Agent 访问应用，然后阻止用户从这两个平台之一访问应用，则用户仍可以访问和使用在阻止应用或应用之前安装的 Power 平台应用。 但是，用户无法再查看或安装 **由你的同事构建**的平台中的任何应用。

> [!NOTE]
> "[管理应用](manage-apps.md)" 页面上的 "**允许与自定义应用进行交互**" 组织范围的应用设置适用于组织中的所有人，并控制他们是否可以与自定义应用交互。 组织范围内的应用设置控制所有用户的行为，并替代分配给用户的任何其他应用权限策略。 默认情况下，此设置处于打开状态。 如果关闭此设置，则你的组织中的用户无法查看或安装任何自定义应用，包括 Power Platform 应用。 若要了解详细信息，请参阅 [管理组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a>为你的组织允许或阻止 Power Platform 应用

默认情况下，你的组织中的所有团队用户都可以使用 **共享的 Power 应用** 和 **共享 Power Virtual Agent 应用** 。 你可以在 "Microsoft 团队管理中心" 的 " [管理应用](manage-apps.md) " 页面上的 "组织" 级别阻止或允许他们。  

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。 您必须是全局管理员或团队服务管理员才能访问该页面。
2. 在应用列表中，执行下列操作之一。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text=""管理应用" 页面的屏幕截图，显示共享的 Power Platform 应用":::

    - 若要阻止在你的组织中的所有用户的 Power Apps 或 Power Virtual 代理中创建的应用，请搜索 **共享的 Power apps** 或 **Shared Power virtual Agent 应用**，将其选中，然后单击 " **阻止**"。
    - 若要为组织中的所有用户允许在 Power Apps 或 Power Virtual Agent 中创建的应用，请搜索 " **共享 Power apps** " 或 " **共享 Power virtual Agent 应用**"，选择它，然后单击 " **允许**"。

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a>针对特定用户允许或阻止 Power Platform 应用

若要允许或阻止组织中的特定用户访问在 Power Apps 或 Power Virtual Agent 中创建的应用，请创建并分配一个或多个自定义 [应用权限策略](teams-app-permission-policies.md)。 

例如，若要阻止特定用户访问在 Power Apps 中创建的应用，请创建一个自定义应用权限策略来阻止 **共享的 Power 应用**，然后为这些用户分配策略。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="已阻止共享 Power 应用的示例自定义应用权限策略的屏幕截图":::

### <a name="use-audit-logs-to-investigate-power-platform-installation-activity"></a>使用审核日志检查 Power Platform 安装活动

你可以使用团队的审核日志来调查用户从团队中的 "应用" 页面的 " **由你的同事构建** 的" 部分中安装了 Power Platform 应用的事件。 若要执行此操作，请在**AppInstalled**操作) 下为用户或用户组搜索**已安装应用**团队事件 (的[审核日志](https://docs.microsoft.com/microsoftteams/audit-log-events)。 若要查找**由你的同事自构建**的应用，请在给定记录的详细信息的**AppDistributionMode**属性中查找**TemplatedInstance**值。 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中的 TemplatedInstance 值的屏幕截图":::

> [!NOTE]
> 你可以以 CSV 格式导出审核记录，以便更轻松地进行筛选。

## <a name="related-topics"></a>相关主题

- [在 Power Apps 中共享画布应用](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [与其他用户共享机器人](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [管理 Microsoft 团队管理中心中的应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [发布通过团队应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)
