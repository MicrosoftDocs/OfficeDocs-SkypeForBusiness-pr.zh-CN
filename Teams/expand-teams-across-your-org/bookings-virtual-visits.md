---
title: 使用Microsoft Teams和Bookings应用进行虚拟约会
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 了解如何在Teams中使用Bookings应用计划、管理和执行虚拟约会。
ms.openlocfilehash: 3a69140bd0a02adb879cc0914d7e5c4703623907
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853203"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>使用Microsoft Teams和Bookings应用进行虚拟约会

## <a name="overview"></a>概述

[Microsoft Teams中的Bookings应用](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)为组织提供了一种为员工和与会者安排和管理虚拟约会的简单方法。 使用它来安排约会，如医疗保健访问、财务咨询、面试、客户支持、虚拟配件和咨询、教育办公时间等。

Bookings应用可轻松管理任何组织的复杂计划需求。 调度程序可以从一次体验中管理多个部门和员工日历，以及与内部和外部与会者的通信。

虚拟约会通过Microsoft Teams会议进行，这些会议提供可靠的视频会议功能。 例如，医生可以与患者共享其屏幕并查看测试结果。 或者，银行顾问可以请求文档上的电子签名，允许他们远程关闭交易。

每个虚拟约会都包含一个Teams会议链接，通过电子邮件发送给与会者，他们可以从 Web 浏览器或任何设备上的Teams轻松加入。 自动电子邮件提醒有助于减少不显示，并增强客户和客户参与度。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

借Bookings，你将获得为行业量身定制的体验。 下面是有关如何在组织中使用它的几个示例：

|行业 | 示例 |
|---------|---------|
|金融服务    |  远程销售和服务的虚拟约会<br/>计划和管理银行关系经理、财务顾问和声明调整器的约会，仅举几例，为客户提供更高的效率和便利性。  |
|零售   | 虚拟拟合和咨询 <br/>安排和管理销售人员、产品专家和设计顾问的约会，以便与客户进行虚拟配件和咨询。   |
|医疗   |  患者护理的虚拟约会 <br/>安排和管理护理团队成员的约会，与患者或其他医疗保健提供商会面，讨论医疗问题。   |

本文概述了如何在Teams中使用Bookings应用计划、管理和执行虚拟约会。

## <a name="before-you-get-started"></a>开始之前

如果你是管理员，请参阅[Teams中的“管理Bookings应用](../bookings-app-admin.md)”，了解在Teams中使用Bookings应用的先决条件、如何控制对组织中Bookings的访问以及建议的策略和管理员设置。

请记住，只有组织中的计划程序需要在Teams中安装Bookings应用。 执行或参与虚拟约会的工作人员不需要该应用。 他们从Teams或Outlook日历或使用预订确认电子邮件中的会议链接加入约会。

## <a name="set-up-a-new-booking-calendar"></a>设置新的预订日历

### <a name="create-the-booking-calendar"></a>创建预订日历

在Teams中，转到 **Bookings** > **开始**，然后选择 **“新建预订日历**”。 完成表单，并确保为组织选择相关的业务类型。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="显示业务类型的新预订日历屏幕的屏幕截图":::

如果你是一个较大的组织，如果希望与会者收到来自特定部门而不是整个组织的预订电子邮件，请考虑创建多个预订日历。
若要了解详细信息，请参阅[“创建Bookings日历](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)。

> [!NOTE]
> 如果这不是你第一次在Bookings应用中工作，或者要在现有预订日历中工作，请在Bookings中，选择组织名称旁边的下拉箭头，然后选择 **“现有预订日历**”。 可以从此处搜索所需内容。

### <a name="add-staff"></a>添加员工

在预订日历中，转到 **“更多”选项** (...) >**设置**，然后选择 **“工作人员**”。 添加员工成员并为你添加的每个人分配一个角色。 最多可将 100 名工作人员添加到预订日历中。

Bookings应用与Outlook集成。 添加员工后，你将能够查看该人员的日历可用性和计划预订。 若要了解详细信息，请参阅[“添加员工”并查看Bookings日历](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)。  

### <a name="create-appointment-types"></a>创建约会类型

创建特定的约会类型来表示组织提供的服务，并定制预订体验。 然后，计划程序可以使用约会类型来安排约会。

在预订日历中，转到 **“更多”选项** (...) >**设置**，选择 **“约会”类型**，然后选择 **“添加约会类型**”。 输入名称&mdash;示例，即开户、处方续订、贷款咨询、税务准备&mdash;以及所需的任何其他信息和设置。

你添加的信息包含在每次预订此类约会时发送给与会者的电子邮件确认中。 可以设置电子邮件提醒和其他选项，例如与会者是否可以[从桌面或移动浏览器加入](browser-join.md)，而无需下载Teams。

如果你是Bookings管理员，则每次预订此约会类型时，最多可以链接四个表单供与会者填写。 例如，可能需要与会者在加入约会之前完成注册表单。 若要链接窗体，请选择 **“链接窗体**”。 输入窗体的 URL，然后选择 **“链接**”。  (如果这是第一次链接窗体，系统会提示你创建一个Microsoft 365组来存储表单。 选择 **“创建组** ”以创建组。 只需为预订日历执行此操作一次。) 

使用表单时，请记住：

- 若要更改已链接到约会类型的表单，请在约会类型中或从Microsoft 365组[https://forms.office.com](https://forms.office.com)中选择表单。
- 当所有与会者都来自同一组织时，支持将文件上传到包含 [文件上传问题的](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) 表单。

当计划程序使用约会类型来安排约会时，他们可以选择包括表单、删除表单或添加你链接到约会类型的任何其他表单。 与会者必须先填写表格，然后才能加入约会。

若要了解详细信息，请参阅 [“创建约会类型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)”。

## <a name="schedule-an-appointment"></a>安排约会 

在预订日历中，选择 **“新建预订**”。 选择约会类型，然后填写相关信息。

这包括与会者联系信息、将要提供服务的工作人员、只有工作人员才能查看的内部笔记、电子邮件提醒，以及与会者是否可以从移动浏览器加入。 如果表单已链接到约会类型，则可以选择包括该表单、删除表单或添加任何其他链接表单。

发送给与会者的电子邮件确认包括会议链接和附件，以便他们可以将虚拟约会添加到日历中。 工作人员还会收到电子邮件确认和会议邀请。 如果约会中包含一个表单，Bookings管理员和计划程序可以查看表单是否由与会者在约会前完成，并可以查看与会者的响应。

若要了解详细信息，请参阅[Teams Bookings应用中的预订计划](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)。

## <a name="conduct-an-appointment"></a>进行约会

在Teams或Outlook日历中，转到预订，然后选择 **“加入**”或“Teams会议链接”。 检查音频和视频设置，然后 **立即选择“加入**”。 若要了解详细信息，请参阅[Bookings约会](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)。

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>监视约会并获取实时状态更新

Bookings中的[队列视图](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6)为员工提供了一个仪表板，用于监视当天的所有虚拟约会，并提供实时更新。 若要查看队列，请转到Bookings中的 **“队列**”选项卡。

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Teams中Bookings应用中的队列视图的屏幕截图" lightbox="../media/bookings-virtual-visits-queue.png":::

从队列中，计划程序可以添加新的预订，查看相关的约会详细信息，并查看全天约会状态。 当患者加入候诊室时，状态会更改，并且会显示和跟踪他们的等待时间。 视图使用颜色编码的更新自动刷新，以便轻松识别更改。

工作人员甚至可以直接从队列加入和管理约会。

> [!NOTE]
> 目前，Bookings应用支持每个预订日历最多增加 100 名员工。 如果使用Graph API 设置员工并将其添加到预订日历，则可能不会强制执行此限制。 在此方案中，“ **队列** ”选项卡将无法呈现员工超过 100 的日历的内容。 为了获得最佳体验，建议在预订日历中添加不超过 100 名员工。 我们正在努力在将来的版本中解决此限制。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web 应用的其他功能

Bookings Web 应用提供其他功能。 例如，可以发布自助在线预订页面，用户可在其中安排与员工的约会。 若要访问Bookings Web 应用，请转到 **更多选项** (...) >**打开Bookings Web 应用**。

若要了解详细信息，请参阅[Microsoft Bookings](/microsoft-365/bookings/bookings-overview)。

## <a name="get-insight-into-virtual-appointments-usage"></a>深入了解虚拟约会使用情况

Microsoft Teams管理中心的[“虚拟访问”使用情况报告](../teams-analytics-and-reports/virtual-visits-usage-report.md)为管理员提供了组织中Teams虚拟约会活动的概述。 此报表显示虚拟约会的详细分析，包括Bookings约会。

可以查看关键指标，例如大厅等待时间和约会持续时间。 使用此信息可深入了解使用趋势，帮助优化虚拟约会以提供更好的业务成果。

## <a name="related-articles"></a>相关文章

- [管理移动浏览器上Teams虚拟约会的联接体验](browser-join.md)

- [Teams虚拟访问使用情况报告](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [开始医疗保健组织的Teams](healthcare/teams-in-hc.md)

- [Bookings Teams帮助文档中的应用](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
