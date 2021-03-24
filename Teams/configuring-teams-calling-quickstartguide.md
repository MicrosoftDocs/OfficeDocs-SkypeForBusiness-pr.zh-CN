---
title: 快速入门指南 - 配置呼叫计划
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 有关在 Microsoft Teams 中配置呼叫计划以便让一组用户正常运行的快速入门指南。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101178"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐
==============================================================

本指南将帮助你启动并运行一组用户，以便他们可以浏览 Teams 中的通话计划。

阅读 2017 年 12 月 12 日 Teams 中的通话计划公告：Intelligent Communications 执行下一步， [在 Teams 中调用](https://aka.ms/ipyqus)

> [!NOTE]
> 我们建议，在此快速入门指南中同时阅读电话系统与通话计划和[](calling-plan-landing-page.md)[FastTrack，](https://aka.ms/cloudvoice)以计划和推动成功推出。

通过添加呼叫计划（由 Skype for Business 支持 Microsoft 365 和 Office 365 功能），你现在可以使用 Teams 通过公用电话交换网 (PSTN) 拨打和接听座机和移动电话的电话呼叫。

![显示 Teams 中的"联系人"页面的屏幕截图](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在 Teams 中启用"通话 **"** 选项卡的先决条件
若要在 Teams **中启用** "通话"选项卡，用户需要在 Teams 中启用 1：1 通话，并且使用支持 1 对 1 Teams 通话的 Teams 客户端。 若要了解如何在 Teams 中管理 1 对 1 通话，请阅读[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 若要了解哪些客户端支持呼叫，请阅读 [Microsoft Teams 的限制和规范](./limits-specifications-teams.md)。

> [!NOTE]
> 目前，语音邮件在"呼叫"选项卡中不可用，除非为用户启用了 PSTN 呼叫。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在 Teams 中启用 **拨号盘** 的先决条件
若要在 Teams 中启用" **拨号** 盘"选项卡并允许用户拨打和接听 PSTN 呼叫，需要为用户预配电话系统和呼叫计划。 若要了解如何设置呼叫计划，请阅读 [设置呼叫计划](./set-up-calling-plans.md)。
此外，对于仅 Teams 用户，必须确保 Teams 呼叫策略中已启用"允许私人通话"。 有关详细信息 [，请参阅在转换到新的 Microsoft Teams 管理中心期间](./manage-teams-skypeforbusiness-admin-center.md) 管理 Teams。
> [!NOTE]
> 您也可以使用直接路由来允许用户拨打和接听 PSTN 呼叫。 若要了解如何设置直接路由，请阅读 [配置直接路由](./direct-routing-configure.md)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制调用位置
为了控制传入呼叫 (和聊天) 是否进入 Teams 或 Skype for Business，管理员使用 TeamsUpgradePolicy，使用 [Microsoft Teams](https://aka.ms/teamsadmincenter) 管理中心或与 Skype for [Business](/powershell/module/skype) cmdlet 进行远程 Windows PowerShell 会话。


TeamsUpgradePolicy 的默认配置是"群岛模式"，目的是确保现有业务工作流在 Teams 部署期间不会中断。 默认情况下，VoIP、PSTN 和针对用户的联合呼叫将继续路由到 Skype for Business，直到你更新策略以启用对 Teams 的入站呼叫。  收件人在岛屿模式下时：

 - 源自 Skype for Business 的传入 VOIP 呼叫始终位于接收者的 Skype for Business 客户端中。
 - 如果发送方和接收方位于同一租户中，源自 Teams 的传入 VOIP 呼叫将登陆 *Teams。*
 - 传入的联合 VOIP (来自哪个客户端) PSTN 呼叫始终位于接收者的 Skype for Business 客户端中。
 
若要确保传入的 VOIP 和 PSTN 呼叫始终进入用户的 Teams 客户端，请更新用户的共存模式，将其更新为 TeamsOnly (这意味着，为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。  有关共存模式和 TeamsUpgradePolicy 详细信息，请参阅将 Teams 与 Skype for Business 一起使用 [组织的迁移和互操作性指南](./migration-interop-guidance-for-teams-with-skype.md)

**说明**
 - Skype for Business IP 电话将接收呼叫，即使用户位于 TeamsOnly 模式。  
 - 已预配了电话系统和呼叫计划许可证以用于 Skype for Business Online (例如，已为其分配了 OnlineVoiceRoutingPolicy) 的值的用户将在 Teams 中启用"呼叫"选项卡，并且无需管理员执行任何管理操作即可从 Teams 拨打出站 PSTN 呼叫。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何将用户配置为在 Teams 中接收所有传入的 VOIP 和 PSTN 呼叫
若要确保用户收到 Teams 中所有传入的 VOIP 和 PSTN 呼叫，在 Microsoft Teams 管理中心将用户的共存模式设置为 TeamsOnly，或使用 Skype for Business 远程 Windows PowerShell 会话更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另请参阅
[设置通话套餐](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[具有通话套餐的电话系统](calling-plan-landing-page.md)

[Skype for Business PowerShell cmdlet 参考](/powershell/module/skype)