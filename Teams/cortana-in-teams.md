---
title: Microsoft 团队中的 Cortana 语音帮助
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何对团队使用 Cortana 语音帮助
localization_priority: Normal
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93ac825d25e7fdb619c2e949fbef0ba517a3fe9
ms.sourcegitcommit: 5a27802a533db13429813a02626de458f4011780
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785386"
---
# <a name="cortana-voice-assistance-in-teams"></a>团队中的 Cortana 语音帮助

> [!Note]
> Microsoft 团队 iOS 和 Android 移动应用中支持 Cortana 语音帮助，并且仅针对美国用户显示了 Microsoft 团队。 目前尚不支持 GCC、GCC-高、DoD、教育机构租户。 其他语言和区域的扩展将在将来的版本中发生。

在团队移动应用和 Microsoft 团队显示设备上的 Cortana 语音帮助使 Microsoft 365 企业用户能够使用语音自然语言优化通信、协作和会议相关任务。 用户可以通过选择位于团队移动应用右上角的麦克风按钮来对 Cortana 讲话，或者说 Microsoft 团队显示 &#8220;Cortana&#8221;。 若要快速随时随地与团队成员联系，用户可以说出诸如 &#8220;呼叫 Megan 之类的查询&#8221; 或 &#8220;向我的下一个会议&#8221; 发送消息。 用户还可以通过说 &#8220;加入我的下一个会议&#8221; 并使用 "语音帮助" 共享文件、检查其日历等，从而加入会议。 这些语音帮助体验是使用 [Cortana 企业级服务](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide) 提供的，这些服务完全遵守 Office 365 的隐私、安全性和合规性承诺反映在 [在线服务条款 (OST) ](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中。

图像显示在移动设备上使用 Cortana 发送聊天。

![图像显示一系列显示 Cortana 聊天会话的移动屏幕](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理员控制和限制

团队中的 Cortana 语音帮助已使用完全遵守 Office 365 企业级隐私、安全性和合规性的服务提供，这些服务反映在在线服务条款 (OST) 中。 默认情况下，将为租户启用该功能。

租户管理员可以控制租户中的哪些人可以使用策略 (TeamsCortanaPolicy) 在团队中使用 Cortana 语音协助。 可以在用户帐户级别或租户级别设置此策略。 管理员可以使用此策略控件中的 CortanaVoiceInvocationMode 字段来确定 Cortana 是否已禁用、是否仅使用压入按钮调用，或者是否与支持它的设备（如 Microsoft 团队显示) ） (一起启用。

管理员可以使用以下 PowerShell cmdlet 管理此策略 (该策略当前在 Microsoft 团队管理中心) 中不可用。

- [新-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [授权-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下面的命令将创建一个名为 &#8220;EmployeeCortanaPolicy&#8221; 的新策略，其中 Microsoft 团队中的 Cortana 语音帮助已禁用。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例显示了使用名称 &#8220;EmployeeCortanaPolicy&#8221; 更新现有策略，并仅使用 push 按钮调用在 Microsoft 团队中启用 Cortana 语音帮助。 用户将能够通过选择团队中的 Cortana 麦克风按钮来调用 Cortana。 唤醒 word ( # B0&#8221; 或 &#8220;Cortana&#8221;) 调用将被禁用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示了如何更新策略并启用了带压按钮和唤醒单词调用的 Cortana 语音帮助。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> 在 Microsoft 365 企业用户首次发布英语版时，团队移动应用将不支持唤醒 word 激活，但将来会受到支持。 唤醒 word 激活功能将在最初版本的 Microsoft 团队显示设备上运行。

## <a name="user-control"></a>用户控件

通过选择 "麦克风" 按钮，单个用户可以在 "团队移动应用" 中试用 Cortana 语音帮助。 他们可以通过简单地说 &#8220;Cortana，在 Microsoft 团队显示设备上试用 Cortana 语音帮助。 &#8221; 他们还可以控制是否使用团队移动应用或 Microsoft 团队显示中的设置为其设备启用团体中的 Cortana。

1. 打开 "团队移动应用"，或转到 Microsoft 团队显示的 "环境 (主页) 屏幕。

2. 在 "团队移动应用" 中，转到 " **设置** "。 在 "Microsoft 团队显示" 中，选择 "用户头像"，然后选择 "设置"。 如果启用了 Cortana，则 &#8220;Cortana，请转到 "设置"。 &#8221;

3. 选择 " **Cortana** "。

4. 将开关移动到 **"打开** " 或 " **关闭** "，具体取决于你是否希望在设备上进行 Cortana 语音协助。
