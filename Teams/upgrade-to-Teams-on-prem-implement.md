---
title: 从 Skype for Business 内部部署升级到团队-Microsoft 团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 从 Skype for Business 升级到 Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533599"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>实现从 Skype for Business 升级到 &mdash; IT 管理员的团队

本文介绍如何实现升级。 本文是介绍 IT 管理员的升级概念和实现的第五个。  

- [概述](upgrade-to-teams-on-prem-overview.md)
- [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)
- [用于管理升级的工具](upgrade-to-teams-on-prem-tools.md)
- [具有 Skype for business 内部部署的组织的其他注意事项](upgrade-to-teams-on-prem-considerations.md)
-  (本文中**实施升级**) 
- [ (PSTN) 注意事项的公共交换电话网络](upgrade-to-teams-on-prem-pstn-considerations.md)

此外，以下文章介绍了重要的升级概念和共存行为：

- [团队和 Skype for business 的共存](upgrade-to-teams-on-prem-coexistence.md)
- [共存模式-参考](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 客户端体验和共存模式的一致性](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>升级选项

本部分介绍如何使用以下升级选项之一实现升级：

- [使用孤岛模式升级 (重叠功能) ](#overlapping-capabilities-upgrade-using-islands-mode)
- [尚未使用团队开始的组织的 "选择功能" 升级](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [已在孤岛模式下使用团队的组织的 "选择功能" 升级](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

如果需要有关这些选项的详细信息，请确保已阅读 [升级方法](upgrade-to-teams-on-prem-upgrade-methods.md)。

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>使用孤岛模式升级 (重叠功能) 

对于重叠功能升级选项：

- 如果您可以快速升级整个组织，请考虑此选项。  由于对最终用户运行两个客户端有潜在的风险，因此最好最大限度地减少用户必须在其中运行这两个客户端的时间段。 你应该确保你的用户知道运行这两个客户端。

- 此选项是现成模型，不需要管理员操作即可开始使用团队，除非分配 Microsoft 365 或 Office 365 许可证。 如果你的用户已有 Skype for Business Online，则你可能已在使用此模型。

- 在重叠的功能模式和移动到 TeamsOnly 时，可能会有挑战性。 由于升级用户仅通过团队进行通信，因此组织中与该用户通信的任何其他用户都必须使用团队。  如果你有尚未开始使用团队的用户，这些用户将暴露给缺失的消息。 此外，他们在 Skype for Business 中看不到 TeamsOnly 用户在线。 某些组织选择使用租户全局策略执行租户范围内的升级以避免这种情况，但需要前期计划以及等待所有用户都准备好升级。


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>尚未使用团队开始的组织的 "选择功能" 升级

如果你的组织还没有团队中的任何活动用户，第一步是将 TeamsUpgradePolicy 的默认租户范围策略设置为 Skype for Business 模式之一，例如 SfbWithTeamsCollab。  尚未开始使用团队的用户将不会注意到行为的任何差异。 但是，在租户级别设置此策略将使用户能够开始将用户升级到 TeamsOnly 模式，并确保已升级的用户仍可以与未升级的用户进行通信。  一旦你确定了你的试点用户，你可以将其升级到 TeamsOnly。  如果他们在本地，请使用 Move-csuser。 如果它们处于联机状态，只需使用 Grant-CsTeamsUpgradePolicy 将其分配 TeamsOnly 模式。 默认情况下，由这些用户安排的任何 Skype for Business 会议将迁移到团队。

下面是键命令：

1. 将租户范围的默认值设置为 mode SfbWithTeamsCollab，如下所示：

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

注释
 
- 你可以将租户范围内的策略设置为 SfbWithTeamsCollab，而不是将其设置为 SfbWithTeamsCollabAndMeetings。 这将导致所有用户在团队中安排所有新会议。
- `Move-CsUser` 是本地工具中的 cmdlet。 `MoveToTeams`切换器需要具有 skype for Business server 2019 或 skype for Business server 2015 和 CU8 或更高版本。 如果你使用的是以前的版本，你可以先将用户移动到 Skype for business Online，然后向该用户授予 TeamsOnly 模式。
- 默认情况下，当升级到 TeamsOnly 模式或分配 SfbWithTeamsCollabAndMeetings 模式时，Skype for business 会议将迁移到团队。  

下图显示了未事先使用团队的组织的 "选择功能" 升级的概念阶段。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。 在孤岛模式下的用户必须确保同时运行两个客户端。

![图表显示选择功能升级但不事先使用团队](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>已在孤岛模式下使用团队的组织的 "选择功能" 升级

如果您的组织中的某些用户在以孤岛模式使用团队，则您可能不希望删除现有用户的功能。 因此，在更改租户范围的策略之前，需要额外步骤。 解决方案是先将这些现有活动团队用户 "grandfather" 用户转换为孤岛模式，然后再将租户范围内的策略设置为 "SfbWithTeamsCollab"。  完成此操作后，你可以按照上面的步骤继续部署，但是你将有两组用户迁移到 TeamsOnly：团队中处于活动状态的用户将处于 "孤岛" 模式下，其余用户将处于 "SfbWithTeamsCollab" 模式。 你可以逐步将这些用户移动到 TeamsOnly 模式。

1. 查找团队中处于活动状态的用户，如下所示：

   1. 从 Microsoft 365 管理中心的左侧导航中，转到 "报表"，然后转到 "使用情况"。 
   2. 在 "选择报表" 下拉列表中，选择 "Microsoft 团队"，然后选择 "用户活动"。 这将提供已在团队中处于活动状态的用户的可导出表。 
   3. 单击 "导出"、"打开 Excel" 和 "筛选" 以仅显示团队中处于活动状态的用户。

2. 对于在步骤1中发现的每个活动团队用户，请在远程 PowerShell 中为其分配孤岛模式。 这允许你转到下一步，并确保不更改用户体验。  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 将租户范围内的策略设置为 SfbWithTeamsCollab：

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 将所选用户升级到 TeamsOnly 模式。 你可以选择在 "孤岛模式" 或 "SfbWithTeamsCollab" 模式下升级用户，但你可能希望首先优先于在孤岛模式下升级用户，以最大程度减少用户处于 "孤岛模式" 时可能出现的混淆的可能性。   

   对于驻留在 Skype for business Online 中的用户：  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   对于驻留在本地 Skype for business 服务器的用户：  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

下图显示了一个选择功能过渡的概念阶段，其中的 "开始" 中有活动的孤岛用户。 条形图的高度表示用户数。 在升级的任何阶段，所有用户都可以相互通信。  Skype for Business 用户使用互操作与 TeamsOnly 用户通信，反之亦然。 


![图中显示了在孤岛模式下与活动用户进行升级的 "选择功能"](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>相关链接

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md) 

[配置 Skype for Business 服务器与 Microsoft 365 或 Office 365 之间的混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[设置共存和升级设置](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[使用会议迁移服务 (MMS) ](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

