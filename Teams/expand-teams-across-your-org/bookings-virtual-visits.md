---
title: 使用 Microsoft Teams 和 Bookings 应用进行虚拟访问
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: 了解如何在应用程序中使用 Bookings Teams计划、管理和执行虚拟访问。
ms.openlocfilehash: a37a024e31c75bbedbdb36d9aa0d6acfd2af614c
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432454"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>使用 Microsoft Teams 和 Bookings 应用进行虚拟访问

## <a name="overview"></a>概述

Microsoft Teams[中的 Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)应用为组织提供了一种简单的方式来安排和管理教职员工和与会者的虚拟约会。 使用它安排虚拟约会，例如医疗保健访问、财务咨询、面试、客户支持、虚拟购物体验、教育办公时间等。

Bookings 应用便于管理任何组织的复杂日程安排需求。 调度程序可以从一次体验中管理多个部门和员工日历，以及与内部和外部与会者的通信。

虚拟访问通过会议Microsoft Teams，这些会议提供强大的视频会议功能。 例如，医生可以与患者共享其屏幕并查看测试结果。 或者，银行顾问可以请求对文档进行电子签名，从而允许他们远程关闭交易。

每个虚拟约会Teams一个会议链接，该链接通过电子邮件发送给与会者，他们可以轻松地从 Web 浏览器加入会议，或者Teams设备上加入。 自动电子邮件提醒有助于减少未显示，并增强客户和客户端的参与度。

通过 Bookings，你可以获得针对你的行业定制的体验。 下面是一些如何在组织中使用它的示例：

|行业 | 示例 |
|---------|---------|
|金融服务    |  远程销售和服务的虚拟访问<br/>安排和管理银行关系经理、财务顾问和索赔调整员的虚拟约会，以提高效率和便利性，为客户提供服务。  |
|医疗保健   |  患者护理虚拟访问 <br/>安排和管理您的护理团队成员的虚拟访问，与患者或其他医疗保健提供商会面，讨论医疗保健问题。   |
|零售   | 虚拟购物体验 <br/>安排和管理销售人员、产品专家和设计顾问的约会，与客户进行虚拟购物体验。   |

本文概述了如何在应用程序中使用 Bookings Teams计划、管理和执行虚拟访问。

## <a name="before-you-get-started"></a>开始之前

如果你是管理员，请参阅在 Teams 中管理 Bookings 应用，了解在 Teams 中使用[Bookings](../bookings-app-admin.md)应用的先决条件、如何控制组织中对 Bookings 的访问，以及建议的策略和管理员设置。

请记住，只有您的组织中的计划程序需要将 Bookings 应用安装在 Teams。 执行或参与虚拟约会的人员不需要该应用。 他们通过自己的会议或Teams Outlook或通过使用预订确认电子邮件中的会议链接加入约会。

## <a name="set-up-a-new-booking-calendar"></a>设置新的预订日历

### <a name="create-the-booking-calendar"></a>创建预订日历

在Teams，转到 **"Bookings**  >  **入门"，** 然后选择"新建 **预订日历"。** 填写表单，并确保为组织选择相关的业务类型。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="显示业务类型的新预订日历屏幕的屏幕截图":::

如果你是一个较大的组织，如果希望与会者接收来自特定部门而不是整个组织的预订电子邮件，请考虑创建多个预订日历。
若要了解详情，请参阅 [创建 Bookings 日历](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)。

> [!NOTE]
> 如果这不是您第一次使用 Bookings 应用，或者您希望使用现有的预订日历，请在 Bookings 中选择组织名称旁边的下拉箭头，然后选择"现有预订日历 **"。** 在此处，可以搜索想要搜索的项。

### <a name="add-staff"></a>添加教职员工

在预订日历中，转到"**更多选项**" (...) >设置"，然后选择"教 **职员工"。** 添加教职员工成员，并为每个添加的人员分配角色。

Bookings 应用与 Outlook。 添加教职员工后，您将能够查看此人的日历可用性并安排其预订。 若要了解详情，请参阅 [添加教职员工并查看 Bookings 日历](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)。  

### <a name="create-appointment-types"></a>创建约会类型

创建特定约会类型来表示组织提供的服务，并定制预订体验。

在预订日历中，转到"更多选项" (...) >"约会类型"，然后选择"新建 **约会类型"。**  输入一 &mdash; 个名称，例如，帐户打开、付款续订、贷款咨询、税务准备以及任何其他 &mdash; 信息和设置。

您添加的信息和链接包含在每次预订这种类型的约会时发送给与会者的电子邮件确认中。 您甚至可以设置电子邮件提醒和其他选项，例如与会者是否可以从移动浏览器加入，[](mobile-browser-join.md)而无需下载Teams。 有关详细信息，请参阅创建 [约会类型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)。

## <a name="schedule-a-virtual-visit"></a>安排虚拟访问

在预订日历中，选择"新建 **预订"。** 选择约会类型，然后填写相关信息。

这包括与会者联系信息、将提供服务的员工、仅职员可以看到的内部备注、电子邮件提醒以及与会者是否可以从移动浏览器加入。 若要了解详情，请参阅[在 Teams Bookings 应用中安排预订](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)。

发送给与会者的电子邮件确认包括会议链接和附件，以便他们可以将虚拟约会添加到他们的日历中。 教职员工还会收到电子邮件确认和会议邀请。

## <a name="conduct-a-virtual-visit"></a>进行虚拟访问

在Teams或Outlook日历中，转到预订，然后选择"加入"或Teams会议链接。  检查音频和视频设置，然后选择"立即 **加入"。** 若要了解详情，请参阅 [进行 Bookings 约会](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web 应用的其他功能

Bookings Web 应用提供其他功能。 例如，你可以发布自助在线预订页面，用户可以在这里安排与职员的约会。 若要访问 Bookings Web 应用，**请转到"更多** 选项" (...) >"**打开 Bookings Web 应用"。**

若要了解详情，请参阅[Microsoft Bookings。](/microsoft-365/bookings/bookings-overview)

## <a name="related-articles"></a>相关文章

[管理在移动浏览器中Teams虚拟访问的加入体验](mobile-browser-join.md)

[适用于医疗保健组织的 Teams 入门](healthcare/teams-in-hc.md)

[Teams 帮助文档中的 Bookings 应用](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
