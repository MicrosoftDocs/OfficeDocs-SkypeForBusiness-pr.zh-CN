---
title: 快速入门指南 - 在 Microsoft Teams 中配置通话套餐
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille, crowe
search.appverid: MET150
description: 快速入门指南中的 Microsoft 团队配置呼叫计划。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd1e9484b522a657a92916815c1ae8940dcc2117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898520"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐
==============================================================

本指南将帮助您获取一组用户设置和运行以便他们可以浏览团队中调用计划。

读取的团队中调用计划的 2017 年 12 月 12，通知：[智能通信所需的下一步中团队调用](https://aka.ms/ipyqus)

> [!NOTE]
> 我们建议，本快速入门指南的同时，在您阅读[电话系统与调用计划](calling-plan-landing-page.md)和[FastTrack](https://aka.ms/cloudvoice)计划和驱动器成功推出。

通过添加调用计划-Office 365 功能由 for Business 的 Skype-您现在可以使用团队发起和接收电话呼叫或从园地行和通过公用电话交换网 (PSTN) 的移动电话。

![团队呼叫](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>启用团队中的**呼叫**选项卡的先决条件
若要启用团队中的**呼叫**选项卡用户需要具有 1:1 调用团队中启用并使用团队的客户端支持 1:1 团队呼叫。 若要了解如何管理中的团队呼叫 1:1，读取[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 若要了解哪些客户端支持呼叫，请阅读[限制和规格的 Microsoft 团队](https://docs.microsoft.com/microsoftteams/limits-specifications-teams)。

> [!NOTE]
> 目前，语音邮件将不可用呼叫选项卡中除非用户启用了 PSTN 呼叫。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>启用团队中的**拨号盘**的先决条件
若要启用团队中的**拔号盘**选项卡，并让用户发起和接收 PSTN 呼叫您需要设置用户的电话系统和调用计划。 若要了解如何设置调用计划，请阅读[Set up 调用计划](https://docs.microsoft.com/microsoftteams/set-up-calling-plans)。

> [!NOTE]
> 您可以使用直接路由要让用户发起和接收 PSTN 呼叫。 若要了解如何设置直接路由，请阅读[配置直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用控件呼叫位于其中 TeamsUpgradePolicy
若要控制传入呼叫 （以及聊天） 位于团队或 Skype for Business 中，管理员可以使用 TeamsUpgradePolicy，使用任一[Microsoft 团队管理中心](https://aka.ms/teamsadmincenter)或远程 Windows PowerShell 会话使用[Skype for Business](https://docs.microsoft.com/powershell/module/skype)cmdlet。


TeamsUpgradePolicy 的默认配置是群岛模式，旨在确保该工作流不会中断团队部署过程中的现有业务。 默认情况下，将继续 VoIP 和 PSTN 和联盟的用户呼叫之前更新策略以启用到团队的入站的呼叫路由至 for Business 的 Skype。  当收件人处于群岛模式中：

 - 传入的 VOIP 呼叫该中起源于的 Skype for Business 始终中收件人的 Skype 业务客户端的园地。
 - 传入 VOIP 呼叫的团队*的发送者和接收者是否位于同一租户*中的团队园地对源自。
 - 传入联盟 （无论哪些客户端发起） 的 VOIP 和 PSTN 呼叫始终在收件人的 Skype 园地 for Business 客户端。
 
若要确保传入 VOIP 和 PSTN 始终调用园地用户的工作组客户端中，更新用户的共存模式为 TeamsOnly （这意味着，将其分配"UpgradeToTeams"TeamsUpgradePolicy 实例。  在共存模式和 TeamsUpgradePolicy 的详细信息，请参阅[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

**NOTES**
 - 业务 IP 电话的 Skype 将接收呼叫，即使用户处于 TeamsOnly 模式。  
 - 业务联机 （例如他们已分配的值为 OnlineVoiceRoutingPolicy），会在工作组中启用呼叫选项卡并可将出站 PSTN 呼叫从已经设置与电话系统和调用计划用于 Skype 的许可证的用户没有管理员无需采取任何管理操作的团队。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何配置用户以接收所有传入的 VOIP 和 PSTN 呼叫的团队中
若要确保用户收到团队中的所有传入的 VOIP 和 PSTN 呼叫，将用户的共存模式设置为 TeamsOnly，在 Microsoft 团队管理中心，或使用业务远程 Windows PowerShell 会话的 Skype 更新 TeamsUpgradePolicy，如下所示：

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a>另请参阅
[设置通话套餐](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[调用计划的电话系统](calling-plan-landing-page.md)

[Skype 的业务 PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/skype)

