---
title: 使用 Microsoft Teams 和 Bookings 应用的虚拟访问
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
description: 了解如何使用 Teams 中的 Bookings 应用计划、管理和执行虚拟Teams。
ms.openlocfilehash: 6241c377cc5daa0986081fbfa30eca5fa7146efc
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929267"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft Teams 和 Bookings 应用进行虚拟访问

## <a name="overview"></a>概述

Microsoft Teams [中的 Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) 应用为组织提供了一种简单的方式来安排和管理教职员工和与会者的虚拟约会。 使用它安排约会，例如医疗保健访问、财务咨询、面试、客户支持、虚拟配件和咨询、教育办公时间等。

Bookings 应用便于管理任何组织的复杂日程安排需求。 调度程序可以从一次体验中管理多个部门和员工日历，以及与内部和外部与会者的通信。

虚拟约会通过会议Microsoft Teams，提供可靠的视频会议功能。 例如，医生可以与患者共享其屏幕并查看测试结果。 或者，银行顾问可以请求对文档进行电子签名，从而允许他们远程关闭交易。

每个虚拟约会Teams一个会议链接，该链接通过电子邮件发送给与会者，他们可以轻松地从 Web 浏览器加入会议，或者Teams设备上加入。 自动电子邮件提醒有助于减少未显示，并增强客户和客户端的参与度。

通过 Bookings，你可以获得针对你的行业定制的体验。 下面是一些如何在组织中使用它的示例：

|行业 | 示例 |
|---------|---------|
|金融服务    |  远程销售和服务的虚拟访问<br/>安排和管理银行关系经理、财务顾问和索赔调整员的约会，只是几个约会，以提高效率和便利性为客户提供服务。  |
|零售   | 虚拟拟合和咨询 <br/>安排和管理销售人员、产品专家和设计顾问的约会，与客户进行虚拟拟合和咨询。   |
|医疗保健   |  患者护理虚拟访问 <br/>安排和管理护理团队成员的预约，与患者或其他医疗保健提供商会面，讨论医疗保健问题。   |

本文概述了如何使用 Teams 中的 Bookings 应用安排、管理和执行虚拟Teams。

## <a name="before-you-get-started"></a>开始之前

如果你是管理员，请参阅在 Teams 中管理 [Bookings](../bookings-app-admin.md) 应用，了解在 Teams 中使用 Bookings 应用的先决条件、如何控制组织中对 Bookings 的访问，以及建议的策略和管理员设置。

请记住，只有您的组织中的计划程序需要将 Bookings 应用安装在 Teams。 执行或参与虚拟约会的人员不需要该应用。 他们通过自己的日历或Teams Outlook或通过使用预订确认电子邮件中的会议链接加入约会。

## <a name="set-up-a-new-booking-calendar"></a>设置新的预订日历

### <a name="create-the-booking-calendar"></a>创建预订日历

在Teams，转到 **"Bookings** > **""** 开始"，然后选择"新建 **预订日历"**。 填写表单，确保为组织选择相关的业务类型。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="显示业务类型的新预订日历屏幕的屏幕截图":::

如果你是一个较大的组织，如果希望与会者接收来自特定部门而不是整个组织的预订电子邮件，请考虑创建多个预订日历。
若要了解详情，请参阅 [创建 Bookings 日历](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)。

> [!NOTE]
> 如果这不是您第一次使用 Bookings 应用，或者您希望使用现有的预订日历，请在 Bookings 中选择组织名称旁边的下拉箭头，然后选择"现有预订日历 **"**。 在此处，可以搜索想要搜索的项。

### <a name="add-staff"></a>添加教职员工

在预订日历中，转到"更多选项 **" (...**) >设置，**然后选择**"教职 **员工"**。 添加教职员工成员，并为每个添加的人员分配角色。 您最多可以将 100 名员工添加到预订日历中。

Bookings 应用与 Outlook。 添加教职员工后，您将能够查看此人的日历可用性并安排其预订。 若要了解详情，请参阅 [添加教职员工并查看 Bookings 日历](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)。  

### <a name="create-appointment-types"></a>创建约会类型

创建特定约会类型来表示组织提供的服务，并定制预订体验。

在预订日历中，转到"更多选项 **" (...** ) > **"** 约会类型"，然后选择"新建 **约会类型"**。 输入名称，&mdash;例如，"帐户打开"、"付款续订"、贷款咨询、税务准备&mdash;以及任何其他信息和设置。

您添加的信息和链接包含在每次预订这种类型的约会时发送给与会者的电子邮件确认中。 您甚至可以设置电子邮件提醒和其他选项，例如与会者是否可以从移动浏览器加入，[](mobile-browser-join.md)而无需下载Teams。 有关详细信息，请参阅 [创建约会类型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)。

## <a name="schedule-a-visit"></a>安排访问

在预订日历中，选择"新建 **预订"**。 选择约会类型，然后填写相关信息。

这包括与会者联系信息、将提供服务的员工、仅职员可以看到的内部备注、电子邮件提醒以及与会者是否可以从移动浏览器加入。 若要了解详情，请参阅[在 Teams Bookings 应用中安排预订](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)。

发送给与会者的电子邮件确认包括会议链接和附件，以便他们可以将虚拟约会添加到他们的日历中。 教职员工还会收到电子邮件确认和会议邀请。

## <a name="conduct-a-visit"></a>执行访问

在Teams日历Outlook，转到预订，然后选择"加入"或"Teams会议"链接。 检查音频和视频设置，然后选择"立即 **加入"**。 若要了解详情，请参阅 [进行 Bookings 约会](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)。

## <a name="monitor-visits-and-get-real-time-status-updates"></a>监视访问并获取实时状态更新

Bookings [中的](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) 队列视图为员工提供一个仪表板，用于监视当天的所有虚拟约会，并实时更新。 若要查看队列，请转到 Bookings **中的"** 队列"选项卡。

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Bookings 应用中队列视图的屏幕截图Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

在队列中，计划人员可以添加新的预订、查看相关的约会详细信息，以及查看全天的约会状态。 当患者加入等待室时，状态会更改，并显示并跟踪其等待时间。 视图会自动刷新颜色编码的更新，以便可以轻松识别更改。

员工甚至可以直接从队列加入和管理约会。

> [!NOTE]
> 目前，Bookings 应用支持每个预订日历最多添加 100 名员工。 如果使用了Graph API 来设置预订日历并添加员工，则可能不会强制实施此限制。 在此方案中 **，"队列** "选项卡无法呈现教职员工数超过 100 的日历的内容。 为获得最佳体验，建议在预订日历中添加不超过 100 名员工。 我们正在努力在未来版本中解决此限制。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web 应用的其他功能

Bookings Web 应用提供其他功能。 例如，你可以发布自助在线预订页面，用户可以在这里安排与职员的约会。 若要访问 Bookings Web 应用， **请转到"更多** 选项" (...) > **打开 Bookings Web 应用**。

若要了解详情，请参阅 [Microsoft Bookings](/microsoft-365/bookings/bookings-overview)。

## <a name="related-articles"></a>相关文章

- [管理移动浏览器上Teams虚拟访问的加入体验](mobile-browser-join.md)

- [Teams虚拟访问使用情况报告](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [医疗保健Teams入门](healthcare/teams-in-hc.md)

- [Teams帮助文档中的 Bookings 应用](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
