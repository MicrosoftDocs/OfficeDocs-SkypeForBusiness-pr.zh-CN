---
title: 与 Skype for Business 共存
author: serdarsoysal
ms.author: serdars
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
description: 用户之间的共存Teams & Skype for Business，包括路由参数、聊天&呼叫路由、聊天&来自预先存在的线程的呼叫、&状态。
ms.openlocfilehash: 1ed59546d871a7ac375061714ceedd67086818d1
ms.sourcegitcommit: 2ce417430b2aac770997daaf5ef5d844aa97fd84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60911826"
---
# <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

客户端和客户端Skype for Business Teams共存模式控制。 有关详细信息，请参阅[迁移和互操作性指南，](migration-interop-guidance-for-teams-with-skype.md)了解将 Teams 与 Skype for Business 一Skype for Business。 2021 年 7 Skype for Business 31 日停用 Skype for Business Online 后，云中的用户始终是 TeamsOnly 用户。 不再能够向联机用户分配除 TeamsOnly 外的其他共存模式。 TeamsOnly 外共存模式仅与在本地部署 Skype for Business Server Lync Server 2013 的组织相关。 本文中对"Skype for Business Server"的任何引用同样适用于 Lync Server 2013。


## <a name="determining-a-users-coexistence-mode"></a>确定用户的共存模式
组织中所有未在本地部署用户的用户Skype for Business Server TeamsOnly 模式，租户的有效模式也是 TeamsOnly。 这可以通过查看租户上的 TeamsUpgradeEffectiveMode 属性或使用 PowerShell 的用户Teams确认。   在 Skype for Business Online 于 2021 年 7 月 31 日停用之前，组织可以更改用户或租户的共存模式。 这不再可行，除非组织在本地部署 Skype for Business Server，但不得使用租户范围的 TeamsOnly 模式。 如果用户或租户上的 TeamsUpgradePolicyIsReadOnly = "ModeAndNotifications"，可以确认不再可更改共存模式。   (用户上的 TeamsUpgradePolicyIsReadOnly 的值与租户的 value.)   


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

在具有本地部署 Skype for Business Server 的组织中，TeamsUpgradePolicy 的租户全局策略可以具有除 *TeamsOnly 外的任何模式*。 允许的模式为：SfBOnly、SfBWithTeamsCollab 和 *SfBWithTeamsCollabAndMeetings。*   也可以直接为用户分配 TeamsUpgradePolicy 实例，这将取代租户全局策略。  托管在云中的用户必须是 TeamsOnly，本地用户必须是 TeamsOnly 外的任何模式。  如果未为用户分配 TeamsUpgradePolicy 实例，则用户会收到租户全局策略中的值。 

## <a name="routing-parameters"></a>路由参数

接收方的共存模式确定在租户中和跨联合租户的聊天、呼叫和状态行为。 如果发送方正在使用Teams，则当创建新的会话线程时，将做出路由决策。 创建会话线程后，其路由不会更改，并保留创建线程时确定的路由方法。

线程路由方法包括：

- *本地* Teams Teams租户内聊天
- *租户* 内Teams Skype for Business会话的互操作
- *当两个用户* 具有 TeamsOnly 模式时，跨租户联合对话的本机联合。 
- *跨租户* 的联合会话的互操作联合，这些租户依赖于 Skype for Business 和 Teams。

> [!NOTES]
> - 无论在同一租户还是联合方案中，当接收方和发送方同时具有 TeamsOnly 模式时，都会发生本机对话。 对话将是一种本机聊天体验，包括所有丰富的消息传送和呼叫功能。 如果要了解更多信息，请阅读 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。 
> - 如果任一对话参与者没有 TeamsOnly 模式，则对话是包含纯文本消息的互操作体验。
> - 多租户云和特殊云环境中 TeamsOnly 用户之间的联合通信 (例如，政府云) 显示为互操作联合聊天。


创建新会话时，决定线程路由方式的因素包括：

- 收件人的共存模式
- 发送方使用的客户端
- 聊天是租户内聊天还是联合会话
- 对话是否可行。 如果用户拥有本地Skype for Business帐户，该用户无法将 Teams 客户端用于租户内互操作性或联合。 该用户只能将 Skype for Business 客户端用于互操作性和联合。 请注意，Teams Teams始终可以与租户内通信。

## <a name="chat-and-call-routing"></a>聊天和呼叫路由
下表显示了给定模式下哪个客户端将接收来自发起方 (三个最左侧) 。 哪个科学家接收呼叫取决于发起方的模式、选择的客户端，以及 Skype for Business 帐户在本地或 (上) 。

在下列表中：

- **Skype for Business** _ 表示以下任何模式：_SfBOnly*、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings 。  
- *Italic 文本* 突出显示互操作对话。
- **"不可能** "表示无法聊天或通话的情况。 在这种情况下，发起Skype for Business必须改为使用。 这是 Microsoft 针对本地和混合客户的规范性指南使用非群岛 (模式（通常为 SfBWithTeamsCollab) ）作为他们升级到 Teams 的起点的原因之一。


### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通话的租户内路由

下表捕获租户内聊天和调用的路由，并且对于未从预先存在的线程启动的新呼叫或聊天有效。 它描述哪个客户端将接收新的呼叫或聊天（如果由左侧的用户发起）到右侧租户内收件人用户。  发送给 TeamsOnly 用户的消息将始终路由到Teams。 发送给用户Skype for Business的消息将始终路由到Skype for Business。 发送到群岛用户的消息将始终路由到发送这些消息的同一客户端。


#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 1a：租户内新聊天或呼叫路由到 TeamsOnly 模式收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>&nbsp;Skype for Businesshomed|<br><br>路由 -- >|TeamsOnly 收件人|
|---|---|---|:---:|---|
|TeamsOnly|Teams|Online|&boxv;|团队|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;|Teams <br> *Teams*|
|Skype for Business | Skype for Business | 本地部署|&boxv;|*Teams*|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表 1b：租户内新聊天或呼叫路由到岛屿模式收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>&nbsp;Skype for Businesshomed|<br><br>路由 -- >|群岛收件人|
|---|---|---|:---:|---|
|TeamsOnly|团队|Online|&boxv;|团队|
|孤岛| Teams <br> Skype for Business|本地部署<br>本地部署|&boxv;<br>&boxv;| 团队 <br> Skype for Business|
|Skype for Business |Skype for Business | 本地部署|&boxv;| Skype for Business|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-recipient-in-a-skype-for-business-mode"></a>表 1c：租户内新聊天或呼叫路由（以实时Skype for Business收件人）

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>&nbsp;Skype for Businesshomed|<br><br>路由 -- >|Skype for Business收件人|
|---|---|---|:---:|---|
|TeamsOnly|团队|Online|&boxv;|*Skype for Business*|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;| **不可能** <br> Skype for Business|
|Skype for Business | Skype for Business| 本地部署|&boxv;| Skype for Business|
||||||


### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或通话的联合路由

下表捕获联合呼叫和聊天的路由，并且对于新呼叫或聊天有效。 它们描述哪个客户端将收到新的呼叫或聊天（如果由左侧的用户发起）到右侧联合目标用户。 总之，如果如上文所述对话可行，发送给 TeamsOnly 用户的消息将始终位于Teams;发送到 Skype for Business 模式的用户始终会进入Skype for Business;发送到群岛用户的消息将始终位于Skype for Business，无论它们从哪个客户端发送。 

联合聊天和呼叫的路由不同于租户内路由，因为群岛用户始终在 Skype for Business。 这是因为联合合作伙伴可能尚未使用Teams。 路由到Skype for Business任何岛屿模式的路由可确保始终接收消息。  如果Teams目标接收者不使用通信，则路由到 Teams。 

#### <a name="table-2a-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 2a：联合的新聊天或呼叫路由到 TeamsOnly 模式收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>Skype for Business homed|<br><br>路由 -- >|TeamsOnly 收件人|
|---|---|---|:---:|---|
|TeamsOnly|团队|Online|&boxv;|团队|
|孤岛|团队 <br> Skype for Business|本地部署 <br> 本地部署|&boxv;<br>&boxv;|**不可能** <br> *Teams*|
|Skype for Business |Skype for Business|本地部署|&boxv;| *Teams*|
||||||


#### <a name="table-2b-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表 2b：联合的新聊天或呼叫路由到群岛收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>Skype for Business homed|<br><br>路由 -- >|群岛收件人|
|---|---|---|:---:|---|
|TeamsOnly|团队|Online|&boxv;|*Skype for Business*|
|孤岛|团队 <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;| **不可能** <br> Skype for Business|
|Skype for Business |Skype for Business| 本地部署|&boxv;| Skype for Business|
|||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-recipient-in-an-skype-for-business-mode"></a>表 2c：联合新聊天或呼叫路由到收件人（Skype for Business模式）

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>Skype for Business homed|<br><br>路由 -- >|Skype for Business收件人|
|---|---|---|:---:|---|
|TeamsOnly|团队|Online|&boxv;|*Skype for Business*|
|孤岛|Teams <br> Skype for Business| 本地部署 <br> 本地部署|&boxv;<br>&boxv;|**不可能** <br> Skype for Business|
|Skype for Business |Skype for Business|本地部署|&boxv;<br>&boxv;|Skype for Business|
||||||



## <a name="chats-and-calls-from-pre-existing-threads"></a>来自预先存在的线程的聊天和通话

### <a name="from-teams"></a>从 Teams

从对话中预先存在的聊天线程启动的Teams以与该线程相同的方式路由。 如果 Teams 中预先存在的线程是本机线程 (即路由到 Teams) ，则来自该线程的其他聊天消息和调用将转到Teams。 如果它是一个互操作线程 (即路由到 Skype for Business) ，则其他聊天消息和呼叫Skype for Business (假设路由选项可用) 。

> [!NOTE]
> Teams 中的现有线程可能不再可路由，例如，当线程是用户之间的互操作线程时，该用户已升级到 Teams。 由于它是作为互操作线程创建的，线程将路由到 Skype for Business，但该用户不再可以使用 Skype for Business 聊天和呼叫。 在这种情况下，线程将被禁用，不允许进一步通信。

### <a name="from-skype-for-business"></a>从Skype for Business

Skype for Business超过 10 分钟的 SIP 会话超时后，其他线程不会保留。 在 SIP 会话过期之前Skype for Business会话中的现有线程的聊天和调用将按照与线程相同的方式路由。 来自 Skype for Business 中超过 SIP 会话超时的现有线程的调用和聊天将路由到远程方 Skype for Business，不管原始线程来自另一方一侧的哪个客户端。

## <a name="presence"></a>状态

在一些用户使用 Teams 客户端，而其他用户使用 Skype for Business 客户端时，其中一些用户可能同时使用这两个客户端。 必须了解，状态是基于用户的共存模式发布的。 例如，如果发起方聊天或呼叫应位于目标的 Skype for Business 客户端上，则应该向发起方显示 Skype for Business 客户端状态。 如果它应位于目标Teams客户端，则应该Teams客户端状态。

根据用户的共存模式共享状态，如下所述：

- 如果用户在 TeamsOnly 模式下，则任何其他用户 (无论是在 Teams 还是 Skype for Business) 都将看到 TeamsOnly 用户Teams状态
- 如果用户位于任何 Skype for Business 模式 (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) 中，则任何其他用户 (无论是 Teams 还是 Skype for Business) 都将看到 Skype for Business 用户的 Skype for Business状态
- 如果用户在群岛模式下，Teams 中的状态和 Skype for Business 中的状态是独立的 (这些值不需要与) 匹配，其他用户将看到一个或多个群岛用户，具体取决于他们是在同一租户中还是联合租户中，以及他们使用哪个客户端
  - 从Teams，同一租户中的其他任何用户将看到该群岛用户Teams状态;这符合上述租户内路由表
  - 从Teams，联合租户中的其他任何用户将看到该群岛用户Skype for Business状态;这符合上面的联合路由表
  - 从Skype for Business中，任何其他用户将看到该群岛用户的Skype for Business状态 (租户内和联合用户) ;这符合上述路由表

### <a name="in-tenant-presence"></a>租户内状态

发送给 TeamsOnly 用户的消息将始终登陆Teams。 如果如上所述Skype for Business会话，发送到 Skype for Business 用户的消息将始终位于Skype for Business中。 发送到群岛用户的消息始终位于其来源客户端中。

下表描述了Publisher观察程序将看到的观察程序状态，具体取决于 Publisher 和新线程的观察程序 (客户端) 。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表 3：租户内状态 (线程) 

<br>

|观察程序<br><br>客户端|<br><br>路由 -- >|<br><br>孤岛|Publisher<br><br>Skype for Business|<br>Teams Only|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>联合状态

联合状态基于表 2 中所示的联合可联系性。  下表描述了Publisher观察程序将看到的 Publisher 状态，具体取决于新线程的 Publisher 和观察程序 (客户端) 。 在实践中，观察程序客户端在此阶段中的联合身份验证没有任何区别。

#### <a name="table-4-federated-presence-new-thread"></a>表 4：联合状态 (新线程) 

<br>

|观察程序<br><br>客户端|<br><br>路由 -- >|<br><br>孤岛|Publisher<br><br>Skype for Business|<br><br>Teams Only|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>预先存在的线程中是否存在

为了在预先存在的线程中对齐状态和可访问性，该线程中公开的目标状态需要与线程的路由保持一致（假设可以路由）。  具体而言，如果您以前具有持久互操作会话线程的收件人已升级到 Teams，该线程将不再反映准确的状态，并且不再可路由。 应启动一个新线程。

### <a name="federation-and-interop-with-office-365-operated-by-21vianet"></a>与世纪Office 365运营的云进行联合和互操作

当多租户 Office 365 用户进入"仅Office 365模式时，支持多租户Office 365与世纪Office 365之间的联合和 Teams互操作。 在这种情况下，Skype for Business世纪Office 365运营的 Office 365 Online 用户能够通过聊天和呼叫与 Teams 仅多租户 Office 365 用户进行通信。 下表显示了此配置中支持的方案：
 
|使用场景|Origin|收件人|是否支持？|
|---|---|---|---|
|状态|团队 <br> Skype for Business <br> | Skype for Business <br> Teams|是<br>是|
|聊天|团队 <br> Skype for Business <br> | Skype for Business <br> Teams|是 (1：1) <br>是 (1：1) |
|音频呼叫|团队 <br> Skype for Business <br> | Skype for Business <br> Teams|是 (1：1) <br>是 (1：1) |
|视频通话|Teams <br> Skype for Business <br> | Skype for Business <br> Teams|是 (1：1) <br>是 (1：1) |
|屏幕共享|Teams <br> Skype for Business <br> | Skype for Business <br> Teams |是 (通过已升级Teams会议) <br>是 (已升级的Skype for Business会议) |
|||||


## <a name="related-links"></a>相关链接
[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[视频：管理用户与用户之间的共存Skype for Business互操作性Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
