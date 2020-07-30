---
title: Microsoft 团队中的 Cortana 语音助手
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: akshbhat
search.appverid: MET150
description: 了解如何将 Cortana 语音助手与团队一起使用
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2db1b5cfbc3a50013872b540521f05a5339dd979
ms.sourcegitcommit: 824c79bd050b0abb576004f6209bb081d5090a8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522310"
---
# <a name="cortana-voice-assistance-in-teams"></a>团队中的 Cortana 语音帮助

[!INCLUDE [template](includes/preview-feature.md)]

> [!Note]
> 仅适用于美国用户的 Microsoft 团队 iOS 和 Android 移动应用支持 Cortana 语音帮助。 目前尚不支持 GCC、GCC-高、DoD、教育机构租户。 其他语言和区域的扩展将在将来的版本中发生。

团队移动应用中的 Cortana 语音帮助使 Microsoft 365 企业用户能够使用语音自然语言优化通信、协作和会议相关任务。 用户可以通过单击位于团队移动应用右上角的麦克风按钮来向 Cortana 讲话。 若要在旅途中快速联系他们的团队，用户可以说出诸如 "呼叫 Megan" 或 "向我的下一会议发送一条消息" 之类的查询。 用户还可以通过说 "加入我的下一个会议" 来加入会议，并使用语音协助共享文件、检查其日历等。 这些语音帮助体验是使用[Cortana 企业级服务](https://docs.microsoft.com/microsoft-365/admin/misc/cortana-integration?view=o365-worldwide)提供的，这些服务完全遵守 Office 365 的隐私、安全性和合规性承诺，这些服务反映在[在线服务条款（OST）](https://www.microsoft.com/licensing/product-licensing/products?rtc=1)中。

图像显示在移动设备上的 Cortana 中发送聊天。

![图像显示一系列显示 Cortana 聊天会话的移动屏幕](media/cortana-on-teams-mobile.png)

## <a name="admin-control-and-limitations"></a>管理员控制和限制

团队中的 Cortana 语音帮助已使用完全遵守 Office 365 企业级隐私、安全性和合规性承诺的服务提供，并反映在在线服务条款（OST）中。 默认情况下，将为租户启用该功能。

租户管理员可以控制租户中的哪些用户可以使用策略（TeamsCortanaPolicy）在团队中使用 Cortana 语音协助。 可以在用户帐户级别或租户级别设置此策略。 管理员可以使用此策略控制中的 CortanaVoiceInvocationMode 字段来确定 Cortana 是否已禁用、是否仅使用压入按钮调用，或者是否同时使用唤醒字词调用（适用于支持它的设备）。

管理员可以使用以下 PowerShell cmdlet 管理此策略（该策略当前在 Microsoft 团队管理中心中不可用）。

- [新-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsCortanaPolicy)

- [CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [授权-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsTeamsCortanaPolicy)

- [Set-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsCortanaPolicy)

- [Remove-CsTeamsCortanaPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsCortanaPolicy)

例如，下面的命令将创建一个名为 "EmployeeCortanaPolicy" 的新策略，其中 Microsoft 团队中的 Cortana 语音助手处于禁用状态。  

```PowerShell
PS C:\> New-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode Disabled
```

此示例显示了如何更新名称为 "EmployeeCortanaPolicy" 的现有策略，并仅使用 push 按钮调用在 Microsoft 团队中启用 Cortana 语音助手。 用户将能够通过点击团队中的 Cortana 麦克风按钮来调用 Cortana。 唤醒 word （"你好小娜"）调用将被禁用。  

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode PushToTalkUserOverride
```

此示例演示了如何更新策略以及如何同时启用 "压入" 按钮和唤醒单词调用的 Cortana 语音助手。

```PowerShell
PS C:\> Set-CsTeamsCortanaPolicy -Identity EmployeeCortanaPolicy -CortanaVoiceInvocationMode WakeWordPushToTalkUserOverride
```

> [!Note]
> 在 Microsoft 365 企业用户首次发布英语版时，团队移动应用将不支持唤醒 word 激活，但将来会受到支持。

## <a name="user-control"></a>用户控件

通过单击 "麦克风" 按钮，单个用户可以在 "团队移动应用" 中试用 Cortana 语音帮助。 他们还可以控制是否使用团队移动应用中的设置为其设备启用了团体中的 Cortana。

1. 打开 "团队移动应用"。

2. 转到 "**设置**"。

3. 选择 " **Cortana**"。

4. 将开关移动到 **"打开**" 或 "**关闭**"，具体取决于你是否希望在设备上进行 Cortana 语音协助。
