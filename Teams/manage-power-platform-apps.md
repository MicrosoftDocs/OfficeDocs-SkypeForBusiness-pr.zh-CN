---
title: 在 Microsoft Teams 管理中心管理 Microsoft Power Platform 应用
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
description: 了解如何在Microsoft Teams管理中心管理基于 Microsoft Power Platform 构建的自定义应用的访问权限。
ms.openlocfilehash: 9f212cf52ec757fc4860f081fb67da2cb1b4fcd5
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2022
ms.locfileid: "65136993"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心管理 Microsoft Power Platform 应用

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams中的 Microsoft Power Platform 应用

本文概述了如何在Microsoft Teams管理中心管理 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 应用。

> [!NOTE]
> 本文适用于组织中创建者使用Power Apps或Power Virtual Agents创建的自定义应用。 这些自定义应用会自动添加到Teams。 本文不适用于从“应用”页安装或通过应用设置策略固定到Teams的Power Apps应用或Power Virtual Agents应用。 可以像在 [“管理应用](manage-apps.md) ”页面上使用 [应用权限策略](teams-app-permission-policies.md)和 [应用设置策略](teams-app-setup-policies.md)对任何其他应用一样管理这些应用。

[Power Apps](https://powerapps.microsoft.com)是一个低代码/无代码应用程序开发环境，组织中的制造商可以使用它来生成连接到业务数据的自定义应用。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents)是一个无代码机器人生成环境，供制造商创建功能强大的机器人。 随着 Microsoft Power Platform 应用与Teams的集成，组织可以简化业务流程，更快地响应不断变化的业务需求，以推动更大的协作，并创建和共享更高效的自定义解决方案。  

组织中制造商创建的 Microsoft Power Platform 应用会自动添加到Teams。 制造商可以通过使用[Power Apps中的共享功能和Power Virtual Agents](/powerapps/maker/canvas-apps/share-app)[中的共享功能](/power-virtual-agents/admin-share-bots)来控制谁可以访问其应用。

创建或共享 Microsoft Power Platform 应用时，用户可以通过转到 **由同事****生成的“为 *组织名称*** > 生成”，在“应用”页面上查看并安装它。  (创建或共享应用后，可能需要几分钟时间才能在此处显示应用。) 

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="“应用”页面的屏幕截图，其中显示了同事在“生成”中列出的 Microsoft Power Platform 应用":::

如果应用满足以下条件之一，用户将看到 **同事在内置** 的应用。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>用户创建了应用。</li><li>应用已直接与用户共享。</li><li>用户最近使用了该应用。 </li></ul>| <ul><li>用户创建了机器人。</li><li>机器人由用户所属的团队拥有。 </li></ul>        |

用户安装 Microsoft Power Platform 应用的方式与安装任何其他Teams应用的方式相同。 请记住，用户只能将应用安装到他们拥有权限的上下文，例如，他们拥有的团队、属于其一部分的聊天或其个人范围。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>管理对 Microsoft Teams 管理中心中的 Microsoft Power Platform 应用的访问权限

作为管理员，你可以控制 Microsoft Power Platform 应用是否 **由同事** 在 Teams 中的“应用”页面上列出。 可以集体阻止或允许在“[管理应用](manage-apps.md)”页面或特定用户使用[应用权限](teams-app-permission-policies.md)策略的组织级别Power Apps或在Power Virtual Agents中创建的所有应用。

组织应用商店中的 **共享Power Apps** 和 **共享 Power Virtual Agent 应用** 表示在该特定平台上创建的所有应用。 如果在组织级别或特定用户中阻止其中一个或两个应用，则这些用户无法从 **同事生成** 的这些平台中看到任何应用，并且无法在Teams中安装这些应用。  

请记住，你可以控制对Power Apps和Power Virtual Agents中创建的所有应用的访问，但不能允许或阻止单个应用。 制造商决定谁可以通过共享功能从Power Apps和Power Virtual Agents中访问他们创建的应用。 如果创建者与用户共享他们在Power Virtual Agents中创建的应用，并且你阻止了该用户的 **共享Power Virtual Agents应用**，则用户将无法在Teams中查看或安装来自该平台的任何应用。

如果允许用户从Power Apps或Power Virtual Agents访问应用，然后又阻止用户从其中一个或两个平台访问应用，则用户仍然可以在阻止应用或应用之前访问和使用他们安装的 Microsoft Power Platform 应用。 但是，用户无法再查看或安装 **同事在内置** 的这些平台中的任何应用。

> [!NOTE]
> “[管理应用](manage-apps.md)”页上允许 **与自定义应用** 组织范围的应用设置交互适用于组织中的每个人，并控制他们是否可以与自定义应用交互。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。 默认情况下，此设置已启动。 如果关闭此设置，组织中的用户将无法查看或安装任何自定义应用，包括 Microsoft Power Platform 应用。 若要了解详细信息，请参阅 [“管理组织范围的应用设置](manage-apps.md#manage-org-wide-app-settings)”。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>允许或阻止组织的 Microsoft Power Platform 应用

默认情况下，允许组织中的所有Teams用户使用 **共享Power Apps** 和 **共享 Power Virtual Agent 应用**。 可以在Microsoft Teams管理中心的[“管理应用](manage-apps.md)”页上阻止或允许它们处于组织级别。  

1. 在Microsoft Teams管理中心的左窗格中，转到 **Teams** **appsManage** >  应用。 必须是全局管理员或Teams服务管理员才能访问该页面。
2. 在应用列表中，执行下列操作之一。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="“管理应用”页的屏幕截图，其中显示了共享的 Microsoft Power Platform 应用":::

    - 若要阻止在组织中的所有用户Power Apps或Power Virtual Agents中创建的应用，请搜索 **共享Power Apps** 或 **共享 Power Virtual Agent Apps**，选择它，然后单击 **“阻止**”。
    - 若要允许在Power Apps或Power Virtual Agents中为组织中的所有用户创建应用，请搜索 **共享Power Apps** 或 **共享 Power Virtual Agent Apps**，选择它，然后单击 **“允许**”。

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>允许或阻止特定用户的 Microsoft Power Platform 应用

若要允许或阻止组织中的特定用户访问在Power Apps或Power Virtual Agents中创建的应用，请创建和分配一个或多个自定义[应用权限策略](teams-app-permission-policies.md)。

例如，若要阻止特定用户访问Power Apps中创建的应用，请创建自定义应用权限策略来阻止 **共享Power Apps**，然后将策略分配给这些用户。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="阻止共享Power Apps的示例自定义应用权限策略的屏幕截图。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>使用审核日志调查 Microsoft Power Platform 安装活动

可以使用Teams审核日志来调查用户在Teams中“应用”页面的“**由同事生成**”部分安装 Microsoft Power Platform 应用的事件。 为此，请在 **AppInstalled** 操作下搜索已 **安装应用** Teams事件 () 用户或用户集的 [审核日志](./audit-log-events.md)。 若要查找 **由同事生成的** 应用，请在给定记录的详细信息中查找 **AppDistributionMode** 属性中的 **TemplatedInstance** 值。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中 TemplatedInstance 值的屏幕截图。":::

> [!NOTE]
> 可以导出 CSV 格式的审核记录，以便更轻松地进行筛选。

## <a name="related-topics"></a>相关主题

- [在Power Apps中共享画布应用](/powerapps/maker/canvas-apps/share-app)
- [与其他用户共享机器人](/power-virtual-agents/admin-share-bots)
- [在Microsoft Teams管理中心管理应用](manage-apps.md)
- [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
- [发布通过Teams应用提交 API 提交的自定义应用](submit-approve-custom-apps.md)
