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
description: 快速入门指南：在 Microsoft Teams 中配置呼叫计划，以便让一组用户正常运行。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0acdfe123a8cd92dab773f5de2e831782d82473273ad01b32847cb5052d7f6c7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299399"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐
==============================================================

本指南将帮助你启动并运行一组用户，以便他们可以在 Teams 中浏览呼叫Teams。

阅读 2017 年 12 月 12 日发布的有关在 Teams 中调用计划的[公告：Intelligent Communications](https://aka.ms/ipyqus)在 Teams

> [!NOTE]
> 建议在此快速入门指南的同时，阅读电话系统套餐和FastTrack计划，推动[](calling-plan-landing-page.md)成功推出。 [](https://aka.ms/cloudvoice)

通过添加呼叫计划-Microsoft 365 和 Office 365 功能（由 Skype for Business 支持）-你现在可以使用 Teams 通过公用电话交换网 (PSTN) 拨打和接听电话，或者从陆地电话和移动电话拨打和接听电话。

![显示"联系人"页面的屏幕截图Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在"通话"选项卡中 **启用**"呼叫"Teams
若要在Teams 中启用"呼叫"选项卡，用户需要在 Teams 中启用 1：1 呼叫，并且使用支持 1：1 Teams的 Teams 客户端。 若要了解如何在 Teams 中管理 1：1 Teams，请阅读[Set-CsTeamsCallingPolicy。](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 若要了解哪些客户端支持呼叫，请阅读客户端[Microsoft Teams。](./limits-specifications-teams.md)

> [!NOTE]
> 目前，语音邮件在"呼叫"选项卡中不可用，除非为用户启用了 PSTN 呼叫。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在键盘中启用 **拨号盘** Teams
若要启用"**拨号** 盘"选项卡Teams并允许用户拨打和接听 PSTN 呼叫，需要为用户预配电话系统呼叫计划。 若要了解如何设置呼叫计划，请阅读 [设置呼叫计划](./set-up-calling-plans.md)。
此外，对于Teams用户，必须确保在呼叫策略中启用了"允许Teams呼叫"。 有关详细信息[，Teams](./manage-teams-skypeforbusiness-admin-center.md)中心转换期间管理Microsoft Teams管理帐户。
> [!NOTE]
> 您也可以使用直接路由来允许用户拨打和接听 PSTN 呼叫。 若要了解如何设置直接路由，请阅读 [配置直接路由](./direct-routing-configure.md)。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制调用位置
为了控制传入呼叫 (和聊天) 是否进入 Teams 或 Skype for Business，管理员使用 TeamsUpgradePolicy，使用[Microsoft Teams](https://aka.ms/teamsadmincenter)管理中心或通过 Skype for Business cmdlet 使用远程[Windows PowerShell](/powershell/module/skype)会话。


TeamsUpgradePolicy 的默认配置是"群岛模式"，该模式可确保现有业务工作流在部署期间不会Teams中断。 默认情况下，VoIP、PSTN 和向用户的联合呼叫将继续路由到 Skype for Business，直到更新策略以启用到 Teams 的入站呼叫。  收件人在岛屿模式下时：

 - 源自该客户端的Skype for Business VOIP 呼叫始终位于接收者的 Skype for Business客户端。
 - 如果发送方和接收方位于同一Teams，源自 Teams 的传入 VOIP 呼叫将登 *陆到该租户*。
 - 传入的联合 VOIP (来自哪个客户端) PSTN 呼叫始终位于接收者的客户端Skype for Business客户端。
 
为了确保传入的 VOIP 和 PSTN 呼叫始终进入用户的 Teams 客户端，将用户的共存模式更新为 TeamsOnly (这意味着，请为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。  有关共存模式和 TeamsUpgradePolicy 详细信息，请参阅迁移[](./migration-interop-guidance-for-teams-with-skype.md)和互操作性指南，了解将 Teams 与 Skype for Business

**说明**
 - Skype for Business即使用户位于 TeamsOnly 模式下，IP 电话也将接收呼叫。  
 - 已预配 电话系统 和呼叫计划许可证以用于 Skype for Business Online (（例如，已为其分配值为 OnlineVoiceRoutingPolicy) ）的用户将在 Teams 中启用"呼叫"选项卡，并且可以从 Teams 拨打出站 PSTN 呼叫，而无需管理员执行任何管理操作。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何将用户配置为在呼叫中接收所有传入的 VOIP 和 PSTN Teams
若要确保用户在 Teams 中收到所有传入的 VOIP 和 PSTN 呼叫，在 Microsoft Teams 管理中心中将用户的共存模式设置为 TeamsOnly，或使用 Skype for Business 远程 Windows PowerShell 会话更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另请参阅
[设置通话套餐](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[具有通话套餐的电话系统](calling-plan-landing-page.md)

[Skype for BusinessPowerShell cmdlet 参考](/powershell/module/skype)