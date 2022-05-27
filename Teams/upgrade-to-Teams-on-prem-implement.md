---
title: IT 管理员的升级策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文面向 IT 管理员，介绍实现从Skype for Business升级到Teams的策略。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681733"
---
# <a name="upgrade-strategies-for-it-administrators"></a>IT 管理员的升级策略

![升级过程的阶段，重点是部署和实现阶段。](media/upgrade-banner-deployment.png "升级过程的阶段，重点是部署和实施阶段")

本文适用于想要实现从Skype for Business升级到Teams的 IT 管理员。

在实现升级之前，我们建议使用以下文章来描述重要的升级概念和共存行为：

- [了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>升级选项

本部分介绍如何使用以下升级选项之一实现升级：

- [使用 Islands 模式升级 (重叠功能) ](#overlapping-capabilities-upgrade-using-islands-mode)
- [对于尚未开始使用Teams的组织，选择功能升级](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [已在 Islands 模式下使用Teams的组织的选择功能升级](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

如果需要有关这些选项的详细信息，请确保已阅读“[选择从Skype for Business到Teams的升级旅程](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>使用 Islands 模式 (重叠功能升级) 

对于重叠功能升级选项：

- 如果可以快速升级整个组织，请考虑此选项。  由于运行这两个客户端的最终用户可能会产生混淆，因此最好尽量缩短用户必须运行这两个客户端的时间段。 应确保用户知道要运行这两个客户端。

- 此选项是现成的模型，除了分配Microsoft 365或Office 365许可证外，不需要管理员操作即可开始使用Teams。 如果用户已Skype for Business联机，则可能已在此模型中。

- 摆脱重叠的功能模式并迁移到 TeamsOnly 可能很有挑战性。 由于升级后的用户仅通过Teams进行通信，因此组织中与该用户通信的任何其他用户必须使用Teams。  如果你的用户尚未开始使用Teams，他们将暴露在缺失的消息中。 此外，他们不会在Skype for Business中看到 TeamsOnly 用户联机。 某些组织选择使用租户全局策略进行租户范围的升级以避免这种情况，但这需要预先规划，并等待所有用户都准备好升级。

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>对于尚未开始使用Teams的组织，选择功能升级

如果组织在Teams中没有任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为Skype for Business模式之一，例如 SfbWithTeamsCollab。  尚未开始使用Teams的用户不会注意到行为有任何差异。 但是，在租户级别设置此策略可以开始将用户升级到 TeamsOnly 模式，并确保升级后的用户仍可与非升级用户通信。  确定试点用户后，可以将其升级到 TeamsOnly。  如果它们在本地，请使用 Move-CsUser。 如果他们处于联机状态，只需使用 Grant-CsTeamsUpgradePolicy 为其分配 TeamsOnly 模式。 默认情况下，这些用户安排的任何Skype for Business会议都将迁移到Teams。

下面是关键命令：

1. 将租户范围的默认设置为模式 SfbWithTeamsCollab，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 将试点用户升级到 TeamsOnly，如下所示：

   - 对于处于联机状态的用户：

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - 对于本地用户：

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**备注**：

- 可以将其设置为 SfbWithTeamsCollab，而不是将租户范围的策略设置为 SfbWithTeamsCollabAndMeetings。 这会导致所有用户在Teams中安排所有新会议。
- 默认情况下，在升级到 TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，会将Skype for Business会议迁移到Teams。

> [!NOTE]
> 为准备即将停用 Skype for Business Online，Microsoft 简化了组织迁移到Teams的方式。 不再需要指定 `-MoveToTeams` 开关 `Move-CsUser` ，以将用户直接从本地直接移动到 TeamsOnly。 以前，如果未指定此开关，则用户将从本地Skype for Business Server托管转换为 Skype for Business Online，并且其模式保持不变。 现在，当用户从本地移动到云`Move-CsUser`时，用户会自动分配 TeamsOnly 模式，并且从本地的会议自动转换为Teams会议，就像是否实际指定了开关一样`-MoveToTeams switch had been specified`。 此行为适用于所有版本的 Skype For Business Server 和 Lync Server 2013 (，这些版本从未支持`-MoveToTeams`过) 。

下图显示了以前未使用Teams的组织选择功能升级的概念阶段。 条的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business用户使用互操作与 TeamsOnly 用户通信，反之亦然。 处于 Islands 模式的用户必须确保运行这两个客户端。

![显示未事先使用Teams的所选功能升级的示意图。](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>已在 Islands 模式下使用Teams的组织的选择功能升级

如果组织中的某些用户在 Islands 模式下积极使用Teams，你可能不想从现有用户中删除功能。 因此，在更改租户范围的策略之前，需要执行额外的步骤。 解决方案是在将租户范围策略设置为 SfbWithTeamsCollab 之前，将这些现有的活动Teams用户“祖父”到 Islands 模式。  完成此操作后，可以按上述方式继续部署，但是，你将拥有两组移动到 TeamsOnly 的用户：处于 Teams 中活动的用户将处于 Islands 模式，其余用户将处于 SfbWithTeamsCollab 模式。 可以逐步将这些用户移动到 TeamsOnly 模式。

1. 查找在Teams中处于活动状态的用户，如下所示：

   1. 从Microsoft 365 管理中心，在左侧导航中，转到“报表”，然后转到“使用情况”。
   2. 在“选择报表”下拉列表中，选择“Microsoft Teams”，然后选择“用户活动”。 这将提供在Teams中处于活动状态的用户的可导出表。
   3. 单击“导出”、“打开Excel”和“筛选器”，以仅显示处于Teams中活动的用户。

2. 对于步骤 1 中找到的每个活动Teams用户，请在远程 PowerShell 中为其分配 Islands 模式。 这允许你转到下一步，并确保不会更改用户体验。

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. 将租户范围的策略设置为 SfbWithTeamsCollab：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. 将所选用户升级到 TeamsOnly 模式。 可以选择在 Islands 模式或 SfbWithTeamsCollab 模式下升级用户，尽管你可能希望首先在 Islands 模式下优先升级用户，以最大程度地减少用户处于 Islands 模式时可能出现的混淆。

   对于在 Skype for Business Online 中居住的用户：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   对于本地Skype for Business Server的用户：

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

下图显示了选择功能转换的概念阶段，其中一开始有活动的 Islands 用户。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business用户使用互操作与 TeamsOnly 用户通信，反之亦然。

![显示在 Islands 模式下使用活动用户进行选择功能升级的关系图。](media/teams-upgrade-2.png)

## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
