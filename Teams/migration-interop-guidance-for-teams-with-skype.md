---
title: 使用团队一起 Skype for Business 的组织的迁移和互操作性指南
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
ms.openlocfilehash: 16a10f73614626a422bf6b869d08c4019982d0d2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375890"
---
# <a name="migration-and-interoperability-guidance-for-organizations-using-teams-together-with-skype-for-business"></a>使用团队一起 Skype for Business 的组织的迁移和互操作性指南

2018 年 4 月版 Microsoft 阐明了其迁移到团队从 Skype 商业和如何这些两个客户端可以共同存在给定用户的指南。 此时，我们将宣布计划的更改以简化可管理性和提高最终用户满意度。 从那时起，Microsoft 已传递到管理员的用户体验，与该计划一致的更新。 本文档中的指南反映这些更改。

如上文宣布，即将弃用 TeamsInteropPolicy。 其功能已整合到 TeamsUpgradePolicy。 使用"共存模式"，如由 TeamsUpgradePolicy 托管互操作和迁移。 控制可以选择的用户的模式，这两个路由的传入呼叫和聊天和用户是否计划团队或 Skype for Business 中的会议。  推出，与即将开始的 TeamsAppPermissionsPolicy 一起使用，模式将也控制用户可在哪些客户端中启动聊天和呼叫。 

配置 TeamsInteropPolicy 不再是必需的。 它不采用除非 TeamsUpgradePolicy 具有模式 = 旧。  TeamsUpgradePolicy 支持过程完成之后，客户应更新其配置为使用旧之外模式。 授予实例 TeamsUpgradePolicy 与 mode = 旧默认情况下被阻止。

## <a name="fundamental-concepts"></a>基本概念

1.  *互操作*： 1 对 1 业务用户 Lync/Skype 和团队用户之间的通信。

2.  *联合身份验证*： 不同租户中的用户之间的通信。

3.  所有用户具有基础 Skype 的业务帐户"驻留"之一 online 的团队或者内部部署：
    - 已为业务 Online 使用 Skype 的用户使用其现有的 online 帐户。
    - 已使用 Skype 业务/Lync 内部部署的用户使用其现有的内部部署帐户。
    - 我们不能为其检测现有 Skype 业务帐户的用户将有 Skype 业务联机时创建团队用户自动配置的帐户。 业务许可证没有 Skype 是必需的。

4.  如果必须在本地部署的任一 Skype 适用于商务或 Lync，并且您希望为团队用户这些用户，您必须至少确保 Azure AD 连接正在同步 msRTCSIP DeploymentLocator 属性到 AAD，因此该团队/Skype for Business联机正确检测您在本地环境。 此外，将任何用户移至仅团队模式 （即，升级用户），*则必须配置为业务混合模式的 Skype*。

5.  适用于业务用户之间团队和 Skype 的互操作才可能*如果团队用户联机驻留在 for Business 的 Skype*。 Skype 可以位于企业用户是本地 （和需要业务混合配置 Skype） 或联机。 位于业务本地 Skype 的用户可以使用团队群岛模式 （定义此文档中的更高版本），但不是能使用互操作的团队或 for Business 使用 Skype 的其他用户与联盟。  

6.  升级到团队的用户 (即，向其授予与模式 TeamsUpgradePolicy = TeamsOnly)，用户必须联机驻留在 for Business 的 Skype。 这是确保互操作、 联盟和团队用户的完整管理所需的。 若要升级用户都驻留在内部部署，使用`Move-CsUser`从内部部署管理工具到第一次移动用户对 Skype 业务 online。 然后 TeamsUpgradePolicy 和 TeamsInteropPolicy 授予联机用户或使用现代门户分配 TeamsOnly 模式。 一次的业务服务器 2015年一起提供的 Skype CU8，客户可以只使用新`-MoveToTeams`中切换`Move-CsUser`其结合使用，这 2 个步骤 1 到。

7.  管理升级和互操作的核心策略是 TeamsUpgradePolicy。 TeamsInteropPolicy 已不再使用除时使用 TeamsUpgradePolicy 模式 = 旧，并使用模式的客户 = 旧应更新其配置的 TeamsUpgradePolicy 使用不同的模式。  授予模式 = 旧现在阻止默认情况下，尽管管理员可以覆盖此使用`-Force`目前。 最终，`-Force`开关将删除和授予模式 = 旧将不能进行。 

8.  使用团队电话系统的功能和用户必须在 TeamsOnly 模式 （即，业务 online 驻留在 Skype 和升级到团队） 中，它们也必须配置 Microsoft 电话系统[直接路由](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Direct-Routing-is-now-Generally-Available/ba-p/210359#M1277)(其中，可以使用电话系统与您拥有 SIP 中继和 SBC） 或 Office 365 调用规划。   

9.  安排音频会议的团队会议 （电话拨入式或通过 PSTN 电话拨出） 是当前仅适用于位于 Skype 业务 online 的用户。 与业务帐户在本地 Skype 支持团队用户正在点击。


## <a name="coexistence-modes"></a>共存模式

若要简化可管理性和提高最终用户满意度，互操作和迁移现在管理基于使用 TeamsUpgradePolicy"共存模式"。 用户模式下确定：

- *传入路由*： 中的客户端 （工作组或业务的 Skype） 执行传入聊天和调用园地？ 
- *会议日程安排*： 哪项服务都用于安排新的会议和确保正确的外接程序在 Outlook 中存在。 请注意 TeamsUpgradePolicy 不管理会议加入。 用户可以始终*加入*任何会议，无论是业务会议或团队会议 Skype。
- *客户端体验*： 哪项功能均可在工作组和/或 Skype 业务客户端？ 这被实现 TeamsOnly 模式。 取决于即将开始的 TeamsAppPermissionsPolicy 支持其他模式。 在此新策略后，TeamsUpgradePolicy 将具有依赖项以确保团队为所需的模式正确配置。

下面列出了计划的模式。 SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 将允许混合的使用这两个客户端，但没有重叠的功能。 群岛模式允许使用情况的两个客户端，但包含重叠的功能。 例如，在群岛模式下，用户无法启动适用于商务或团队中任一 Skype 聊天，但在 SfBWithTeamsCollab，他们可以仅聊天中 for Business 的 Skype。 请注意，不是所有模式尚未完全可用。  
</br>
</br>

|模式|路由行为|会议日程安排|客户端体验|
|---|---|---|---|
|群岛|传入的 VOIP 呼叫和聊天园地中为原始发件人<sup>1</sup>的同一客户端|两者|最终用户可以发起呼叫和聊天从任一客户端，并可以安排从任一客户端的会议。|
|SfBOnly|传入呼叫和聊天路由至 Skype for Business|Skype for Business 仅|最终用户可以发起呼叫以及仅从 for Business 的 Skype 聊天和仅业务会议安排 Skype。 （还未实施）|
|SfBWithTeamsCollab<sup>2</sup>|传入呼叫和聊天路由至 Skype for Business|Skype for Business 仅|最终用户可以发起呼叫以及仅从 for Business 的 Skype 聊天和仅业务会议安排 Skype。 他们还可以在工作组中使用通道。 （还未实施）|
|SfBWithTeamsCollabAndMeetings<sup>3</sup>|传入呼叫和聊天路由至 Skype for Business|仅团队|最终用户可以发起呼叫，并从业务仅和唯一的 Skype 聊天安排团队会议。 他们还可以在工作组中使用通道。 （还未实施）|
|TeamsOnly|传入呼叫和聊天路由至团队|仅团队|最终用户可以发起呼叫以及仅来自团队聊天。 Skype for Business 才可用于加入会议。|
|旧|路由基于 TeamsInteropPolicy|不会影响|没有任何影响。 这是临时的简化从 TeamsInteropPolicy 过渡到 TeamsUpgradePolicy 模式。 完全支持 TeamsUpgradePolicy，因此客户不应使用此模式不再和应更新其配置为非旧的模式。 |
|||||

**说明：**

<sup>1</sup>的 PSTN 呼叫的详细信息，请参阅本文档末尾的表。

<sup>2</sup> SfBWithTeamsCollab 未尚未公开中管理用户体验因为其当前不不同 SfBOnly 模式行为。 客户端体验传递时，此模式将提供。

<sup>3</sup> SfBWithTeamsCollabAndMeetings 尚不可用。 

## <a name="teamsupgradepolicy-managing-migration-and-co-existence"></a>TeamsUpgradePolicy： 管理迁移和共存

TeamsUpgradePolicy 公开三个属性。 主属性是模式和 NotifySfbUsers。 操作旧参数，是完全冗余的模式和 NotifySfbUsers 的组合。
</br>
</br>

|参数|类型|允许的值</br>（默认斜体中）|说明|
|---|---|---|---|
|模式|枚举|*群岛*</br>TeamsOnly</br>SfBOnly</br>SfBWithTeamsCollab</br>旧|指示客户端应中运行的模式。 如果模式 = 旧，使用此策略的组件将还原为考虑 TeamsInteropPolicy。 TeamsUpgradePolicy 现在完全支持，客户应更新其配置使用模式旧之外。|
|NotifySfbUsers|Bool|*False*或 true|指示是否在业务客户端通知用户团队很快将替换 for Business 的 Skype Skype 中显示的标题。 这不能为 true 如果模式 = TeamsOnly。|
|操作|枚举|*无*、 通知，请升级|这是将最终删除旧参数，因为它是冗余的模式和 NotifySfbUsers 的组合。 |
|||||

团队提供的内置的只读策略通过 TeamsUpgradePolicy 所有相关的实例。 因此，仅获取并且可授予 cmdlet。 下面列出了内置的实例。
</br>
</br>

|Identity |模式|NotifySfbUsers|操作|备注|
|---|---|---|---|---|
|群岛|群岛|False|无||
|IslandsWithNotify|群岛|True|通知||
|SfBOnly|SfBOnly|False|无|现在，此模式实际上是设置首选的客户端相同 = SfB。 我们将来预期这将限制团队功能。|
|SfBOnlyWithNotify|SfBOnly|True|通知|现在，此模式实际上是设置首选的客户端相同 = SfB。 我们将来预期这将限制团队功能。|
|SfBWithTeamsCollab|SfBWithTeamsCollab|False|无|此模式在 PowerShell 层存在但不是在管理用户体验中尚未公开。 从路由的角度看，这是与 SfBOnly 模式相同。 可用 TeamsAppPolicy 时，这将只允许团队应用程序中的通道。|
|SfBWithTeamsCollabWithNotify|SfBWithTeamsCollab|True|通知|此模式在 PowerShell 层存在但不是在管理用户体验中尚未公开。 从路由的角度看，这是与 SfBOnly 模式相同。 可用 TeamsAppPolicy 时，这将只允许团队应用程序中的通道。|
|UpgradeToTeams|TeamsOnly|False|升级|将用户升级到团队，并阻止聊天、 电话和在 Skype for Business 中计划的会议，请使用此模式。|
|全局|旧|False|无|模式将近期更新到群岛。|
|NoUpgrade|旧|False|无|最终将停用此实例。|
|NotifyForTeams|旧|True|通知|最终将停用此实例。|
||||||

向单个用户或在租户范围内，可以授予这些策略实例。 例如：
- 若要将用户 ($SipAddress) 升级到团队，授予"UpgradeToTeams"实例：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress`
- 若要升级的整个租户，省略 identity 参数从授予命令：</br>
`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`



## <a name="teamsinteroppolicy-being-retired"></a>正在停用的 TeamsInteropPolicy 

如前所述，已由 TeamsUpgradePolicy 取代 TeamsInteropPolicy。 已更新以前适用 TeamsInteropPolicy 的所有组件，以改为服从 TeamsUpgradePolicy。 

Microsoft 以前引入"旧"模式，以便从 TeamsInteropPolicy 转换为 TeamsUpgradePolicy，在旧模式，理解 TeamsUpgradePolicy 的路由组件将还原回为 TeamsInteropPolicy。 路由现在完全支持 TeamsUpgradePolicy 并且不再需要使用旧模式。 客户使用旧模式应更新其配置的 TeamsUpgradePolicy 使用其他模式之一。 

仅 TeamsInteropPolicy 下面列出的三个特定实例所支持都会提醒客户仍在使用旧模式。 每种情况下，CallingDefaultClient 的值匹配的 ChatDefaultClient，值和 AllowEndUserClientOverride 始终为 false。 
</br>
</br>
**使用 TeamsUpgradePolicy 模式时支持实例 TeamsInteropPolicy = 旧**
|Identity |AllowEndUserClientOverride|CallingDefaultClient|ChatDefaultClient|
|---|---|---|---|
|`DisallowOverrideCallingDefaultChatDefault`|False|默认|默认|
|`DisallowOverrideCallingSfbChatSfb`|False|Sfb|Sfb|
|`DisallowOverrideCallingTeamsChatTeams`|False|Teams|Teams|
|||||

使用以下 cmdlet 语法，其中 $policy 是标识的上述值之一：`Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

## <a name="federation-considerations"></a>联合身份验证的注意事项

从工作组 for Business 使用 Skype 的另一个用户的联盟要求 for Business 的 Skype 联机托管团队用户。 最终，用户驻留在 Skype 的业务本地团队都将能够与其他团队用户联盟。

TeamsUpgradePolicy 控制传入的联盟的聊天和呼叫路由。 为了方便启动与您的组织中的用户的联盟的通信其他组织，建议选择专门路由之一模式到业务或团队，而群岛 Skype。
</br>
|将呼叫路由和聊天到...|授予 TeamsUpgradePolicy 实例</br> 使用这些模式之一
|---|---|
|Skype for Business|SfBOnly，SfBWithTeamsCollab， </br>SfBWithTeamsCollabAndMeetings|
|Teams|TeamsOnly |
|||

当收件人群岛模式中时，聊天，并从联盟的用户园地 SfB 中调用。

## <a name="completing-the-transition-to-mode-management"></a>完成转换到模式管理

今年更高版本，Microsoft 计划引入新策略的类型，TeamsAppPermissionsPolicy，以控制哪些部分团队客户端启用 （如 IM、 会议、 聊天、 通道）。 要启用/禁用团队中的工作负荷的新策略何时有空，将更新 TeamsUpgradePolicy，，以便当管理员尝试向用户授予 TeamsUpgradePolicy 实例，它将将首先检查，以确保 TeamsAppPolicy 正确配置所需的模式。 如果没有，授予将失败并解释如何必须先设置其他策略产生错误。 

直到 TeamsAppPolicy 可用，TeamsUpgradePolicy 本质上控制呼叫和聊天，以及会议安排 （如公开通过 Outlook 加载项） 的路由。 因为团队的客户端行为尚不就地，并非所有模式都启用现代门户中。 从路由的角度看，SfBOnly、 SfBWithTeamsCollab 和 SfBWithTeamsCollabAndMeetings 模式是相同的。 

## <a name="action-required-for-organizations-that-have-already-used-teamsinteroppolicy"></a>已使用 TeamsInteropPolicy 的组织所需的操作

仍在使用旧模式任何客户必须执行以下操作：

1. 确保具有 TeamsInteropPolicy 用户分配这些三个内置情况下，之一的哪些 CallingDefaultClient = ChatDefaultClient，和哪些 AllowEndUserClientOverride = false。 这些实例是：
   </br>
   </br>

   |Identity |AllowEndUserClientOverride |CallingDefaultClient|ChatDefaultClient|
   |---|---|---|---|
   |`DisallowOverrideCallingDefaultChatDefault`|False|默认|默认|
   |`DisallowOverrideCallingSfbChatSfb`|False|Sfb|Sfb|
   |`DisallowOverrideCallingTeamsChatTeams`|False|Teams|Teams|
   |||||

    使用以下 cmdlet 语法，其中 $policy 是标识的上述值之一：

    `Grant-CsTeamsInteropPolicy -PolicyName $policy -Identity $SipAddress`

    **Microsoft 请求客户按 2018 年 6 月 30，更新其策略。** 一段时间后，Microsoft 走 TeamsInteropPolicy 其他实例。</br> 
    ***不更新这些实例之一的组织将最终让其自动更新为这些实例之一的用户。我们很明显首选客户此操作，以便您可以选择什么是最适用于您的用户。***

2. 如果您自定义内置的全局策略，撤销此操作。 您的全局策略应具有以下值：
   </br>
   </br>

    |参数|值|
    |---|---|
    |`AllowEndUserClientOverride`|False|
    |`CallingDefaultClient`|默认|
    |`ChatDefaultClient`|默认|
    |||

    如果任何值都与以上不同，运行以下命令以删除所有租户特定的自定义：

    `Grant-CsTeamsInteropPolicy -PolicyName $null`

## <a name="detailed-mode-descriptions"></a>详细的模式说明
</br>
</br>

|模式|解释|
|---|---|
|**群岛**|单个用户运行业务和团队-并行这两个 Skype。 此用户：</br><ul><li>可以启动聊天和 VOIP 呼叫中任一 Skype 业务或团队的客户端。 注意： 具有 for Business 的 Skype 用户驻留在本地无法启动从工作组与另一个 Skype 的企业用户取得联系。<li>接收聊天和 Skype for Business 中发起通过其 Skype 业务客户端中的其他用户的 VOIP 呼叫。<li>接收 VOIP 由其团队客户端中的另一个用户团队中发起的呼叫。<li>接收聊天中的其他用户启动团队中：<ul><li>Skype for Business 提供联机驻留收件人并将其从不登录到团队<li>其他所有情况下的团队。</ul><li>具有 PSTN 功能如下所述：<ul><li>如果用户驻留在 Skype 业务本地，启动和 Skype for Business 中收到 PSTN 呼叫。<li>如果用户驻留 online，用户具有电话系统，这种情况下用户：<ul><li>发起和接收团队中的 PSTN 呼叫，如果对用户配置直接路由<li>发起和接收 Skype for Business 中的 PSTN 呼叫，如果用户已制定 MS 调用计划或连接到 PSTN 网络通过任一 Skype 商务云连接器版或 Skype 的内部部署业务服务器 （混合语音）</ul></ul><li>可以安排会议在团队或 Skype for Business 中的 （和默认情况下将看到两个插件）。<li>可以加入业务或团队会议; 任何 Skype会议将在各自的客户端中打开。</ul>|
|**SfBOnly**|单个用户运行仅 for Business 的 Skype。 此用户：</br><ul><li>可以启动聊天和仅从 for Business 的 Skype 调用。<li>收到任何聊天/呼叫中的业务客户端，其 Skype 无论其中启动，除非发起者团队用户拥有 for Business 的 Skype 驻留在本地。*<li>可以安排仅 Skype 业务会议，但可以加入 Skype 业务或团队的会议。</br>* 与内部部署用户使用群岛模式不建议在组合与 SfBOnly 模式中的其他用户。 如果具有 for Business 的 Skype 的团队用户驻留在本地启动呼叫或向 SfBOnly 用户聊天，SfBOnly 用户无法连接到并接收错过的聊天呼叫 email.*|
|**SfBWithTeamsCollab**|单个用户运行业务和团队-并行这两个 Skype。 此用户：</br><ul><li>具有 SfBOnly 模式中的用户的功能。<li>工作组已启用仅对组协作 （通道）;聊天/呼叫/会议安排将被禁用。</ul>|
|**SfBWithTeamsCollab</br>AndMeetings**</br>（已计划）|单个用户运行业务和团队-并行这两个 Skype。 此用户：<ul><li>已在 SfBOnly 模式下的聊天和用户的呼叫功能。<li>团队已启用组协作 （通道）;聊天和呼叫将被禁用。<li>可以安排仅团队会议，但可以加入 Skype 业务或团队的会议。</ul>|
|**TeamsOnly**</br>（需要 SfB Online 主页）|单个用户运行仅团队。 此用户：<ul><li>接收任何聊天并中调用他们团队的客户端，而不管在启动。<li>可以启动聊天和仅来自团队呼叫。<li>可以安排会议仅在工作组中的，但可以加入 Skype 业务或团队的会议。<li>可以继续使用 Skype 业务 IP 电话。</ul> |
|**旧**</br>（默认值）|此模式在转换到 TeamsUpgradePolicy TeamsInteropPolicy 期间用来确保一致的体验作为软件更改推出。既然完全支持 TeamsUpgradePolicy 不再需要此模式。 使用模式的客户 = 旧应更新其配置上使用的其他模式。|
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
