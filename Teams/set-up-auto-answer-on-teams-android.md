---
title: 为 Android 设备Teams自动应答
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: kponnus
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
  - M365-collaboration
appliesto:
  - Microsoft Teams
f1.keywords:
  - CSH
ms.custom: null
description: 了解如何使用 PowerShell 在 Android Microsoft Teams 会议室视频电话Teams设置自动应答功能。
---

# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>在 Android 和 Microsoft Teams 会议室 设备上为 Teams 设置自动应答

本文将帮助你在 Android 和Microsoft Teams 会议室设备上设置自动Teams功能。 自动应答允许组织中具有管理权限的用户更改其设备设置，以自动接受传入会议邀请，并自动接受视频呼叫。

## <a name="enable-auto-answer-with-powershell"></a>使用 PowerShell 启用自动答案

使用以下属性在 Android 和Microsoft Teams 会议室设备上的 Teams上启用自动应答：

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 打开传入会议邀请的自动应答

使用 **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** 打开传入会议邀请的自动应答。 默认情况下， **自动应答已关闭** 。 此策略仅适用于传入会议邀请，不支持其他呼叫类型。 有关 cmdlet 详细信息，请阅读 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 。

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2. 设置设备登录模式

使用 **Set-CsTeamsIPPhonePolicy -SignInMode** 设置设备的登录模式，以确定登录到 Teams。 有关 cmdlet 详细信息，请阅读 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 。

登录模式有三个选项：

- **UserSignIn：** 启用单个Teams手机上的体验。
- **CommonAreaPhoneSignIn：** 在手机上启用公用区域电话体验。
- **MeetingSignIn：** 在手机上启用会议室体验。

例如，以下策略将登录模式设置为会议室体验。

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>配置设备设置

启用自动应答后，具有管理权限的用户可以在其设备设置中启用该功能。 若要在设备级别启用该功能，需要启用"自动 **接受传入会议邀请"**。 还可以打开"通过 **视频自动接受"**。 默认情况下，这两个设置都已关闭。

## <a name="related-topics"></a>相关主题

[Microsoft 支持：呼叫和设备](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
