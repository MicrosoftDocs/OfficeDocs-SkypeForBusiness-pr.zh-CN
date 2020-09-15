---
title: 管理你的组织的倒班应用
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中的一线工作人员的团队中设置和管理倒班应用。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8c41c4435877860a2193e6b50f45f714c8c85cb2
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814731"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中为组织管理 Shifts 应用

> [!IMPORTANT]
> 2020年6月30日生效，Microsoft StaffHub 已停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 已停止为2020年6月30日的所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅 [Microsoft StaffHub 已停](microsoft-staffhub-to-be-retired.md)用。  

## <a name="overview-of-shifts"></a>倒班概述

Microsoft 团队中的 "移动" 应用让一线工作人员保持连接和同步。它首先构建了移动，为团队提供快速、有效的时间管理和沟通。 倒班让一线工作者和他们的经理使用自己的移动设备管理计划和保持联系。

- 经理负责创建、更新和管理团队的倒班计划。 他们可以将邮件发送给一个人， ( "地板上有溢出" ) 或整个团队 ( "区域 GM 在20分钟内送达" ) 。 他们还可以发送策略文档、新闻公告和视频。 
- 员工查看他们的即将到来的班次，可查看当天安排的其他人、请求交换或提供班次，以及请求下班时间。 

请务必知道当前班次不支持来宾用户。 这意味着在团队中启用来宾访问时，无法将团队中的来宾添加到或使用倒班计划。 

 > [!Note]
 > 有关详细信息，请参阅 [按平台的团队功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) 。

## <a name="availability-of-shifts"></a>倒班的可用性

倒班在所有企业版 Sku 可用，其中有团队可用。

## <a name="location-of-shifts-data"></a>倒班数据的位置

倒班数据当前存储在北美、西欧和亚太地区数据中心的 Azure 中。 有关存储数据的位置的详细信息，请参阅 [我的数据在哪里](http://o365datacentermap.azurewebsites.net/)？

## <a name="set-up-shifts"></a>设置倒班

### <a name="enable-or-disable-shifts-in-your-organization"></a>启用或禁用组织中的班次

默认情况下，将为组织中的所有团队用户启用倒班。 你可以在 Microsoft 团队管理中心的 " [管理应用](../../manage-apps.md) " 页面上，关闭或打开组织级别的应用。

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **管理应用**"。
2. 在应用列表中，执行下列操作之一：

    - 若要为你的组织关闭班次，请搜索 "倒班" 应用，选择它，然后单击 " **阻止**"。
    - 若要为你的组织启用倒班，请搜索 "倒班" 应用，选择它，然后单击 " **允许**"。

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>启用或禁用组织中特定用户的班次

若要允许或阻止组织中的特定用户使用倒班，请确保在 " [管理应用](../../manage-apps.md) " 页面上为你的组织启用了班次，然后创建自定义应用权限策略并将其分配给这些用户。 若要了解详细信息，请参阅 [管理团队中的应用权限策略](../../teams-app-permission-policies.md)。

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>使用 FirstlineWorker 应用设置策略固定对团队的倒班

应用设置策略允许你自定义团队，以突出显示你的组织中的用户最重要的应用。 策略中设置的应用将固定到应用程序栏，应用栏 &mdash; 位于团队桌面客户端和团队移动客户端的底部， &mdash; 用户可在其中快速轻松地访问它们。
 
团队包括一个内置的 FirstlineWorker 应用设置策略，可分配给你的组织中的一线工作人员。 默认情况下，该策略包括活动、班次、聊天和呼叫应用。 

若要查看 FirstlineWorker 策略，请在 Microsoft 团队管理中心的左侧导航中，转到 "**团队应用**  >  **应用" 设置策略**。

![FirstlineWorker 应用设置策略的屏幕截图](../../media/firstline-worker-app-setup-policy.png "Microsoft 团队管理中心中的 FirstlineWorker 应用设置策略的屏幕截图")

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>将 FirstlineWorker 应用设置策略分配给用户

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>在审核日志中搜索倒班事件

**（处于预览阶段）**

您可以在您的组织中搜索 "审核日志" 以查看倒班活动。  若要了解有关如何搜索审核日志和查看审核日志中记录的 [班次活动](../../audit-log-events.md#shifts-in-teams-activities) 列表的详细信息，请参阅 [在审核日志中搜索团队中的事件](../../audit-log-events.md)。

在搜索审核日志之前，必须先在 [安全 & 合规中心](https://protection.office.com)启用审核。 若要了解详细信息，请参阅 [打开或关闭审核日志搜索](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014)。 请记住，审核数据仅在你打开审核的位置可用。

## <a name="related-topics"></a>相关主题

- [倒班一线工作者的帮助](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [向团队中的用户分配策略](../../assign-policies.md)
