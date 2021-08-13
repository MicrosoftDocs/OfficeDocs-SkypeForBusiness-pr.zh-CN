---
title: Microsoft Teams面板上的 Microsoft Teams 应用/业务 (LOB) 应用Teams支持
author: amandafrechinjackson
ms.author: v-amandaf
manager: jsarrasin
ms.date: 8/5/2021
ms.topic: conceptual
audience: ITPro
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 介绍对应用Teams LOB 应用的支持。
ms.collection:
- M365-voice
- M365-collaboration
- skype-for-business-itpro
- skype-for-business-online
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56c26cef98e316a821f31d3baa014cd1e9f9695743c34493c8880ac85f232830
ms.sourcegitcommit: 0e9516c51105e4d89c550d2ea2bd8e7649a1163b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2021
ms.locfileid: "54591216"
---
# <a name="microsoft-teams-appsline-of-business-lob-app-support-on-teams-panels"></a>Microsoft Teams面板上的 Microsoft Teams 应用/业务 (LOB) 应用Teams支持

Teams面板添加了对 TEAMS 应用/业务线 (LOB) 的支持。 这将使企业能够添加面板上的其他体验，以满足组织的需求。 此版本支持静态 Web 内容。

> [!IMPORTANT]
> 此功能仅在将你的 Teams 面板设备 (后) 。 你需要拥有 Teams 应用版本 1449/1.0.97.2021070601 或更高版本，以在 Teams 面板中提供应用支持。

## <a name="set-up-and-manage-teams-panels-apps-in-teams-admin-center"></a>在管理中心Teams和管理Teams面板应用 

Microsoft Teams应用将关键信息、常用工具和受信任的流程引入人们收集、学习和工作的地方。 Teams应用[通过集成功能运行](/platform/concepts/capabilities-overview)。 现在，作为 IT 管理员，可以选择将哪些应用包括在组织的 Teams 面板设备中，然后通过 Teams 管理中心自定义权限。

现在，可以在Teams面板Teams应用，并基于组织的需求自定义用户体验。 你可以决定用户可以访问和使用哪个 Web 应用，并设置应用视图的优先级。 目前不支持某些选项，如机器人和消息传递功能。 了解有关应用Teams以及如何在应用中管理设备Microsoft Teams。

## <a name="manage-apps-on-teams-panels-in-teams-admin-center"></a>在管理Teams中管理Teams面板上的应用

**注意**：你必须是全局管理员或 Teams服务管理员才能访问Teams中心。

最终用户可以在应用面板上查看Teams安装应用。 作为管理员，可以通过管理中心Teams组织的所有 Teams应用。 通过"管理应用"页，详细了解如何在 Microsoft Teams 管理 **中心管理** 应用。 管理 **中心** 内的"管理Teams页面也是你可以上传自定义 [应用的地方](/manage-apps#publish-a-custom-app-to-your-organizations-app-store)。

设置应用后，可以使用应用[权限策略](/teams-app-permission-policies)和应用设置策略为[](/teams-app-setup-policies)组织中特定会议室帐户配置应用体验。

## <a name="pin-apps-on-teams-panels-with-app-setup-policies"></a>使用应用设置Teams固定面板上的应用

由于 Teams 能够显示各种应用，因此管理员可以决定哪些应用对于组织来说最为重要，并仅为 Teams 面板主屏幕固定这些应用以便快速访问。  如果固定的应用或任何未固定的应用超过五个，它们将显示在更多 **屏幕** 下。 Microsoft 建议专门为应用面板创建自定义Teams策略。

![应用设置策略页面的用户界面屏幕截图。](media/appsetup1.png) 

若要管理显示在 Teams 面板上的固定应用，请登录到组织的 Teams 管理中心并导航到 **Teams 应用** 设置策略 选择或创建新策略 固定的应用 \>  \>  \> 。

![用户界面中固定的应用的屏幕截图部分。](media/appsetup2.png) 

Microsoft 建议关闭自定义 **Upload"** 和"允许用户固定"，以在Teams上获得最佳Teams体验。

有关固定应用的信息，请参阅管理 [应用设置策略](/teams-app-setup-policies)。

## <a name="manage-apps-display-order-in-teams-panels"></a>在面板中管理Teams顺序 

![用户界面中的"应用"部分屏幕截图。](media/appsetup3.png) 

若要管理应用在 Teams 面板上的显示顺序，请登录到组织的 Teams 管理中心并导航到 **Teams 应用** 设置策略 选择策略固定应用 \>  \>  \> **：** 上 **移/下** 移。

## <a name="assigning-setup-policies-to-a-room-resource-account"></a>将设置策略分配给会议室资源帐户

创建设置策略后，管理员需要将此策略分配给将登录到"会议室"Teams帐户。 有关详细信息，请参阅向 [用户和组分配策略](/assign-policies-users-and-groups)。

## <a name="faq"></a>常见问题

### <a name="how-long-does-it-take-for-teams-panels-to-get-the-new-or-updated-app-setup-policies"></a>应用面板获取新的Teams更新的应用设置策略需要多久？

在管理中心编辑或分配Teams策略后，更改可能需要 24 小时才能生效。 管理员可以尝试从面板注销/登录、点击设置图标，然后返回到主屏幕以尝试刷新策略。 

### <a name="what-is-the-ordering-of-the-apps-on-the-more-screen"></a>应用在"更多"屏幕上的排序是什么？

在" **更多** 应用"页面上，固定的应用将首先显示。 然后，任何其他已安装的应用将按字母顺序显示。

### <a name="why-are-bot-apps-not-showing-up-on-teams-panels"></a>为什么自动程序应用未显示在Teams面板上？

目前仅支持静态选项卡 Web 内容。

### <a name="why-are-native-teams-apps-such-as-calendar-and-tasks-not-appearing-on-teams-panels"></a>为什么本机Teams（如日历和任务）未显示在Teams面板上？

本机Teams应用（如日历和任务）不会显示在Teams面板上。

### <a name="in-the-teams-admin-center-under-the-setup-policies-section-what-is-the-difference-between-installed-apps-and-pinned-apps"></a>在Teams管理中心的"设置策略"部分下，已安装的应用和固定的应用之间有什么区别？

对于Teams，Microsoft 建议使用固定的应用，以便管理员能够选择所需的应用并重新安排其排序。

**注意：** 某些应用不支持应用固定。 请联系应用开发人员以启用应用固定功能。

### <a name="why-are-other-apps-appearing-in-the-more-screen-even-though-they-are-not-part-of-the-installed-or-pinned-apps-in-the-teams-app-setup-policy-section"></a>为什么其他应用显示在"更多"屏幕中，即使它们不是应用设置策略部分中的已安装或Teams应用的一部分？

如果应用以前是通过其他应用策略安装的，或者手动安装在 Teams 面板上使用的会议室资源帐户的 Teams 桌面/Web 客户端中，管理员可能需要在 Teams 中登录到会议室资源帐户，然后通过右键单击该应用手动卸载应用，然后选择"卸载"。 

### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>为什么我在"添加固定的应用"窗格中找不到应用？

并非所有应用都可以通过应用设置Teams固定到应用。 某些应用可能不支持此功能。 若要查找可固定的应用，可在"添加固定的应用"窗格中 **搜索** 该应用。 有关详细信息，请参阅使用应用 [设置策略中的常见问题](/teams-app-setup-policies#why-cant-i-find-an-app-in-the-add-pinned-apps-pane)解答。

### <a name="why-am-i-seeing-an-allow-user-pinning-pop-up-in-the-setup-policies-panel-after-i-turn-off-allow-user-pinning"></a>为什么我在关闭"允许用户固定"后，在设置策略面板中看到"允许用户固定"弹出窗口？

![用户界面中的设置策略部分屏幕截图，弹出窗口确认用户固定处于活动状态。](media/appsetup4.png) 

此行为适用于共享空间中的设备，有助于防止意外的应用固定。