---
title: Cortana语音帮助Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何通过语音Cortana语音Teams
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe6434fe874367757dfb7ad954aacaf8d3755041
ms.sourcegitcommit: 7cc7e237b0da270c9cf4a3e535db16dd113e4300
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61205492"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana语音帮助Teams

> [!Note]
> Cortana iOS 和 Android 的 Microsoft Teams 移动应用以及适用于美国、英国、加拿大、印度和澳大利亚的用户的 Microsoft Teams 移动应用中支持语音协助。 Microsoft Teams 会议室 Windows 区域设置设置为 en-us 的设备才支持本地设置。 Cortana语音帮助目前不适用于 GCC-High GCC DoD 和非 US EDU 租户。 Cortana EDU 客户Teams移动应用中的语音帮助。 在将来的版本中，将扩展到其他语言和地区。


Cortana移动应用中Teams语音帮助，在 Microsoft Teams 会议室 上Windows，在 Microsoft Teams 显示设备上启用Microsoft 365 企业版 用户可简化使用口语自然语言的通信、协作和会议相关任务。 用户可以通过选择 Teams 移动应用右上角的麦克风按钮，或者通过在 Microsoft Teams 会议室中说出"Cortana"或者使用 Microsoft Teams 显示器来与 Cortana 讲话。 要免费与团队快速联系，用户可以在离开时说出"呼叫 Megan"或"向下一次会议发送消息"等查询。 用户还可以说"加入我的下一次会议"，并使用语音协助来共享文件、查看其日历等来加入会议。 这些语音协助体验是使用[Cortana](/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)企业级服务提供的，这些服务完全符合 Office 365 的隐私、安全性和合规性承诺，如在线服务条款[ (OST ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)) 所反映。

## <a name="admin-control-and-limitations"></a>管理员控制和限制

Cortana中Teams语音帮助是使用完全符合 Office 365 企业级隐私、安全性和合规性承诺的服务提供的，如联机服务条款 (OST) 所反映。 默认情况下，将为租户启用该功能。

租户管理员可以使用 TeamsCortanaPolicy Cortana策略控制Teams租户中的 (语音) 。 此策略在用户帐户级别或租户级别设置。 管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定是禁用了 Cortana、仅启用了按钮调用还是启用了唤醒词调用， (也适用于支持它的设备，如 Microsoft Teams 显示) 。

管理员可以使用以下 PowerShell cmdlet 来管理此策略 (该策略当前在 Microsoft Teams 管理中心) 。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，以下命令创建一个名称为"EmployeeCortanaPolicy"的新策略，Cortana禁用Microsoft Teams语音帮助。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例演示了更新名称为"EmployeeCortanaPolicy"的现有策略，并Cortana按钮调用在 Microsoft Teams中启用语音帮助。 用户将能够通过在 Cortana 中选择"Cortana麦克风"按钮来Teams。 唤醒 ("你好Cortana"或"Cortana") 将禁用调用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示了如何更新策略，以及Cortana按钮和唤醒词调用启用语音帮助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在初始发布时，美国Microsoft 365 企业版用户使用英语，以下是可用的函数：

- Teams移动应用不支持唤醒词激活，但将来会支持。  

- Microsoft Teams 会议室和Windows Microsoft Teams将支持唤醒词激活。

## <a name="user-control"></a>用户控件

单个用户可以尝试Cortana设备提供语音帮助：

- 在移动应用中选择麦克风Teams按钮。

- 选择麦克风按钮或在麦克风Cortana说"Microsoft Teams 会议室。

- 在显示器Cortana说"Microsoft Teams"。

可以使用设备Cortana，Teams设备中设置来控制设备是否已启用设备内设置。

![显示启用移动窗口时移动窗口Cortana。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Microsoft Teams 会议室上Windows

仅在租户级别启用了Cortana，才能在设备级别进行更改。 

在设备级别，可以将Cortana两种不同的方式使用。 可以同时启用任一选项或同时启用两个选项： 
- 通过点击麦克风（称为"Cortana _说话）_
- 通过说"你好，Cortana"，这称为Cortana _语音激活"_

Cortana如果聊天室设置为以下任何语言，则默认启用推送交谈：en-au (澳大利亚) 、en-ca (加拿大) 、en-gb (英国) 、en-in (印度) 、en-us (美国) 。 [了解更多信息。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana图标将取代"更多..."下的 _"呈现__"按钮。_ "会议室"Teams菜单。 若要禁用Cortana _推送以交谈，请使用_ PowerShell。[了解更多信息。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

若要启用Cortana _激活_，必须满足以下条件：
- Cortana认证设备必须连接到 Teams 会议室。 可以在本文末尾找到已认证设备的列表。
- Teams 会议室必须使用以下任何语言设置：en-au (澳大利亚) 、en-ca (Canada) 、en-gb (英国) 、en-in (印度) 、en-us (美国) 。 以后会提供更多语言。
- 必须做出以下配置更改之一：
  - 在管理中心打开Teams[了解更多。](/microsoftteams/rooms/rooms-manage)
  - 将以下 XML 属性添加到 SkypeSettings XML 文件：

    ```xml
    <SkypeSettings>  
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>  
    </SkypeSettings> 
    ```
    
在会议级别，只有在设备级别启用了Cortana _激活时_，才能进行更改。  若要 _在Cortana启用_ 语音激活，请移动开关 **"打开**"或 **"关闭"** 以禁用。 会议结束后，Cortana设备级别设置集。


如果在设备级别启用了Cortana，可在会议级别进行更改。

若要在Cortana启用语音激活，请移动开关 **"打开"或**"**关闭"。** 会议结束后，Cortana设备级别设置集。


## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana认证设备Teams 会议室
Cortana _Lenovo_ 中心 500 或其中任何设备连接到会议室，可以启用语音激活：
- Jabra Panacast 50 
- 力举麦克风
- Bose 视频栏 VB1

