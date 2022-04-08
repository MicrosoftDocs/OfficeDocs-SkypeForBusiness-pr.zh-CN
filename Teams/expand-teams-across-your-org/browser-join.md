---
title: 管理浏览器上Teams虚拟访问的联接体验
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
description: 了解浏览器上Teams虚拟访问的联接体验。
ms.openlocfilehash: 276e33b16972f0543566014adf264fd12e45c4ae
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703739"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-browsers"></a>管理浏览器上Teams虚拟访问的联接体验

Microsoft Teams使用户无需下载Teams即可轻松加入虚拟约会。 为了获得更无缝的体验，与会者可以从桌面或移动浏览器加入医疗访问和财务咨询等约会。 与会者无需在其设备上安装Teams应用。

使用浏览器加入时，与会者加入约会时，不会提示他们下载Teams。 相反，Teams在浏览器中打开，与会者现在可以选择 **"加入**"加入。 使用此功能，请记住，如果设备上已安装Teams，则Teams将在浏览器中打开，而不是在应用中打开。

目前，浏览器联接可用于通过以下步骤安排的约会：

- [Bookings应用](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams电子运行状况记录 (EHR) 连接器

  - 与 [Cerner EHR 集成](healthcare/ehr-admin-cerner.md)
  - 与 [Epic EHR 集成](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>设置浏览器联接

### <a name="appointments-scheduled-through-the-bookings-app"></a>通过Bookings应用安排的约会

组织中的计划程序可以针对特定的约会类型和Bookings应用中的单个约会启用此功能。

启用此功能后，发送给与会者的确认电子邮件或短信将包含在桌面或移动浏览器中打开Teams的会议加入链接。 有关支持的浏览器列表，请参阅 [支持的浏览器](#supported-browsers)。

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>为约会类型启用浏览器联接

在Bookings中，转到 **设置** > **Appointment 类型**，选择 [约会类型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)，然后打开 **"允许与会者从浏览器加入**"。 执行此操作可为此类的所有约会启用浏览器联接。

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="允许与会者从Bookings应用中的约会类型的浏览器设置加入的屏幕截图":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>为单个约会启用浏览器联接

在Bookings中，选择 **"新建预订**"，然后打开 **"允许与会者从浏览器加入**"。

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="&quot;允许与会者从Bookings应用中新预订表单上的浏览器设置加入&quot;的屏幕截图":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>通过 Teams EHR 连接器安排的约会

你或你的员工不需要设置！

**与 Cerner EHR** 集成：Teams EHR 连接器支持患者通过短信中的链接加入虚拟约会。 预约时，患者可以通过点击短信中的链接加入，Teams在浏览器中打开。

**与 Epic EHR** 集成：Teams EHR 连接器支持患者通过 MyChart Web 和移动设备加入虚拟约会。 预约时，患者可以使用 **"开始"虚拟访问** 按钮从 MyChart 开始访问，Teams在浏览器中打开。

## <a name="supported-browsers"></a>支持的浏览器

下面是当前支持的浏览器。 我们支持最新版本加上两个以前的版本，除非另有说明。

|平台  |铬 |Safari |边缘 (Chromium) |
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1;&sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1;iOS 或 Android 不支持传出屏幕共享。

&sup2;Safari 上的 iOS 应用无法选择麦克风和扬声器设备。 例如，蓝牙设备。 这是控制默认设备选择的操作系统的限制。

## <a name="things-to-consider"></a>要考虑的事项

进行访问的工作人员可以与从桌面或移动浏览器加入的与会者共享其Teams桌面、移动或 Web 客户端的屏幕。 但是，与会者无法从桌面或移动浏览器共享其屏幕。

## <a name="related-articles"></a>相关文章

- [使用Teams和Bookings应用进行虚拟访问](bookings-virtual-visits.md)
- [创建Bookings约会类型](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [以与会者身份加入Bookings约会](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [使用 Teams 进行虚拟访问 - 集成到 Cerner EHR](healthcare/ehr-admin-cerner.md)
- [使用 Teams 进行虚拟访问 - 集成到 Epic EHR](healthcare/ehr-admin.md)
