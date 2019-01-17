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
ms.openlocfilehash: cc1c20f87103dc91a317e58dac03389275b255f2
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694694"
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
若要启用团队中的**呼叫**选项卡用户需要具有 1:1 调用团队中启用并使用团队的客户端支持 1:1 团队呼叫。 若要了解如何管理中的团队呼叫 1:1，读取[设置 CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)。 若要了解哪些客户端支持呼叫，请阅读[限制和规格的 Microsoft 团队](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams)。

> [!NOTE]
> 目前，语音邮件将不可用呼叫选项卡中除非用户启用了 PSTN 呼叫。 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a>启用团队中的**拨号盘**的先决条件
若要启用团队中的**拔号盘**选项卡，并让用户发起和接收 PSTN 呼叫您需要设置用户的电话系统和调用计划。 若要了解如何设置调用计划，请阅读[Set up 调用计划](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans)。

> [!NOTE]
> 您可以使用直接路由允许您强制用户和接收 PSTN 呼叫。 若要了解如何设置直接路由，请阅读[配置直接路由](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure)。

## <a name="teams-interop-policy-configuration"></a>Teams 互操作性策略配置
若要启用团队以开始接收呼叫，您将需要更新团队升级策略和团队互操作性策略，使用[的 Microsoft 团队 & Skype 的业务管理中心](https://aka.ms/teamsadmincenter)或使用远程 Windows PowerShell 会话 Skype for Business [ `*-CsTeamsUpgradePolicy`和`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)cmdlet，以将重定向到团队呼叫。

有关升级团队的策略和团队互操作性策略的详细信息，请参阅[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)。

> [!TIP]
> 若要查找所需的 PowerShell cmdlet，键入"CsTeamsUpgradePolicy"或"CsTeamsInteropPolicy"的**筛选器**框中[的业务 PowerShell cmdlet 文档 Skype](https://docs.microsoft.com/powershell/module/skype)。

### <a name="default-teams-upgrade-and-interop-policies"></a>默认团队需要升级和互操作性策略
Teams 具有默认策略配置，旨在确保在部署 Teams 期间，现有业务工作流不会中断。 默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。 这可确保在你开始试点和部署 Teams 时，语音服务不会出现意外中断。

默认情况下升级策略保留在将服从团队互操作性策略，以确定要在其中聊天和呼叫的路由-的旧版模式的团队团队或 for Business 的 Skype。

> [!NOTE]
> 团队的行为升级策略和[迁移和组织使用团队一起 for Business 的 Skype 的互操作性指南](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)中所述，将发生更改团队互操作性策略

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
若要接收团队中的入站的 PSTN 呼叫，您需要通过应用与相应团队互操作性策略设置的团队升级策略调用应用程序的默认配置团队`CallingDefaultClient`团队参数。

> [!IMPORTANT]
> 我们建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置以利用 Teams 中这些令人兴奋的新通话功能。

如果您选择要继续使用旧的团队升级策略，则使用下面的预配置的团队互操作性策略路由到团队的入站的 PSTN 呼叫：

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

如果您选择使用更新的团队升级策略，您需要向用户分配 TeamsOnly 模式。

以上策略的行为如下：
* **对于现有 Skype for Business 客户**，此策略旨在将传入呼叫重定向至 Teams。 这包括 VoIP（来自 Teams 和 Skype for Business）和 PSTN 呼叫。 
* **对于没有 Skype for Business 的客户**，此策略生效后，PSTN 呼叫将在 Teams 中接听。

> [!WARNING]
> 当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。 传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。 请有关对现有认证的 SIP 电话支持的信息，参阅[Microsoft 365 路线图](https://aka.ms/O365Roadmap)。

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a>如何配置用户以接收 PSTN 呼叫的团队中
使用旧的团队升级策略时应用团队互操作性策略，如上述通过业务远程 Windows PowerShell 会话的 Skype 重定向到团队呼叫：

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

如果您选择使用 TeamsOnly 模式，您可以为 TeamsOnly 更改用户的共存模式，通过 Microsoft 团队 & Skype 的业务管理中心中，或通过业务远程 Windows PowerShell 会话的 Skype 重定向到团队呼叫：

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a>另请参阅
[设置通话套餐](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[Microsoft Teams 中具有通话套餐的电话系统实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/teams)
