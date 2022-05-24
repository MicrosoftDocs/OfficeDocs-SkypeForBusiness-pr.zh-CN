---
title: 为Teams Android设备设置自动应答
author: mkbond007
ms.author: mabond
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
ms.custom: ''
description: 了解如何使用 PowerShell 在Android和Teams视频电话设备上为Microsoft Teams 会议室设置自动应答功能。
ms.openlocfilehash: fac458a2b7b100a2074dbaac0e209fbdd3527eef
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646591"
---
# <a name="set-up-auto-answer-for-microsoft-teams-rooms-on-android-and-teams-video-phone-devices"></a>为Android和Teams视频电话设备上的Microsoft Teams 会议室设置自动应答

本文将帮助你在Android和Teams视频电话设备上的Microsoft Teams 会议室上设置自动应答功能。 自动应答允许组织中具有管理权限的人员更改其设备设置，以自动接受传入会议邀请，并使用视频自动接受呼叫。

## <a name="enable-auto-answer-with-powershell"></a>使用 PowerShell 启用自动应答

使用以下属性在Android和Teams视频电话设备上的Microsoft Teams 会议室上启用自动应答：

- **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType**
- **Set-CsTeamsIPPhonePolicy -SignInMode**

### <a name="1-turn-on-auto-answer-for-incoming-meeting-invites"></a>1. 为传入的会议邀请启用自动应答

使用 **Set-CsTeamsCallingPolicy -AutoAnswerEnabledType** 为传入会议邀请启用自动答案。 默认情况下，自动应答 **处于关闭状态** 。 此策略仅适用于传入会议邀请，不支持其他呼叫类型。 有关 cmdlet 的详细信息，请阅读 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) 。

```powershell
Set-CsTeamsCallingPolicy -AutoAnswerEnabledType Enabled
```

### <a name="2-set-the-device-sign-in-mode"></a>2.设置设备登录模式

使用 **Set-CsTeamsIPPhonePolicy -SignInMode** 为设备设置登录模式，以确定登录Teams时的行为。 有关 cmdlet 的详细信息，请阅读 [Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy) 。

登录模式有三个选项：

- **UserSignIn：** 在手机上启用单个用户Teams体验。
- **CommonAreaPhoneSignIn：** 在手机上启用常见区域电话体验。
- **MeetingSignIn：** 在电话上启用会议室体验。

例如，以下策略将登录模式设置为会议室体验。

```powershell
Set-CsTeamsIPPhonePolicy -Identity Device -SignInMode MeetingSignIn
```

### <a name="configure-device-settings"></a>配置设备设置

启用自动应答后，具有管理权限的用户可在其设备设置中启用该功能。 若要在设备级别启用该功能，需要启用 **“自动接受传入会议邀请**”。 还可以使用 **视频启用“自动接受**”。 默认情况下，这两个设置都处于关闭状态。

## <a name="related-topics"></a>相关主题

[Microsoft 支持部门：呼叫和设备](https://support.microsoft.com/office/calls-and-devices-4d96653e-6176-4978-98ab-2c19df137e43#ID0EBBD=Devices)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Set-CsTeamsIPPhonePolicy](/powershell/module/skype/set-csteamsipphonepolicy)
