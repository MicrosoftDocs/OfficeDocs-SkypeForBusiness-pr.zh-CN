---
title: 在Teams中分配策略
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 了解在Microsoft Teams中为用户和组分配策略和策略包的不同方法。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 48d0e771f50379c548cc801d4f6a3c38bcc81f5e
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284087"
---
# <a name="assign-policies-in-teams--getting-started"></a>在Teams中分配策略 – 入门

作为管理员，可以使用策略来控制组织中用户可用的Teams功能。 例如，有调用策略、会议策略和消息传递策略，仅举几例。

组织具有具有独特需求的不同类型的用户。 创建和分配的自定义策略允许根据这些需求为不同的用户集定制策略设置。

若要轻松管理组织中的策略，Teams提供了多种方法来向用户分配策略。 通过批处理分配将策略直接分配给用户，或者直接分配给用户是其成员的组。 还可以使用策略包向组织中具有类似角色的用户分配策略的预设集合。 选择的选项取决于所管理的策略数以及要向其分配策略的用户数。 全局 (组织范围内的默认) 策略适用于组织中数量最多的用户。 只需将策略分配给那些需要专用策略的用户。

本文介绍可为用户分配策略的不同方式，以及何时使用策略的建议方案。

有关如何 **向用户和组分配策略** 的详细信息，请参阅 [向用户和组分配策略](assign-policies-users-and-groups.md)。 有关如何 **分配策略包** 的详细信息，请参阅 [分配策略包](assign-policy-packages.md)。

## <a name="which-policy-takes-precedence"></a>哪个策略优先？

用户对每个策略类型都有一个有效的策略。 用户有可能直接分配策略，也可以是分配了相同类型的策略的一个或多个组的成员。 在这些方案中，哪个策略优先？ 用户的有效策略是根据优先级规则确定的，如下所示。

如果直接为用户分配策略 (单独或通过批处理分配) ，则该策略优先。 在下面的视觉示例中，用户的有效策略是直接分配给用户的林肯广场会议策略。

![显示直接分配的策略优先级的示意图。](media/assign-policies-example-directly-assigned.png)

如果未直接为用户分配给定类型的策略，则分配给用户所属的组的策略优先。 如果用户是多个组的成员，则对给定策略类型具有最高 ([组分配排名](assign-policies-users-and-groups.md#group-assignment-ranking)) 的策略优先。

在此视觉示例中，用户的有效策略是 Exec Teams和 HD 策略，它相对于用户所属的其他组具有最高的分配排名，并且还分配了相同策略类型的策略。  

![显示从组继承的策略优先级的示意图。](media/assign-policies-example-group.png)

如果用户未直接分配策略或不是分配策略的任何组的成员，则用户将获取该策略类型的全局 (组织范围的默认) 策略。 下面是一个视觉示例。

![显示全局策略优先级的示意图。](media/assign-policies-example-global.png)

若要了解详细信息，请参阅 ([优先级规则](assign-policies-users-and-groups.md#precedence-rules)) 。

## <a name="ways-to-assign-policies"></a>分配策略的方法

下面概述了如何向用户分配策略，以及每个策略的建议方案。 选择链接以了解详细信息。

在将策略分配给单个用户或组之前，首先 [设置全局 (组织范围的默认) 策略](#set-the-global-policies) ，以便它们适用于组织中数量最多的用户。  设置全局策略后，只需将策略分配给那些需要专用策略的用户。

|执行此操作  |如果。。。  | 使用。。。
|---------|---------|----|
|[向单个用户分配策略](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | 你刚开始Teams，或者只需要向少数用户分配一个或几个策略。 |Teams PowerShell 模块中的Microsoft Teams管理中心或 PowerShell cmdlet
|[将策略分配给组](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |根据用户的组成员身份分配策略。 例如，将策略分配给安全组或通讯组列表中的所有用户。| Teams PowerShell 模块中的Microsoft Teams管理中心或 PowerShell cmdlet|
|[将策略分配给一批用户](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | 将策略分配给大型用户集。 例如，一次向组织中的数百或数千名用户分配策略。 |Teams PowerShell 模块中的Microsoft Teams管理中心或 PowerShell cmdlet|
|[向用户分配策略包](assign-policy-packages.md#assign-a-policy-package-to-users)  |将多个策略分配给组织中具有相同或相似角色的特定用户集。 例如，将教育 (教师) 策略包分配给学校中的教师，让他们能够完全访问聊天、通话和会议。 将教育 (中学生) 政策包分配给中学生，以限制某些功能，如私人呼叫。  |Teams PowerShell 模块中的Microsoft Teams管理中心或 PowerShell cmdlet|
|[将策略包分配给组。](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |将多个策略分配给组织中具有相同或相似角色的一组用户。 例如，将策略包分配给安全组或通讯组列表中的所有用户。 |Microsoft Teams管理中心 (即将在 Teams PowerShell 模块中) 或 PowerShell cmdlet|
|[将策略包分配给一批用户](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|将多个策略分配给组织中具有相同或相似角色的一批用户。 例如，使用批量分配将教育 (教师) 策略包分配给学校中的所有教师，使他们能够完全访问聊天、通话和会议。 将教育 (中学生) 政策包分配给一批中学生，以限制某些能力，如私人呼叫。|Teams PowerShell 模块中的 PowerShell cmdlet|

## <a name="set-the-global-policies"></a>设置全局策略

按照以下步骤为每个策略类型设置全局 (组织范围的默认) 策略。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 管理中心

1. 在Microsoft Teams管理中心的左侧导航中，转到要更新的策略类型的策略页。 例如，**Teams** >  **Teams** 策略、**MeetingsMeetings** >  策略、**消息传送策略** 或 **VoiceCalling** >  策略。
2. 选择 **全局 (组织范围的默认)** 策略以查看当前设置。
3. 根据需要更新策略，然后选择 **“应用**”。

![更新Teams管理中心的全局策略。](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>使用 PowerShell

若要使用 PowerShell 设置全局策略，请使用全局标识符。  首先，查看当前的全局策略以确定要更改的设置。

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

接下来，根据需要更新全局策略。  只需为要更改的设置指定值。

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>在活动日志中查看策略分配

将策略分配给Microsoft Teams管理中心中的用户时，可以在[活动日志](https://admin.teams.microsoft.com/activitylog)中查看这些策略分配的状态。 活动日志显示网络记录上传信息、来自Teams管理中心和 PowerShell 的组策略操作，以及过去 30 天内从Teams管理中心) 的 20 多名用户 (批处理策略操作。

![“活动日志”页的屏幕截图。](media/Activity_Log.png)

若要在活动日志中查看策略操作，请执行以下操作：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **仪表板**，然后在 **“活动日志**”下选择 **“查看详细信息**”。
2. 你将看到有关每个策略操作的以下信息：
    - **活动**：策略操作的名称。 例如： **组策略分配**
    - **组名称**：策略操作已完成的组的名称。
    - **策略类型**：策略的类型。
    - **策略名称**：策略操作的名称。 对于批处理策略分配，可以选择链接以查看更多详细信息。 这包括策略分配给的用户数以及已完成、正在进行且未启动的分配数。 你还将看到批处理中的用户列表，以及每个用户的状态和结果。
    - **提交者**：提交策略操作的用户的名称。
    - **提交日期**：提交策略操作的日期和时间。
    - **完成日期**：策略操作完成的日期和时间。
    - **受影响**：批处理或组中的用户数。
    - **总体状态**：策略操作的状态。 策略可以具有以下状态之一：
        - **未启动**：策略操作由管理员提交。
        - **正在进行**：策略操作已开始处理。
        - **向用户推出**：系统已开始向用户应用策略更新。
        - **已完成**：策略更新已应用所有用户。
        - **已完成并出现“x”错误**：策略操作已完成，但存在错误。

> [!NOTE]
> 还可以从 **“用户** ”页访问活动日志。 选择 **“应用** ”以提交批量策略分配后，页面顶部会显示横幅。 选择横幅中的 **活动日志** 链接。

## <a name="related-topics"></a>相关主题

- [将策略分配给用户和组](assign-policies-users-and-groups.md)
- [将策略包分配给用户和组](assign-policy-packages.md)
- [使用策略管理Teams](manage-teams-with-policies.md)
- [Teams PowerShell 概览](teams-powershell-overview.md)
