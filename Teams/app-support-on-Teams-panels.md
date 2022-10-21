---
title: Microsoft Teams 应用/业务线 (LOB) Teams 面板上的应用支持
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 介绍对 Teams 应用/LOB 应用的支持。
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c8d28a3f985a38e174030ddbe0e6d43e2153738
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656068"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams 应用/业务线 (LOB) Teams 面板上的应用支持

Teams 面板正在添加对 [Teams 应用/业务线 (LOB) 应用](/microsoftteams/platform/overview)的支持。 这使企业能够在面板上添加其他体验，以满足组织的需求。 此版本支持静态 Web 内容。

> [!IMPORTANT]
> 此功能仅在更新 Teams 面板设备 () 后才可用。 需要让 Teams 应用版本 1449/1.0.97.2021070601 或更高版本在 Teams 面板中获得应用支持。

## <a name="teams-app-experience-on-teams-panels"></a>Teams 面板上的 Teams 应用体验

![Teams 管理中心的屏幕截图，其中显示了允许用户导航到应用的部分。](media/tac1update.png)

*Teams 面板主屏幕包含应用导航选项，在屏幕截图中以红色显示。请注意，这些是示例图标，可能不可用。*

![可在其中添加应用的应用画布的屏幕截图。](media/appscreen.png)

*当最终用户点击其中一个应用图标时，他们将看到 Teams 应用屏幕显示在前面的屏幕截图中。屏幕截图中的灰色矩形是应用在Teams 面板上显示的位置。应用栏是固定的，是 Teams 面板应用的一部分。*

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>在 Teams 管理中心设置和管理 Teams 面板应用

Microsoft Teams 应用将关键信息、常用工具和受信任的流程引入到用户收集、学习和工作的位置。 Teams 应用 [通过集成功能工作](/microsoftteams/platform/concepts/capabilities-overview)。 现在，作为 IT 管理员，可以选择在组织的 Teams 面板设备中包含哪些应用，并通过 [Teams 管理中心](https://admin.teams.microsoft.com/)自定义权限。

现在可以在 Teams 面板上使用 Teams 应用，并根据组织的需求自定义用户体验。 可以确定用户可以访问和使用哪个 Web 应用，并确定应用视图的优先级。 目前不支持某些选项，例如机器人和消息传送功能。 详细了解 [Teams 应用](/microsoftteams/platform/overview) 以及 [如何在 Microsoft Teams 中管理设备](/microsoftteams/devices/device-management)。

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>在 Teams 管理中心管理 Teams 面板上的应用

**注意**：必须是全局管理员或 Teams 服务管理员才能访问 [Teams 管理中心](https://admin.teams.microsoft.com/)。

最终用户可以在 Teams 面板上查看但不能安装应用。 作为管理员，可以通过 Teams 管理中心查看和管理组织的所有 Teams 应用。 详细了解如何通过“**管理应用**”页面 [在 Microsoft Teams 管理中心管理](/microsoftteams/manage-apps)应用。 Teams 管理中心内的 **“管理应用** ”页面也是可上传 [自定义应用](/microsoftteams/manage-apps#publish-a-custom-app-to-your-organizations-app-store)的位置。

设置应用后，可以使用 [应用权限策略](/microsoftteams/teams-app-permission-policies) 和 [应用设置策略](/microsoftteams/teams-app-setup-policies) 为组织中的特定会议室帐户配置应用体验。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>使用应用设置策略将应用固定在 Teams 面板上

由于 Teams 提供显示各种应用的功能，因此管理员可以确定哪些应用对组织最为重要，并且仅将这些应用固定到 Teams 面板 **主** 屏幕以快速访问。 如果有五个以上的固定应用或任何未固定的应用，它们将显示在 **“更多** ”屏幕下。 Microsoft 建议在应用设置策略中专门为 Teams 面板创建自定义策略。

![应用设置策略页的用户界面屏幕截图。](media/appsetup1.png)

若要管理 Teams 面板上显示的固定应用，请登录到组织的 Teams 管理中心并导航到 **Teams 应用** \> **设置策略** \> **选择或创建新的策略** \> **固定应用**。

![用户界面内固定应用部分的屏幕截图。](media/appsetup2.png)

*此映像中包含的应用只是示例，可能无法使用。*

Microsoft 建议关闭 **“上传自定义应用** ”和 **“用户固定”** ，以获得 Teams 面板上的最佳 Teams 应用体验。

有关固定应用的详细信息，请参阅 [“管理应用设置策略](/microsoftteams/teams-app-setup-policies)”。

## <a name="manage-apps-display-order-in-teams-panels"></a>在 Teams 面板中管理应用显示顺序

![用户界面中“应用”部分的屏幕截图。](media/appsetup3.png)

*此映像中包含的应用只是示例，可能无法使用。*

若要管理在 Teams 面板上显示应用的顺序，请登录到组织的 Teams 管理中心并导航到 **Teams 应用** \> **设置策略** \> **选择**\>策略 **固定应用：****向上/向下移动**。

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>将设置策略分配到会议室资源帐户

创建设置策略后，管理员需要将此策略分配给将登录到 Teams 面板的会议室资源帐户。 有关详细信息，请参阅 [为用户和组分配策略](/microsoftteams/assign-policies-users-and-groups)。

## <a name="faq"></a>常见问题

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>Teams 面板需要多长时间才能获取新的或更新的应用设置策略？

在 Teams 管理中心编辑或分配新策略后，更改最长可能需要 24 小时才能生效。 管理员可以尝试从面板注销/登录，点击 **“设置”** 图标，然后返回到 **“主页** ”屏幕，尝试刷新策略。

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>“更多”屏幕上的应用排序是什么？

在 **“更多** 应用”页上，固定的应用将首先显示。 然后，任何其他已安装的应用都将按字母顺序显示。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>为什么机器人应用未显示在 Teams 面板上？

目前仅支持静态选项卡 Web 内容。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>为什么本机 Teams 应用（如日历和任务）不出现在 Teams 面板上？

本机 Teams 应用（如日历和任务）不会显示在 Teams 面板上。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>在 Teams 管理中心，在“设置策略”部分下，已安装的应用和固定应用之间有何区别？

对于 Teams 面板，Microsoft 建议使用固定应用，因此管理员能够选择所需的应用并重新排列其排序。

**注意：** 某些应用不支持应用固定。 请联系应用开发人员以启用应用固定功能。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>为什么其他应用会出现在“更多”屏幕中，即使它们不是 Teams 应用设置策略部分中已安装或固定的应用的一部分？

如果应用以前是通过其他应用策略安装的，或者在 Teams 面板上使用的会议室资源帐户的 Teams 桌面/Web 客户端中手动安装，则管理员可能需要登录 Teams 中的会议室资源帐户，然后通过右键单击应用，然后选择 **“卸载**”手动卸载应用。

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>为什么在“添加固定应用”窗格中找不到应用？

并非所有应用都可以通过应用设置策略固定到 Teams。 某些应用可能不支持此功能。 要查找可以固定的应用，请在“**添加固定的应用**”窗格中搜索应用。 有关详细信息，请参阅使用 [应用设置策略中的常见问题解答](/microsoftteams/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)。

### <a name="why-am-i-seeing-an-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-user-pinning"></a>为什么在关闭“用户固定”后，我在“设置策略”面板中看到“用户固定”弹出窗口？

![用户界面内设置策略部分的屏幕截图，其中弹出了确认用户固定处于活动状态。](media/appsetup4.png)

*此映像中包含的应用只是示例，可能无法使用。*

对于共享空间中的设备，此行为是意料之中的，有助于防止意外应用固定。
