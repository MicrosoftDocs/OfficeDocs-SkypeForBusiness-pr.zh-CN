---
title: 快速入门指南 - 配置呼叫计划
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 快速入门指南：在 Microsoft Teams 中配置呼叫计划，以便让一组用户正常运行。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7be6b946d174241467d2afa1b9d2e30f7946365c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398436"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐

本指南将帮助你启动并运行一组用户，以便他们可以在 Teams 中浏览呼叫计划。

阅读 2017 年 12 月 12 日发布的有关在 Teams 中调用计划的公告：[Intelligent Communications](https://aka.ms/ipyqus) 在 Teams

> [!NOTE]
> 我们建议，在此快速入门指南的同时，阅读电话系统套餐和FastTrack计划并[](calling-plan-landing-page.md)推动成功推出。[](https://aka.ms/cloudvoice)

通过添加呼叫计划-Microsoft 365 和 Office 365 功能，Skype for Business 现在可以使用 Teams 通过公用电话交换网 (PSTN) 拨打和接听电话呼叫，或者接听电话呼叫。

![显示"联系人"页面的屏幕截图Teams。](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在"呼叫"选项卡中 **启用**"呼叫"Teams
若要在 Teams  中启用"呼叫"选项卡，用户需要在 Teams 中启用 1：1 呼叫，并且使用支持 1：1 Teams呼叫的 Teams 客户端。 若要了解如何管理 1：1 Teams，请阅读 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。 若要了解哪些客户端支持呼叫，请阅读呼叫[限制和Microsoft Teams](./limits-specifications-teams.md)。

> [!NOTE]
> 目前，语音邮件在"呼叫"选项卡中不可用，除非为用户启用了 PSTN 呼叫。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在键盘中启用 **拨号盘** Teams
若要在"**拨号盘**"选项卡Teams并允许用户拨打和接听 PSTN 呼叫，需要为用户预配电话系统和呼叫计划。 若要了解如何设置呼叫计划，请阅读 [设置呼叫计划](./set-up-calling-plans.md)。
此外，对于Teams用户，必须确保在呼叫策略中启用了"允许Teams呼叫"。 有关详细信息[Teams，请参阅在Microsoft Teams管理中心期间](./manage-teams-skypeforbusiness-admin-center.md)管理管理员。
> [!NOTE]
> 您也可以使用直接路由来允许用户拨打和接听 PSTN 呼叫。 若要了解如何设置直接路由，请阅读 [配置直接路由](./direct-routing-configure.md)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制调用位置
为了控制传入 (和聊天) 进入 Teams 还是 Skype for Business，管理员使用 TeamsUpgradePolicy，使用 [Microsoft Teams](https://aka.ms/teamsadmincenter) 管理中心或使用与 Windows PowerShell 的远程 Windows PowerShell 会话[Skype for Business](/powershell/module/skype) cmdlet。


TeamsUpgradePolicy 的默认配置是"群岛模式"，该模式可确保现有业务工作流在部署期间不会Teams中断。 默认情况下，VoIP、PSTN 和用户的联合呼叫将继续路由到 Skype for Business，直到更新策略以启用入站呼叫到 Teams。  收件人在岛屿模式下时：

 - 源自该客户端的传入 VOIP Skype for Business始终位于接收方的 Skype for Business 客户端。
 - 如果发送方和接收方位于同一租户Teams，源自 Teams 的传入 VOIP 呼叫将登 *陆到该租户*。
 - 传入的联合 VOIP (来自哪个客户端) PSTN 呼叫始终位于接收者的客户端Skype for Business客户端。
 
为了确保传入的 VOIP 和 PSTN 呼叫始终进入用户的 Teams 客户端，将用户的共存模式更新为 TeamsOnly (这意味着，请为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。  有关共存模式和 TeamsUpgradePolicy 详细信息，请参阅迁移和互操作性[](./migration-interop-guidance-for-teams-with-skype.md)指南，了解将 Teams 与 Skype for Business

**说明**
 - Skype for Business IP 电话将接收呼叫，即使用户位于 TeamsOnly 模式。  
 - 已预配 电话系统 和呼叫计划许可证以用于 Skype for Business Online (（例如，已为其分配了 OnlineVoiceRoutingPolicy) 值）的用户将在 Teams 中启用"呼叫"选项卡，并且可以从 Teams 拨打出站 PSTN 呼叫，而无需管理员执行任何管理操作。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何将用户配置为在呼叫中接收所有传入的 VOIP 和 PSTN Teams
若要确保用户在 Teams 中收到所有传入的 VOIP 和 PSTN 呼叫，在 Microsoft Teams 管理中心中将用户的共存模式设置为 TeamsOnly，或使用 Skype for Business 远程 Windows PowerShell 会话更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另请参阅
[设置通话套餐](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[具有通话套餐的电话系统](calling-plan-landing-page.md)

[Skype for Business PowerShell cmdlet 参考](/powershell/module/skype)
