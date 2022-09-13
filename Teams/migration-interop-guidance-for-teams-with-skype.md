---
title: 迁移和互操作性 - Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解管理组织从Skype for Business过渡到 Teams 的基本概念。
ms.localizationpriority: medium
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
ms.openlocfilehash: b6c8e96c1aeb8fabcbe42ba403c51b4a8d6f4836
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657262"
---
# <a name="coexistence-modes---reference"></a>共存模式 - 参考

> [!Important] 
> - 在 2021 年 7 月 31 日停用 Skype for Business Online 后，不再可以将 TeamsOnly 以外的共存模式分配给云中托管的用户。 与退休前的情况一样，可以为本地Skype for Business Server的用户分配除 TeamsOnly *以外的* 任何模式。 

当组织从Skype for Business过渡到 Teams 时，共存模式为最终用户提供了一种简单且可预测的体验。 对于迁移到 Teams 的组织，TeamsOnly 模式是每个用户的最终目标，但并非所有用户都需要同时分配 TeamsOnly (或任何模式) 。 在用户达到 TeamsOnly 模式之前，组织可以使用 SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings (的任何Skype for Business模式) ，以确保 TeamsOnly 用户与尚未使用的用户之间进行可预测的通信。

从技术角度来看，用户模式控制用户体验的几个方面：

- *传入路由*：在哪个客户端 (Teams 或Skype for Business) 进行传入聊天和呼叫？ 
- *状态发布*：用户的状态是根据用户在 Teams 中的活动向其他用户显示还是Skype for Business？ 
- *会议日程安排*：哪些服务用于安排新会议并确保 Outlook 中存在适当的加载项？ TeamsUpgradePolicy 不管理会议加入。 用户始终可以 *加入* 任何会议，无论是Skype for Business会议还是 Teams 会议。
- *客户端体验*：Teams 和/或 Skype for Business 客户端中提供了哪些功能？ 用户是否可以在 Teams、Skype for Business 或两者中启动呼叫和聊天？ Teams &频道体验是否可用？  

有关基于模式的路由和状态行为的详细信息，请参阅[Skype for Business共存](./coexistence-chat-calls-presence.md)。

但是，从体验的角度来看，模式可描述为定义以下体验：
- *聊天和通话*：用户使用哪个客户端？
- *会议日程安排*：用户是否将新会议安排为 Teams 或Skype for Business会议？
- *Teams 客户端中协作功能的可用性*。 当用户仍有Skype for Business时，Teams &频道和文件功能是否可用？

下面列出了这些模式。 云用户必须是 TeamsOnly，而本地用户必须是 TeamsOnly 以外的任何模式。 
</br>
</br>

|模式|通话和聊天|会议日程<sup>安排 1</sup>|Teams &频道|用例|
|---|---|---|---|---|
|**TeamsOnly <sup>2</sup>**</br>*仅当用户在Skype for Business Server中没有本地帐户时才可能*|Teams|Teams|是|正在升级的最终状态。 新租户的默认值，除非检测到混合配置。|
|孤岛|任一|任一|是|混合组织的默认配置。 允许单个用户并行评估两个客户端。 聊天和呼叫可以进入任一客户端，因此用户必须始终运行这两个客户端。 为了避免混淆或回归Skype for Business体验，Skype for Business继续处理外部 (联合) 通信、PSTN 语音服务和语音应用程序、Office 集成和其他几个集成。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|Teams|是|“会议优先”。 主要是为了让本地组织从 Teams 会议功能中受益，如果他们尚未准备好将呼叫移动到云。|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|是|需要更严格管理控制的复杂组织的备用起点。|
|SfBOnly|Skype for Business|Skype for Business|否<sup>3</sup>|针对对数据控制有严格要求的组织的专用方案。 Teams 仅用于加入其他人安排的会议。|
||||||

</br>
</br>

**笔记：**

<sup>1</sup> 加入现有会议的能力 (无论是在 Teams 中还是在Skype for Business) 中计划，都不受模式控制。 默认情况下，用户始终可以加入他们受邀参加的任何会议。

<sup>2</sup> 默认情况下，将 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 分配给单个用户时，该用户为将来安排的任何现有Skype for Business会议将转换为 Teams 会议。 如果需要，可以通过在`-MigrateMeetingsToTeams $false`授予 TeamsUpgradePolicy 时指定或在 Teams 管理员 门户中取消选中复选框，将这些会议保留为Skype for Business会议。 在租户范围内授予 TeamsUpgradePolicy 时，无法将会议从Skype for Business转换为 Teams。 

<sup>3</sup> 目前，Teams 无法禁用 Teams 和频道功能，因此目前仍启用此功能。


## <a name="using-teamsupgradepolicy"></a>使用 TeamsUpgradePolicy

TeamsUpgradePolicy 公开两个关键属性：模式和 NotifySfbUsers。 
</br>
</br>

|参数|类型|允许的值</br>斜体 (默认值) |说明|
|---|---|---|---|
|模式|枚举|*孤岛*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|指示客户端应运行的模式。|
|NotifySfbUsers|Bool|*False* 或 true|指示是否在Skype for Business客户端中显示横幅，告知用户 Teams 将很快替换Skype for Business。 如果 Mode=TeamsOnly，则不能为 true。|
|||||

Teams 通过内置的只读策略提供 TeamsUpgradePolicy 的所有相关实例。 因此，只有 Get 和 Grant cmdlet 可用。 下面列出了内置实例。
</br>
</br>

|Identity |模式|NotifySfbUsers|
|---|---|---|
|孤岛|孤岛|False|
|IslandsWithNotify|孤岛|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|全局</br>*Default*|孤岛|False|
||||

可以将这些策略实例授予单个用户或租户范围。 例如：
- 若要将用户 ($SipAddress) 升级到 Teams，请授予“UpgradeToTeams”实例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升级整个租户，请从 grant 命令中省略标识参数：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`

## <a name="the-teams-client-user-experience-when-using-skype-for-business-modes"></a>使用Skype for Business模式时的 Teams 客户端用户体验

当用户处于 SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 的任何Skype for Business (模式时，所有传入聊天和呼叫都会路由到用户的Skype for Business客户端。 为了避免最终用户混淆并确保正确的路由，当用户处于任何Skype for Business模式时，Teams 客户端中的呼叫和聊天功能会自动禁用。 同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，Teams 中的会议计划会自动禁用，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时自动启用。 有关详细信息，请参阅 [Teams 客户端体验和共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)。

> [!Note] 
> - 在执行 Teams 和 Channel 的自动强制之前，SfbOnly 和 SfBWithTeamsCollab 模式的行为相同。


## <a name="detailed-mode-descriptions"></a>详细模式说明
</br>
</br>

|模式|解释|
|---|---|
|**孤岛**</br>仅在本地 () |用户并排运行Skype for Business和 Teams。 此用户：</br><ul><li>可以在 Skype for Business 或 Teams 客户端中启动聊天和 VoIP 调用。 注意：在本地拥有Skype for Business的用户无法从 Teams 发起，以访问其他Skype for Business用户，而不管收件人的模式如何。<li>接收Skype for Business客户端中另一用户在Skype for Business发起的 voIP 呼叫&聊天。<li>接收在 Teams 中由 Teams 客户端中的另一个用户发起& VoIP 呼叫的聊天（如果用户 *位于同一租户* 中）。<li>接收在 Teams 中由其Skype for Business客户端中的另一个用户发起& VoIP 呼叫的聊天（如果它们位于 *联合租户中）*。 <li>具有 PSTN 功能，如下所述：<ul><li>当用户驻留在本地Skype for Business并企业语音时，始终会在Skype for Business中启动和接收 PSTN 调用。<li>当用户在 Skype for Business Online 上托管并拥有 Microsoft Phone System 时，用户始终在Skype for Business中启动和接收 PSTN 呼叫：<ul><li>无论用户有 Microsoft 呼叫计划，还是通过Skype for Business 云连接器版本或本地部署Skype for Business Server (混合语音) 连接到 PSTN 网络，都会发生这种情况。<li>**注意：在 Islands 模式下不支持电话系统直接路由。**</ul></ul><li>在Skype for Business中接收 Microsoft 呼叫队列和自动助理呼叫：<ul><li>分配给呼叫队列和自动助理的电话号码 **不能** 是岛屿模式下的电话系统直接路由号码。</ul></ul><li>可以在 Teams 或 Skype for Business (中安排会议，默认情况下会看到这两个插件) 。<li>可以加入任何Skype for Business或 Teams 会议;会议将在各自的客户端中打开。</ul>|
|**SfBOnly**</br>仅在本地 () |用户仅运行Skype for Business。 此用户：</br><ul><li>只能从Skype for Business发起聊天和呼叫。<li>接收其Skype for Business客户端中的任何聊天/呼叫（无论从何处启动），除非发起者是具有本地Skype for Business的 Teams 用户。*<li>只能安排Skype for Business会议，但可以加入Skype for Business或 Teams 会议。</br>\** 建议不要将 Islands 模式与本地用户结合使用到 SfBOnly 模式中的其他用户。 如果本地Skype for Business托管的 Teams 用户发起与 SfBOnly 用户的电话或聊天，则无法访问 SfBOnly 用户，并收到错过的聊天或呼叫电子邮件。*|
|**SfBWithTeamsCollab**</br>仅在本地 () |用户并排运行Skype for Business和 Teams。 此用户：</br><ul><li>具有 SfBOnly 模式下用户的功能。<li>仅启用 Teams 以进行组协作 (频道) ;聊天/呼叫/会议计划已禁用。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>仅在本地 () |用户并排运行Skype for Business和 Teams。 此用户：<ul><li>具有 SfBOnly 模式下用户的聊天和通话功能。<li>已为团队 (频道启用了组协作 - 包括频道对话) ;聊天和呼叫已禁用。<li>只能安排 Teams 会议，但可以加入Skype for Business或 Teams 会议。</ul>|
|**TeamsOnly**</br>仅 (云用户) |用户仅运行 Teams。 此用户：<ul><li>接收其 Teams 客户端中的任何聊天和呼叫，无论从何处启动。<li>只能从 Teams 发起聊天和呼叫。<li>只能在 Teams 中安排会议，但可以加入Skype for Business或 Teams 会议。<li>可以继续使用Skype for Business IP 电话。<br><br>*在 Teams 采用饱和之前，不建议将 TeamsOnly 模式与其他在 Islands 模式下的用户结合使用;也就是说，所有 Islands 模式用户都积极使用和监视 Teams 和Skype for Business客户端。如果 TeamsOnly 用户发起与 Islands 用户的呼叫或聊天，则该呼叫或聊天将进入 Islands 用户的 Teams 客户端;如果 Islands 用户未使用或监视 Teams，则该用户将脱机显示，TeamsOnly 用户无法访问。* <li>在某些情况下，TeamsOnly 模式下的参与者只能以匿名用户身份使用 Skype for Business Web应用 或 Skype 会议应用加入Skype for Business会议。 最终，对于 TeamsOnly 模式下的所有用户来说，这种情况都是如此。 有关详细信息，请参[阅Skype for Business联机停用](skype-for-business-online-retirement.md#what-to-expect-post-retirement)。</ul> |
|||




## <a name="related-topics"></a>相关主题

[与 Skype for Business 共存](./coexistence-chat-calls-presence.md)

[Teams 客户端体验和共存模式的一致性](./teams-client-experience-and-conformance-to-coexistence-modes.md)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用会议迁移服务 (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
