---
title: 面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
description: 用于管理从 Skype for Business 切换到团队的指南
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.teamsupgrade.overview
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6656cab6918cfa0b04da28f0197137a300bbf79
ms.sourcegitcommit: a49caec01ff724475d6670b303d851ddd8266c2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2019
ms.locfileid: "36207188"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导

> [!Tip] 
> 观看以下会话以了解[共存和互操作性](https://aka.ms/teams-upgrade-coexistence-interop)

作为具有 Skype for Business 的组织开始采纳团队, 管理员可以使用共存 "模式" (它是 TeamsUpgradePolicy 的一个属性) 的概念来管理其组织中的用户体验。 使用模式, 管理员可管理互操作和迁移, 因为它们管理从 Skype for Business 到团队的过渡。  用户模式确定在哪种情况下, 客户端传入的聊天和呼叫世界, 以及安排新会议的服务 (团队或 Skype for business)。 它还控制团队客户端中可用的功能。 


## <a name="fundamental-concepts"></a>基本概念

1.  *互操作*: 1 到1个 Lync/Skype for business 用户与团队用户之间的通信。

2.  *联盟*: 不同租户中的用户之间的通信。

3.  所有团队用户都拥有基础 Skype for Business 帐户, 该帐户 "托管" 是联机或本地的:
    - 已使用 Skype for Business Online 的用户使用其现有的在线帐户。
    - 已使用 Skype for Business/Lync 本地用户使用其现有本地帐户的用户。
    - 无法检测到现有 Skype for Business 帐户的用户将在创建团队用户时自动设置 Skype for business Online 帐户。

4.  如果你有 Skype for Business 或 Lync 的本地部署, 并且希望这些用户成为团队用户, 你必须至少确保 Azure AD Connect 将 msRTCSIP DeploymentLocator 属性同步到 AAD 中, 以便团队/Skype for Business联机地检测你的本地环境。 此外, 若要将任何用户移动到 "仅团队" 模式 (即升级用户),*必须首先配置 Skype for business 混合模式*。 有关更多详细信息, 请参阅[为 Skype for business 和团队配置 AZURE AD Connect](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

5.  只有*团队用户在 Skype for business 中托管*时, 才可以在团队和 skype for business 用户之间进行互操作。 收件人 Skype for Business 用户可以在本地托管 (并且需要配置 Skype for business 混合) 或在线。 托管在本地 Skype for Business 中的用户可以使用孤岛模式 (在本文档后面已定义) 中的团队, 但不能使用团队互操作或与其他使用 Skype for Business 的用户联盟。  

6.  升级和互操作行为是根据用户的共存模式确定的, 下文所述。 模式由 TeamsUpgradePolicy 管理。 

7.  将用户升级到 TeamsOnly 模式可确保所有传入聊天和呼叫始终位于用户的团队客户端, 无论其来源于哪种客户端。 这些用户还将计划团队中的所有新会议。 若要处于 TeamsOnly 模式, 用户必须在 Skype for Business 中联机。 这是确保团队用户的互操作、联盟和完全管理所必需的。要将用户升级到 TeamsOnly, 请执行以下操作:
    - 如果用户托管在 Skype for Business online 中 (或从未拥有任何 Skype 帐户), 请使用 PowerShell 使用 "UpgradeToTeams" 实例向他们授予 TeamsUpgradePolicy with Mode = TeamsOnly, 或使用团队管理中心选择 TeamsOnly 模式。
    - 如果用户在本地托管, 请从本地管理员`Move-CsUser`工具中使用, 首先将用户移动到 Skype For business Online。  如果您有 skype for business Server 2019 或 CU8 for Skype for business Server 2015, 则可以在 " `-MoveToTeams`联机移动`Move-CsUser` " 中指定切换以将用户直接移动到团队。 此选项还会将用户的会议迁移到团队。 如果`-MoveToTeams`未指定或不可用, 则完成后`Move-CsUser` , 使用 PowerShell 或团队管理中心将 TeamsOnly 模式分配给该用户。 有关详细信息, 请参阅[在本地和云之间移动用户](https://docs.microsoft.com/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  有关会议迁移的详细信息, 请参阅[使用会议迁移服务 (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

8.  若要将 Microsoft Phone 系统与团队一起使用, 用户必须处于 TeamsOnly 模式 (例如, 托管在 Skype for business Online 并升级到团队), 并且它们必须配置为使用 Microsoft Phone 系统[直接路由](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)(这允许你将手机系统与您自己的 SIP 中继和 SBC) 或拥有 Office 365 呼叫计划。 在孤岛模式下不支持 Microsoft Phone 系统直接路由。    

9.  无论用户是否托管在 Skype for Business Online 或本地 Skype for business 中, 通过音频会议安排团队会议 (通过 PSTN 拨入或拨出) 都是可用的。 


## <a name="coexistence-modes"></a>共存模式

将根据 "共存模式" 使用 TeamsUpgradePolicy 来管理互操作和迁移。 当组织从 Skype for Business 切换到团队时, 共存模式为最终用户提供简单且可预测的体验。 对于迁移到团队的组织, TeamsOnly 模式是每个用户的最终目标, 但并非所有用户都需要同时分配 TeamsOnly (或任何模式)。 在用户到达 TeamsOnly 模式之前, 组织可以使用任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 确保 TeamsOnly 用户和尚未使用的用户之间可预测的通信。


从技术角度来看, 用户模式控制用户体验的多个方面:

- *传入路由*: 客户 (团队或 Skype for business) 进行传入聊天和呼叫土地？ 
- *状态发布*: 根据用户在团队或 Skype for business 中的活动是否向其他用户显示的用户状态？ 
- *会议计划*: 哪个服务用于安排新会议和确保 Outlook 中显示正确的加载项？ 请注意, TeamsUpgradePolicy 不管理会议加入。 无论是 Skype for business 会议还是团队会议, 用户都可以随时*加入*任何会议。
- *客户体验*: 团队和/或 Skype for business 客户端提供哪些功能？ 用户是否可以在团队、Skype for business 或两者中发起呼叫和聊天？ 团队是否提供 & 频道体验？  

有关基于模式的路由和状态行为的详细信息, 请参阅[与 Skype For Business 共存](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)。

但是, 从体验角度来看, 模式更简单地描述为定义的体验:
- *聊天和通话*: 用户使用哪种客户端？
- *会议日程安排*: 用户将新会议安排为团队或 Skype for business 会议？
- *团队客户端中的协作功能的可用性*。 在用户仍然拥有 Skype for business 的情况下, 团队 & 频道和文件功能是否可用？

模式如下所示。
</br>
</br>

|众|通话和聊天|会议日程安排<sup>1</sup>|& 频道的团队|用例|
|---|---|---|---|---|
|**TeamsOnly<sup>2</sup>**</br>*Skype for Business Online 需要家庭版*|Teams|Teams|是|升级的最终状态。 <500 座位的新租户的默认值。|
|群岛|某|某|是|默认配置。 允许单个用户并排评估这两个客户端。 聊天和通话可以在客户端中进行土地, 因此用户必须始终运行这两个客户端。 为避免令人困惑或 regressed 的 Skype for business 体验、外部 (联合) 通信、PSTN 语音服务和语音应用、Office 集成以及其他一些其他集成将继续由 Skype for Business 处理。|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|Skype for Business|团队|是|"首先开会"。 主要供本地组织从团队会议功能中获益, 前提是他们尚未准备好将呼叫转移到云。|
|SfBWithTeamsCollab|Skype for Business|Skype for Business|是|需要更严格的管理控制的复杂组织的备用起始点。|
|SfBOnly|Skype for Business|Skype for Business|无<sup>3</sup>|针对数据控制严格要求的组织的专用方案。 团队仅用于加入由其他人计划的会议。|
||||||

</br>
</br>

**笔记**

<sup>1</sup>加入现有会议 (无论是在团队中还是在 Skype for business 中安排) 的功能不受模式控制。 默认情况下, 用户始终可以加入受邀参加的任何会议。

<sup>2</sup>默认情况下, 向单个用户分配 TeamsOnly 或 SfbWithTeamsCollabAndMeetings 时, 该用户将来安排的任何现有 Skype for business 会议都将转换为团队会议。 如果需要, 您可以通过`-MigrateMeetingsToTeams $false`在授予 TeamsUpgradePolicy 或取消选中团队管理门户中的复选框来将这些会议保留为 Skype for business 会议。   请注意, 在租户范围内授予 TeamsUpgradePolicy 时, 将不会 avaialble 将会议从 Skype for Business 转换为团队的功能。 

<sup>3</sup>目前, 团队不具备禁用团队和频道功能的功能, 因此现在可以继续使用。



## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy: 管理迁移和共存

TeamsUpgradePolicy 公开两个键属性: Mode 和 NotifySfbUsers。 
</br>
</br>

|参数|类型|允许值</br>(默认值为斜体)|说明|
|---|---|---|---|
|众|枚举|*群岛*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|指示客户端应在其中运行的模式。|
|NotifySfbUsers|Bool|*False*或 true|指示是否在 Skype for Business 客户端中显示横幅, 通知用户团队将很快更换 Skype for Business。 如果 Mode = TeamsOnly, 则此值不能为 true。|
|||||

团队通过内置的只读策略提供 TeamsUpgradePolicy 的所有相关实例。 因此, 只有获取和授予 cmdlet 可用。 下面列出了内置的实例。
</br>
</br>

|Identity |众|NotifySfbUsers|
|---|---|---|
|群岛|群岛|False|
|IslandsWithNotify|群岛|True|
|SfBOnly|SfBOnly|False|
|SfBOnlyWithNotify|SfBOnly|True|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|
|UpgradeToTeams|TeamsOnly|False|
|全局</br>*Default*|群岛|False|
||||

可以向单个用户或租户范围授予这些策略实例。 例如：
- 若要将用户 ($SipAddress) 升级到团队, 请授予 "UpgradeToTeams" 实例:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升级整个租户, 请从 "授予" 命令中省略 identity 参数:</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>联盟注意事项

从团队到其他使用 Skype for Business 的用户的联盟要求团队用户在 Skype for business 中托管用户在线。 最终, 托管在本地 Skype for business 中的团队用户将能够与团队的用户进行联盟。

TeamsUpgradePolicy 控制传入联盟聊天和呼叫的路由。 *除 "孤岛" 模式之外*, 联合路由行为与相同租户方案相同。  当收件人处于 "孤岛" 模式时: 
- 如果收件人在*联盟租户*中, 将从 SfB 中的团队土地发起聊天和通话。
- 如果收件人位于*同一个租户*中, 则从团队中的团队土地发起聊天和通话。
- 通过 SfB 发起的聊天和通话始终位于 Skype for Business 中。

有关更多详细信息, 请参阅[与 Skype For Business 共存](https://docs.microsoft.com/en-us/MicrosoftTeams/coexistence-chat-calls-presence)。

## <a name="the-teams-client-user-experience-when-using-sfb-modes"></a>团队客户端在使用 SfB 模式时的用户体验
当用户处于任何 Skype for Business 模式 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 时, 所有传入聊天和通话都将路由到用户的 Skype for Business 客户端。 为避免最终用户混淆和确保正确路由, 当用户处于任何 Skype for Business 模式时, 将自动禁用团队客户端中的呼叫和聊天功能。 同样, 当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时, 将自动禁用团队中的会议计划, 并在用户处于 "SfBWithTeamsCollabAndMeetings" 模式时自动启用。 有关详细信息, 请参阅[团队客户体验和共存模式一致性](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)。

> [!Note] 
> - 在交付团队和频道的自动强制之前, SfbOnly 和 SfBWithTeamsCollab 模式的行为相同。


## <a name="detailed-mode-descriptions"></a>详细模式说明
</br>
</br>

|众|解释|
|---|---|
|**群岛**</br>默认|用户并排运行 Skype for business 和团队。 此用户:</br><ul><li>可以在 Skype for Business 或团队客户端中发起聊天和 VoIP 呼叫。 注意: 无论收件人的模式如何, 使用 Skype for business 托管内部部署的用户都无法从团队发起, 从而访问其他 Skype for Business 用户。<li>接收 skype for business 客户端中其他用户在 Skype for Business 中发起的聊天 &。<li>在团队客户端中的其他用户 (如果它们位于*同一租户*中) 中接收 & VoIP 呼叫的聊天。<li>如果其他用户在*联盟租户*中, 则在其他用户的 Skype for business 客户端中发起的 VoIP 呼叫 & 的聊天。 <li>具有如下所述的 PSTN 功能:<ul><li>如果用户托管在本地 Skype for business 且具有企业语音, 则在 Skype for Business 中始终发起和接收 PSTN 呼叫。<li>当用户托管在 Skype for business Online 且拥有 Microsoft 手机系统时, 用户将始终在 Skype for Business 中启动并接收 PSTN 呼叫:<ul><li>无论用户是否具有 Microsoft 通话计划, 都是如此, 还是通过 skype for business 云连接器版或 Skype for business Server 的内部部署 (混合语音) 连接到 PSTN 网络。<li>**注意: Microsoft 团队手机系统直接路由在孤岛模式下不受支持。**</ul></ul><li>在 Skype for Business 中接收 Microsoft 通话队列和自动助理通话。<li>可以在团队或 Skype for business 中安排会议 (并且默认情况下将看到两个插件)。<li>可以加入任何 Skype for Business 或团队会议;会议将在相应的客户端中打开。</ul>|
|**SfBOnly**|用户仅运行 Skype for Business。 此用户:</br><ul><li>只能从 Skype for Business 发起聊天和通话。<li>在其 Skype for Business 客户端中接收任何聊天/呼叫, 除非发起人是具有 Skype for business 托管内部部署的团队用户。*只能安排 skype for business 会议, 但可以加入 skype for business 或团队会议。 <li></br>* 将 SfBOnly 模式中的其他用户结合使用时, 不建议将孤岛模式与本地用户结合使用。 如果使用 Skype for Business 托管内部部署的团队用户发起呼叫或与 SfBOnly 用户聊天, 则无法访问 SfBOnly 用户并收到错过的聊天/呼叫电子邮件。 *|
|**SfBWithTeamsCollab**|用户并排运行 Skype for business 和团队。 此用户:</br><ul><li>在 SfBOnly 模式下具有用户的功能。<li>只有组协作 (频道) 才启用团队;聊天/通话/会议计划已禁用。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|用户并排运行 Skype for business 和团队。 此用户:<ul><li>在 SfBOnly 模式下具有用户的聊天和通话功能。<li>已为组协作启用团队 (频道-包括频道对话);已禁用聊天和通话。<li>只能安排团队会议, 但可以加入 Skype for Business 或团队会议。</ul>|
|**TeamsOnly**</br>(需要 SfB Online 主页)|用户仅运行团队。 此用户:<ul><li>接收团队客户端中的任何聊天和通话, 无论启动的位置如何。<li>可以仅发起来自团队的聊天和呼叫。<li>只能在团队中安排会议, 但可以加入 Skype for Business 或团队会议。<li>可以继续使用 Skype for Business IP 手机。<br><br>*建议在 TeamsOnly 模式中与其他用户结合使用模式, 直到团队采纳达到饱和, 即所有孤岛模式的用户都会主动使用和监视团队和 Skype for business 客户端。如果 TeamsOnly 用户发起了与孤岛用户的呼叫或聊天, 则该通话或聊天将在孤岛用户的团队客户端中进行连接;如果孤岛用户不使用或监视团队, 则该用户将显示为脱机状态, 并且 TeamsOnly 用户将无法访问该用户。*</ul> |
|||




## <a name="related-topics"></a>相关主题

[与 Skype for Business 共存](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Teams 客户端体验和共存模式的一致性](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-client-experience-and-conformance-to-coexistence-modes)

[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[授权-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[使用会议迁移服务 (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
