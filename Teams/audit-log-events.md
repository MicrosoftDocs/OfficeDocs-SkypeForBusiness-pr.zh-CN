---
title: "在 Microsoft Teams 中搜索事件的审核日志 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何从审核日志检索 Microsoft Teams 数据。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b63f6b88d950038ec2e40e7b32eb74bc551cbdf1
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>在 Microsoft Teams 中搜索事件的审核日志
==================================================

通过审核日志可以对 Office 365 服务中的重大事件进行特定搜索。 就 Microsoft Teams 具体而言，下面是一些捕获的事件示例：

-   团队创建

-   团队删除

-   添加了频道

-   更改了设置

Office 365 中的完整事件列表相当广泛，请参阅[此处](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities)。

必须先启用审核，你才可以深入探索审核。 要启用审核，请访问*安全性和合规性*管理中心。 在*“搜索活动”*下方，单击**“立即开始录制”**。 24 小时后，可以通过位于*“搜索和调查”*选项卡下方的*“审核日志搜索”*获取审核数据。


> [!IMPORTANT]
> 只能在启用了审核的点获取审核数据。



![安全性和合规性中心的“审核日志搜索”页面屏幕截图。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

现在，我们来看看如何从审核日志检索 Microsoft Teams 数据：

1.  要检索审核日志信息，请导航到[安全性和合规性管理中心](https://go.microsoft.com/fwlink/?linkid=855775)。 在*“搜索和调查”*下方，选择**“审核日志搜索”**。

    a.  Microsoft Teams 已定义可以选择的审核活动，如下所示。

![安全性和合规性中心的“审核日志搜索”页面屏幕截图。](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  选择感兴趣的活动后，提供要基于其检索 Microsoft Teams 信息的日期范围和用户。 单击**“搜索”**检索结果。

3.  此信息可以导出到 Excel，并可以根据需要筛选。


> [!IMPORTANT]
> 如果以前未启用审核，则需要将其启用，数据才会显示在审核日志中。


