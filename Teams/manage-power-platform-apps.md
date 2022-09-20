---
title: 在 Microsoft Teams 管理中心管理 Microsoft Power Platform 应用
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何在 Teams 管理中心管理对使用 Microsoft Power Platform 生成的自定义应用的访问。
ms.openlocfilehash: 34c8235481ef29afc21cbada13b0d80f1a3c7e38
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837182"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>在 Teams 管理中心管理 Microsoft Power Platform 应用

## <a name="microsoft-power-platform-apps-in-teams"></a>Teams 中的 Microsoft Power Platform 应用

本文概要介绍如何在 Microsoft Teams 管理中心管理 [Microsoft Power Platform](https://powerplatform.microsoft.com/) 应用。

> [!NOTE]
> 本文适用于组织的开发人员使用 Power Apps 或 Power Virtual Agents 创建的自定义应用。 本文不适用于从“应用”页面安装或通过应用设置策略固定到 Teams 的 Power Apps 应用或 Power Virtual Agents 应用。 可以使用[应用权限策略](teams-app-permission-policies.md)和[应用设置策略](teams-app-setup-policies.md)管理应用商店应用。

[Power Apps](https://powerapps.microsoft.com) 是一个低代码或无代码应用程序开发环境，组织的应用创建者可以使用它来构建连接到你的业务数据的自定义应用。 [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 是一个无代码机器人生成环境，可供应用开发人员创建功能强大的机器人。 通过将 Microsoft Power Platform 应用集成到 Teams，组织可以简化业务流程、更快速地响应不断变化的业务需求以提高协作水平，并创建和共享自定义解决方案以提高工作效率。  

由组织的开发人员创建的 Microsoft Power Platform 应用会自动添加到 Teams。 开发人员可以使用 [Power Apps 中的共享功能](/powerapps/maker/canvas-apps/share-app) 和 [Power Virtual Agents 中的共享功能](/power-virtual-agents/admin-share-bots)来控制谁可以访问其应用。

创建或共享 Microsoft Power Platform 应用时，用户可以通过转到“**使用 Power Platform 生成**”，在“应用”页面上查看并安装它。 （创建或共享应用后，可能需要几分钟时间才能在此处显示应用。）

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="“应用”页面的屏幕截图，显示“使用 Power Platform 生成”中列出的 Microsoft Power Platform 应用。":::

如果应用满足以下条件之一，最终用户会在“**使用 Power Platform 生成**”中看到该应用。

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>用户创建了应用。</li><li>应用已直接与用户共享。</li><li>用户最近使用了该应用。 </li></ul>| <ul><li>用户创建了自动程序。</li><li>自动程序由用户所属的团队拥有。 </li></ul>        |

用户安装 Microsoft Power Platform 应用的方式与安装任何其他 Teams 应用的方式相同。 请记住，用户只能将应用安装到他们拥有权限的上下文。 例如，用户拥有的团队、用户所属的聊天或其个人范围。

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>在 Teams 管理中心管理对 Microsoft Power Platform 应用的访问

作为管理员，你可以控制 Microsoft Power Platform 应用是否在 Teams 的“应用”页面的“**使用 Power Platform 生成**”中列出。 可以在“[管理应用](manage-apps.md)”页面上的组织级别集体阻止或允许在 Power Apps 中创建的所有应用或在 Power Virtual Agents 中创建的所有应用，也可以使用[应用权限策略](teams-app-permission-policies.md)为特定用户阻止或允许。

组织的应用商店中的“**共享的 Power Apps**”和“**共享的 Power Virtual Agent 应用**”应用代表在该特定平台上创建的所有应用。 如果为整个组织或特定用户阻止其中一个或两个应用，则用户可以查看此类应用（如阻止的应用），但无法在 Teams 中安装它们。 用户可以[请求管理员批准以允许应用](user-requests-approve-apps.md)。

请记住，你可以控制对在 Power Apps 和 Power Virtual Agents 中创建的所有应用的访问，但不能允许或阻止单个应用。 应用创建者决定谁可以通过 Power Apps 和 Power Virtual Agents 中的共享功能访问他们创建的应用。 如果创建者与用户共享他们在 Power Virtual Agents 中创建的应用，并且你阻止了该用户的“**共享的 Power Virtual Agents 应用**”，则用户将无法在 Teams 中查看或安装来自该平台的任何应用。

如果允许用户从 Power Apps 或 Power Virtual Agents 访问应用，然后又阻止用户从其中一个或两个平台访问应用，则用户仍然可以访问和使用在你阻止应用之前他们安装的 Microsoft Power Platform 应用。 但是，用户不能再在“**使用 Power Platform 生成**”中安装来自这些平台的任何应用。

> [!NOTE]
> “[管理应用](manage-apps.md)”页面上的“**允许与自定义应用交互**”组织范围的应用设置适用于你组织中的每个人，并控制他们是否可以与自定义应用交互。 组织范围的应用设置可控制所有用户的行为，并且可覆盖分配给用户的任何其他应用权限策略。 如果关闭此设置，组织中的用户将无法安装任何自定义应用，包括 Microsoft Power Platform 应用。 若要了解详细信息，请参阅[管理组织范围的应用设置](manage-apps.md#manage-org-wide-app-settings)。

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>对组织允许或阻止 Microsoft Power Platform 应用

默认情况下，组织中的所有 Teams 用户都允许使用“**共享 Power Apps**”和“**共享 Power Virtual Agent 应用**”。 你可以在 Microsoft Teams 管理中心的“[管理应用](manage-apps.md)”页面上的组织级别阻止或允许它们。  

1. 登录 Teams 管理中心并访问 **Teams 应用** > **[管理应用](https://admin.teams.microsoft.com/policies/manage-apps)** ，必须是全局管理员或 Teams 服务管理员才能访问页面。
1. 在应用列表中，执行下列操作之一。

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="“管理应用”页面的屏幕截图，显示共享的 Microsoft Power Platform 应用。":::

    * 若要阻止组织中的所有用户使用在 Power Apps 或 Power Virtual Agents 中创建的应用，请搜索“**共享的 Power Apps**”或“**共享的 Power Virtual Agent 应用**”，选择它，然后选择“**阻止**”。
    * 若要允许组织中的所有用户使用在 Power Apps 或 Power Virtual Agents 中创建的应用，请搜索“**共享的 Power Apps 应用**”或“**共享的 Power Virtual Agent 应用**”，选择它，然后选择“**允许**”。

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>允许特定用户使用 Microsoft Power Platform 应用

若要允许或阻止组织中的特定用户访问在 Power Apps 或 Power Virtual Agents 中创建的应用，请创建和分配一个或多个自定义[应用权限策略](teams-app-permission-policies.md)。

例如，若要阻止特定用户访问在 Power Apps 中创建的应用，请创建自定义应用权限策略来阻止“**共享的 Power Apps**”，然后将策略分配给这些用户。

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="阻止共享的 Power Apps 应用的示例自定义应用权限策略的屏幕截图。":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>使用审核日志调查 Microsoft Power Platform 安装活动

可以使用 Teams 的审核日志来调查用户从 Teams 的“应用”页面的“**使用 Power Platform 生成**”部分安装 Microsoft Power Platform 应用的事件。 为此，请 [搜索审核日志](./audit-log-events.md)，以查找某个用户或一组用户的“**已安装应用**”Teams 事件（在 **AppInstalled** 操作下）。 若要查找从“**使用 Power Platform 生成**”安装的应用，请在给定记录的详细信息中的 **AppDistributionMode** 属性中查找 **TemplatedInstance** 值。

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="AppDistributionMode 属性中 TemplatedInstance 值的屏幕截图。" lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> 可以以 CSV 格式导出审核记录，以便更轻松地进行筛选。

## <a name="related-articles"></a>相关文章

* [在 Power Apps 中共享画布应用](/powerapps/maker/canvas-apps/share-app)
* [与其他用户共享机器人](/power-virtual-agents/admin-share-bots)
* [在 Microsoft Teams 管理中心中管理应用](manage-apps.md)
* [在 Teams 中管理应用权限策略](teams-app-permission-policies.md)
* [发布通过 Teams 应用提交 API 所提交的自定义应用](submit-approve-custom-apps.md)
