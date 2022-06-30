---
title: 与 Skype for Business 共存
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: Teams & Skype for Business之间的共存行为，包括路由参数、聊天&呼叫路由、聊天&来自预先存在的线程的调用，&状态。
ms.openlocfilehash: bd3bd0c2cfad9dc06ae53ae6e26496fb48561874
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562391"
---
# <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

Skype for Business和 Teams 客户端之间的共存和互操作性由共存模式控制。 有关详细信息，请参阅[使用 Teams 和 Skype for Business 的组织迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)。 2021 年 7 月 31 日 Skype for Business Online 停用后，驻留在云中的用户始终是 TeamsOnly 用户。 不再可以将 TeamsOnly 以外的共存模式分配给联机用户。 除 TeamsOnly 之外的共存模式仅与部署 Skype for Business Server 或 Lync Server 2013 的组织相关。 在本文中，对“Skype for Business Server”的任何引用也适用于 Lync Server 2013。


## <a name="determining-a-users-coexistence-mode"></a>确定用户的共存模式
组织中没有任何本地部署Skype for Business Server的所有用户都是 TeamsOnly 模式，租户的有效模式也是 TeamsOnly。 可以通过查看租户或使用 Teams PowerShell 的用户的 TeamsUpgradeEffectiveMode 属性来确认这一点。   在 2021 年 7 月 31 日 Skype for Business Online 停用之前，组织能够更改用户或租户的共存模式。 这不再可能，但本地部署Skype for Business Server的组织除外，这些组织不得具有 TeamsOnly 的租户范围模式。 如果 TeamsUpgradePolicyIsReadOnly = 用户或租户上的“ModeAndNotifications”，则可以确认无法再更改共存模式。   (任何用户上的 TeamsUpgradePolicyIsReadOnly 将具有与租户值相同的值。)   


 ```powershell
 //Check if Tenant is TeamsOnly and if mode is read only.
$t=Get-CsTenant
$t|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications

 //Check if user is TeamsOnly and if mode is read only.
$u=Get-CsOnlineUser
$u|fl TeamsUpgradeEffectiveMode, TeamsUpgradePolicyIsReadOnly

TeamsUpgradeEffectiveMode  : TeamsOnly
TeamsUpgradePolicyIsReadOnly: ModeAndNotifications
 ```

在部署Skype for Business Server的组织中，TeamsUpgradePolicy 的租户全局策略可以具有 *TeamsOnly 以外的* 任何模式。 允许的模式为： *SfBOnly*、 *SfBWithTeamsCollab* 和 *SfBWithTeamsCollabAndMeetings*。 还可以直接为用户分配 TeamsUpgradePolicy 实例，这将取代租户全局策略。  云中托管的用户必须是 TeamsOnly，而本地用户必须是 TeamsOnly 以外的任何模式。  如果未为用户分配 TeamsUpgradePolicy 实例，则用户将从租户全局策略接收值。 

## <a name="routing-parameters"></a>路由参数

收件人的共存模式决定了聊天、呼叫和状态的行为，无论是在租户中还是在联合租户之间。 如果发件人使用 Teams，则在创建新的会话线程时会做出路由决策。 创建会话线程后，其路由不会更改，并且会保留创建线程时确定的路由方法。

线程路由方法包括：

- *本机* 用于 Teams 到 Teams 的租户内对话
- Teams 在租户中Skype for Business会话的 *互操作*
- 当两个用户都具有 TeamsOnly 模式时，本 *机联合* 在租户之间进行联合会话。 
- *互操作联合* 在依赖于 Skype for Business 和 Teams 之间的互操作的租户之间进行联合对话。

> [!NOTE]
> - 当接收方和发件人都具有 TeamsOnly 模式时，无论是在同一租户还是联合方案中，都会发生本机对话。 对话将是一种本机聊天体验，其中包括所有丰富的消息传送和通话功能。 如果要了解更多信息，请阅读 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。 
> - 如果任一对话参与者没有 TeamsOnly 模式，则会话是具有仅文本消息的互操作体验。
> - 多租户云中的 TeamsOnly 用户与特殊云环境之间的联合通信 (例如，政府云) 将显示为互操作联合聊天。


创建新会话时，确定线程路由方式的因素包括：

- 收件人的共存模式
- 发件人使用的客户端
- 对话是租户内还是联合
- 对话是否可能。 如果用户的Skype for Business帐户托管在本地，则该用户不能将 Teams 客户端用于租户内互操作性或联合身份验证。 该用户只能使用Skype for Business客户端进行互操作性和联合。 请注意，Teams 到 Teams 的通信始终可以在租户内进行。

## <a name="chat-and-call-routing"></a>聊天和呼叫路由
下表显示了在给定模式下哪个客户端将从发起方 () 的三个最左侧列接收调用。 哪个 cient 接收呼叫取决于发起方的模式、选择的客户端，以及Skype for Business帐户在本地或联机)  (所在的位置。

在以下表中：

- **Skype for Business** _ 表示以下任一模式：_SfBOnly*、*SfBWithTeamsCollab*、*SfBWithTeamsCollabAndMeetings*。
- *斜体文本* 突出显示互操作对话。
- **“不可能** ”表示无法进行聊天或通话的情况。 在这种情况下，发起人必须改用Skype for Business。 这也是 Microsoft 对本地和混合客户的规范性指导使用除 Islands (通常 SfBWithTeamsCollab) 之外的模式作为升级到 Teams 的起点的原因之一。


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通话的租户内路由

下表捕获租户内聊天和呼叫的路由，并且对未从预先存在的线程启动的新呼叫或聊天有效。 它描述哪个客户端将收到新的呼叫或聊天（如果由左侧的用户发起）到右侧的租户内收件人用户。  发送到 TeamsOnly 用户的消息将始终路由到 Teams。 发送到Skype for Business用户的消息将始终路由到Skype for Business。 发送到 Islands 用户的消息将始终路由到从中发送消息的同一客户端。


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 1a：租户内新聊天或呼叫路由到 TeamsOnly 模式收件人

<br>

|<br><br>模式|鼻祖<br><br>客户端|<br><br>&nbsp;Skype for Business homed|<br><br>Route->|TeamsOnly 收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;|Teams <br> *Teams*|
|Skype for Business | Skype for Business | 本地部署|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表 1b：租户内新聊天或呼叫路由到岛屿模式收件人

<br>

|<br><br>模式|鼻祖<br><br>客户端|<br><br>&nbsp;Skype for Business homed|<br><br>Route->|岛屿收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|孤岛| Teams <br> Skype for Business|本地部署<br>本地部署|&boxv;<br>&boxv;| Teams <br> Skype for Business|
|Skype for Business |Skype for Business | 本地部署|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>表 1c：以Skype for Business模式向收件人进行租户内新聊天或呼叫路由

<br>

|<br><br>模式|鼻祖<br><br>客户端|<br><br>&nbsp;Skype for Business homed|<br><br>Route->|Skype for Business收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;| **不可能** <br> Skype for Business|
|Skype for Business | Skype for Business| 本地部署|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>用于新聊天或通话的联合路由

下表捕获联合呼叫和聊天的路由，对新呼叫或聊天有效。 他们描述哪个客户端将收到新的呼叫或聊天（如果由左侧用户发起）到右侧的联合目标用户。 总之，如果如上所述可以进行对话，则发送到 TeamsOnly 用户的消息将始终登陆 Teams;发送到Skype for Business模式的消息用户始终会进入Skype for Business;发送到 Islands 用户的消息将始终在Skype for Business中登陆，而不考虑从中发送这些消息的客户端。 

联合聊天和呼叫的路由不同于租户内路由，因为 Islands 用户始终会在Skype for Business中接收联合通信。 这是因为联合合作伙伴可能尚未使用 Teams。 路由到任何岛屿模式的Skype for Business可确保始终接收消息。  如果预期收件人不使用 Teams，则路由到 Teams 可能会导致错过通信。 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 2a：联合新聊天或呼叫路由到 TeamsOnly 模式收件人

<br>

|<br><br>模式|鼻祖<br><br>客户端|<br><br>Skype for Business主页|<br><br>Route->|TeamsOnly 收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|Teams|
|孤岛|Teams <br> Skype for Business|本地部署 <br> 本地部署|&boxv;<br>&boxv;|**不可能** <br> *Teams*|
|Skype for Business |Skype for Business|本地部署|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表 2b：联合新聊天或呼叫路由到 Islands 收件人

<br>

|<br><br>模式|鼻祖<br><br>客户端|<br><br>Skype for Business主页|<br><br>Route->|岛屿收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;| **不可能** <br> Skype for Business|
|Skype for Business |Skype for Business| 本地部署|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>表 2c：在Skype for Business模式下联合新聊天或呼叫路由给收件人

<br>

|<br><br>模式|鼻祖<br><br>客户端|<br><br>Skype for Business主页|<br><br>Route->|Skype for Business收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;|**不可能** <br> Skype for Business|
|Skype for Business |Skype for Business|本地部署|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>来自预先存在的线程的聊天和调用

### <a name="from-teams"></a>从 Teams

从 Teams 中预先存在的会话线程开始的呼叫或聊天的路由方式与该线程相同。 如果 Teams 中预先存在的线程是本机线程 (即路由到 Teams) ，则来自该线程的其他聊天消息和呼叫将转到 Teams。 如果它是一个互操作线程 (即路由到Skype for Business) ，则假设路由选项) 可用，则其他聊天消息和呼叫将转到Skype for Business (。

> [!NOTE]
> Teams 中预先存在的线程可能不再可路由，例如，当线程是已升级到 Teams 的用户的互操作线程时。 由于该线程是作为互操作线程创建的，因此会路由到Skype for Business，但该用户不再可以使用Skype for Business进行聊天和呼叫。 在这种情况下，线程将被禁用，不允许进一步通信。

### <a name="from-skype-for-business"></a>从Skype for Business

Skype for Business线程不会持续超过 10 分钟的 SIP 会话超时。 SIP 会话过期之前，Skype for Business中现有线程的聊天和调用将以与线程相同的方式路由。 从 SIP 会话超时之外Skype for Business现有线程的呼叫和聊天将路由到远程方的Skype for Business，而不管原始线程来自另一方的哪个客户端。

## <a name="presence"></a>状态

在某些用户使用 Teams 客户端，而另一些用户使用Skype for Business客户端的情况下，其中一些用户可能同时使用这两个客户端。 请务必了解，状态是根据用户的共存模式发布的。 例如，如果发起人的聊天或呼叫应落在目标的Skype for Business客户端上，则应向发起人显示Skype for Business客户端的状态。 如果它应位于目标的 Teams 客户端上，则应显示 Teams 客户端的状态。

基于用户的共存模式共享状态，如下所述：

- 如果用户处于 TeamsOnly 模式，则任何其他用户 (在 Teams 中还是Skype for Business) 会看到 TeamsOnly 用户的 Teams 状态
- 如果用户处于 SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) 的任何Skype for Business (模式，则在 Teams 或Skype for Business) 中 (的任何其他用户都将看到该Skype for Business用户的Skype for Business状态
- 如果用户处于“岛屿”模式，则 Teams 中的状态和Skype for Business中的状态是独立的 (这些值不需要匹配) 其他用户将看到一个或另一个存在 Islands 用户，具体取决于他们是在同一租户中还是在同一租户中，以及他们使用哪个客户端
  - 在 Teams 中，同一租户中的任何其他用户都将看到 Islands 用户的 Teams 状态;这与上面的租户内路由表对齐
  - 在 Teams 中，联合租户中的任何其他用户都将看到 Islands 用户的Skype for Business状态;这与上面的联合路由表一致
  - 从Skype for Business，任何其他用户将看到 Islands 用户的Skype for Business状态 (租户内和联合) ;这与上面的路由表一致

### <a name="in-tenant-presence"></a>租户内状态

发送到 TeamsOnly 用户的消息将始终登陆 Teams。 发送到Skype for Business模式用户的消息将始终进入Skype for Business，如果可以按上述方式进行对话。 发送给 Islands 用户的消息将始终登陆其源自的客户端。

该表描述了观察程序将看到发布服务器的状态，具体取决于发布服务器的模式以及观察程序 (新线程) 的客户端。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表 3：租户内状态 (新线程) 

<br>

|观察家<br><br>客户端|<br><br>Route->|<br><br>孤岛|Publisher<br><br>Skype for Business|<br>Teams Only|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>联合状态

联合状态基于表 2 中所示的联合可访问性。  下表描述了观察程序将看到发布服务器的状态，具体取决于发布服务器的模式以及观察程序 (的新线程) 的客户端。 实际上，观察程序的客户端在此阶段在联合身份验证方面没有区别。

#### <a name="table-4-federated-presence-new-thread"></a>表 4：联合状态 (新线程) 

<br>

|观察家<br><br>客户端|<br><br>Route->|<br><br>孤岛|Publisher<br><br>Skype for Business|<br><br>Teams Only|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>预先存在的线程中的状态

若要使预先存在的线程中的状态和可访问性保持一致，目标在该线程中公开的状态需要与线程的路由保持一致，前提是路由是可能的。  特别是，如果你以前具有持久互操作对话线程的收件人已升级到 Teams，则该线程将不再反映准确的状态，并且将不再可路由。 应启动新线程。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>与由世纪互联运营的Office 365联合和互操作

当多租户Office 365用户处于仅限 Teams 模式时，支持多租户Office 365与由 21Vianet 运营的Office 365之间的联合和互操作。 在这种情况下，21Vianet 运营的Office 365中的 Skype for Business Online 用户将能够通过聊天和呼叫与多租户Office 365中的仅 Teams 用户通信。 下表显示了此配置中支持的方案：
 
|使用场景|起源|收件人|是否支持？|
|---|---|---|---|
|状态|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|是<br>是|
|聊天|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|是 (1：1 仅) <br>是 (1：1 仅) |
|音频呼叫|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|是 (1：1 仅) <br>是 (1：1 仅) |
|视频呼叫|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|是 (1：1 仅) <br>是 (1：1 仅) |
|屏幕共享|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |是 (通过提升的 Teams 会议) <br>是 (通过提升的Skype for Business会议) |
|||||


## <a name="related-links"></a>相关链接
[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[视频：管理Skype for Business和 Teams 之间的共存和互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
