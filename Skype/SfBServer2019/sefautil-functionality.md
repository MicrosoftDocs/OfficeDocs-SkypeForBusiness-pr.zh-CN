---
title: 在 Skype for Business Server 2019 中支持在 PowerShell 中使用 SEFAUtil 功能
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：了解如何在安装累积更新 1 后，使用 PowerShell 在 Skype for Business Server 2019 中获取 SEFAUtil 功能。
ms.openlocfilehash: d97dd84a3d05cf18752e40dd73a8c5f7e9752d3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120503"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="d7239-103">在 Skype for Business Server 2019 中通过 PowerShell 使用 SEFAUtil 功能</span><span class="sxs-lookup"><span data-stu-id="d7239-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="d7239-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing， call-forwarding， and Group Call Pickup settings on behalf of a Skype for Business Server user.</span><span class="sxs-lookup"><span data-stu-id="d7239-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="d7239-105">此工具还允许管理员查询为特定用户发布的呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="d7239-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="d7239-106">安装 Skype for Business Server 2019 7 月累积更新后，当前仅能通过 SEFAUtil 管理的以下功能也可通过 PowerShell 进行管理：</span><span class="sxs-lookup"><span data-stu-id="d7239-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="d7239-107">呼叫转发设置</span><span class="sxs-lookup"><span data-stu-id="d7239-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="d7239-108">委派设置</span><span class="sxs-lookup"><span data-stu-id="d7239-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="d7239-109">团队成员和相关设置</span><span class="sxs-lookup"><span data-stu-id="d7239-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="d7239-110">呼叫转发设置</span><span class="sxs-lookup"><span data-stu-id="d7239-110">Call forwarding settings</span></span>

<span data-ttu-id="d7239-111">管理员可以在 PowerShell 中通过以下 cmdlet 更改呼叫转发设置：</span><span class="sxs-lookup"><span data-stu-id="d7239-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="d7239-112">此 cmdlet 将指定用户的呼叫转发设置作为对象返回，并在屏幕上显示相同的设置。</span><span class="sxs-lookup"><span data-stu-id="d7239-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="d7239-113">此 cmdlet 可修改指定用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="d7239-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="d7239-114">此 cmdlet 将指定用户的呼叫转发设置作为对象返回，如果成功，则在屏幕上显示相同的设置。</span><span class="sxs-lookup"><span data-stu-id="d7239-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="d7239-115">如果失败，将显示相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d7239-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="d7239-116">此 cmdlet 可禁用用户的呼叫转发设置， (此处显示了两个不同的参数) 。</span><span class="sxs-lookup"><span data-stu-id="d7239-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="d7239-117">此 cmdlet 可修改用户的呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="d7239-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="d7239-118">此 cmdlet 使用两个参数示例再次 (SimulRing 设置，一个针对语音邮件未ansanswered，另一个未ansanswered to other) 。</span><span class="sxs-lookup"><span data-stu-id="d7239-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="d7239-119">委派设置</span><span class="sxs-lookup"><span data-stu-id="d7239-119">Delegation settings</span></span>

<span data-ttu-id="d7239-120">管理员可以在 PowerShell 中通过以下 cmdlet 更改委派设置：</span><span class="sxs-lookup"><span data-stu-id="d7239-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="d7239-121">此 cmdlet 返回委派列表的对象，并显示指定用户的委派列表（如果成功）。</span><span class="sxs-lookup"><span data-stu-id="d7239-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="d7239-122">如果失败，将显示相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d7239-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="d7239-123">此 cmdlet 可修改指定用户的委派设置，返回委派列表的对象并显示委派列表（如果成功）。</span><span class="sxs-lookup"><span data-stu-id="d7239-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="d7239-124">如果失败，将显示相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d7239-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="d7239-125">此 cmdlet 可添加或删除代理。</span><span class="sxs-lookup"><span data-stu-id="d7239-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="d7239-126">此 cmdlet 将委派列表设置到特定代理。</span><span class="sxs-lookup"><span data-stu-id="d7239-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="d7239-127">团队成员和相关设置</span><span class="sxs-lookup"><span data-stu-id="d7239-127">Team members and related settings</span></span>

<span data-ttu-id="d7239-128">管理员可以在 PowerShell 中通过以下 cmdlet 更改团队成员和相关设置：</span><span class="sxs-lookup"><span data-stu-id="d7239-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="d7239-129">此 cmdlet 返回包含团队成员列表的对象，如果成功，则在屏幕上显示该对象。</span><span class="sxs-lookup"><span data-stu-id="d7239-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="d7239-130">如果失败，将显示相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d7239-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="d7239-131">此 cmdlet 可修改指定用户的团队成员列表，返回一个包含团队成员列表的对象，如果成功，则在屏幕上显示该对象。</span><span class="sxs-lookup"><span data-stu-id="d7239-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="d7239-132">如果失败，将显示相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d7239-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="d7239-133">此 cmdlet 可添加或删除团队成员。</span><span class="sxs-lookup"><span data-stu-id="d7239-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="d7239-134">此 cmdlet 将团队列表设置给特定成员。</span><span class="sxs-lookup"><span data-stu-id="d7239-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="d7239-135">更多信息</span><span class="sxs-lookup"><span data-stu-id="d7239-135">More information</span></span>

<span data-ttu-id="d7239-136">对于本地部署，根据下面指定的访问级别，此功能中引入的 cmdlet 只能由以下各组的成员运行：</span><span class="sxs-lookup"><span data-stu-id="d7239-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="d7239-137">CsAdministrator – 获取和设置所有 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7239-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="d7239-138">CsVoiceAdministrator - 获取和设置所有 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7239-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="d7239-139">CsHelpDesk - 获取所有 cmdlet</span><span class="sxs-lookup"><span data-stu-id="d7239-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="d7239-140">有关这些管理员角色详细信息，请参阅创建 [Skype for Business Server 控制面板管理员](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md)。</span><span class="sxs-lookup"><span data-stu-id="d7239-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="d7239-141">管理员可以直接或远程登录到服务器计算机来访问这些 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d7239-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="d7239-142">对于混合部署，Skype for Business 管理员应能够调用所有 cmdlet 的 Get 和 Set。</span><span class="sxs-lookup"><span data-stu-id="d7239-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="d7239-143">有关角色的完整列表详细信息，请参阅关于 [管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="d7239-143">For more information about the full list of roles, see [About admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

> [!NOTE]
> <span data-ttu-id="d7239-144">必须启用服务器自动发现。</span><span class="sxs-lookup"><span data-stu-id="d7239-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="d7239-145">不会引入其他许可要求来使用 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d7239-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>