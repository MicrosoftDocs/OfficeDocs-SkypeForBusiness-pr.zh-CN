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
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 了解如何管理会议网络研讨会Teams策略。
ms.openlocfilehash: 1ab4f082a270e4d9b3107c0b6ffbb27bd7c70110
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612971"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中设置网络Microsoft Teams

本文将帮助你将组织设置为举办网络研讨会。

## <a name="what-are-webinars"></a>什么是网络研讨会？

网络研讨会是结构化会议，演示者和参与者具有明确的角色，通常用于培训或销售和营销潜在顾客生成方案。

在组织中设置网络研讨会后，用户可以安排网络研讨会并向与会者开放注册。 与包含许多讨论和任务分配的传统会议不同，网络研讨会适用于交互式演示文稿，并提供用于与会者分析的工具。

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>允许用户在管理中心内Teams网络研讨会

可以使用 Teams 管理中心为组织设置网络研讨会。 您将在会议管理中心的"会议Teams下找到设置 **网络**  >  **研讨会的策略**。

### <a name="allow-meeting-registration"></a>允许会议注册

如果启用此功能，用户可以安排网络研讨会。 默认情况下，此选项已打开。 如果要关闭会议注册，请将其策略设置为"关闭 **"。**

> [!IMPORTANT]
> **必须打开允许安排** 私人会议，以便会议注册正常工作。 默认情况下，此策略在管理中心Teams打开。 对于教育租户中的学生，此策略默认已关闭。 若要详细了解如何为学生启用私人会议计划，请参阅Teams 教育版[策略包](policy-packages-edu.md)。

### <a name="who-can-register"></a>Who注册

如果选择" **每个人"，** 则所有用户（包括匿名用户）都可以注册并参加网络研讨会。 如果选择" **组织中所有人"，** 则只有你组织中用户可以注册网络研讨会。 如果会议注册已关闭，此选项将不可用，并且没有人可以注册网络研讨会。

> [!NOTE]
> 可 **注册Who的** 默认值 **是组织中教育** 租户中的每个人。 有关详细信息，请参阅策略[Teams 教育版向导](easy-policy-setup-edu.md)。

### <a name="allow-engagement-report"></a>允许参与报告

如果启用此功能，组织者可以看到有关谁注册并参加他们设置的网络研讨会的报告。 默认情况下，此策略已关闭。 有关详细信息，请参阅会议[策略 -Teams - 允许参与报告](meeting-policies-in-teams-general.md#allow-engagement-report)。 有关最终用户体验的信息，请参阅 [查看和下载会议出席报告](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>允许用户使用 PowerShell 安排网络研讨会

可以在 **Set-CsTeamsMeetingPolicy** cmdlet Windows PowerShell 中使用以下属性为 Teams 中的网络研讨会设置。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

有关 cmdlet 详细信息，请阅读[Set-CsTeamsMeetingPolicy。](/powershell/module/skype/set-csteamsmeetingpolicy)

> [!NOTE]
> 在运行这些 cmdlet 之前，必须先连接到 Microsoft Teams PowerShell。 有关详细信息，请参阅使用 Teams [PowerShell Microsoft Teams管理数据](/microsoftteams/teams-powershell-managing-teams)。

### <a name="allow-users-to-schedule-webinars"></a>允许用户计划网络研讨会

可以将注册限制为仅组织内部用户，或者向租户内外的每个人开放注册。 默认情况下 **，WhoCanRegister** 已启用，并设置为"每个人 **"。** 如果要关闭会议注册，将 **AllowMeetingRegistration 设置为** **False。**

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** 必须设置为True，AllowMeetingRegistration **正常工作**。 此外，Microsoft Lists需要在 SharePoint 中设置。 若要了解有关详细信息，请参阅控件[的控件Microsoft Lists。](/sharepoint/control-lists)

1. 打开会议注册

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 启用私人会议计划

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

如果希望组织者分析注册和参加网络研讨会的人，则需要启用 **AllowEngagementReport** 策略。 为此，请运行 PowerShell 中的以下命令。

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Enabled
```

## <a name="configure-webinar-settings"></a>配置网络研讨会设置

为网络研讨会启用环境后，无需进一步管理管理员。 策略控制向网络研讨会组织者显示的选项。

## <a name="related-topics"></a>相关主题

- [会议策略 - Teams - 常规](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 文档](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams 教育版策略向导](easy-policy-setup-edu.md)
