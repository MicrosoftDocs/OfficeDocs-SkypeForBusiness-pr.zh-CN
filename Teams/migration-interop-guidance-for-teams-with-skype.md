---
title: 面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: 从 for Business 的 Skype 管理向工作组的过渡指南
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e924311188e077e10e844b55e4a429ab5344dca
ms.sourcegitcommit: 3070dd7c091e6c97c6d746c6bfb866625184ba87
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "29786426"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导

> [!Tip] 
> 观看下面的会话了解[共存及互操作性](https://aka.ms/teams-upgrade-coexistence-interop)

在启动时具有 for Business 的 Skype 的组织采用团队，管理员可以管理其组织使用的概念共存是 TeamsUpgradePolicy 属性的"模式"中的用户体验。 使用模式，管理员管理互操作和迁移，他们管理从 for Business 的 Skype 到团队转换。  用户模式下确定哪些客户端中传入的聊天和呼叫园地以及哪些服务 （工作组或业务的 Skype） 新会议计划中。 将来，模式，还将使用定义团队将可以使用哪些功能方面的客户端行为。 


## <a name="fundamental-concepts"></a>基本概念

1.  *互操作*： 1 对 1 业务用户 Lync/Skype 和团队用户之间的通信。

2.  *联合身份验证*： 不同租户中的用户之间的通信。

3.  所有用户具有基础 Skype 的业务帐户"驻留"之一 online 的团队或者内部部署：
    - 已为业务 Online 使用 Skype 的用户使用其现有的 online 帐户。
    - 已使用 Skype 业务/Lync 内部部署的用户使用其现有的内部部署帐户。
    - 我们不能为其检测现有 Skype 业务帐户的用户将有 Skype 业务联机时创建团队用户自动配置的帐户。 业务许可证没有 Skype 是必需的。

4.  如果必须在本地部署的任一 Skype 适用于商务或 Lync，并且您希望为团队用户这些用户，您必须至少确保 Azure AD 连接正在同步 msRTCSIP DeploymentLocator 属性到 AAD，因此该团队/Skype for Business联机正确检测您在本地环境。 此外，将任何用户移至仅团队模式 （即，升级用户），*您必须首先配置 Skype 业务混合模式*。 有关详细信息，请参阅[配置 Azure AD 连接的 Skype 业务和团队](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

5.  适用于业务用户之间团队和 Skype 的互操作才可能*如果团队用户联机驻留在 for Business 的 Skype*。 Skype 可以位于企业用户是本地 （和需要业务混合配置 Skype） 的收件人或联机。 位于业务本地 Skype 的用户可以使用团队群岛模式 （定义此文档中的更高版本），但不是能使用互操作的团队或 for Business 使用 Skype 的其他用户与联盟。  

6.  升级和互操作性行为决定基于由 TeamsUpgradePolicy 的用户的共存模式。 TeamsInteropPolicy 不再兑现和授予模式 = 不再允许旧。 

7.  将用户升级到 TeamsOnly 模式可确保的所有传入的聊天和呼叫将始终位于用户的团队的客户端，无论哪些客户端中它从 orignated。 这些用户还将安排团队中的所有新会议。 若要在 TeamsOnly 模式下，用户必须驻留联机 Skype for Business 中。 这是确保互操作、 联盟和团队用户的完整管理所需的。升级到 TeamsOnly 用户：
    - 如果用户驻留在 for Business 的 Skype 联机 （或永远不会有任何 Skype 帐户），向其授予与模式 TeamsUpgradePolicy = TeamsOnly 使用"UpgradeToTeams"实例使用 PowerShell，或使用团队 Admin Center 选择 TeamsOnly 模式。
    - 如果用户驻留在内部部署，请使用`Move-CsUser`从内部部署管理工具到第一次移动用户对 Skype 业务 online。  如果您具有 Skype 业务服务器 2019年或 CU8 Skype 的业务服务器 2015年，您可以指定`-MoveToTeams`中切换`Move-CsUser`用户直接移至团队移动的一部分联机。 此选项还将到团队迁移用户的会议，（尽管现在，会议迁移才正常工作的点击客户）。 如果`-MoveToTeams`不指定或不可用，然后后`Move-CsUser`完成后，将 TeamsOnly 模式分配给该用户使用 PowerShell 或团队 Admin Center。  
     有关详细信息，请参阅[将内部部署和云之间的用户移动](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/move-users-between-on-premises-and-cloud)。  有关会议迁移的详细信息，请参阅[使用会议迁移服务 (MMS)](https://docs.microsoft.com/en-us/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

8.  使用团队系统小组电话功能，用户必须是在 TeamsOnly 模式 （即，业务 online 驻留在 Skype 和升级到团队） 中，以及他们必须配置 Microsoft 电话系统[直接路由](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)（这使您可以使用电话系统与您自己的 SIP 中继和 SBC） 或 Office 365 调用规划。   

9.  安排音频会议的团队会议 （电话拨入式或通过 PSTN 电话拨出） 是当前仅适用于位于 Skype 业务 online 的用户。 与业务帐户在本地 Skype 支持团队用户正在点击。


## <a name="coexistence-modes"></a>共存模式

根据"共存模式"使用 TeamsUpgradePolicy 托管互操作和迁移。 用户模式下确定：

- *传入路由*： 中的客户端 （工作组或业务的 Skype） 执行传入聊天和调用园地？ 
- *会议日程安排*： 哪项服务都用于安排新的会议和确保正确的外接程序在 Outlook 中存在。 请注意 TeamsUpgradePolicy 不管理会议加入。 用户可以始终*加入*任何会议，无论是业务会议或团队会议 Skype。
- *客户端体验*： 哪项功能均可在工作组和/或 Skype 业务客户端？ 这被实现 TeamsOnly 模式。 未来计划支持的其他模式。 

下面列出了模式。 SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 将允许混合的使用这两个客户端，但没有重叠的功能。 群岛模式允许使用情况的两个客户端，但包含重叠的功能。 例如，在群岛模式下，用户无法启动中任一 Skype 聊天适用于商务或团队，但在 SfBWithTeamsCollab，他们可以仅聊天中 for Business 的 Skype （尽管它们可以参与团队通道对话）。 请注意，客户端 expeirence SfB 模式尚未完善。  
</br>
</br>

|模式|路由行为|会议日程安排|客户端体验|
|---|---|---|---|
|群岛|传入 VOIP 呼叫和除聊天园地为原始发件人，同一客户端中的，如果收件人联盟和在群岛模式下，在这种情况下它们位于在 SfB。<sup>1</sup>|两者|最终用户可以发起呼叫和聊天从任一客户端，并可以安排从任一客户端的会议。|
|SfBOnly|传入呼叫和聊天路由至 Skype for Business|Skype for Business 仅|最终用户可以发起呼叫以及仅从 for Business 的 Skype 聊天和仅业务会议安排 Skype。 （还未实施）|
|SfBWithTeamsCollab<sup>2</sup>|传入呼叫和聊天路由至 Skype for Business|Skype for Business 仅|最终用户可以发起呼叫以及仅从 for Business 的 Skype 聊天和仅业务会议安排 Skype。 他们还可以在工作组中使用通道。 （还未实施）|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|传入呼叫和聊天路由至 Skype for Business|仅团队|最终用户可以发起呼叫，并从业务仅和唯一的 Skype 聊天安排团队会议。 它们可以参与团队通道对话。 （还未实施）|
|TeamsOnly|传入呼叫和聊天路由至团队|仅团队|最终用户可以发起呼叫以及仅来自团队聊天。 Skype for Business 才可用于加入会议。|
|||||

**说明：**

<sup>1</sup>的 PSTN 呼叫的详细信息，请参阅本文档末尾的表。

<sup>2</sup> SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 尚未中未公开的管理员的用户体验因为他们当前不不同 SfBOnly 模式下，除了控制 Outlook 加载项行为。客户端体验是传递之后，这些模式将在管理门户中可用。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy： 管理迁移和共存

TeamsUpgradePolicy 公开两个关键属性： 模式和 NotifySfbUsers。 
</br>
</br>

|参数|类型|允许的值</br>（默认斜体中）|说明|
|---|---|---|---|
|模式|枚举|*群岛*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>SfBWithTeamsCollabAndMeetings|指示客户端应中运行的模式。|
|NotifySfbUsers|Bool|*False*或 true|指示是否在业务客户端通知用户团队很快将替换 for Business 的 Skype Skype 中显示的标题。 这不能为 true 如果模式 = TeamsOnly。|
|||||

团队提供的内置的只读策略通过 TeamsUpgradePolicy 所有相关的实例。 因此，仅获取并且可授予 cmdlet。 下面列出了内置的实例。
</br>
</br>

|Identity |模式|NotifySfbUsers|
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
|全局</br>*默认*|群岛|False|
||||

向单个用户或在租户范围内，可以授予这些策略实例。 例如：
- 若要将用户 ($SipAddress) 升级到团队，授予"UpgradeToTeams"实例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升级的整个租户，省略 identity 参数从授予命令：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`


## <a name="federation-considerations"></a>联合身份验证的注意事项

从工作组 for Business 使用 Skype 的另一个用户的联盟要求 for Business 的 Skype 联机托管团队用户。 最终，用户驻留在 Skype 的业务本地团队都将能够与其他团队用户联盟。

TeamsUpgradePolicy 控制传入的联盟的聊天和呼叫路由。 联盟路由行为与同一租户方案，*但在群岛模式下*的相同。  当收件人处于群岛模式中： 
- 聊天和如果收件人是*联盟的租户*中从团队园地 SfB 中发起的呼叫。
- 如果收件人是*同一租户*中时，团队中将位于聊天和团队从发起的呼叫。
- 聊天和始终从 SfB 发起的呼叫停放在 SfB。


## <a name="the-intended-client-user-experience-in-teams-when-using-sfb-modes"></a>使用 SfB 模式时，预期的客户端用户体验中团队

当用户在任何业务模式 （SfBOnly、 SfBWithTeamsCollab、 SfBWithTeamsCollabAndMeetings） Skype*团队应用程序中的呼叫和聊天功能旨在被禁用*，但当前未尚未禁用。 同样，当用户在 SfBOnly 或 SfBWithTeamsCollab 模式下，*在工作组中计划会议旨在被禁用*，但其当前不是。 计划自动提供此体验的解决方案。

直到传递此解决方案，管理员可以通过手动配置 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的值强制 TeamsUpgradePolicy 模式的预期的客户端体验。 此外，当使用`Grant-CsTeamsUpgradePolicy`在 PowerShell 中，cmdlet 将自动检查 determmine TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 中的相应设置的配置这些设置时与兼容指定的模式。 如果任何未正确配置，则授予会成功，但将提供警告，表明未正确配置哪些设置。 管理员随后应更新指示的策略中团队提供兼容的最终用户体验。 如果管理员决定不执行任何操作由于警告，用户仍可以访问聊天，呼叫和/或会议中团队的日程安排功能，具体取决于 TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的值可能会造成的混乱的最终用户体验。

### <a name="expected-values-of-workload-policy-settings-per-mode"></a>需要每模式的工作负荷策略设置的值
下表显示检查授予 TeamsUpgradeMode 时策略设置。 将来，目的是为 SfBOnly 模式也禁用团队; 中的通道但是，是当前通道功能允许在要禁用的团队中没有设置。


|**形式 （应用程序）**|**Policy.Setting**|
|---|---|
|聊天|TeamsMessagingPolicy.AllowUserChat|
|通话|TeamsCallingPolicy.AllowPrivateCalling|
|会议日程安排|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

下面显示，对于给定的模式，这些设置的预期值：

|模式|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly 或群岛|已启用|已启用|已启用|已启用|
|SfBWithTeamsCollabAndMeetings|已禁用|已禁用|已启用|已启用|
|SfBWithTeamsCollab 或 SfBOnly|已禁用|已禁用|已禁用|已禁用|
||||||


如果授予 CsTeamsUpgradePolicy 过程中检测到这些设置的任何其他组合，授予会成功，但将显示一条警告，指示不符合预期的行为的特定设置。 暂时，管理员应启用/禁用通过核心工作负荷策略的工作负荷。  自动实施基于 TeamsUpgradePolicy 实现后，将更新 PowerShell 警告，告知客户端体验，会自动应用的管理员。 在这种情况下，TeamsMessagingPolicy、 TeamsCallingPolicy 和 TeamsMeetingPolicy 的值保持不变 –，但将根据 TeamsUpgradePolicy 实施预期的客户端体验。

下面是 PowerShell 警告可能外观的示例：


`PS C:\Users\janedoe> Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab
WARNING: The user 'user1@contoso.com' currently has effective policy enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the near term, when granting TeamsUpgradePolicy with mode=SfBWithTeamsCollab to a user, you must also separately assign policy to ensure the user has effective policy disabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling. In the future, the capability will automatically honor TeamsUpgradePolicy.
PS C:\Users\janedoe>`


之前的客户端行为上述自动实施传递，每个 SfB 模式行为本质上是相同。 SfBOnly、 SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 模式是如何它们路由传入呼叫和聊天中都相同。 唯一的区别，现在，是是否启用团队 Outlook 外接程序和 Skype for Business 中。 传递区分客户端 experiece，直到在管理门户中启用的 SfB 模式仅为 1。 但所有模式在 PowerShell 中可用。


## <a name="teamsinteroppolicy-and-legacy-mode-has-been-retired"></a>已失效 TeamsInteropPolicy 和旧版模式 

已由 TeamsUpgradePolicy 取代 TeamsInteropPolicy。 已更新以前适用 TeamsInteropPolicy 的所有组件，以改为服从 TeamsUpgradePolicy。  Microsoft 有以前推出 TeamsUpgradePolicy 以便于从 TeamsInteropPolicy 转换为 TeamsUpgradePolicy 的"旧"模式。 在旧模式下，理解 TeamsUpgradePolicy 的路由组件将还原回为 TeamsInteropPolicy。 路由现在完全支持 TeamsUpgradePolicy。 不再支持旧版模式和不再可以授予旧版模式


## <a name="detailed-mode-descriptions"></a>详细的模式说明
</br>
</br>

|模式|说明 （includeding 计划的客户端体验）|
|---|---|
|**群岛**</br>（默认值）|用户运行业务和团队-并行这两个 Skype。 此用户：</br><ul><li>可以启动聊天和 VOIP 呼叫中任一 Skype 业务或团队的客户端。 注意： 具有 for Business 的 Skype 用户驻留在本地无法启动从团队访问另一个 Skype 业务用户，无论收件人的模式。<li>接收聊天 & VOIP 呼叫中已开始的 Skype for Business 中其 Skype 业务客户端的其他用户。<li>接收聊天 & VOIP 呼叫他们团队的客户端中已开始另一个用户团队它们是否为*同一租户*中。<li>接收聊天 & VOIP 呼叫中已开始另一个用户的团队中其 Skype for Business 客户端它们是否在*联盟的租户*。 <li>具有 PSTN 功能如下所述：<ul><li>如果用户驻留在 Skype 业务本地，启动和 Skype for Business 中收到 PSTN 呼叫。<li>如果用户驻留 online，用户具有电话系统，这种情况下用户：<ul><li>发起和接收团队中的 PSTN 呼叫，如果对用户配置直接路由<li>发起和接收 Skype for Business 中的 PSTN 呼叫，如果用户已制定 MS 调用计划或连接到 PSTN 网络通过任一 Skype 商务云连接器版或 Skype 的内部部署业务服务器 （混合语音）</ul></ul><li>可以安排会议在团队或 Skype for Business 中的 （和默认情况下将看到两个插件）。<li>可以加入业务或团队会议; 任何 Skype会议将在各自的客户端中打开。</ul>|
|**SfBOnly**|用户运行仅 for Business 的 Skype。 此用户：</br><ul><li>可以启动聊天和仅从 for Business 的 Skype 调用。<li>收到任何聊天/呼叫中的业务客户端，其 Skype 无论其中启动，除非发起者团队用户拥有 for Business 的 Skype 驻留在本地。*<li>可以安排仅 Skype 业务会议，但可以加入 Skype 业务或团队的会议。</br>* 与内部部署用户使用群岛模式不建议在组合与 SfBOnly 模式中的其他用户。 如果具有 for Business 的 Skype 的团队用户驻留在本地启动呼叫或向 SfBOnly 用户聊天，SfBOnly 用户无法连接到并接收错过的聊天呼叫 email.*|
|**SfBWithTeamsCollab**|用户运行业务和团队-并行这两个 Skype。 此用户：</br><ul><li>具有 SfBOnly 模式中的用户的功能。<li>工作组已启用仅对组协作 （通道）;聊天/呼叫/会议安排将被禁用。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|用户运行业务和团队-并行这两个 Skype。 此用户：<ul><li>已在 SfBOnly 模式下的聊天和用户的呼叫功能。<li>已启用组协作的团队 （通道-包括通道对话）;聊天和呼叫将被禁用。<li>可以安排仅团队会议，但可以加入 Skype 业务或团队的会议。</ul>|
|**TeamsOnly**</br>（需要 SfB Online 主页）|用户运行仅团队。 此用户：<ul><li>接收任何聊天并中调用他们团队的客户端，而不管在启动。<li>可以启动聊天和仅来自团队呼叫。<li>可以安排会议仅在工作组中的，但可以加入 Skype 业务或团队的会议。<li>可以继续使用 Skype 业务 IP 电话。</ul> |
|||




## <a name="related-topics"></a>相关主题

[与 Skype for Business 共存](https://docs.microsoft.com/en-us/microsoftteams/coexistence-chat-calls-presence)

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[授予 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[设置 CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)


