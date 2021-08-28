---
title: 适用于 IT 管理员的升级策略
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 本文适用于 IT 管理员，并介绍了实现从本地到 Skype for Business Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c44d988bdcfbd08f462a99c76b4095bb01ac60c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619338"
---
# <a name="upgrade-strategies-for-it-administrators"></a>适用于 IT 管理员的升级策略

![升级旅程的阶段，着重强调部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")

本文适用于想要从公司升级到 Teams 的 IT Skype for Business。

在实施升级之前，我们建议阅读以下文章，其中介绍了重要的升级概念和共存行为：

- [了解 Microsoft Teams 和 Skype for Business 的共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [共存模式 - 参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>升级选项

本部分介绍如何使用下列升级选项之一实现升级：

- [使用群岛模式 (重叠功能升级) ](#overlapping-capabilities-upgrade-using-islands-mode)
- [为尚未开始使用 Teams 的组织选择功能Teams](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [为已在群岛模式下使用Teams选择功能升级](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

如果需要有关选项的详细信息，请确保已阅读选择从 Skype for Business 到[Teams 的升级Teams。](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>使用群岛模式 (重叠功能升级) 

对于重叠功能升级选项：

- 如果可以针对整个组织执行快速升级，请考虑使用此选项。  由于运行这两个客户端的最终用户存在混淆的潜在风险，因此最好尽量减少用户必须运行这两个客户端的时间段。 应确保用户知道运行这两个客户端。

- 此选项是开箱即用模型，不需要管理员操作来开始使用 Teams，Microsoft 365 或 Office 365 许可证。 如果用户已拥有 Skype for Business Online，则您可能已在此模型中。

- 从重叠的功能模式迁移到 TeamsOnly 可能很有难度。 由于升级后的用户仅Teams通信，因此组织中与该用户通信的其他任何用户都必须使用Teams。  如果用户尚未开始使用 Teams，则他们可能会丢失消息。 此外，他们将不会看到 TeamsOnly 用户在 Skype for Business。 某些组织选择使用租户全局策略进行租户级升级以避免这种情况，但是，这需要提前规划，并等待所有用户准备好升级。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>为尚未开始使用 Teams 的组织选择功能升级

如果组织在 Teams 中没有任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为 Skype for Business 模式之一，例如 SfbWithTeamsCollab。  尚未开始使用应用Teams不会注意到任何行为差异。 但是，在租户级别设置此策略可以开始将用户升级到 TeamsOnly 模式，并确保升级的用户仍可以与非升级的用户通信。  确定试点用户后，可将其升级到 TeamsOnly。  如果它们位于本地，请使用 Move-CsUser。 如果他们在线，只需使用 Grant-CsTeamsUpgradePolicy 为其分配 TeamsOnly 模式。 默认情况下，这些Skype for Business安排的任何会议都将迁移到Teams。

下面是关键命令：

1. 将租户范围的默认值设置为 SfbWithTeamsCollab 模式，如下所示：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 将试点用户升级到 TeamsOnly，如下所示：

   - 对于联机用户：

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 对于本地用户：

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

注释
 
- 可以设置为 SfbWithTeamsCollabAndMeetings，而不是将租户范围策略设置为 SfbWithTeamsCollabAndMeetings。 这会导致所有用户在会议中安排所有新Teams。
- 默认情况下，Skype for Business TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，Teams会议迁移到其他会议。  

> [!NOTE]
> 为准备即将停用 Skype for Business Online，Microsoft 简化了组织转移到Teams。 不再需要指定 中的开关，直接将用户从本地 `-MoveToTeams` `Move-CsUser` 移动到 TeamsOnly。 以前，如果未指定此开关，则用户从本地Skype for Business Server到 Skype for Business Online，其模式保持不变。 现在，使用 将用户从本地移动到云时，系统会自动为用户分配 TeamsOnly 模式，并且其会议从本地自动转换为 Teams 会议，就像 ， 而不考虑是否实际指定了开关一样。 `Move-CsUser` `-MoveToTeams switch had been specified` 此行为适用于从未支持 Skype For Business Server 和 Lync Server 2013 (的所有 `-MoveToTeams` 版本) 。

下图显示了组织选择功能升级的概念性阶段，无需事先使用Teams。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business使用互操作与 TeamsOnly 用户通信，反之亦然。 位于群岛模式的用户必须确保运行这两个客户端。

![显示选择功能升级的示意图，其中未事先使用Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>为已在群岛模式下使用Teams选择功能升级

如果组织中的某些用户正在以Teams模式主动使用云，则你可能不希望删除现有用户的功能。 因此，在更改租户范围策略之前，需要执行额外的步骤。 解决方法是在将租户范围策略设置为 SfbWithTeamsCollab 之前，Teams现有活动用户"加入群岛模式"。  完成上述部署后，可以继续部署，但是，你将有两组用户迁移到 TeamsOnly：在 Teams 中处于活动状态的用户将位于群岛模式，其余用户将位于 SfbWithTeamsCollab 模式下。 可以逐步将这些用户移动到 TeamsOnly 模式。

1. 按如下所示查找Teams活动的用户：

   1. 在Microsoft 365 管理中心导航栏中，转到"报表"，然后转到"使用情况"。 
   2. 在"选择报表"下拉列表中，选择"Microsoft Teams"，然后选择"用户活动"。 这会提供已在 Teams 中处于活动状态的用户的可导出Teams。 
   3. 单击"导出Excel打开"，然后进行筛选，以仅显示当前在 Teams。

2. 对于在步骤 1 Teams活动用户，在远程 PowerShell 中为其分配"群岛模式"。 这样，你可以转到下一步，并确保不会更改用户体验。  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 将租户范围策略设置为 SfbWithTeamsCollab：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 将所选用户升级到 TeamsOnly 模式。 可以选择在群岛模式或 SfbWithTeamsCollab 模式下升级用户，尽管你可能希望首先优先升级在群岛模式下的用户，以尽量减少在用户进入群岛模式时可能出现的混淆。   

   对于在 Skype for Business Online 中的用户：  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   对于本地Skype for Business Server用户：  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下图显示了一些选择功能过渡的概念阶段，其中一开始有活跃的群岛用户。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business使用互操作与 TeamsOnly 用户通信，反之亦然。 


![显示以岛屿模式活动用户进行选择功能升级的示意图](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business Server 与 Microsoft 365 或 Office 365 之间的混合连接](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
