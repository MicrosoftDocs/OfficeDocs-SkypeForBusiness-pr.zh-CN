---
title: Microsoft Teams 中的 Cortana 语音帮助
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何通过 Teams 使用 Cortana 语音协助
ms.localizationpriority: medium
ms.custom:
- Teams-upgrade-guidance
- chat-teams-channels-revamp
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 502f09891942796a326deba35e29fab234e6548a
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198494"
---
# <a name="cortana-voice-assistance-in-teams"></a>Teams 中的 Cortana 语音帮助

> [!NOTE]
> 美国、英国、加拿大、印度和澳大利亚的用户Microsoft适用于 iOS 和 Android 的 Teams 移动应用、Microsoft Teams 显示器和 Windows 上的Microsoft Teams 会议室支持 Cortana 语音协助。 Teams 移动应用中的 Cortana 语音帮助现在可供 en-US 中的 EDU 客户使用。 作为未来版本的一部分，将扩展到其他语言和区域。 Cortana 语音协助目前不适用于 GCC、GCC-High、DoD 和非美国 EDU 租户。

Teams 移动应用、Windows Microsoft Teams 会议室和 Microsoft Teams 显示设备上的 Cortana 语音帮助使Microsoft 365 企业版用户能够使用口语自然语言简化通信、协作和会议相关任务。 用户可以通过选择位于 Teams 移动应用右上角的麦克风按钮，或者在Microsoft Teams 会议室中或使用Microsoft Teams 屏幕时说“Cortana”来与 Cortana 交谈。 为了在外出时免手动快速与团队联系，用户可以说出“呼叫 Megan”或“向我的下一次会议发送消息”等查询。 用户还可以通过说“加入我的下一次会议”来加入会议，并使用语音协助共享文件、检查日历等。 这些语音协助体验是使用 [Cortana 企业级服务](/microsoft-365/admin/misc/cortana-integration)提供的，这些服务完全符合Office 365的隐私、安全性和合规性承诺，如[在线服务条款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true)所反映。

## <a name="admin-control-and-limitations"></a>管理员控制和限制

Teams 中的 Cortana 语音协助是使用完全遵守Office 365企业级隐私、安全性和合规性承诺的服务提供的，如在线服务条款 (OST) 所反映。 默认情况下，将为租户启用此功能。

租户管理员可以使用策略 (TeamsCortanaPolicy) 来控制租户中的哪些人可以使用 Teams 中的 Cortana 语音协助。 此策略在用户帐户级别或租户级别设置。 管理员可以使用此策略控制中的 CortanaVoiceInvocationMode 字段来确定是禁用、仅通过一键调用启用 Cortana，还是使用唤醒词调用以及 (适用于支持 Cortana 的设备（如 Microsoft Teams 显示) ）

管理员可以使用以下 PowerShell cmdlet 来管理此策略， (策略目前在 Microsoft Teams 管理中心) 不可用。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，以下命令创建名为“EmployeeCortanaPolicy”的新策略，禁用了 Microsoft Teams 中的 Cortana 语音协助。

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例演示如何更新名为“EmployeeCortanaPolicy”的现有策略，并在Microsoft Teams 中仅通过一键调用启用 Cortana 语音协助。 用户可以通过在 Teams 中选择 Cortana 麦克风按钮来调用 Cortana。 将禁用 (“你好小娜”或“Cortana”) 调用的唤醒词。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示如何更新策略，并使用按下按钮和唤醒词调用启用 Cortana 语音协助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

目前，对于美国Microsoft 365 企业版用户的初始版本（英语），以下函数可用：

- Teams 移动应用不支持唤醒词激活，但将来将支持该激活。

- Windows 和 Microsoft Teams 显示设备上的Microsoft Teams 会议室将支持唤醒词激活。

## <a name="user-control"></a>用户控件

单个用户可以在不同的设备中尝试 Cortana 语音协助：

- 在 Teams 移动应用中选择麦克风按钮。

- 在Microsoft Teams 会议室中选择麦克风按钮或说出“Cortana”。

- Microsoft Teams 显示设备上说“Cortana”。

可以使用设备中的设置来控制是否为设备启用了 Teams 中的 Cortana。

![显示启用 Cortana 时移动窗口的进度。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Windows 上的Microsoft Teams 会议室

只有在租户级别启用了 Cortana 时，才能在设备级别进行更改。

在设备级别，可以将 Cortana 配置为以两种不同的方式使用。 可以同时启用任一选项或同时启用这两个选项：

- 通过点击称为 Cortana _推送进行对话_ 的麦克风
- 说“你好，Cortana”，称为 _Cortana 语音激活_

如果聊天室设置为以下任一语言，则默认启用 Cortana _推送对话_：en-au (澳大利亚) 、en-ca (加拿大) 、en-gb (英国) 、en-in (印度) 、en-us (美国) 。 [了解更多信息。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana 图标将取代 Teams 会议室控制台中 _“更多...”_ 菜单下的 _“演示_”按钮。 若要禁用 Cortana _Push to talk_ ，请使用 PowerShell。[了解更多信息。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1&preserve-view=true)

若要启用 Cortana _语音激活_，必须满足以下条件：

- Cortana 认证设备必须连接到 Teams 会议室。 可以在本文末尾找到认证设备的列表。
- Teams 会议室必须使用以下任何语言进行设置：en-au (Australia) 、en-ca (Canada) 、en-gb (英国) 、zh-in (India) 、en-us (美国) 。 以后将提供更多语言。
- 必须进行以下配置更改之一：
  - 在 Teams 管理中心中打开该功能 [了解详细信息。](/microsoftteams/rooms/rooms-manage)
  - 将以下 XML 属性添加到 SkypeSettings XML 文件：

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

在会议级别，只有在设备级别启用了 Cortana _语音激活_ 时，才能进行更改。  若要在会议期间启用 Cortana _语音激活_ ，请移动“ **打开**”或“ **关闭”** 开关以禁用。 会议结束后，Cortana 将返回到设备级别设置。

如果在设备级别启用了 Cortana，则可在会议级别进行更改。

若要在会议期间启用 Cortana _语音激活_ ，请移动“ **打开** ”或“ **关闭”** 开关。 会议结束后，Cortana 将返回到设备级别设置。

## <a name="cortana-certified-devices-for-teams-rooms"></a>适用于Teams 会议室的 Cortana 认证设备

如果你使用的是 Lenovo Hub 500 或已将以下任何设备连接到你的房间，则可以启用 Cortana _语音激活_ ：

- Jabra Panacast 50
- Logi Rally Plus 会议系统
- Bose 视频栏 VB1
- EPOS EXPAND 捕获 5
- Yealink MSpeech
