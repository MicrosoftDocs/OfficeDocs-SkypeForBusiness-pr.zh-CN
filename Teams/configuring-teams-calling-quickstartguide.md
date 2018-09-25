---
title: 快速入门指南 - 在 Microsoft Teams 中配置通话套餐
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: 有关在 Microsoft Teams 中配置通话套餐的快速入门指南。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a1fb82f57035f238ce222bf7f21b72983d21075
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015930"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐
==============================================================

本指南帮助你安排一组用户并使其能够进行操作，以便他们可以在 Teams 中使用通话套餐。

请参阅 2017 年 12 月 12 日 Teams 中的通话套餐公告：[Teams 中通话功能的下一个阶段是智能通信](https://aka.ms/ipyqus)

> [!NOTE]
> 我们建议你与此快速入门指南一起使用[实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)和 [FastTrack](https://aka.ms/cloudvoice) 来规划和推动成功的部署。

通过添加由 Skype for Business 提供技术支持的 Office 365 功能 - 通话套餐，现在可以使用 Teams 通过公用电话交换网 (PSTN) 向座机和手机拨打电话，也可以接听来自座机和手机的电话。

![在 Teams 中进行通话](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在 Teams 中启用 **“通话”** 选项卡的先决条件
要在 Teams 中启用 **“通话”** 选项卡，并允许你的用户拨打和接听 PSTN 呼叫，你需要为电话系统和通话套餐预配用户。 要了解如何对此进行设置，请参阅[设置通话套餐](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)。

## <a name="teams-interop-policy-configuration"></a>Teams 互操作性策略配置
要启用 Teams 以开始接听呼叫，需要使用 [Microsoft Teams 和 Skype for Business 管理中心](https://aka.ms/teamsadmincenter)或结合使用远程 Windows PowerShell 会话与 Skype for Business [`*-CsTeamsUpgradePolicy` 和 `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlet 来更新 Teams 升级策略和 Teams 互操作性策略以将呼叫重定向至 Teams。

有关 Teams 升级策略和 Teams 互操作性策略的详细信息，请参阅[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)。

> [!TIP]
> 要查找你所需的 PowerShell cmdlet，请在 [Skype for Business PowerShell cmdlet 文档](https://docs.microsoft.com/powershell/module/skype)中的 **“筛选”** 框中键入“CsTeamsUpgradePolicy”或“CsTeamsInteropPolicy”。

### <a name="default-teams-upgrade-and-interop-policies"></a>默认的 Teams 升级和互操作性策略
Teams 具有默认策略配置，旨在确保在部署 Teams 期间，现有业务工作流不会中断。 默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。 这可确保在你开始试点和部署 Teams 时，语音服务不会出现意外中断。

默认情况下，Teams 升级策略处于旧模式，以支持 Teams 互操作性策略确定聊天和通话的路由位置 - Teams 或 Skype for Business。

> [!NOTE]
> 按照[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)中所述，Teams 升级策略和 Teams 互操作性策略的行为不久将会更改。

Teams 互操作性策略具有以下默认配置：

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

默认配置的行为如下：
* **对于现有 Skype for Business 客户**，此策略旨在确保 Skype for Business 呼叫定向至 Skype for Business，Teams 呼叫定向至 Teams。 此策略生效后，PSTN 和联合呼叫将定向至 Skype for Business。
* **对于没有 Skype for Business 的客户**，此策略生效后，除了 Teams 用户之间的呼叫外，Teams 中将仅支持出站 PSTN 呼叫。 要在 Teams 接听 PSTN 呼叫，你需要更改为你的用户分配的 Teams 互操作性策略。

> [!NOTE]
> 对于预配了用于 Skype for Business Online 的电话系统和通话套餐许可证并且配置了默认全局 Teams 互操作性策略的用户，Teams 中将会启用“通话”选项卡，在无需管理员采取任何管理操作的情况下，他们可以从 Teams 进行出站 PSTN 呼叫。

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>配置 Teams 以接听入站 PSTN 呼叫
要在 Teams 中接听入站 PSTN 呼叫，需要应用 Teams 升级策略以及 `CallingDefaultClient` 参数设置为 Teams 的相应 Teams 互操作性策略，以将 Teams 配置为默认通话应用。

> [!IMPORTANT]
> 我们建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置以利用 Teams 中这些令人兴奋的新通话功能。

如果你选择继续使用旧的 Teams 升级策略，请使用以下预配置的 Teams 互操作性策略以将入站 PSTN 呼叫路由到 Teams：

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

如果你选择使用更新的 Teams 升级策略，则需要为用户分配 TeamsOnly 模式。

以上策略的行为如下：
* **对于现有 Skype for Business 客户**，此策略旨在将传入呼叫重定向至 Teams。 这包括 VoIP（来自 Teams 和 Skype for Business）和 PSTN 呼叫。 
* **对于没有 Skype for Business 的客户**，此策略生效后，将在 Teams 中接听 PSTN 呼叫。

> [!WARNING]
> 当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。 传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。 有关对现有的已认证 SIP 电话的支持的信息，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>如何配置用户以在 Teams 中接听 PSTN 通话
使用旧的 Teams 升级策略时，通过 Skype for Business 远程 Windows PowerShell 会话应用上文所述的 Teams 互操作性策略以将呼叫重定向至 Teams：

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

如果你选择使用 TeamsOnly 模式，可以通过 Microsoft Teams 和 Skype for Business 管理中心或通过 Skype for Business 远程 Windows PowerShell 会话将用户的共存模式更改为 TeamsOnly 以将呼叫重定向至 Teams：

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>另请参阅
[设置通话套餐](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Microsoft Teams 中具有通话套餐的电话系统实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/teams)
