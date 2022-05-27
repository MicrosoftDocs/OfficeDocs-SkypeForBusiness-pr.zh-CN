---
title: Cortana语音协助Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何通过Teams使用Cortana语音帮助
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
ms.openlocfilehash: b79640b5f9d85b845c8d7c74fa1d6931931a6b50
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674984"
---
# <a name="cortana-voice-assistance-in-teams"></a>Cortana语音协助Teams

> [!NOTE]
> 美国、英国、加拿大、印度和澳大利亚的用户支持Cortana Microsoft Teams iOS和Android和Microsoft Teams显示的移动应用中的语音帮助。 Windows上的Microsoft Teams 会议室仅支持区域设置为 en-us 的设备。 Cortana语音协助目前不适用于GCC、GCC高、DoD 和非美国 EDU 租户。 Cortana Teams移动应用中的语音帮助现在适用于 en-US 中的 EDU 客户。 在将来的版本中，将扩展到其他语言和区域。

Cortana Teams移动应用、Windows Microsoft Teams 会议室和Microsoft Teams显示设备上的语音帮助可实现Microsoft 365 企业版 用户可使用口语自然语言简化通信、协作和会议相关任务。 用户可以通过选择位于Teams移动应用右上角的麦克风按钮，或在Microsoft Teams会议室或使用Microsoft Teams显示器时说“Cortana”与Cortana交谈。 若要快速与团队进行免提连接，并且在外出时，用户可以说出诸如“呼叫 Megan”或“向下一次会议发送消息”之类的查询。 用户还可以通过说“加入我的下一次会议”来加入会议，并使用语音帮助来共享文件、检查其日历等。 这些语音协助体验是使用[Cortana企业级服务](/microsoft-365/admin/misc/cortana-integration)提供的，这些服务完全符合Office 365的隐私、安全和合规性承诺，如[在线服务条款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1&preserve-view=true)所反映。

## <a name="admin-control-and-limitations"></a>管理员控制和限制

Cortana语音协助Teams是使用完全符合Office 365企业级隐私、安全和合规性承诺的服务提供的，如在线服务条款 (OST) 中所反映的那样。 默认情况下，将为租户启用此功能。

租户管理员可以使用策略 (TeamsCortanaPolicy) 控制租户中谁可以在Teams中使用Cortana语音帮助。 此策略设置在用户帐户级别或租户级别。 管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定是禁用Cortana、仅使用按钮调用启用，还是使用唤醒词调用，以及 (适用于支持它的设备，如Microsoft Teams显示) 。

管理员可以使用以下 PowerShell cmdlet 来管理此策略， (策略当前在Microsoft Teams管理中心) 中不可用。

- [New-CsTeamsCortanaPolicy](/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [Get-CsTeamsCortanaPolicy](/powershell/module/skype/Get-CsTeamsCortanaPolicy)

- [Grant-CsTeamsCortanaPolicy](/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，以下命令创建名为“EmployeeCortanaPolicy”的新策略，其中禁用了Microsoft Teams Cortana语音帮助。

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例演示如何更新名为“EmployeeCortanaPolicy”的现有策略，并在仅使用按钮调用Microsoft Teams中启用Cortana语音帮助。 用户可以通过在Teams中选择“Cortana麦克风”按钮来调用Cortana。 将禁用唤醒词 (“嘿Cortana”或“Cortana”) 调用。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示如何更新策略，并使用推送按钮和唤醒单词调用启用Cortana语音帮助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

在为美国Microsoft 365 企业版用户提供英语的初始版本中，有以下可用函数：

- Teams移动应用不支持唤醒词激活，但将来会支持它。

- Windows和Microsoft Teams显示设备上的Microsoft Teams 会议室将支持唤醒词激活。

## <a name="user-control"></a>用户控件

单个用户可以在不同的设备中尝试Cortana语音协助：

- 选择Teams移动应用中的麦克风按钮。

- 在Microsoft Teams 会议室中选择麦克风按钮或说“Cortana”。

- 在显示设备Microsoft Teams上说“Cortana”。

可以使用设备中的设置控制是否为设备启用Teams中的Cortana。

![显示启用Cortana时移动窗口的进度。](media/cortana-mobile-sequence.png)

### <a name="microsoft-teams-rooms-on-windows"></a>Windows上的Microsoft Teams 会议室

仅当在租户级别启用了Cortana时，才可在设备级别进行更改。

在设备级别，可以将Cortana配置为以两种不同的方式使用。 可以同时启用或同时启用这两个选项：

- 点击麦克风，这称为Cortana _推来说话_
- 通过说“嘿，Cortana”，这被称为 _Cortana语音激活_

如果使用以下任一语言设置了会议室，则默认情况下会启用Cortana _推送对话_：en-au (澳大利亚) 、en-ca (加拿大) 、en-gb (英国) 、 (印度) 、en-us (美国) 。 [了解更多信息。](/MicrosoftTeams/rooms/console#to-apply-your-desired-language) Cortana图标会在Teams会议室控制台的 _“更多..._”菜单下替换“_当前_”按钮。 若要禁用Cortana _推送对话，_ 请使用 PowerShell。[了解更多信息。](/powershell/module/skype/new-csteamscortanapolicy?view=skype-ps#example-1)

若要启用Cortana _语音激活_，必须满足以下条件：

- Cortana认证设备必须连接到Teams会议室。 可在本文末尾找到经过认证的设备列表。
- Teams会议室必须使用以下任何语言设置：en-au (澳大利亚) 、en-ca (加拿大) 、en-gb (英国) 、 (印度) 、en-us (美国) 。 稍后将提供更多语言。
- 必须进行以下配置更改之一：
  - 在Teams管理中心启用此功能[了解详细信息。](/microsoftteams/rooms/rooms-manage)
  - 将以下 XML 属性添加到 SkypeSettings XML 文件：

    ```xml
    <SkypeSettings>
        <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
    </SkypeSettings>
    ```

在会议级别，仅当设备级别启用了Cortana _语音激活_ 时，才可进行更改。  若要在会议期间启用Cortana _语音激活_，请移动切换 **打开** 或 **关闭** 以禁用。 会议结束后，Cortana返回到设备级别设置集。

如果在设备级别启用了Cortana，则可以在会议级别进行更改。

若要在会议期间启用Cortana _语音激活_，请移动切换 **打开** 或 **关闭**。 会议结束后，Cortana返回到设备级别设置集。

## <a name="cortana-certified-devices-for-teams-rooms"></a>Cortana Teams 会议室认证设备

如果使用的是联想中心 500，或者有以下任何设备连接到你的会议室，则可以启用Cortana _语音激活_：

- Jabra Panacast 50
- Rally 麦克风
- Bose 视频栏 VB1
- EPOS EXPAND 捕获 5
- Yealink MSpeech
