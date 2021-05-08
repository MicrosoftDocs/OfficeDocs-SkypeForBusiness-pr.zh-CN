---
title: Cortana 语音帮助Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何将 Cortana 语音协助用于Teams
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2f8e24bd9035d45639ac4211435355fe7b792a2d
ms.sourcegitcommit: b782ca2ef946ae25e847c2d1847a89993a8edef8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "51886731"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana 语音帮助Teams

> [!Note]
> 适用于 iOS 和 Android 的 Microsoft Teams 移动应用支持 Cortana 语音帮助，Microsoft Teams美国、英国、加拿大、印度和澳大利亚的用户使用 Cortana 语音帮助。  Microsoft Teams 会议室Windows仅美国用户支持登录。 Cortana 语音帮助目前不适用于 GCC-High GCC DoD、EDU 租户。 在将来的版本中，将扩展到其他语言和地区。

> [!Note]
> Microsoft 会议室中的 Cortana 语音Teams预览版下发布。 在其预览版中，只有美国支持 Cortana，在连接了 Rally 麦克风的设备上支持语言 EN-US。

Teams 移动应用、Windows 上的 Microsoft Teams 会议室 和 Microsoft Teams 显示设备中的 Cortana 语音帮助可让 Microsoft 365 企业版 用户使用口语自然语言简化通信、协作和会议相关任务。 用户可以通过选择位于 Teams 移动应用右上角的麦克风按钮，或在 Microsoft Teams 会议室中说出 &#8220;Cortana&#8221; 或者使用 Microsoft Teams 显示器来与 Cortana 讲话。 要免费与团队快速联系，用户可以说查询，例如 &#8220;呼叫 Megan&#8221; 或 &#8220;将消息发送到我的下一个会议&#8221;。 用户还可以加入会议，&#8220;加入下一&#8221;会议，并使用语音协助共享文件、查看其日历等。 这些语音协助体验是使用[Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企业级服务提供的，这些服务完全符合 Office 365 的隐私、安全性和合规性承诺，如联机服务条款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 一样。

该图像显示使用 Cortana 在移动设备上发送聊天。

![显示 Cortana 聊天会话的一系列移动屏幕](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理员控制和限制

Teams 中的 Cortana 语音帮助是使用完全符合 Office 365 企业级隐私、安全性和合规性承诺的服务提供的，如在线服务条款 (OST) 。 默认情况下，将为租户启用该功能。

租户管理员可以使用 TeamsCortanaPolicy Teams策略控制租户中的哪些 (Cortana 语音) 。 可在用户帐户级别或租户级别设置此策略。 管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定 Cortana 是已禁用、是否仅通过推送按钮调用启用，还是通过唤醒词调用启用 (以及适用于支持它的设备（如 Microsoft Teams 显示) ）。

管理员可以使用以下 PowerShell cmdlet 来管理此策略 (该策略目前Microsoft Teams管理中心) 。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，以下命令创建一个名称为 EmployeeCortanaPolicy &#8220;策略&#8221;禁用 Cortana 语音Microsoft Teams策略。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例演示了使用 EmployeeCortanaPolicy &#8220;更新现有策略&#8221;并仅在使用推送按钮调用Microsoft Teams启用 Cortana 语音帮助。 用户将能够通过选择 Cortana 麦克风按钮来调用 Cortana Teams。 唤醒 (&#8220;你好小娜&#8221;或&#8220;Cortana&#8221;) 调用将被禁用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示了通过推送按钮和唤醒词调用更新策略并启用 Cortana 语音协助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在首次发布时，Microsoft 365 企业版美国用户使用英语，以下是可用的函数：

- Teams移动应用不支持唤醒词激活，但将来会支持。  

- Microsoft Teams 会议室和Windows Microsoft Teams将支持唤醒词激活。

## <a name="user-control"></a>用户控件

单个用户可以在不同的设备中试用 Cortana 语音帮助：

- 选择移动应用中的麦克风Teams按钮。

- 选择麦克风按钮或说"Cortana"，Microsoft Teams 会议室。

- 在显示器设备上说Microsoft Teams"Cortana"。

通过使用设备中的设置Teams控制是否为设备启用了 Cortana。

### <a name="teams-mobile-app-or-the-microsoft-teams-display"></a>Teams移动应用或Microsoft Teams显示

  1. 打开 Teams 移动应用。

  2. 选择 **"设置**  >  **Cortana"。**

  3. 将开关移动到 **"开"或**"**关"。**

### <a name="microsoft-teams-display"></a>Microsoft Teams显示

  1. 转到显示器 () 环境Microsoft Teams环境。

  2. 选择用户头像，然后选择 **"设置"。** 如果启用了 Cortana，请说"Cortana，转到设置"。

  3. 将开关移动到 **"开"或**"**关"。**
  
### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 会议室上Windows

如果在租户级别启用了 Cortana，可在设备级别进行更改。 默认情况下，Cortana 将解除禁用。

若要在设备级别启用 Cortana，必须在 SkypeSettings XML 文件中添加这些 XML 属性：

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

如果在设备级别启用了 Cortana，则可在会议级别进行更改。

若要在会议期间启用 Cortana 语音协助，请移动开关"**打开"或**"**关闭"。** 会议结束后，Cortana 将返回到设备级别设置集。
