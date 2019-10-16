---
title: 快速入门指南 - 在 Microsoft Teams 中配置通话套餐
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: 有关在 Microsoft 团队中配置呼叫计划的快速入门指南。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87670ea398150e4895f2d87ccc48f60aba2d1377
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516477"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐
==============================================================

本指南将帮助您获取并运行一组用户，以便他们可以浏览团队中的呼叫计划。

阅读2017年12月12日，发布团队中的通话计划：[智能通信在团队中进行下一步通话](https://aka.ms/ipyqus)

> [!NOTE]
> 我们建议，与本快速入门指南并行，[使用通话计划](calling-plan-landing-page.md)和[FastTrack](https://aka.ms/cloudvoice)阅读电话系统以规划和推动成功的推出。

通过添加呼叫计划-Skype for Business 支持的 Office 365 功能-您现在可以使用团队通过公共交换电话网络（PSTN）拨打和接收来自土地线路和移动电话的电话呼叫。

![显示团队中的联系人页面的屏幕截图](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>启用团队中的 "**调用**" 选项卡的先决条件
若要启用团队中的 "**通话**" 选项卡，用户需要在团队中启用1:1 通话并使用支持1:1 团队通话的团队客户端。 若要了解如何在团队中管理1:1 通话，请参阅[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 若要了解哪些客户端支持呼叫，请阅读[Microsoft 团队的限制和规范](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)。

> [!NOTE]
> 目前，语音邮件将在 "通话" 选项卡中不可用，除非用户已启用 PSTN 呼叫。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>启用团队中的**拨号键盘**的先决条件
若要启用团队中的 "**拨号盘**" 选项卡并允许用户拨打和接收 PSTN 呼叫，您需要为用户预配电话系统和通话计划。 若要了解如何设置通话计划，请参阅[设置通话计划](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)。

> [!NOTE]
> 您还可以使用直接路由允许用户拨打和接收 PSTN 呼叫。 若要了解如何设置直接路由，请参阅[配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制呼叫所在的位置
若要控制团队或 Skype for business 中的传入呼叫（和聊天）领域，管理员是否使用[Microsoft 团队管理中心](https://aka.ms/teamsadmincenter)或使用与[Skype for](https://docs.microsoft.com/powershell/module/skype) Business 的远程 Windows PowerShell 会话使用 TeamsUpgradePolicypowershell.


TeamsUpgradePolicy 的默认配置为 "孤岛" 模式，它旨在确保现有业务工作流在团队部署期间不会中断。 默认情况下，对你的用户的 VoIP、PSTN 和联合呼叫将继续路由到 Skype for business，直到你更新策略以启用到团队的入站呼叫。  当收件人处于 "孤岛" 模式时：

 - 在 Skype for Business 中发起的 VOIP 呼叫始终位于接收方的 Skype for business 客户端中。
 - *如果发件人和接收方位于同一个租户*中，则为团队中的团队土地发起的 VOIP 呼叫。
 - 传入的联合 VOIP （无论发起哪种客户端）和 PSTN 呼叫始终位于接收方的 Skype for business 客户端中。
 
若要确保传入 VOIP 和 PSTN 呼叫始终位于用户的团队客户端，请将用户的共存模式更新为 TeamsOnly （这意味着，为他们分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例。  有关共存模式和 TeamsUpgradePolicy 的详细信息，请参阅[使用团队与 Skype For business 一起使用的组织的迁移和互操作指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**笔记**
 - Skype for Business IP 手机将接收呼叫，即使用户处于 TeamsOnly 模式。  
 - 已使用手机系统和通话计划许可证（如已为 Skype for Business Online）使用的用户（如已分配了 OnlineVoiceRoutingPolicy 的值）将在团队中启用 "呼叫" 选项卡，并且可以将出站 PSTN 呼叫从无需管理员执行任何管理操作的团队。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何配置用户以接收团队中的所有传入 VOIP 和 PSTN 呼叫
为确保用户收到团队中所有传入的 VOIP 和 PSTN 呼叫，请将用户的共存模式设置为 Microsoft 团队管理中心中的 TeamsOnly，或使用 Skype for Business 远程 Windows PowerShell 会话更新 TeamsUpgradePolicy，如下所示：

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>另请参阅
[设置通话套餐](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[具有通话套餐的电话系统](calling-plan-landing-page.md)

[Skype for Business PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/skype)

