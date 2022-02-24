---
title: 管理移动浏览器上Teams虚拟访问的加入体验
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
ms.reviewer: hafarmer
description: 了解在移动浏览器中Teams虚拟访问的加入体验。
ms.openlocfilehash: 698a87ba633892f5ebef864c60c101084aa296f1
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929317"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>管理移动浏览器上Teams虚拟访问的加入体验

Microsoft Teams，用户无需下载约会即可轻松地在移动设备上加入Teams。 为获得更无缝的体验，与会者可以从移动浏览器加入约会，例如医疗保健访问、财务咨询、教师办公时间等。 与会者无需在 Android 或 iOS 移动设备上Teams移动应用。

使用移动浏览器加入时，当与会者从移动设备加入约会时，系统不会提示他们下载Teams。 相反，Teams在移动浏览器中打开，与会者可以在其中选择"立即 **加入**"以加入。 使用此功能时，请记住，如果Teams安装在与会者的移动设备上，Teams浏览器中打开，而不是在应用中打开。

目前，移动浏览器加入可用于通过以下方式计划的约会：

- [Bookings 应用](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams EHR) 连接器 (电子运行状况记录

  - 与 [Cerner EHR 集成](healthcare/ehr-admin-cerner.md)
  - 与 [长篇 EHR 集成](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>设置移动浏览器加入

### <a name="appointments-scheduled-through-the-bookings-app"></a>通过 Bookings 应用安排的约会

您的组织中的计划人员可以在 Bookings 应用中为特定约会类型和单个约会启用此功能。

启用此功能后，发送给与会者的确认电子邮件或短信文本将包含在移动浏览器中打开Teams加入链接。 在 Android 移动设备上，Teams Chrome 中打开。 在 iOS 移动设备上，Teams Safari 中打开。

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>为约会类型启用移动浏览器加入

在 Bookings 中 > ，设置选择约会类型，然后打开"允许与会者从移动 [](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)**浏览器加入"**。 这样做可让移动浏览器加入此类型的所有约会。

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Bookings 应用中约会类型的"允许与会者从移动浏览器加入"设置的屏幕截图":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>为单个约会启用移动浏览器加入

在 Bookings **中，选择**"新建预订"，然后打开"允许与会者 **从移动浏览器加入"**。

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Bookings 应用中新预订表单上的"允许与会者从移动浏览器加入"设置的屏幕截图":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>通过 EHR 连接器Teams约会

你或你的员工不需要任何设置！

**与 Cerner EHR** 集成：Teams EHR 连接器支持患者通过移动设备加入虚拟预约。 预约时，患者可以通过点击短信中的链接加入。 患者选择他们想要的浏览器，Teams浏览器中打开。

**与长篇 EHR** 集成：Teams EHR 连接器支持患者通过 MyChart Web 和移动设备加入虚拟约会。 预约时，患者可以使用"开始虚拟访问"按钮从 MyChart **开始** 访问。 患者选择他们想要的浏览器，Teams浏览器中打开。

## <a name="supported-mobile-browsers"></a>支持的移动浏览器

以下是当前支持的移动浏览器。 除非另有说明，否则我们支持最新版本加上两个以前的版本。

|平台  |Chrome |Safari |Edge (Chromium) |
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1;Safari 上的 iOS 应用无法选择麦克风和扬声器设备。 例如，蓝牙设备。 这是操作系统的限制，它控制默认设备选择。

&sup2;需要 Safari 14+ 和 macOS 11+ 才能提供传出视频支持。

## <a name="things-to-consider"></a>要考虑的问题

执行访问的职员可以从桌面、移动Teams客户端与从移动浏览器加入的与会者共享其屏幕。 但是，与会者无法从移动浏览器共享其屏幕。

> [!NOTE]
> 我们将在将来的 Teams 版本中向会议加入体验添加更多功能，因此请返回查看最新信息。 若要随时了解即将推出的Teams功能，请查看Microsoft 365[路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。

## <a name="related-articles"></a>相关文章

- [使用 Teams 和 Bookings 应用的虚拟访问](bookings-virtual-visits.md)
- [创建 Bookings 约会类型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [作为与会者加入 Bookings 约会](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [使用虚拟访问Teams - 集成到 Cerner EHR](healthcare/ehr-admin-cerner.md)
- [使用虚拟访问Teams - 集成到长篇 EHR](healthcare/ehr-admin.md)
