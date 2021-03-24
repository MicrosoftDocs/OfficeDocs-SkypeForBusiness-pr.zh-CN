---
title: 迁移和互操作性 - Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解管理组织从 Skype for Business 过渡到 Teams 的基本概念。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.coexistence
- ms.teamsadmincenter.teamsupgrade.overview
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3a446213a5c10126b9ae42986fe2fa1986bc9e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098328"
---
# <a name="coexistence-modes---reference"></a>共存模式 - 参考

当组织从 Skype for Business 过渡到 Teams 时，共存模式为最终用户提供简单且可预测的体验。 对于迁移到 Teams 的组织，TeamsOnly 模式是每个用户的最终目标，尽管并非所有用户都需要同时分配 TeamsOnly (或任何) 模式。 在用户进入 TeamsOnly 模式之前，组织可以使用任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 以确保 TeamsOnly 用户与尚未登录的用户之间的通信可预测。

从技术角度来看，用户模式控制用户体验的几个方面：

- *传入路由*：Teams 或 Skype for Business (哪个客户端) 传入聊天和通话登陆？ 
- *状态* 发布：用户状态是否基于他们在 Teams 或 Skype for Business 中的活动向其他用户显示？ 
- *会议计划*：哪些服务用于安排新会议并确保 Outlook 中提供正确的加载项？ TeamsUpgradePolicy 不控制会议加入。 用户始终 *可以加入* 任何会议，无论是 Skype for Business 会议还是 Teams 会议。
- *客户端体验*：Teams 和/或 Skype for Business 客户端提供哪些功能？ 用户能否在 Teams 和 Skype for Business 中发起通话和聊天，或同时发起这两者？ Teams &频道体验是否可用？  

有关基于模式的路由和状态行为详细信息，请参阅 [与 Skype for Business 共存](./coexistence-chat-calls-presence.md)。

但是，从体验的角度来看，模式可以描述为定义以下项的体验：
- *聊天和通话*：用户使用哪个客户端？
- *会议计划*：用户是否将新会议安排为 Teams 或 Skype for Business 会议？
- *Teams 客户端中的协作功能的可用性*。 当用户& Skype for Business 时，Teams 频道和文件功能是否可用？

下面列出了这些模式。
</br>
</br>

|模式|通话和聊天|会议计划<sup>1</sup>|Teams & 频道|用例|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*在 Skype for Business Online 中需要主页*|Teams|Teams|是|正在升级的最终状态。 也是新租户的默认值。|
|Islands|任一|任一|是|默认配置。 允许单个用户并排评估这两个客户端。 聊天和通话可以登陆任一客户端，因此用户必须始终运行这两个客户端。 为了避免令人困惑或回归的 Skype for Business 体验，Skype for Business 将继续处理外部 (联合) 通信、PSTN 语音服务和语音应用程序、Office 集成和其他一些集成。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|是|"会议第一"。 主要面向本地组织，如果尚未准备好将呼叫转移到云，则他们可受益于 Teams 会议功能。|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|是|需要更严格管理控制的复杂组织的备用起点。|
|SfBOnly|Skype for Business|Skype for Business|否<sup>3</sup>|针对对数据控制有严格要求的组织的专用方案。 Teams 仅用于加入其他人安排的会议。|
||||||

</br>
</br>

**注意：**

<sup>1</sup> 无论是在 Teams 中 (Skype for Business) ，加入现有会议的能力都不受模式约束。 默认情况下，用户始终可以加入他们受邀参加的任何会议。

<sup>2</sup> 默认情况下，向单个用户分配 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 时，该用户计划用于将来的任何现有 Skype for Business 会议将转换为 Teams 会议。 如果需要，可以通过在授予 TeamsUpgradePolicy 时指定 ，或在 Teams 管理门户中取消选中复选框，将这些会议保留为 Skype for Business  `-MigrateMeetingsToTeams $false` 会议。 在租户范围内授予 TeamsUpgradePolicy 时，无法将会议从 Skype for Business 转换为 Teams。 

<sup>3</sup> 目前，Teams 无法禁用 Teams 和频道功能，因此目前仍保持启用状态。


## <a name="using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy

TeamsUpgradePolicy 公开两个关键属性：Mode 和 NotifySfbUsers。 
</br>
</br>

|参数|类型|允许的值</br> (以斜体显示) |说明|
|---|---|---|---|
|模式|枚举|*Islands*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|指示客户端应运行的模式。|
|NotifySfbUsers|Bool|*False* 或 true|指示是否显示 Skype for Business 客户端中的横幅，告知用户 Teams 即将替换 Skype for Business。 如果 Mode=TeamsOnly，这不能为 true。|
|||||

Teams 通过内置的只读策略提供 TeamsUpgradePolicy 的所有相关实例。 因此，只有 Get 和 Grant cmdlet 可用。 下面列出了内置实例。
</br>
</br>

|Identity |模式|NotifySfbUsers|
|---|---|---|
|Islands|Islands|False|
|IslandsWithNotify|Islands|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|全局</br>*Default*|Islands|False|
||||

这些策略实例可以授予单个用户，也可以基于租户范围授予。 例如：
- 若要将用户 ($SipAddress) Teams，请授予"UpgradeToTeams"实例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升级整个租户，请省略 grant 命令中的 identity 参数：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>使用 Skype for Business 模式时 Teams 客户端用户体验

如果用户位于任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 中，所有传入的聊天和呼叫将路由到用户的 Skype for Business 客户端。 为了避免最终用户混淆并确保正确的路由，当用户处于任何 Skype for Business 模式时，将自动禁用 Teams 客户端中的呼叫和聊天功能。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，Teams 中的会议计划会自动禁用，当用户处于 SfBWithTeamsCollabAndMeetings 模式时自动启用。 有关详细信息，请参阅 [Teams 客户端体验和共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)。

> [!Note] 
> - 在交付 Teams 和频道的自动强制执行之前，SfbOnly 和 SfBWithTeamsCollab 模式的行为相同。


## <a name="detailed-mode-descriptions"></a>详细模式说明
</br>
</br>

|模式|解释|
|---|---|
|**Islands**</br> (默认) |用户同时运行 Skype for Business 和 Teams。 此用户：</br><ul><li>可以在 Skype for Business 或 Teams 客户端中发起聊天和 VoIP 呼叫。 注意：在本地拥有 Skype for Business 的用户无法从 Teams 启动以联系其他 Skype for Business 用户，无论接收者的模式如何。<li>接收其他& Skype for Business 客户端在 Skype for Business 中发起的 VoIP 呼叫的聊天。<li>在 Teams 客户端&用户在 Teams 中发起 VoIP 呼叫时接收聊天（如果他们位于同一 *租户中*）。<li>接收由& Skype for Business 客户端中的其他用户在 Teams 中发起的 VoIP 呼叫的聊天（如果他们在联合租户  *中*）。 <li>具有 PSTN 功能，如下所述：<ul><li>当用户在本地的 Skype for Business 中企业语音，PSTN 呼叫始终在 Skype for Business 中发起和接收。<li>当用户位于 Skype for Business Online 上并且拥有 Microsoft Phone System 时，用户始终在 Skype for Business 中发起和接收 PSTN 呼叫：<ul><li>无论用户具有 Microsoft 呼叫计划，还是通过 Skype for Business Cloud Connector Edition 或 Skype for Business Server (混合语音本地部署连接到 PSTN 网络，) 。<li>**注意：在群岛模式下不支持电话系统直接路由。**</ul></ul><li>在 Skype for Business 中接收 Microsoft 呼叫队列和自动助理呼叫：<ul><li>在群岛模式下，分配给呼叫队列和自动助理的电话号码不能 **是电话** 系统直接路由号码。</ul></ul><li>可以在 Teams 或 Skype for Business (安排会议，并且将默认看到这两个) 。<li>可以加入任何 Skype for Business 或 Teams 会议;会议将在相应的客户端中打开。</ul>|
|**SfBOnly**|用户仅运行 Skype for Business。 此用户：</br><ul><li>只能从 Skype for Business 发起聊天和通话。<li>无论发起在何处，都可以在 Skype for Business 客户端中接收任何聊天/呼叫，除非发起者是在本地拥有 Skype for Business 的 Teams 用户。*<li> 只能安排 Skype for Business 会议，但可以加入 Skype for </br> \* Business 或 Teams 会议。* 不建议将群岛模式与本地用户结合使用，而不要与 SfBOnly 模式下的其他用户结合使用。 如果本地拥有 Skype for Business 的 Teams 用户发起与 SfBOnly 用户的通话或聊天，则 SfBOnly 用户不可访问，并收到错过的聊天或呼叫电子邮件。*|
|**SfBWithTeamsCollab**|用户同时运行 Skype for Business 和 Teams。 此用户：</br><ul><li>具有 SfBOnly 模式下用户的功能。<li>仅为组协作和频道 (Teams) ;聊天/通话/会议安排被禁用。</ul>|
|**SfBWithTeamsCollab </br> AndMeetings**|用户同时运行 Skype for Business 和 Teams。 此用户：<ul><li>具有 SfBOnly 模式下用户的聊天和通话功能。<li>已启用 Teams 进行组协作 (频道 - 包括频道对话) ;聊天和通话已禁用。<li>只能安排 Teams 会议，但可以加入 Skype for Business 或 Teams 会议。</ul>|
|**TeamsOnly**</br> (SfB Online 家庭版) |用户仅运行 Teams。 此用户：<ul><li>无论从何处启动，都可以在 Teams 客户端中接收任何聊天和通话。<li>只能从 Teams 发起聊天和通话。<li>只能在 Teams 中安排会议，但可以加入 Skype for Business 或 Teams 会议。<li>可以继续使用 Skype for Business IP 电话。<br><br>*在 Teams 采用饱和之前，不建议在群岛模式下将 TeamsOnly 模式与其他用户结合使用;也就是说，所有岛屿模式用户都主动使用和监视 Teams 和 Skype for Business 客户端。如果 TeamsOnly 用户发起与群岛用户的通话或聊天，该呼叫或聊天将登陆到群岛用户的 Teams 客户端;如果群岛用户不使用或监视 Teams，该用户将显示为脱机状态，并且 TeamsOnly 用户无法访问该用户。*</ul> |
|||




## <a name="related-topics"></a>相关主题

[与 Skype for Business 共存](./coexistence-chat-calls-presence.md)

[Teams 客户端体验和共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)