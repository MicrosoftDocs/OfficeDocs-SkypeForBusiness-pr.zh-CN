---
title: 在管理中心内管理 microsoft Power Platform Microsoft Teams应用
author: cichur
ms.author: v-cichur
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在管理中心内管理对基于 Microsoft Power Platform 的自定义Microsoft Teams的访问权限。
ms.openlocfilehash: bd2155342fa1618f8201a86db8f9fc07c2af0e90
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628324"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在管理中心内管理 microsoft Power Platform Microsoft Teams应用

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams 中的 Microsoft Power Platform 应用

本文概述了如何在管理中心内管理 Microsoft [Power Platform](https://powerplatform.microsoft.com/) Microsoft Teams应用。

> [!NOTE]
> 本文适用于组织中制造商使用自定义应用或Power Apps Power Virtual Agents。 这些自定义应用会自动添加到Teams。 本文不适用于从"应用"Power Apps或Power Virtual Agents应用设置策略固定到Teams应用的应用。 你可以像管理应用页面上任何其他应用一样使用应用权限策略[](manage-apps.md)[和应用设置](teams-app-permission-policies.md)策略来管理[这些应用](teams-app-setup-policies.md)。

[Power Apps](https://powerapps.microsoft.com)是一个低代码/无代码的应用程序开发环境，您的组织中的制造商可以使用该环境构建连接到业务数据的自定义应用。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)是一个无代码机器人生成环境，制造商可以创建功能强大的机器人。 将 Microsoft Power Platform 应用集成到 Teams 后，组织可以简化业务流程、更快速地响应不断变化的业务需求，从而推动更好的协作，并创建和共享自定义解决方案以提高工作效率。  

由您组织中制造商创建的 Microsoft Power Platform 应用会自动添加到Teams。 制作者可以使用应用中的共享功能以及 Power Apps[](/powerapps/maker/canvas-apps/share-app)中的共享功能来控制[谁可以访问Power Virtual Agents。](/power-virtual-agents/admin-share-bots)

创建或共享 Microsoft Power Platform 应用后，用户可以在"应用"页面上查看并安装该应用，**** 其方式为"为同事构建的组织名称  >  **生成"。**  (创建或共享应用后，可能需要几分钟时间，应用才能在此处显示。) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text=""应用"页的屏幕截图，显示"由同事构建"中列出的 Microsoft Power Platform 应用":::

如果应用满足 **以下条件之** 一，用户将看到同事生成的应用。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>用户创建了应用。</li><li>该应用已直接与用户共享。</li><li>用户最近使用过该应用。 </li></ul>| <ul><li>用户创建了机器人。</li><li>机器人由用户所属团队拥有。 </li></ul>        |

用户安装 Microsoft Power Platform 应用的方式与安装任何其他 Teams相同。 请记住，用户只能将应用安装到他们拥有权限的上下文中，例如，他们拥有的团队、他们参与的聊天或者他们的个人范围。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在管理中心内管理对 Microsoft Power Platform Microsoft Teams的访问权限

作为管理员，你可以控制 Microsoft Power Platform 应用是否列在"应用"页面的"构建"Teams。 你可以统一阻止或允许在 Power Apps 中创建的所有应用，或者允许所有在 Power Virtual Agents 中创建的应用在"管理应用"[](manage-apps.md)页面上组织级别创建，或者允许特定用户使用应用权限[策略 创建的所有应用](teams-app-permission-policies.md)。

组织的 **应用商店Power Apps** 共享应用和共享 **Power Virtual Agent** 应用表示该特定平台上创建的所有应用。 如果在组织级别或针对特定用户阻止一个或两个这些应用，这些用户无法从同事构建的这些平台看到任何应用，并且无法将它们安装在 Teams 中。  

请记住，你可以控制对在 Power Apps 和 Power Virtual Agents 中创建的所有应用的访问，但不能允许或阻止单个应用。 制作者决定谁可以通过共享功能从游戏和游戏内访问Power Apps Power Virtual Agents。 如果制作者与用户共享了他们在 Power Virtual Agents 中创建的应用，并且你阻止了该用户的共享 **Power Virtual Agents** 应用，则用户将无法在 Teams 中查看或安装来自该平台的任何应用。

如果允许用户从 Power Apps 或 Power Virtual Agents 访问应用，然后阻止用户从一个或两个平台访问应用，则在您阻止应用或应用之前，该用户仍可以访问和使用他们安装的 Microsoft Power Platforms 应用。 但是，用户不再可以在同事构建的 中查看或安装这些 **平台的任何应用**。

> [!NOTE]
> "**管理应用**"页上的"允许与自定义应用与组织 [](manage-apps.md)范围的自定义应用交互"设置适用于组织中的每个人，并控制他们是否可与自定义应用交互。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。 默认情况下，此设置已启动。 如果此设置已关闭，则您的组织中的用户无法查看或安装任何自定义应用，包括 Microsoft Power Platform 应用。 有关详细信息，请参阅 [管理组织范围内的应用设置](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>为组织允许或阻止 Microsoft Power Platform 应用

默认情况下，**组织中Power Apps****共享应用程序和共享 Power Virtual Agent 应用** Teams共享 Power Virtual Agent 应用。 可以在管理中心的"管理应用"页面上在组织级别阻止[](manage-apps.md)或Microsoft Teams应用。  

1. 在 Microsoft Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。 只有全局管理员或Teams才能访问页面。
2. 在应用列表中，执行下列操作之一。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text=""管理应用"页面的屏幕截图，显示共享的 Microsoft Power Platform 应用":::

    - 若要阻止在 Power Apps 或 Power Virtual Agents 中创建的应用，请搜索"共享 **Power Apps"或"共享 Power Virtual Agent 应用****"，** 将其选中，然后单击"阻止 **"。**
    - 若要允许在 Power Apps 或 Power Virtual Agents 中创建应用，请搜索"共享 Power Apps"或 **"共享 Power Virtual Agent** 应用 **"，** 将其选中，然后单击"允许 **"。**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>允许或阻止特定用户的 Microsoft Power Platform 应用

若要允许或阻止组织中特定用户访问在 Power Apps 或 Power Virtual Agents 中创建的应用，请创建并分配一个或多个自定义[应用权限策略](teams-app-permission-policies.md)。 

例如，若要阻止特定用户访问在 Power Apps 中创建的应用，请创建自定义应用权限策略来阻止共享 **Power Apps，然后将** 策略分配给这些用户。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="阻止了共享应用的自定义应用权限Power Apps屏幕截图":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>使用审核日志调查 Microsoft Power Platform 安装活动

可以使用适用于 Teams 的审核日志，调查用户从"应用"页的"同事生成"部分安装Microsoft Power Platform Teams。 为此，在"appInstalled"审核日志 **Teams或** 一组 (的 **"安装** 的应用") 中搜索"已安装的应用"事件。 [](./audit-log-events.md) 若要查找从同事 **生成安装的应用**，请查找给定记录详细信息 **中 AppDistributionMode** 属性中的 **TemplatedInstance** 值。 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中 TemplatedInstance 值的屏幕截图":::

> [!NOTE]
> 可以导出 CSV 格式的审核记录，以便更轻松地筛选。

## <a name="related-topics"></a>相关主题

- [在应用中共享画布Power Apps](/powerapps/maker/canvas-apps/share-app)
- [与其他用户共享机器人](/power-virtual-agents/admin-share-bots)
- [在管理中心Microsoft Teams应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [发布通过应用提交 API Teams的自定义应用](submit-approve-custom-apps.md)