---
title: Cortana语音帮助Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何通过语音Cortana语音Teams
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
ms.openlocfilehash: 3d0f31c8841a5a357034cc083f1a62d0d6704805
ms.sourcegitcommit: ede53639ac782eb51d7560fc41fb01ec6979dfd9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53428208"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana语音帮助Teams

> [!Note]
> Cortana iOS 和 Android 的 Microsoft Teams 移动应用以及适用于美国、英国、加拿大、印度和澳大利亚的用户的 Microsoft Teams 移动应用中支持语音协助。 Microsoft Teams 会议室Windows仅美国用户支持登录。 Cortana EDU 租户目前GCC GCC、DoD 和非 US EDU 租户提供语音协助。 Cortana EDU 客户Teams移动应用中的语音帮助。 在将来的版本中，将扩展到其他语言和地区。

> [!Note]
> Cortana预览下Microsoft Teams 会议室语音帮助。 在其预览版中，Cortana在连接了 Rally 麦克风的设备上仅支持语言 EN-US 的语言。

Cortana Teams 移动应用、Windows 上的 Microsoft Teams 会议室 和 Microsoft Teams 显示设备上提供语音帮助，Microsoft 365 企业版 用户可以使用口语自然语言简化通信、协作和会议相关任务。 用户可以通过Cortana Teams 移动应用右上角的麦克风按钮，或者通过在 Microsoft Teams 会议室中说出 &#8220;Cortana&#8221; 或者使用 Microsoft Teams 显示器来与 Microsoft Teams 讲话。 要免费与团队快速联系，用户可以说查询，例如 &#8220;呼叫 Megan&#8221; 或 &#8220;将消息发送到我的下一个会议&#8221;。 用户还可以加入会议，&#8220;加入下一&#8221;会议，并使用语音协助共享文件、查看其日历等。 这些语音协助体验[是使用 Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企业级服务提供的，这些服务完全符合 Office 365 的隐私、安全性和合规性承诺，如在线服务条款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 所反映。

## <a name="admin-control-and-limitations"></a>管理员控制和限制

Cortana中Teams语音帮助是使用完全符合 Office 365 企业级隐私、安全性和合规性承诺的服务提供的，如在线服务条款 (OST) 所反映。 默认情况下，将为租户启用该功能。

租户管理员可以使用 TeamsCortanaPolicy Cortana策略控制Teams租户中的 (语音) 。 此策略在用户帐户级别或租户级别设置。 管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定是禁用了 Cortana，还是启用了按钮调用，或者启用了唤醒词调用， (也适用于支持它的设备，如 Microsoft Teams 显示) 。

管理员可以使用以下 PowerShell cmdlet 来管理此策略 (该策略目前Microsoft Teams管理中心) 。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，以下命令创建一个名称为 employeeCortanaPolicy &#8220;的策略，&#8221;禁用Cortana语音Microsoft Teams策略。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例演示了使用 EmployeeCortanaPolicy &#8220;更新现有策略&#8221;并仅在Cortana按钮调用Microsoft Teams启用语音帮助。 用户将能够通过在 Cortana 中选择"Cortana麦克风"按钮来调用Teams。 唤醒 (&#8220;"Cortana&#8221;或&#8220;Cortana&#8221;) 调用将被禁用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示了通过推送按钮和唤醒Cortana更新策略并启用语音帮助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在首次发布时，Microsoft 365 企业版美国用户使用英语，以下是可用的函数：

- Teams移动应用不支持唤醒词激活，但将来会支持。  

- Microsoft Teams 会议室和Windows Microsoft Teams将支持唤醒词激活。

## <a name="user-control"></a>用户控件

单个用户可以尝试Cortana设备提供语音帮助：

- 选择移动应用中的麦克风Teams按钮。

- 选择麦克风按钮或在麦克风Cortana说"Microsoft Teams 会议室"。

- 在Cortana显示设备Microsoft Teams说"Microsoft Teams"。

通过使用设备中的Cortana Teams，可以控制设备是否已启用设备内设置。

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 会议室上Windows

如果在租户级别启用了 Cortana，则可在设备级别进行更改。 Cortana将默认释放"关"。

若要Cortana级别启用配置，必须在 SkypeSettings XML 文件中添加以下 XML 属性：

```xml
<SkypeSettings>  

        <CortanaEnabled>true</CortanaEnabled>  

        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  

</SkypeSettings> 
```

如果在设备级别启用了Cortana，可在会议级别进行更改。

若要在Cortana启用语音协助，请移动开关"**开"或**"**关"。** 会议结束后，Cortana设备级别设置集。
