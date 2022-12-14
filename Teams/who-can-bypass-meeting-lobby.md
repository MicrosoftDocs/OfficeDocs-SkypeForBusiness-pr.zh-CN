---
title: 控制谁可以绕过 Microsoft Teams 中的会议大厅
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何使用 Microsoft Teams 中的会议大厅，以仅允许某些会议参与者直接加入会议。
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392702"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>控制谁可以绕过 Microsoft Teams 中的会议大厅

Teams 会议大厅是一种防止某些类型的会议参与者加入会议的方法，直到会议组织者、共同组织者或演示者承认他们。 当参与者进入大厅时，组织者、共同组织者和演示者会收到通知，可以选择是否允许他们参加会议。

使用 Teams 管理中心中的大厅设置，可以为哪些类型的会议参与者能够绕过大厅创建默认值，哪些参与者必须在那里等待，直到获准加入会议。 可以控制以下类型的参与者如何与大厅交互：

- 会议组织者和共同组织者
- 组织中的人员
- 来宾
- 受信任组织中的人员
- 匿名参与者

加入会议的人员的身份由 Microsoft 365 进行验证，除非参与者是匿名的。 无法验证匿名参与者。

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>与组织外部人员会面的先决条件

Teams 中的多个设置控制组织外部人员是否可以与 Teams 交互。 组织外部人员必须启用以下设置才能加入会议：

- 必须启用 [Teams 中的来宾访问](guest-access.md)才能让来宾能够加入会议。
- 必须启用[外部访问](manage-external-access.md)才能让受信任组织中的人员加入会议。 必须配置组织与外部组织之间的相互信任，并且必须为组织中的会议组织者以及外部组织中的任何参与者启用外部访问。
- **两个匿名用户可以加入会议** 设置 (组织级别) 和会议策略 (为创建会议) 的组织者必须为 **“打开**”，以便匿名参与者加入会议。

如果关闭这些设置中的任何一个，则无论大厅设置如何，该类型的外部参与者都将无法加入会议。

## <a name="overview-of-lobby-settings-and-policies"></a>大厅设置和策略概述

下表显示了影响会议参与者与大厅交互方式的 Teams 会议策略。

|设置|说明|
|:------|:----------|
|**匿名用户和拨入呼叫者可以开始会议**|这是允许无领导会议的每个组织者策略。 此设置控制匿名参与者和拨入用户是否可以在没有已验证与会者的情况下加入会议。 此设置仅在 **“谁可以绕过大厅”** 设置为“ **每个人**”时适用。 如果 **“匿名用户可以加入会议** 组织”或“会议”设置为 **“关闭**”，则此设置仅适用于拨入呼叫者。 默认情况下，此设置处于关闭状态，以防止匿名用户可能滥用会议链接。 <br><br> **关闭** 时，匿名参与者和拨入用户将在大厅中等待，直到已验证的参与者 (包括拨入组织者) 加入会议，此时将自动允许他们加入会议。 会议开始后，匿名参与者和拨入用户将自动加入呼叫，即使组织者离开也是如此。 <br><br> 如果此设置设置为 **“打开**”，则匿名参与者和电话拨入参与者可以在没有已验证参与者的情况下开始并加入会议。|
|**人员拨入可以绕过大厅**|这是按组织者的策略。 此设置控制通过电话拨入的人员是直接加入会议还是在大厅中等待。 当此设置设置为 **“关闭**”时，拨入用户将在大厅中等待，直到组织者、共同组织者或演示者加入会议并接受他们。 当此设置设置为 **“打开**”时，拨入用户将自动加入会议，而无需通过大厅。  (如果 **匿名用户和拨入呼叫者可以启动会议** 为 **“关闭**”，他们将在大厅中等待，直到会议开始。) |
|**谁可以绕过大厅**|这是按组织者的策略。 此设置控制哪些参与者类型 (，但通过电话拨入) 直接加入会议的人员除外，以及哪些类型的参与者在大厅中等待，直到被组织者、共同组织者或演示者接纳。|

下表显示了 **“谁可以绕过大厅** ”策略的每个选项如何影响每 *种类型的会议参与者*。

|策略值：|所有人|我的组织中人员、受信任的组织和来宾|组织中用户和来宾|我的组织中的人员|仅受邀者|仅组织者和共同组织者|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*组织者和共同组织者*|旁路|旁路|旁路|旁路|旁路|旁路|
|*组织中的人员*|旁路|旁路|旁路|旁路|发送或转发邀请的人员将绕过;其他人在大厅中等待|大堂|
|*来宾*|旁路|旁路|旁路|大堂|发送或转发邀请的人员将绕过;其他人在大厅中等待|大堂|
|*受信任组织中的人员*|旁路|旁路|大堂|大堂|发送或转发邀请的人员将绕过;其他人在大厅中等待|大堂|
|*匿名参与者*|旁路|大堂|大堂|大堂|大堂|大堂|

**仅受邀者** 仅适用于已发送邀请或已向其转发邀请的已验证参与者。 作为通讯组的一部分添加的用户将在大厅中等待。

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>选择谁可以在组织主持的会议中绕过大厅

可以在 Teams 管理中心配置上述设置和策略。 有关在不同情况下要选择的设置的指导，请参阅以下部分。 有关会议策略工作原理的信息，请参阅[在 Microsoft Teams 中管理会议策略](/microsoftteams/meeting-policies-overview)。

> [!Important]
> 会议组织者可以更改你为 **拨入人员选择的默认值可以绕过大厅** 和 **谁可以绕过大厅** 设置。 如果需要对特定值强制实施这些设置，可以使用会议模板或敏感度标签 (Teams Premium 所需的) 。  有关详细信息，请参阅[为敏感会议配置 Microsoft Teams 会议大厅](configure-lobby-sensitive-meetings.md)。

设置会议加入和大厅策略
1. 在 Teams 管理中心中，展开 **“会议”** ，然后选择“ **会议策略**”。
1. 选择要更新的策略。
1. 在 **“参与者&来宾** ”部分中，更新要更改的设置：
   - **允许匿名人员加入会议**
   - **允许匿名用户启动会议**
   - **自动允许 (** 谁可以绕过大厅) 
   - **拨入用户可以绕过大厅**

    ![显示 Teams 管理中心中的会议加入和大厅策略的屏幕截图。](media/meeting-join-and-lobby-tac-settings.png)
1. 选择“**保存**”。

请注意，更改最长可能需要 24 小时才能生效。

如果要允许匿名会议访问，请确保 **“匿名用户可以加入会议** ”设置也已启用。

为匿名会议加入设置组织范围的会议设置
1. 在 Teams 管理中心中，展开 **“会议”** ，然后选择“ **会议设置**”。
1. 在 **“参与者** ”部分中，将 **“匿名用户可以加入会议** ”设置为 **“打开** ”或 **“关闭**”。
    ![显示 Teams 管理中心中的会议加入和大厅设置的屏幕截图。](media/anonymous-users-can-join-meetings-org-setting.png)
1. 选择“**保存**”。

## <a name="control-access-to-meetings-by-anonymous-participants"></a>控制匿名参与者对会议的访问权限

匿名参与者是匿名的，因为他们没有登录到可由 Microsoft 365 验证的帐户。 这可能包括：

- 未使用工作或学校帐户登录到 Microsoft 365 的人员 
-  (外部[访问](manage-external-access.md)) 中配置的不受信任的组织人员。
- 来自你信任但不信任你的组织的组织的人员

如果要阻止匿名参与者完全加入会议，可以关闭 **“匿名用户可以加入会议** 组织范围的会议”设置。 还可以通过使用匿名用户可以加入会议策略为特定会议组织者禁用 **匿名加入** 。

如果希望匿名加入的人员在大厅中等待，可以将 **“谁可以绕过大厅** 会议”策略设置为除 **“所有人**”之外的任何设置。  (此设置不会影响通过电话拨入的人员。) 

默认情况下， **匿名用户和拨入呼叫者可以启动会议** 策略为 **“关闭**”。 这意味着，如果已验证的参与者尚未开始会议，匿名参与者和通过电话呼叫的人员将始终在大厅中等待。 如果希望允许匿名参与者和通过电话呼叫的人员开始会议，建议你将其关闭，尽管你可以打开此设置。  启用此设置后，拥有未经验证帐户的人员可以开始会议，包括使用会议链接在计划外的时间举行会议。

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>控制通过电话拨入的人员对会议的访问权限

默认情况下，**拨入人员可以绕过大厅** 策略为 **“关闭**”，但会议组织者可以在设置会议时更改此设置。 可以通过更新 **人员拨入可以绕过大厅策略，** 或者可以使用会议模板强制实施特定值，从而更改默认值。

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>控制来宾和受信任组织中的人员对会议的访问权限

组织外部有两种类型的人员可以作为已验证的参与者加入会议：

- 来宾 - 组织中具有 [Azure Active Directory (Azure AD) B2B 协作帐户](/azure/active-directory/external-identities/what-is-b2b) 的人员
- 外部访问用户 - 在 Teams [外部访问](manage-external-access.md)中定义的受信任组织中具有 Azure AD 帐户的人员

如果希望组织外部的所有已验证会议参与者在大厅中等待，可以将“谁可以绕过大厅”策略设置为 **人员我的组织中**，或 **仅组织者和共同组织者** (，前提是来宾不是组织者或共同组织者) 。 如果只希望受信任组织中的人员 (外部访问用户) 在大厅中等待，则可以在 **我的组织和来宾中选择人员**。

## <a name="control-access-to-meetings-by-people-without-invitations"></a>控制不带邀请的人员对会议的访问权限

如果希望仅允许有邀请的人员直接加入会议，并让所有其他参与者在大厅中等待，请将 **“谁可以绕过大厅** ”设置为 **“仅受邀人员**”。 不包括通过通讯组列表邀请的 (人员。) 

**“仅受邀者**”设置包括邀请转发到的已验证参与者，而不仅仅是组织者直接邀请的参与者。 它不包括具有会议加入链接但不包含邀请本身和未经验证 (匿名) 参与者的人员。 他们必须在大厅等待。

请注意，如果会议组织者仅希望他们直接邀请的人员参加会议，则可以禁用转发会议邀请。

## <a name="control-access-to-meetings-by-non-organizers"></a>控制非组织者对会议的访问权限

如果你有共享敏感信息或受法规要求约束的会议，你可能希望让所有参与者在大厅中等待，直到会议组织者或共同组织者允许他们。 在这种情况下，可以将 **“谁可以绕过大厅”** 设置为 **“仅组织者和共同组织者**”。

由于 **谁可以绕过大厅** 仅设置会议组织者可以更改的默认值，因此，如果在此区域中有合规性要求，请考虑使用敏感度标签或会议模板强制实施值。 有关详细信息，请参阅[为敏感会议配置 Microsoft Teams 会议大厅](configure-lobby-sensitive-meetings.md)。

## <a name="set-meeting-policies-by-using-powershell"></a>使用 PowerShell 设置会议策略

可以通过使用以下参数使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) PowerShell cmdlet 来设置本文中所述的会议策略：

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) 以控制匿名用户是否可以加入会议
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) 控制通过电话拨入的人是否可以绕过大厅
- [-AutoAdmittedUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) ，用于控制谁可以绕过大厅

## <a name="related-topics"></a>相关主题

[在没有 Teams 帐户的情况下加入会议](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[使用 Microsoft Teams 管理中心配置组织范围的策略](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[外部参与者会收到“登录到 Teams 以加入或联系会议组织者”](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)
