---
title: 面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: 从 for Business 的 Skype 管理向工作组的过渡指南
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bc6d3c48dc0812311b511ead0583d3b9b9fcfa2
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201490"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导

> [!Tip] 
> 观看下面的会话了解[共存及互操作性](https://aka.ms/teams-upgrade-coexistence-interop)

使用"共存模式"，如由 TeamsUpgradePolicy 托管互操作和迁移。 控制可以选择的用户的模式，这两个路由的传入呼叫和聊天和用户是否计划团队或 Skype for Business 中的会议。  推出，与即将开始的 TeamsAppPermissionsPolicy 一起使用，模式将也控制用户可在哪些客户端中启动聊天和呼叫。 

已失效 TeamsInteropPolicy。 其功能已整合到 TeamsUpgradePolicy，并配置 TeamsInteropPolicy 不再需要，通常不保证。 如果 TeamsUpgradePolicy 模式，则不会接受 TeamsInteropPolicy = 旧，但还停用该模式。  既然 TeamsUpgradePolicy 支持已完成，*客户必须更新其配置为使用旧之外模式*。 授予实例 TeamsUpgradePolicy 与 mode = 旧被阻止。  删除所有实例 TeamsInteropPolicy 和使用模式 TeamsUpgradePolicy 任何实例处于 Microsoft = 旧。

## <a name="fundamental-concepts"></a>基本概念

1.  *互操作*： 1 对 1 业务用户 Lync/Skype 和团队用户之间的通信。

2.  *联合身份验证*： 不同租户中的用户之间的通信。

3.  所有用户具有基础 Skype 的业务帐户"驻留"之一 online 的团队或者内部部署：
    - 已为业务 Online 使用 Skype 的用户使用其现有的 online 帐户。
    - 已使用 Skype 业务/Lync 内部部署的用户使用其现有的内部部署帐户。
    - 我们不能为其检测现有 Skype 业务帐户的用户将有 Skype 业务联机时创建团队用户自动配置的帐户。 业务许可证没有 Skype 是必需的。

4.  如果必须在本地部署的任一 Skype 适用于商务或 Lync，并且您希望为团队用户这些用户，您必须至少确保 Azure AD 连接正在同步 msRTCSIP DeploymentLocator 属性到 AAD，因此该团队/Skype for Business联机正确检测您在本地环境。 此外，将任何用户移至仅团队模式 （即，升级用户），*则必须配置为业务混合模式的 Skype*。 有关详细信息，请参阅[配置 Azure AD 连接的 Skype 业务和团队](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/configure-azure-ad-connect)。

5.  适用于业务用户之间团队和 Skype 的互操作才可能*如果团队用户联机驻留在 for Business 的 Skype*。 Skype 可以位于企业用户是本地 （和需要业务混合配置 Skype） 的收件人或联机。 位于业务本地 Skype 的用户可以使用团队群岛模式 （定义此文档中的更高版本），但不是能使用互操作的团队或 for Business 使用 Skype 的其他用户与联盟。  

6.  升级到团队的用户 (即，向其授予与模式 TeamsUpgradePolicy = TeamsOnly)，用户必须联机驻留在 for Business 的 Skype。 这是确保互操作、 联盟和团队用户的完整管理所需的。 若要升级用户都驻留在内部部署，使用`Move-CsUser`从内部部署管理工具到第一次移动用户对 Skype 业务 online:

    - 如果您具有 Skype 业务服务器 2019年或 CU8 Skype 的业务服务器 2015年，指定`-MoveToTeams`中切换`Move-CsUser`将用户移动到团队直接。
    - 否则为之后`Move-CsUser`完成后，将 TeamsOnly 模式分配给该用户使用 PowerShell 或团队 Admin Center。 

7.  管理升级和互操作的核心策略是 TeamsUpgradePolicy。 TeamsInteropPolicy 不再适用时使用 TeamsUpgradePolicy 模式除 = 旧，并使用模式的客户 = 旧必须更新其配置的 TeamsUpgradePolicy 使用不同的模式。  授予模式 = 不再允许旧。 

8.  使用团队系统小组电话功能，用户必须是在 TeamsOnly 模式 （即，业务 online 驻留在 Skype 和升级到团队） 中，以及他们必须配置 Microsoft 电话系统[直接路由](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)（这使您可以使用电话系统与您自己的 SIP 中继和 SBC） 或 Office 365 调用规划。   

9.  安排音频会议的团队会议 （电话拨入式或通过 PSTN 电话拨出） 是当前仅适用于位于 Skype 业务 online 的用户。 与业务帐户在本地 Skype 支持团队用户正在点击。


## <a name="coexistence-modes"></a>共存模式

根据"共存模式"使用 TeamsUpgradePolicy 托管互操作和迁移。 用户模式下确定：

- *传入路由*： 中的客户端 （工作组或业务的 Skype） 执行传入聊天和调用园地？ 
- *会议日程安排*： 哪项服务都用于安排新的会议和确保正确的外接程序在 Outlook 中存在。 请注意 TeamsUpgradePolicy 不管理会议加入。 用户可以始终*加入*任何会议，无论是业务会议或团队会议 Skype。
- *客户端体验*： 哪项功能均可在工作组和/或 Skype 业务客户端？ 这被实现 TeamsOnly 模式。 取决于即将开始的 TeamsAppPermissionsPolicy 支持其他模式。 在此新策略后，TeamsUpgradePolicy 将具有依赖项以确保团队为所需的模式正确配置。

下面列出了计划的模式。 SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 将允许混合的使用这两个客户端，但没有重叠的功能。 群岛模式允许使用情况的两个客户端，但包含重叠的功能。 例如，在群岛模式下，用户无法启动中任一 Skype 聊天适用于商务或团队，但在 SfBWithTeamsCollab，他们可以仅聊天中 for Business 的 Skype （尽管它们可以参与团队通道对话）。 请注意，不是所有模式尚未完全可用。  
</br>
</br>

|模式|路由行为|会议日程安排|客户端体验|
|---|---|---|---|
|群岛|传入 VOIP 呼叫和除聊天园地为原始发件人，同一客户端中的，如果收件人联盟和在群岛模式下，在这种情况下它们位于在 SfB。<sup>1</sup>|两者|最终用户可以发起呼叫和聊天从任一客户端，并可以安排从任一客户端的会议。|
|SfBOnly|传入呼叫和聊天路由至 Skype for Business|Skype for Business 仅|最终用户可以发起呼叫以及仅从 for Business 的 Skype 聊天和仅业务会议安排 Skype。 （还未实施）|
|SfBWithTeamsCollab<sup>2</sup>|传入呼叫和聊天路由至 Skype for Business|Skype for Business 仅|最终用户可以发起呼叫以及仅从 for Business 的 Skype 聊天和仅业务会议安排 Skype。 他们还可以在工作组中使用通道。 （还未实施）|
|SfBWithTeamsCollabAndMeetings<sup>2</sup>|传入呼叫和聊天路由至 Skype for Business|仅团队|最终用户可以发起呼叫，并从业务仅和唯一的 Skype 聊天安排团队会议。 它们可以参与团队通道对话。 （还未实施）|
|TeamsOnly|传入呼叫和聊天路由至团队|仅团队|最终用户可以发起呼叫以及仅来自团队聊天。 Skype for Business 才可用于加入会议。|
|旧</br>*弃用*|路由基于 TeamsInteropPolicy|不会影响|没有任何影响。 这是临时的简化从 TeamsInteropPolicy 过渡到 TeamsUpgradePolicy 模式。 完全支持 TeamsUpgradePolicy 以便*客户必须更新其配置为非旧的模式。*  授予的旧模式已不再可能。 |
|||||

**说明：**

<sup>1</sup>的 PSTN 呼叫的详细信息，请参阅本文档末尾的表。

<sup>2</sup> SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 尚未中未公开的管理员的用户体验因为他们当前行为无不同 SfBOnly 模式。 客户端体验是传递之后，将提供这些模式。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy： 管理迁移和共存

TeamsUpgradePolicy 公开两个关键属性： 模式和 NotifySfbUsers。 
</br>
</br>

|参数|类型|允许的值</br>（默认斜体中）|说明|
|---|---|---|---|
|模式|枚举|*群岛*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>旧|指示客户端应中运行的模式。 如果模式 = 旧，使用此策略的组件将还原为考虑 TeamsInteropPolicy。 TeamsUpgradePolicy 现在完全支持，客户应更新其配置使用模式旧之外。|
|NotifySfbUsers|Bool|*False*或 true|指示是否在业务客户端通知用户团队很快将替换 for Business 的 Skype Skype 中显示的标题。 这不能为 true 如果模式 = TeamsOnly。|
|||||

团队提供的内置的只读策略通过 TeamsUpgradePolicy 所有相关的实例。 因此，仅获取并且可授予 cmdlet。 下面列出了内置的实例。
</br>
</br>

|Identity |模式|NotifySfbUsers|备注|
|---|---|---|---|
|群岛|群岛|False||
|IslandsWithNotify|群岛|True||
|SfBOnly|SfBOnly|False|现在，此模式实际上是设置首选的客户端相同 = SfB。 我们将来预期这将限制团队功能。|
|SfBOnlyWithNotify|SfBOnly|True|现在，此模式实际上是设置首选的客户端相同 = SfB。 我们将来预期这将限制团队功能。|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|此模式在 PowerShell 层存在但不是在管理用户体验中尚未公开。 从路由的角度看，这是与 SfBOnly 模式相同。 可用 TeamsAppPolicy 时，这将只允许团队应用程序中的通道。|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|此模式在 PowerShell 层存在但不是在管理用户体验中尚未公开。 从路由的角度看，这是与 SfBOnly 模式相同。 可用 TeamsAppPolicy 时，这将只允许团队应用程序中的通道。|
|SfBWithTeamsCollabAndMeetings|SfBWithTeamsCollabAndMeetings|False|此模式在 PowerShell 层存在但不是在管理用户体验中尚未公开。 从路由的角度看，这是与 SfBOnly 模式相同。 可用 TeamsAppPolicy 时，这将使通道和在工作组中计划的会议。|
|SfBWithTeamsCollabAndMeetingsWithNotify|SfBWithTeamsCollabAndMeetings|True|此模式在 PowerShell 层存在但不是在管理用户体验中尚未公开。 从路由的角度看，这是与 SfBOnly 模式相同。 可用 TeamsAppPolicy 时，这将使通道和在工作组中计划的会议。|
|UpgradeToTeams|TeamsOnly|False|将用户升级到团队，并阻止聊天、 电话和在 Skype for Business 中计划的会议，请使用此模式。|
|全局|群岛|False|是默认策略。|
|NoUpgrade|旧|False|将立即终止此实例。 不再可能向用户授予此策略|
|NotifyForTeams|旧|True|将立即终止此实例。 不再可能向用户授予此策略|
|||||

向单个用户或在租户范围内，可以授予这些策略实例。 例如：
- 若要将用户 ($SipAddress) 升级到团队，授予"UpgradeToTeams"实例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升级的整个租户，省略 identity 参数从授予命令：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-and-legacy-mode-being-retired"></a>TeamsInteropPolicy 和正在停用旧模式 

如前所述，已由 TeamsUpgradePolicy 取代 TeamsInteropPolicy。 已更新以前适用 TeamsInteropPolicy 的所有组件，以改为服从 TeamsUpgradePolicy。 

Microsoft 以前推出 TeamsUpgradePolicy 以便于从 TeamsInteropPolicy 转换为 TeamsUpgradePolicy 的"旧"模式。 在旧模式下，理解 TeamsUpgradePolicy 的路由组件将还原回为 TeamsInteropPolicy。 路由现在完全支持 TeamsUpgradePolicy 并且不再需要使用旧模式。 *使用旧模式客户必须更新 TeamsUpgradePolicy 使用其他模式之一其配置。* 


## <a name="federation-considerations"></a>联合身份验证的注意事项

从工作组 for Business 使用 Skype 的另一个用户的联盟要求 for Business 的 Skype 联机托管团队用户。 最终，用户驻留在 Skype 的业务本地团队都将能够与其他团队用户联盟。

TeamsUpgradePolicy 控制传入的联盟的聊天和呼叫路由。 联盟路由行为与同一租户方案，*但在群岛模式下*的相同。  当收件人处于群岛模式中： 
- 聊天和如果收件人是*联盟的租户*中从团队园地 SfB 中发起的呼叫。
- 如果收件人是*同一租户*中时，团队中将位于聊天和团队从发起的呼叫。
- 聊天和始终从 SfB 发起的呼叫停放在 SfB。


## <a name="completing-the-transition-to-mode-management"></a>完成转换到模式管理

今年更高版本，Microsoft 计划引入新策略的类型，TeamsAppPermissionsPolicy，以控制哪些部分团队客户端启用 （如 IM、 会议、 聊天、 通道）。 要启用/禁用团队中的工作负荷的新策略何时有空，将更新 TeamsUpgradePolicy，，以便当管理员尝试向用户授予 TeamsUpgradePolicy 实例，它将将首先检查，以确保 TeamsAppPolicy 正确配置所需的模式。 如果没有，授予将失败并解释如何必须先设置其他策略产生错误。 

直到 TeamsAppPolicy 可用，TeamsUpgradePolicy 本质上控制呼叫和聊天，以及会议安排 （如公开通过 Outlook 加载项） 的路由。 因为团队的客户端行为尚不就地，并非所有模式都启用现代门户中。 从路由的角度看，SfBOnly、 SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 模式是相同的。 



## <a name="action-required-for-organizations-that-are-using-modelegacy-andor-teamsinteroppolicy"></a>无需执行操作的使用模式组织 = 旧和/或 TeamsInteropPolicy
使用模式的客户 = TeamsUpgradePolicy 中的旧 (策略实例 = NoUpgrade 或策略实例 = NotifyForTeams) 必须更新其配置要使用的策略与旧之外的模式。  此外，使用 TeamsInteropPolicy 客户应移除此策略的任何工作分配，因为它不再由系统，除在旧模式下，即将弃用。  请注意，它不再可以授予旧模式。 将在将来删除旧模式和 TeamsInteropPolicy。

所需的操作：
 - 使用用户的 TeamsInteropPolicy 客户*不*在旧模式下： 策略不影响以及它的建议您删除的任何用户级别分配和仅使用默认值使用全局策略。
 - 使用旧模式 TeamsInteropPolicy 传送到 SfB (DisallowOverrideCallingSfbChatSfb) 的客户： 这些组织应改用在 TeamsUpgradePolicy 中使用 SfB 模式 (SfBOnly，SfBWithTeamsCollab，SfbWithTeamsCollabAndMeetings) 之一。 从路由的角度看，这些模式任一行为与使用旧模式 TeamsInteropPolicy 传送到 SfB 相同。
  - 使用旧模式 TeamsInteropPolicy 传送到团队 (DisallowOverrideCallingTeamsChatTeams) 的客户： 这些组织应切换到 TeamsOnly 模式。  从路由的角度看，这将是具有相同的。 一个不同之处在于，仅在工作组模式中的用户将不再能够发起聊天和呼叫，也不能在 Skype for Business 中安排会议。 但是，他们仍可以加入任何 Skype 业务会议。


 **Microsoft 请求客户删除通过 2018 年 11 月 15，所有使用旧模式。** 一段时间后，Microsoft 走实例与模式 TeamsUpgradePolicy = 旧。</br> 


## <a name="detailed-mode-descriptions"></a>详细的模式说明
</br>
</br>

|模式|解释|
|---|---|
|**群岛**</br>（默认值）|单个用户运行业务和团队-并行这两个 Skype。 此用户：</br><ul><li>可以启动聊天和 VOIP 呼叫中任一 Skype 业务或团队的客户端。 注意： 具有 for Business 的 Skype 用户驻留在本地无法启动从工作组与另一个 Skype 的企业用户取得联系。<li>接收聊天和 Skype for Business 中发起通过其 Skype 业务客户端中的其他用户的 VOIP 呼叫。<li>接收聊天链接如果它们位于*同一租户*中团队发起通过其团队客户端中的另一个用户的 VOIP 呼叫。<li>接收聊天和它们是否在*联盟的租户*，团队中其 Skype 业务客户端中的其他用户发起的 VOIP 呼叫。 <li>具有 PSTN 功能如下所述：<ul><li>如果用户驻留在 Skype 业务本地，启动和 Skype for Business 中收到 PSTN 呼叫。<li>如果用户驻留 online，用户具有电话系统，这种情况下用户：<ul><li>发起和接收团队中的 PSTN 呼叫，如果对用户配置直接路由<li>发起和接收 Skype for Business 中的 PSTN 呼叫，如果用户已制定 MS 调用计划或连接到 PSTN 网络通过任一 Skype 商务云连接器版或 Skype 的内部部署业务服务器 （混合语音）</ul></ul><li>可以安排会议在团队或 Skype for Business 中的 （和默认情况下将看到两个插件）。<li>可以加入业务或团队会议; 任何 Skype会议将在各自的客户端中打开。</ul>|
|**SfBOnly**|单个用户运行仅 for Business 的 Skype。 此用户：</br><ul><li>可以启动聊天和仅从 for Business 的 Skype 调用。<li>收到任何聊天/呼叫中的业务客户端，其 Skype 无论其中启动，除非发起者团队用户拥有 for Business 的 Skype 驻留在本地。*<li>可以安排仅 Skype 业务会议，但可以加入 Skype 业务或团队的会议。</br>* 与内部部署用户使用群岛模式不建议在组合与 SfBOnly 模式中的其他用户。 如果具有 for Business 的 Skype 的团队用户驻留在本地启动呼叫或向 SfBOnly 用户聊天，SfBOnly 用户无法连接到并接收错过的聊天呼叫 email.*|
|**SfBWithTeamsCollab**|单个用户运行业务和团队-并行这两个 Skype。 此用户：</br><ul><li>具有 SfBOnly 模式中的用户的功能。<li>工作组已启用仅对组协作 （通道）;聊天/呼叫/会议安排将被禁用。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**|单个用户运行业务和团队-并行这两个 Skype。 此用户：<ul><li>已在 SfBOnly 模式下的聊天和用户的呼叫功能。<li>已启用组协作的团队 （通道-包括通道对话）;聊天和呼叫将被禁用。<li>可以安排仅团队会议，但可以加入 Skype 业务或团队的会议。</ul>|
|**TeamsOnly**</br>（需要 SfB Online 主页）|单个用户运行仅团队。 此用户：<ul><li>接收任何聊天并中调用他们团队的客户端，而不管在启动。<li>可以启动聊天和仅来自团队呼叫。<li>可以安排会议仅在工作组中的，但可以加入 Skype 业务或团队的会议。<li>可以继续使用 Skype 业务 IP 电话。</ul> |
|**旧**</br>（已过时）|此模式在转换到 TeamsUpgradePolicy TeamsInteropPolicy 期间用来确保一致的体验作为软件更改推出。既然完全支持 TeamsUpgradePolicy 不再需要此模式。 使用模式的客户 = 旧必须更新其配置上使用的其他模式。|
|||




## <a name="related-topics"></a>相关主题

[Get CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradepolicy?view=skype-ps)

[授予 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Get CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsinteroppolicy?view=skype-ps)

[授予 CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsinteroppolicy?view=skype-ps)

[删除 CsTeamsInteropPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsinteroppolicy?view=skype-ps)

[Get CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradeconfiguration?view=skype-ps)

[新 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsupgradepolicy?view=skype-ps)

[删除 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsupgradepolicy?view=skype-ps)

[设置 CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradeconfiguration?view=skype-ps)

[设置 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsupgradepolicy?view=skype-ps)
