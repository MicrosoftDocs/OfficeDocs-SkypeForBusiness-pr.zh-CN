---
title: 了解 Microsoft Teams 中的应用
ms.reviewer: ''
description: 了解应用，并根据组织的用户配置和业务要求决定在 Teams 中允许哪些应用。
ms.topic: conceptual
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 10/01/2022
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020; intro-overview; intro-hub-or-landing
ms.openlocfilehash: 9b8d4ca3140b6bd8907938b5c2ac86aeabb39e37
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912621"
---
# <a name="understand-microsoft-teams-apps-and-their-capabilities"></a>了解 Microsoft Teams 应用及其功能

Teams 中的应用可帮助用户将其工作区工具和服务汇集在一起，并与他人协作。 例如，最终用户在 Teams 中使用固定日历应用快速与他人协作，使用带有机器人功能的应用可以通知用户在 Teams 频道中使用 Web 服务质量的应用，以及用于在频道中共享任务，并向各种最终用户分配任务的应用。 Microsoft Teams 应用是基于 Web 的 SaaS 应用，无需在本地部署。

作为管理员，你将设置一个应用治理流程，以平衡最终用户的广泛需求以及组织的 IT 策略、标准和风险配置文件。

我们广泛的经过验证的安全 Teams 应用 [目录](https://appsource.microsoft.com/marketplace/apps?product=office%3Bteams&page=1) 为最终用户提供了对组织每天所需的工具和服务的访问权限。 Teams 管理中心为管理员提供企业级控制和配置来管理应用。 可在各种上下文（如会议、聊天和频道）中控制每个用户的应用可用性。

本文可帮助你了解应用的类型以及用户访问这些应用的位置。 若要详细了解应用的用途，请阅读 [针对最终用户的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。

最终用户可在 Teams 中使用不同类型的应用包括：

* [属于 Teams 的核心应用](#core-apps)。
* [Microsoft 创建的其他应用](#apps-created-by-microsoft)。
* 合作伙伴创建[的第三方应用](#third-party-apps-created-by-independent-app-developers) (Microsoft) 验证。
* 由自己组织创建的[自定义应用](#custom-apps-created-within-an-organization-for-internal-use)。

## <a name="core-apps"></a>核心应用

一些 Teams 功能（例如活动源、团队、聊天、日历、通话、文件和作业 [教育版租户]）是默认可用的，并且默认固定，以便最终用户可以轻松访问。 对于一线工作人员，则仅提供和固定了活动、班次、聊天和通话功能。 作为管理员，可以使用 [安装策略](/microsoftteams/teams-app-setup-policies)修改默认行为。

:::image type="content" source="media/core-apps-pinned1.png" alt-text="核心应用是默认情况下固定在 Teams 中的应用。" lightbox="media/core-apps-pinned2.png":::

## <a name="apps-created-by-microsoft"></a>Microsoft 创建的应用

Microsoft 提供了许多应用来提高工作效率和协作。 若要找到这些应用，你和最终用户可以在 Teams 管理中心中查找发布者为 Microsoft 的应用，或在 Team 应用商店中查找提供者为 Microsoft 的应用。

Teams自带一组内置应用，包括列表、任务、表扬、审批等。 建议在初始 Teams 推出中包括 Planner 等特色应用。

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="显示 Teams 管理中心中的 Microsoft 应用列表的屏幕截图。" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-created-by-independent-app-developers"></a>由独立应用开发人员创建的第三方应用

除了 Microsoft 提供的应用之外，还可以使用第三方应用。 Microsoft 会严格验证所有这些应用的功能和安全性。 在使这些应用在 Teams 应用商店中可用之前，会执行精心的手动和自动测试，即使在应用实时发布后，许多测试也会继续以常规节奏进行。 若要了解应用验证的优势，请参阅 [第三方应用的验证](overview-of-app-validation.md)。 某些应用订阅 [Microsoft 合规性计划](overview-of-app-certification.md) ，以在验证之外进行多层进一步检查。

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Teams 应用商店中第三方应用示例的屏幕截图。":::

## <a name="custom-apps-created-within-an-organization-for-internal-use"></a>在组织内创建的自定义应用供内部使用

组织中开发人员创建的应用称为自定义应用（或业务线应用）。 组织可以根据组织特定的要求委托创建自定义应用。 你有权为整个组织或特定用户允许或阻止此类应用。 组织中的开发人员可以通过使用 Teams 与 [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions) 集成，快速构建自定义低代码解决方案。

管理员允许使用自定义应用后，最终用户在 Teams 应用商店的左侧导航中选择“**专为组织构建**”即可找到此类应用。

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 桌面应用中 Teams 应用商店中自定义应用的屏幕截图。" lightbox="media/built-for-your-org2.png":::

有关详细信息，请参阅[了解和管理自定义和旁加载应用](custom-app-overview.md)。

## <a name="about-app-templates"></a>关于应用模板

Microsoft 使用应用开发方法创建并提供功能和生产就绪示例应用。 这些应用统称为 Teams 应用模板，提供给：

* 说明 Teams 中的一些协作用例。
* 展示应用开发最佳做法和方法。
* 提供开发人员可以扩展以创建自己的应用的开源应用。

组织开发人员通过对提供的源代码进行简单更改来自定义应用模板。 为满足任何组织需求，可将这些应用作为自定义应用提供给最终用户。

若要了解详细信息，请参阅 [Microsoft Teams 应用模板](https://adoption.microsoft.com/microsoft-teams/app-templates/)。

## <a name="understand-app-capabilities"></a>了解应用功能

Teams 应用功能是可在应用中构建以启用集成和交互的核心功能。

:::row:::
    :::column span="":::
    :::column-end:::
    :::column span="3":::
        :::image type="content" source="media/teams-app-capabilities-group.png" alt-text="显示 Microsoft Teams 应用的应用功能的图形。" border="false":::
    :::column-end:::
    :::column:::
    :::column-end:::
:::row-end:::

为了提供允许最终用户在 Teams 中工作的丰富体验，应用开发人员使用以下功能创建应用：

* **机器人**：机器人也称为聊天机器人或对话机器人。 它是执行简单重复任务的应用。 机器人交互可以是快速问答，也可以是提供服务或协助访问的复杂对话。 用户可以在个人聊天、频道或群组聊天中与机器人进行对话。 有关详细信息，请参阅 [Microsoft Teams 中的机器人](/microsoftteams/platform/bots/what-are-bots)。

  Teams 支持在私人聊天和频道中使用聊天机器人。 管理员可以控制是否允许在 Microsoft 365 和 Office 365 组织中使用机器人。 有关打开或关闭自定义机器人的信息，请参阅 [Teams 管理中心中的应用管理和治理概述](manage-apps.md)。

* **选项卡**：选项卡是固定在频道或聊天顶部的 Teams 感知网页。 选项卡允许你使用类似 Web 的体验与内容和服务交互。 它们是简单的 HTML <iframe\> 标记，指向在应用清单中声明的域，并且可以作为频道添加到团队、群组聊天或个人用户的个人应用中。 有关详细信息，请参阅 [Microsoft Teams 选项卡](/microsoftteams/platform/tabs/what-are-tabs)。

  在私人聊天中，默认情况下已创建了“对话”、“文件”、“组织”和“活动”选项卡。 除了这些内置选项卡，开发人员还可以设计和添加自定义选项卡。 有关详细信息，请参阅[在 Teams 中使用内置和自定义选项卡](/microsoftteams/platform/tabs/what-are-tabs)。

* **Webhook 和连接器**：Webhook 和连接器有助于将 Web 服务连接到 Microsoft Teams 中的频道和团队。 Webhook 是用户定义的 HTTP 回调，可通知用户 Teams 通道中发生的任何操作。 这是应用获取实时数据的一种方式。 连接器允许用户订阅以接收来自 Web 服务的通知和消息。 有关详细信息，请参阅 [Webhook 和连接器](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)。

  若要允许用户在 Teams 中使用自定义连接器，请参阅 [在 Teams 中使用自定义连接器](office-365-custom-connectors.md)。

* **消息传递扩展**：消息传递扩展是插入应用内容或对消息进行操作的快捷方式，无需最终用户离开对话。 用户可以从撰写消息区域、命令框或直接从邮件搜索或启动外部系统中的操作。 有关详细信息，请参阅 [消息扩展](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions?tabs=dotnet)。

* **会议扩展**：用户可以通过在会议中集成选项卡、机器人和消息扩展来增强会议体验，并提高会议效率。 可以识别各种参与者角色和用户类型、获取会议事件以及生成会议内对话。 有关详细信息，请参阅 [Teams 会议应用](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings)。

* **卡片和任务模块**：卡片在对话流中为用户提供各种视觉、音频和可选消息和帮助。 任务模块可帮助你在 Microsoft Teams 中创建模式弹出体验。 它们可用于开始和完成任务，或者显示丰富的信息（如视频或 Power 商业智能 (BI) 仪表板）。 有关详细信息，请参阅 [卡片和任务模块](/microsoftteams/platform/task-modules-and-cards/cards-and-task-modules)。

若要查看映射到 Teams 功能的常见用例，请参阅 [将用例映射到 Teams 应用功能](/microsoftteams/platform/concepts/design/map-use-cases)。

## <a name="related-articles"></a>相关文章

* [详细了解 Teams 应用模板](/microsoftteams/platform/samples/app-templates)
* [Teams 管理中心中的应用管理和治理概述](manage-apps.md)
