---
title: Microsoft Teams 的电话功能
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
localization_priority: Normal
description: 本文介绍针对 microsoft 团队认证的手机的列表，以及 Microsoft 团队的手机认证中支持的功能。
ms.openlocfilehash: b811a92977d10601aa601e1bae811ef73c34dce8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836862"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft Teams 的电话功能

Microsoft 团队为需要传统电话体验的用户支持一套桌面电话。 本文介绍针对 microsoft 团队认证的手机的列表，以及 Microsoft 团队的手机认证中支持的功能。 若要获取有关团队认证的设备的最新信息和最新信息，请转到[团队市场](https://office.com/teamsdevices)。

## <a name="teams-certified-ip-phones"></a>团队认证的 IP 电话

为在手机上提供高质量和可靠的 Microsoft 团队体验，我们将与 Yealink、Crestron、Polycom 和 Audiocodes 进行合作并主动处理，以开发和认证一系列桌面手机和会议室音频设备。 请参阅当前[经过认证的 IP 电话](teams-ip-phones.md#currently-certified-ip-phones)以获取当前受支持的设备。

## <a name="microsoft-teams-phones-feature-set"></a>Microsoft 团队手机功能集

下表提供了团队认证的 IP 电话支持的高级功能集。

|功能 |桌面电话（个人模式） |会议室电话（共享模式）|
|---------|---------|---------|
|**身份验证** | |  |
|使用用户凭据登录 |  必需 | 是|
|使用 PC/智能手机登录  | 必需 |是|
|现代化身份验证 | 必需 |是 |
|电话锁定/解锁 | 是 |否 |
|**通话** |  |  |
|传入/传出 P2P 呼叫 | 必需  |是 |
|通过 UI 进行的通话控制（静音、保持/恢复、转移、结束呼叫）| 必需  |是 |
|PSTN 呼叫| 必需  |是 |
|可视语音邮件 | 是 | 否 |
|911支持  | 必需  |是 |
|**日历和状态**|   | |
|日历访问和会议详细信息|必需 |是|
|状态集成 |是|是|
|Exchange 日历集成 |必需|是|
|联系人图片集成  |必需|是|
|公司目录访问 | 必需|是|
|**会议**|   ||
|会议的一次单击加入  | 必需  |是 |
|加入 Skype for Business 会议 | 必需  | 是|
|会议呼叫控件（静音/取消静音、保持/恢复、挂断、添加/删除参与者）|必需|是|
|会议详细信息|是|否|

我们正在努力不断添加功能，以帮助我们的用户在手机上增强其团队体验。 下面的屏幕截图展示了我们目前支持的一些体验。

## <a name="sign-in-experience"></a>登录体验

当用户单击团队中的登录按钮时，通过公司门户启动登录。 用户可以通过在手机上输入用户凭据或通过选择从其他设备登录来选择登录。 如果用户选择从其他设备登录，则用户可以从其 PC 或智能手机完成身份验证。

**用户使用凭据登录**

![通过凭据登录的屏幕截图](media/sign-in-with-credentials.png)

**通过 PC/智能手机进行用户登录**

![通过其他设备登录的屏幕截图](media/sign-in-with-device.jpg)

## <a name="personalshared-mode"></a>个人/共享模式

登录成功后，用户可以选择是将设备用于个人使用还是共享会议室。

!["个人" 或 "共享帐户" 选项的屏幕截图](media/personal-vs-shared-mode.jpg)

"团队手机体验" 根据用户的选择进行了优化。

**个人模式**

![个人模式下的帐户的屏幕截图](media/personal-mode.png)

**共享模式**

![共享模式下的帐户的屏幕截图](media/shared-mode.png)

## <a name="calling-experience"></a>通话体验

Microsoft 团队用户可以抬起话筒或按扬声器按钮，在通话屏幕上启动拨号盘。 或者，用户可以使用硬件按钮（如果可用）拨出号码。

**屏幕上的拨号盘**

![屏幕上拨号盘的屏幕截图](media/on-screen-dial-pad.png)

**通话屏幕**

![通话屏幕的屏幕截图](media/calling-screen.png)

## <a name="meeting-experience"></a>会议体验

Microsoft 团队用户可以导航到 "会议" 选项卡以查看其会议，并使用 "**加入**" 按钮加入其团队会议。

**日历视图**

![日历视图中会议的屏幕截图](media/calendar-view.png)

**会议联接视图**

!["加入" 视图中会议的屏幕截图](media/meeting-join-view.png)


## <a name="voicemail"></a>语音邮件

Microsoft 团队用户在导航到 "**语音邮件**" 选项卡时可以访问他们的语音邮件。

!["语音邮件" 选项卡的屏幕截图](media/voicemail-tab.png)

## <a name="user-sign-out"></a>用户注销

工作组电话用户可以从左上方菜单中选择 "**注销**" 选项来选择注销。

![注销团队的屏幕截图](media/teams-sign-out.png)

## <a name="finding-the-firmware-version-on-a-mobile-device"></a>在移动设备上查找固件版本

通过选择右上角的 "**设置**" 图标，然后单击 "**关于**"，可以在团队登录页面上检查最低固件版本。

**团队登录页面**

![团队登录页面的屏幕截图](media/teams-sign-in-page.jpg)

**设置页面**

!["团队设置" 页面的屏幕截图](media/teams-settings-page.jpg)

## <a name="required-licenses"></a>所需的许可证

Microsoft 团队许可证可以作为其[Office 365 订阅](Office-365-licensing.md)的一部分进行购买。 若要了解有关在手机上使用 Microsoft 团队所需的许可证的详细信息，请参阅可用的[电话系统许可证](https://products.office.com/microsoft-teams/voice-calling)。

有关获取团队的详细信息，请查看[如何获取 Microsoft 团队的访问权限？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="see-also"></a>另请参阅

[团队市场](https://office.com/teamsdevices)

[适用于 Microsoft 团队的 IP 手机认证](teams-ip-phones.md)
