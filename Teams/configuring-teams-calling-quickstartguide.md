---
title: "快速入门指南 - 在 Microsoft Teams 中配置通话套餐"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "有关在 Microsoft Teams 中配置通话套餐的快速入门指南。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e38317132190b3035f37509d1fa7b2da5e4785c7
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>快速入门指南：在 Microsoft Teams 中配置通话套餐
==============================================================

本指南帮助你安排一组用户并使其能够进行操作，以便他们可以在 Teams 中使用通话套餐。

请参阅 2017 年 12 月 12 日 Teams 中的通话套餐公告：[Teams 中通话功能的下一个阶段是智能通信](https://aka.ms/ipyqus)

> [!NOTE]
> 我们建议你与此快速入门指南一起使用[实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)和 [FastTrack](https://aka.ms/cloudvoice) 来规划和推动成功的部署。

通过添加由 Skype for Business 提供技术支持的 Office 365 功能 - 通话套餐，现在可以使用 Teams 通过公用电话交换网 (PSTN) 向座机和手机拨打电话，也可以接听来自座机和手机的电话。

![在 Teams 中进行通话](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>在 Teams 中启用**“通话”**选项卡的先决条件
要在 Teams 中启用**“通话”**选项卡，并允许你的用户拨打和接听 PSTN 呼叫，你需要为电话系统和通话套餐预配用户。 要了解如何对此进行设置，请参阅[设置通话套餐](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)。

> [!IMPORTANT]
> 在 Teams 中配置通话套餐之前，请注意以下限制：
> * **Teams 不支持混合语音** - Teams 当前不支持混合语音。 建议混合语音客户不要为了在 Teams 接听电话而更改任一策略，因为这会导致服务中断。
> * **Teams 不支持联合呼叫** - Teams 当前不支持联合呼叫（在租户/公司之间呼叫）。 在 Teams 中支持联合呼叫之前，它们会一直路由到 Skype for Business，无论你如何配置呼叫。

## <a name="teams-interop-policy-configuration"></a>Teams 互操作性策略配置
为了能够在 Teams 中开始接听呼叫，需要结合使用远程 Windows PowerShell 会话与 Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlet 来更新 Teams 互操作性策略，以将呼叫重定向至 Teams。 有关 Teams 互操作性策略的详细信息，请参阅 [Microsoft Teams 和 Skype for Business 互操作性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)。

> [!TIP]
> 要查找你所需的 PowerShell cmdlet，请在 [Skype for Business PowerShell cmdlet 文档](https://docs.microsoft.com/powershell/module/skype)中的**“筛选”**框中键入 "CsTeamsInteropPolicy"。

### <a name="default-teams-interop-policy"></a>默认 Teams 互操作性策略
Teams 具有默认策略配置，旨在确保在部署 Teams 期间，现有业务工作流不会中断。 默认情况下，向你的用户拨打的 VoIP、PSTN 和联合呼叫将仍路由至 Skype for Business，直到你更新策略以在 Teams 中启用入站通话。 这可确保在你开始试点和部署 Teams 时，语音服务不会出现意外中断。

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

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>如何配置 Teams 以使用默认策略
默认情况下，全局 Teams 互操作性策略应用于你的租户中的所有用户，且该策略配置有默认设置，如上文所述。 如果由于某种原因，你向你的用户授予了不同的策略，但希望恢复默认设置，则需要通过 Skype for Business 远程 Windows PowerShell 会话应用全局 Teams 互操作性策略：

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> 虽然可以修改全局 Teams 互操作性策略的默认值，但我们强烈建议不要这么做。 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>配置 Teams 以接听入站 PSTN 呼叫
要在 Teams 中接听入站 PSTN 呼叫，需要应用 `CallingDefaultClient` 参数设置为 Teams 的 Teams 互操作性策略，以将 Teams 配置为默认通话应用程序。

> [!IMPORTANT]
> 我们建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置以利用 Teams 中这些令人兴奋的新通话功能。

请考虑使用以下预配置的 Teams 互操作性策略以将入站 PSTN 呼叫路由至 Teams：

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

以上策略的行为如下：
* **对于现有 Skype for Business 客户**，此策略旨在将传入呼叫重定向至 Teams。 这包括 VoIP（来自 Teams 和 Skype for Business）和 PSTN 呼叫。 联合呼叫仍将在 Skype for Business 中接听。 
* **对于没有 Skype for Business 的客户**，此策略生效后，PSTN 呼叫将在 Teams 中接听。 Teams 当前**不支持**联合呼叫。

> [!WARNING]
> 当前，将 `CallingDefaultClient` 更改为 Teams 还将影响向 Skype for Business IP 电话拨打的呼叫。 传入呼叫不会在电话上接收，而只会使 Teams 客户端响铃。 有关对现有的已认证 SIP 电话的支持的信息，请参阅 [Skype for Business 到 Microsoft Teams 功能路线图](https://aka.ms/skype2teamsroadmap)。

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>如何配置 Teams 以接听 PSTN 呼叫
通过 Skype for Business 远程 Windows PowerShell 会话应用上文所述的 Teams 互操作性策略以将呼叫重定向至 Teams：

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>配置 Teams 以允许用户更改其首选通话体验
为了让用户自行决定首选通话体验（在 Teams 中还是在 Skype for Business 中接听呼叫），你需要创建启用 `AllowEndUserClientOverride` 参数的自定义 Teams 互操作性策略。

下面是用于支持用户选择首选通话体验的 Teams 互操作性策略示例：

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

向用户应用此自定义策略后，Teams 客户端中将提供用于更改首选通话应用程序的选项，以便用户自行进行更改。

![首选通话应用程序选项](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> 建议在进行较广范围或组织级别的更改之前，对一组初始用户应用此配置。

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>如何创建和应用自定义 Teams 互操作性策略
要通过 Skype for Business 远程 Windows PowerShell 会话创建上文所述的自定义 Teams 互操作性策略，请执行以下操作：

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>另请参阅
[设置通话套餐](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Microsoft Teams 和 Skype for Business 互操作性](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Microsoft Teams 中具有通话套餐的电话系统实践指导](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Skype for Business PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/skype)

[Teams PowerShell cmdlet 参考](https://docs.microsoft.com/powershell/module/teams)
