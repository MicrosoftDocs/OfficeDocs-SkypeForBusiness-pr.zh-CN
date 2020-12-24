---
title: 为组织管理列表应用
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 了解如何在 Teams 中为贵组织的用户管理列表应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8ba05b4922b25cc6294fc85f1264a44bdb031660
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731120"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理列表应用

## <a name="overview-of-lists"></a>列表概述

Microsoft Teams 中的列表应用可帮助你组织中用户跟踪信息、组织工作和管理工作流。 使用列表，用户可以使用可自定义的视图、规则和警报跟踪问题、资产、例程、联系人、清单、事件、医生、患者等数据，使团队中的每个人都保持同步。

在 Teams 中，用户以频道中的选项卡访问列表。 单击 **+** 以打开选项卡库，将新的列表应用选项卡实例添加到频道以开始使用。

![选项卡库中的列表应用](media/lists-tab.png)

用户可以从同一团队内或他们有权访问的不同 SharePoint 网站中创建新列表或固定现有列表。 可以从内置模板、基于现有列表的结构或导入 Excel 工作簿的数据，从头开始创建新列表。 列表应用在 Teams 桌面、Web 和移动客户端中可用。

![如何在列表应用中创建列表](media/lists-create-list.png)

## <a name="templates"></a>模板

列表中模板专门针对用户的常见信息跟踪方案而定制。 每个模板在列表视图和详细信息视图级别都附带预定义的列表结构、表单布局和格式设置选项，以帮助用户快速入门。 选择模板后，用户可以预览列表的外观以及一些示例数据。 下面是组织中团队如何使用列表中预定义模板的一些示例：

- 使用问题跟踪器模板跟踪问题并关闭它们。
- 使用事件行程模板组织所有活动详细信息。
- 使用"患者"模板记录医疗保健组织中健康团队患者的需求和状态，以监视和协调护理。
- 使用"贷款"模板跟踪贷款申请的状态。

## <a name="example-scenario"></a>示例方案

本地邮政局负责对其地区中的邮件进行排序和传递。 每天上午，该邮政局都有一个团队来查看每日目标、共享公告和讨论已知事件。

之后，邮件运营商会选取其邮件并开始其传递路线。 路线上可能会发生事故，例如汽车事故、与狗相关的问题或社会性政治者。 当邮件运营商遇到事件时，他们会使用移动设备上的 Teams 来记录事件详细信息，这些详细信息在团队频道的列表中进行跟踪。 团队中的每个人（包括现场的邮件运营商）都可以查看此信息并随时了解相关信息。

在迁移到 Teams 之前，邮件运营商必须返回到邮政局，以完成一个硬复制表单，以报告在 Excel 电子表格中输入的事件。 Teams 首先为邮件运营商提供移动版体验，他们可以使用列表在事件发生时报告现场事件、与团队成员共享事件详细信息、在频道上就这些事件展开对话，以及推动事件解决。

## <a name="what-you-need-to-know-about-lists"></a>有关列表的需知信息

### <a name="lists-is-available-in-every-team-and-channel"></a>列表可在每个团队和频道中使用

列表已预装给所有 Teams 用户，可直接在每个团队和频道的选项卡库中使用。 这意味着用户不必转到 Teams 应用商店进行安装。

### <a name="lists-and-sharepoint"></a>列表和 SharePoint

列表数据存储在 SharePoint Online 团队网站中。 若要详细了解 SharePoint Online 如何与 Teams 交互，请参阅 SharePoint Online 和 [OneDrive for Business](SharePoint-OneDrive-interact.md)如何与 Teams 交互。

在 SharePoint 中设置的权限适用于在列表应用中创建的列表。 默认情况下，列表从它们所属的网站继承权限。 这些权限控制用户可以执行的操作类型，例如他们是否可以创建或编辑列表。 有关详细信息，请参阅 SharePoint Server 中[的权限级别](https://docs.microsoft.com/sharepoint/understanding-permission-levels)[、用户权限和权限级别](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)。

在某些情况下，你可能希望限制用户可以在列表中执行哪些操作。 例如，工作组中的人编辑列表视图，这将更改所有团队成员的列表视图，并且您希望仅允许团队所有者或某些团队成员编辑列表视图。 若要了解有关详细信息，请参阅["自定义 SharePoint 列表或库的权限"。](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)

> [!NOTE]
> 此时，团队中的所有者和成员权限不会以任何方式链接到管理列表或列表应用行为的团队网站中的权限。 但是，根据客户反馈和使用情况，这将考虑在将来的产品迭代中。  

### <a name="limitations"></a>限制

使用列表，用户可以获得桌面、Web 和移动体验。 必须知道，用户不能使用 Teams 移动客户端上的列表创建新列表或固定现有列表。 若要在 Teams 移动客户端上查看或编辑列表，必须先使用 Teams 桌面或 Web 客户端上的列表创建或添加列表。

来宾无法创建或删除列表。 他们可以向现有列表添加列表项、开始有关列表项的新对话，以及答复有关列表项的现有对话。

### <a name="lists-and-the-sharepoint-app"></a>列表和 SharePoint 应用

如果您的组织中用户使用 SharePoint 应用程序创建的列表，这些列表将自动移动到列表，无需用户执行任何操作。 若要在 Teams 中获得最佳和最丰富的列表集成体验，请使用列表应用并固定现有列表。

## <a name="set-up-lists"></a>设置列表

### <a name="enable-or-disable-lists-in-your-organization"></a>在组织中启用或禁用列表

默认情况下，为组织的所有 Teams 用户启用列表。 可以在 Microsoft Teams 管理中心的"管理应用"页面上关闭或[](manage-apps.md)打开组织级别的应用。

1. 在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"Teams 应用**  >  **管理应用"。**
2. 执行下列操作之一：

    - 若要为组织关闭列表，请搜索"列表"应用，将其选中，然后单击"阻止 **"。**
    - 若要为组织启用列表，请搜索"列表"应用，将其选中，然后单击"允许 **"。**

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>为组织中特定用户启用或禁用列表

若要允许或阻止组织中特定用户使用列表，请确保在"管理应用"页面上为组织启用列表，然后创建自定义应用权限[](manage-apps.md)策略并将其分配给这些用户。 若要了解有关详细信息，请参阅["在 Teams 中管理应用权限策略"。](teams-app-permission-policies.md)

## <a name="search-the-audit-log-for-list-events"></a>在审核日志搜索列表事件

列表通过企业级审核启用，因此，可以在安全与合规中心审核日志搜索列表和&事件。 有关详细信息，请参阅安全中心 [审核日志搜索&搜索](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

有关与 Teams 中的列表应用相关的审核事件列表，请参阅 [SharePoint 列表活动](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)。

在搜索安全中心审核日志，首先必须打开安全中心& [审核](https://protection.office.com)。 请记住，只有启用审核时，审核数据才可用。

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate、Power Apps 和图形 API

列表支持 [Power Automate](https://docs.microsoft.com/power-automate/flow-types) 用于工作流 [，Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) 支持列表窗体。 开发人员可以使用列表 [API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) 通过 Microsoft Graph 将列表数据作为源进行连接。

## <a name="give-feedback-or-report-an-issue"></a>提供反馈或报告问题
  
若要向我们发送反馈或报告问题，请单击Teams 中左侧导航底部附近的"帮助"，然后选择"**报告问题"。** 选择 **"** 列表"，然后输入有关你遇到的问题的反馈或详细信息。

## <a name="related-topics"></a>相关主题

- [列出帮助文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
