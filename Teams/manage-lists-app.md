---
title: 管理你的组织的列表应用
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在团队中针对组织中的用户管理列表应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 339f914ee1802fd4c9307e2a2f3e7faf20ac8eb4
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277286"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft 团队中管理你的组织的列表应用

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a>列表概述

Microsoft 团队中的 "列表" 应用可帮助你的组织中的用户跟踪信息、组织工作和管理工作流。 使用列表，用户可以使用可自定义的视图、规则和通知来跟踪问题、资源、例行、联系人、库存、事件、贷款、病人等数据，以使团队中的每个人保持同步。

在团队中，用户将列表作为频道中的选项卡进行访问。 单击 **+** 以打开选项卡库，然后将新列表应用选项卡实例添加到频道以开始使用。 

![选项卡库中的列表应用的屏幕截图](media/lists-tab.png)

用户可以从同一团队或他们有权访问的其他 SharePoint 网站中创建新列表或固定现有列表。 可以从内置模板、基于现有列表的结构或从 Excel 工作簿导入数据，从头开始创建新列表。 "列表" 应用在 "团队桌面版"、"web" 和 "移动客户端" 中可用。

![如何在列表应用中创建列表的屏幕截图](media/lists-create-list.png)

## <a name="templates"></a>Templates

列表中的模板针对用户的常见信息跟踪方案进行了量身定制。 每个模板都附带一个预定义的列表结构、表单布局和格式设置选项，同时列表视图和详细信息视图级别可帮助用户快速入门。 选择模板后，用户将获得列表外观的预览，以及一些示例数据。 下面是一些有关组织中的团队如何使用列表中的预定义模板的示例：

- 使用 "问题跟踪器" 模板跟踪问题并使其关闭。
- 通过 "活动路线" 模板整理您的所有活动详细信息。
- 使用病人模板记录患者的需求和状态，以供您的医疗组织中的护理团队监视和协调护理。
- 通过贷款模板跟踪贷款申请的状态。

## <a name="example-scenario"></a>示例方案

本地邮局负责在其区域中对邮件进行排序和传递。 邮局每天早上都有一个团队 huddle 来审查日常目标、分享公告以及讨论已知事件。

Huddle 后，邮件运营商将选择其邮件并开始送达路线。 事件可能沿着一个路线发生，例如，车辆事故、狗相关的问题或社会 unrest 拒付。 当邮件运营商遇到事件时，他们使用移动设备上的团队记录事件详细信息，这些详细信息在团队频道中的列表中进行跟踪。 团队中的每个人（包括域中的邮件运营商）都可以查看此信息并保持通知。

在迁移到团队之前，邮件运营商必须返回到邮局才能完成硬拷贝表单，以报告在 Excel 电子表格中输入的事件。 团队首先向邮件运营商提供移动版，在哪里可以使用列表来在现场报告事件，与团队成员共享事件详细信息，在频道中与他们进行对话，以及将事件驱动到解决方案。

## <a name="what-you-need-to-know-about-lists"></a>您需要了解的有关列表的哪些信息

### <a name="lists-is-available-in-every-team-and-channel"></a>列表在每个团队和频道中可用

列表是为所有团队用户预安装的，可直接在每个团队和频道的选项卡库中使用。 这意味着用户不必转到 "团队" 应用商店进行安装。

### <a name="lists-and-sharepoint"></a>列表和 SharePoint

列表数据存储在 SharePoint Online 团队网站中。 若要了解有关 SharePoint Online 如何与团队交互的详细信息，请参阅 [SharePoint online 和 OneDrive For Business 如何与团队交互](SharePoint-OneDrive-interact.md)。

在 SharePoint 中设置的权限将应用于 "列表" 应用中创建的列表。 默认情况下，列表继承其所属网站的权限。 这些权限控制用户可以执行的操作类型，例如，他们是否可以创建或编辑列表。 若要了解详细信息，请参阅 sharepoint [中的权限级别](https://docs.microsoft.com/sharepoint/understanding-permission-levels) 和 [sharepoint Server 中的用户权限和权限级别](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels)。

在某些情况下，你可能希望限制用户可以在列表中执行的操作。 例如，团队的人员编辑列表视图，该视图对所有团队成员进行更改，并且你希望仅允许团队所有者或特定团队成员编辑列表视图。 若要了解详细信息，请参阅 [自定义 SharePoint 列表或库的权限](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013)。

> [!NOTE]
> 此时，团队中的所有者和成员权限不会以任何方式链接到团队网站中管理列表行为或列表应用的权限。 但是，根据客户反馈和使用情况，将考虑产品的未来迭代。  

### <a name="limitations"></a>优缺点

使用列表，用户可以获得桌面版、web 和手机体验。 请务必了解，用户无法使用团队移动客户端上的列表创建新列表或固定现有列表。 若要查看或编辑团队移动客户端上的列表，必须首先使用团队桌面或 web 客户端上的列表创建或添加列表。

来宾无法创建或删除列表。 他们可以向现有列表添加列表项、启动有关列表项的新对话，以及答复有关列表项的现有对话。

### <a name="lists-and-the-sharepoint-app"></a>列表和 SharePoint 应用

如果您的组织中的用户使用 SharePoint 应用创建了列表，这些列表将自动移至列表，用户无需执行任何操作。 若要获得团队中最丰富的列表集成体验，请使用 "列表" 应用并固定现有列表。

## <a name="set-up-lists"></a>设置列表

### <a name="enable-or-disable-lists-in-your-organization"></a>启用或禁用组织中的列表

默认情况下，将为组织中的所有团队用户启用列表。 你可以在 Microsoft 团队管理中心的 " [管理应用](manage-apps.md) " 页面上，关闭或打开组织级别的应用。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 执行下列操作之一：

    - 若要为你的组织关闭列表，请搜索 "列表" 应用，将其选中，然后单击 " **阻止**"。
    - 若要为你的组织打开列表，请搜索 "列表" 应用，将其选中，然后单击 " **允许**"。

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用列表

若要允许或阻止组织中的特定用户使用列表，请确保在 " [管理应用](manage-apps.md) " 页面上为你的组织启用了列表，然后创建自定义应用权限策略并将其分配给这些用户。 若要了解详细信息，请参阅 [管理团队中的应用权限策略](teams-app-permission-policies.md)。

## <a name="search-the-audit-log-for-list-events"></a>在审核日志中搜索列表事件

通过企业级审核启用列表，以便你可以在安全 & 合规中心的审核日志中搜索列表和列表项事件。 若要了解详细信息，请参阅 [在安全 & 合规中心中搜索审核日志](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)。

有关与团队中的列表应用相关的审核事件的列表，请参阅 [SharePoint 列表活动](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities)。

在搜索审核日志之前，必须先在 [安全 & 合规中心](https://protection.office.com)启用审核。 请记住，审核数据仅在你打开审核的位置可用。

## <a name="power-automate-power-apps-and-graph-api"></a>Power 自动化、Power Apps 和 Graph API

列表支持工作流和适用于列表表单的[Power 应用](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)的[power 自动化](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint)。 开发人员可以使用 [列表 API](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) 通过 Microsoft Graph 将列表数据连接为源。

## <a name="give-feedback-or-report-an-issue"></a>提供反馈或报告问题
  
若要向我们发送反馈或报告问题，请单击 "团队" 左侧导航底部附近的 " **帮助** "，然后选择 " **报告问题**"。 选择 " **列表**"，然后输入您的反馈或有关您所遇到的问题的详细信息。

## <a name="related-topics"></a>相关主题

- [列出帮助文档](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)
