---
title: 快速入门指南 - 配置通话套餐
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: 有关在 Microsoft Teams 中配置呼叫计划的快速入门指南，以便可以启动和运行一组用户。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0ff6c85e337e2a3fe226347fc0b0ef68710d3d18
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789577"
---
# <a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐

本指南将帮助你启动和运行一组用户，以便他们可以在 Teams 中浏览通话套餐。

阅读 2017 年 12 月 12 日，Teams 中通话套餐的公告： [智能通信在 Teams 中调用下一步](https://aka.ms/ipyqus)

> [!NOTE]
> 建议与本快速入门指南并行阅读 [具有通话套餐](calling-plan-landing-page.md) 和 [FastTrack](https://aka.ms/cloudvoice) 的电话系统，以规划和推动成功推出。

通过添加由 Skype for Business 提供支持的 Microsoft 365 和 Office 365 功能，现在可以使用 Teams 通过公共交换电话网络 (PSTN) 来拨打或接听陆路电话和移动电话的电话。

![显示 Teams 中“联系人”页面的屏幕截图。](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在 Teams 中启用 **“呼叫”** 选项卡的先决条件
若要在 Teams 中启用 **“呼叫”** 选项卡，用户需要在 Teams 中启用 1：1 呼叫，并使用支持 1：1 Teams 呼叫的 Teams 客户端。 若要了解如何在 Teams 中管理 1：1 呼叫，请阅读 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。 若要了解哪些客户端支持呼叫，请阅读 [Microsoft Teams 的限制和规范](./limits-specifications-teams.md)。

> [!NOTE]
> 目前，语音邮件在“呼叫”选项卡中不可用，除非用户已启用 PSTN 调用。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>在 Teams 中启用 **Dial Pad** 的先决条件
若要在 Teams 中启用 **“拨号板”** 选项卡并允许用户拨打和接收 PSTN 呼叫，需要为用户预配电话系统和呼叫计划。 若要了解如何设置呼叫计划，请阅读 [“设置呼叫计划](./set-up-calling-plans.md)”。
此外，对于仅限 Teams 用户，必须确保在 Teams 呼叫策略中启用“允许专用呼叫”。 有关详细信息，请参阅在 [过渡到新的 Microsoft Teams 管理中心期间管理 Teams](./manage-teams-skypeforbusiness-admin-center.md) 。
> [!NOTE]
> 还可以使用直接路由来允许用户拨打和接收 PSTN 呼叫。 若要了解如何设置直接路由，请阅读“ [配置直接路由](./direct-routing-configure.md)”。

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a>使用 TeamsUpgradePolicy 控制调用土地的位置
若要控制传入呼叫是 (和聊天) 位于 Teams 中还是Skype for Business，管理员使用 TeamsUpgradePolicy，使用 [Microsoft Teams 管理中心](https://aka.ms/teamsadmincenter)或使用与 Skype for Business cmdlet 的远程[Windows PowerShell](/powershell/module/skype)会话。


TeamsUpgradePolicy 的默认配置是 Islands 模式，旨在确保在 Teams 部署期间不会中断现有业务工作流。 默认情况下，对用户的 VoIP、PSTN 和联合调用将继续路由到Skype for Business，直到更新策略以启用对 Teams 的入站呼叫。  当收件人处于岛模式时：

 - 源自Skype for Business的传入 VOIP 调用始终位于收件人的Skype for Business客户端中。
 - *如果发件人和接收方位于同一租户* 中，则源自 Teams 中的传入 VOIP 调用将登陆 Teams。
 - 传入联合 VOIP (无论哪个客户端) ，PSTN 调用始终位于收件人Skype for Business客户端中。
 
若要确保传入的 VOIP 和 PSTN 调用始终位于用户的 Teams 客户端中，请将用户的共存模式更新为 TeamsOnly (这意味着，为其分配 TeamsUpgradePolicy 的“UpgradeToTeams”实例。  有关共存模式和 TeamsUpgradePolicy 的详细信息，请参阅使用 [Teams 和 Skype for Business 的组织迁移和互操作性指南](./migration-interop-guidance-for-teams-with-skype.md)

**笔记**
 - Skype for Business IP 电话将接收呼叫，即使用户处于 TeamsOnly 模式。  
 - 已使用电话系统和呼叫计划许可证预配以用于Skype for Business联机 (的用户，例如，已为其分配了 OnlineVoiceRoutingPolicy) 值，将在 Teams 中启用“呼叫”选项卡，并且可以从 Teams 发出出站 PSTN 呼叫，而无需管理员执行任何管理操作。


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a>如何配置用户以接收 Teams 中所有传入的 VOIP 和 PSTN 调用
若要确保用户在 Teams 中接收所有传入的 VOIP 和 PSTN 调用，请在 Microsoft Teams 管理中心将用户的共存模式设置为 TeamsOnly，或使用Skype for Business远程Windows PowerShell会话更新 TeamsUpgradePolicy，如下所示：

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a>另请参阅
[设置通话套餐](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[具有通话套餐的电话系统](calling-plan-landing-page.md)

[Skype for Business PowerShell cmdlet 参考](/powershell/module/skype)
