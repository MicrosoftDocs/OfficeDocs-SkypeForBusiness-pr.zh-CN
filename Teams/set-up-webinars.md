---
title: 在 Microsoft Teams 中为网络研讨会进行设置
ms.author: mabond
author: mkbond007
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
description: 了解如何管理 Teams 会议的网络研讨会策略。
ms.openlocfilehash: 26863b26f960b50d81fa1d98090c3616d5b492a7
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706479"
---
# <a name="set-up-for-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中为网络研讨会进行设置

本文将帮助你将组织设置为托管网络研讨会。

## <a name="what-are-webinars"></a>什么是网络研讨会？

网络研讨会是结构化会议，演示者和参与者具有明确的角色，通常用于培训目的或销售和营销潜在顾客生成方案。

在组织中设置网络研讨会后，用户可以计划网络研讨会并向与会者打开注册。 与包括许多讨论和任务分配的传统会议不同，网络研讨会用于交互式演示文稿，并为与会者提供分析工具。

> [!IMPORTANT]
> 若要让用户设置网络研讨会，必须在 SharePoint 中通过启用创建个人列表来配置Microsoft Lists。 若要了解详细信息，请参阅[Microsoft Lists的控制设置](/sharepoint/control-lists)。

## <a name="allow-users-to-schedule-webinars-in-the-teams-admin-center"></a>允许用户在 Teams 管理中心计划网络研讨会

可以使用 Teams 管理中心为组织设置网络研讨会。 你将根据 **会议** > 会议策略在 Teams 管理中心找到设置网络研讨会 **的策略**。

### <a name="meeting-registration"></a>会议注册

如果启用此功能，用户可以计划网络研讨会。 默认情况下，此操作处于打开状态。 如果要关闭会议注册，请将此策略设置为 **“关闭**”。

> [!IMPORTANT]
> 要使会议注册正常工作，必须启用 **私人会议日程安排**。 默认情况下，此策略在 Teams 管理中心打开。 对于教育租户中的学生，此策略默认处于关闭状态。 有关如何为学生启用私人会议安排的详细信息，[请参阅Teams 教育版策略和策略包](policy-packages-edu.md)。

### <a name="who-can-register"></a>谁可以注册

如果选择 **“每个人**”，所有用户（包括匿名用户）都可以注册并参加网络研讨会。 如果选择 **组织中的“每个人**”，则只有组织中的用户才能注册网络研讨会。 如果会议注册被关闭，则此选项将不可用，并且没有人可以注册网络研讨会。

> [!NOTE]
> **谁可以注册** 的默认值是 **教育租户中的组织中的每个人**。 有关详细信息，请参阅[Teams 教育版策略向导](easy-policy-setup-edu.md)。

### <a name="engagement-report"></a>Engagement 报表

此时，组织者可以看到有关谁注册并参加了他们设置的网络研讨会的报告。 默认情况下，此策略处于启用状态。 有关详细信息，请参阅 [Teams 中的会议策略 - Engagement 报告](meeting-policies-in-teams-general.md#engagement-report)。 有关最终用户体验的信息，请 [参阅“查看”并下载会议出席情况报告](https://support.microsoft.com/office/view-and-download-meeting-attendance-reports-in-teams-ae7cf170-530c-47d3-84c1-3aedac74d310?ui=en-US&#x26;rs=en-US&#x26;ad=US)。

## <a name="allow-users-to-schedule-webinars-using-powershell"></a>允许用户使用 PowerShell 计划网络研讨会

可以在 Windows PowerShell **Set-CsTeamsMeetingPolicy** cmdlet 中使用以下属性在 Teams 中设置 Webinars。

- AllowMeetingRegistration
- WhoCanRegister
- AllowPrivateMeetingScheduling

有关 cmdlet 的详细信息，请阅读 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 。

> [!NOTE]
> 在运行这些 cmdlet 之前，必须连接到 Microsoft Teams PowerShell。 有关详细信息，请参阅 [使用 Microsoft Teams PowerShell 管理 Teams](/microsoftteams/teams-powershell-managing-teams)。

### <a name="allow-users-to-schedule-webinars"></a>允许用户计划网络研讨会

只能将注册限制为组织中的用户，也可以向租户内部和外部的所有人开放注册。 默认情况下，为 **全局 (组织范围的默认)** 策略启用 **WhoCanRegister** 并将其设置为 **“每个人**”。 如果要关闭会议注册，请将 **AllowMeetingRegistration** 设置为 **False**。

> [!IMPORTANT]
> **AllowPrivateMeetingScheduling** 必须设置为 **True** 才能使 **AllowMeetingRegistration** 正常工作。

1. 启用会议注册

```powershell
Set-CsTeamsMeetingPolicy -AllowMeetingRegistration $True
```

2. 启用私人会议计划

```powershell
Set-CsTeamsMeetingPolicy -AllowPrivateMeetingScheduling $True
```

3. 配置谁可以注册网络研讨会

***仅* 允许组织中的用户注册网络研讨会**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister EveryoneInCompany
```

**若要允许任何人（包括匿名用户）注册网络研讨会，请运行：**

```powershell
Set-CsTeamsMeetingPolicy -WhoCanRegister Everyone
```

> [!CAUTION]
> 如果在会议设置中关闭匿名加入，则匿名用户无法加入网络研讨会。 若要了解详细信息并启用此设置，请参阅 [Teams 中的会议设置](meeting-settings-in-teams.md)。

### <a name="collect-meeting-attendance"></a>收集会议出席情况

**AllowEngagementReport** 参数允许你查看注册和参加网络研讨会的人员。 默认情况下，此策略处于打开状态。 若要将其关闭，请在 PowerShell 中运行以下命令：

```powershell
Set-CsTeamsMeetingPolicy -AllowEngagementReport Disabled
```

## <a name="configure-webinar-settings"></a>配置网络研讨会设置

为网络研讨会启用环境后，无需进一步管理管理员。 策略控制网络研讨会组织者显示的选项。

## <a name="related-topics"></a>相关主题

- [Teams 中的会议策略 - 常规](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy 文档](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Teams 教育版策略向导](easy-policy-setup-edu.md)
