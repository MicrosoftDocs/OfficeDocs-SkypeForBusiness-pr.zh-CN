---
title: 在 Microsoft Teams 中设置网络Microsoft Teams
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 了解如何管理会议网络研讨会Teams策略。
ms.openlocfilehash: 8386ef4ea9dd90d60cdc8c891461c3dc1a6b37ad4f3f7c47e42808e3c8f826a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330876"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中设置网络Microsoft Teams

本文将帮助你将组织设置为举办网络研讨会。

## <a name="what-are-webinars"></a>什么是网络研讨会？

网络研讨会是结构化会议，演示者和参与者具有明确的角色，通常用于培训或销售和营销潜在顾客生成方案。

在组织中设置网络研讨会后，用户可以安排网络研讨会并向与会者开放注册。 与包含许多讨论和任务分配的传统会议不同，网络研讨会适用于交互式演示文稿，并提供用于与会者分析的工具。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>允许用户使用 PowerShell 安排网络研讨会

可以在 Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet 中使用以下属性为 Teams 中的网络研讨会设置。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

有关 cmdlet 详细信息，请阅读[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> 在运行这些 cmdlet 之前，必须先连接到 Microsoft Teams PowerShell。 有关详细信息，请参阅使用[powerShell Teams管理Microsoft Teams。](/microsoftteams/teams-powershell-managing-teams)

### <a name="allow-users-to-schedule-webinars"></a>允许用户计划网络研讨会

可以将注册限制为仅组织内部用户，或者向租户内外的每个人开放注册。 默认情况下 **，WhoCanRegister** 已启用，并设置为"每个人 **"。** 如果要关闭会议注册，将 **AllowMeetingRegistration 设置为** **False。**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** 必须设置为True，AllowMeetingRegistration **正常工作**。 此外，Microsoft Lists需要在 SharePoint 中设置。 若要了解有关详细信息，请参阅[控件的控件Microsoft Lists。](/sharepoint/control-lists)

1. 打开会议注册

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 打开私人会议安排

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. 配置谁可以注册网络研讨会

**仅 *允许* 您的组织中的用户注册网络研讨会**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**若要允许任何人（包括匿名用户）注册网络研讨会，请运行：**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 如果在会议设置中关闭匿名加入，则匿名用户无法加入网络研讨会。 若要了解并启用此设置，请参阅会议[Teams。](meeting-settings-in-teams.md)

### <a name="collect-meeting-attendance"></a>收集会议出席情况

如果希望组织者分析谁注册和参加网络研讨会，则需要启用 **AllowEngagementReport** 策略。 为此，请运行 PowerShell 中的以下命令。

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

### <a name="configure-webinar-settings"></a>配置网络研讨会设置

为网络研讨会启用环境后，无需进一步管理管理员。 策略控制向网络研讨会组织者显示的选项。

## <a name="related-topics"></a>相关主题

- [会议策略 - Teams - 常规](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 文档](/powershell/module/skype/set-csteamsmeetingpolicy)
