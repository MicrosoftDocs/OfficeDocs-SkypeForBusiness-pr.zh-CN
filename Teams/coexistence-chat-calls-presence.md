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
ms.openlocfilehash: efd40be76e1a733e74d3e85c767cf2847d3cccbc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582426"
---
# <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

TeamsUpgrade 模式定义了 Skype for Business 和 Teams 客户端与用户之间的共存和互操作性，如将 Teams 与 Skype for Business 一起用于组织的迁移和互操作性指南[中所述](migration-interop-guidance-for-teams-with-skype.md)。

默认情况下或管理员显式为任何给定用户分配 TeamsUpgrade 模式。 默认值为 *"群岛"。* 升级到 Teams的用户具有 *TeamsOnly 模式*。  *SfBOnly、SfBWithTeamsCollab* 和 *SfBWithTeamsCollabAndMeetings* 也是可能的模式。

## <a name="routing-parameters"></a>路由参数

收件人的 TeamsUpgrade 模式对于确定租户内和跨联合租户的聊天、呼叫和状态行为十分关键。

如果发送方正在使用Teams，则创建新的聊天线程时，将做出路由决策。 Teams中的现有聊天线程始终保留创建线程时确定的路由方法：Teams持久线程。

 线程路由方法包括：

- *本机*，Teams Teams租户内聊天
- *租户* 内Teams Skype业务对话的互操作
- *联合* 进行跨租户的联合会话

确定线程路由方法的参数包括：

- 收件人的 TeamsUpgrade 模式
- 发送方使用的客户端
- 聊天是新会话还是现有线程的一部分
- 聊天是租户内聊天还是联合会话
- 对话是否可行
  - *租户内* 互操作性要求租户是纯联机的或Skype for Business混合。 纯本地租户不能具有租户内互操作性。
  - *跨租户联合始终* 需要适当的Skype for Business联合身份验证配置，以及Teams租户的正确联合身份验证配置。 Skype for Business任一租户都不需要混合。
  - 如果Skype for Business方的帐户位于本地，该用户无法将 Teams 客户端用于租户内互操作性或联合。 该用户只能将 Skype for Business 客户端用于互操作性和联合。
  - Teams Teams始终在租户内实现通信。

> [!NOTE]
> 如果接收方和发送方都处于 TeamsOnly 升级模式，对话将是一种本机的聊天体验，其中包括所有富消息和呼叫功能。 如果要了解更多信息，请阅读 [Teams 中外部 (联合) 用户的本机聊天体验](native-chat-for-external-users.md)。 如果任一对话参与者未处于 TeamsOnly 升级模式，则对话仍具有纯文本消息的互操作体验。

## <a name="chat-and-call-routing"></a>聊天和呼叫路由

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>新聊天或通话的租户内路由

下表捕获租户内聊天和调用的路由，并且对于未从预先存在的线程启动的新呼叫或聊天有效。 它描述哪个客户端将接收新的呼叫或聊天（如果由左侧的用户发起）到右侧租户内收件人用户。

发送给 TeamsOnly 用户的消息将始终路由到Teams。 如果可以如上所述，发送到 SfB 用户的消息Skype for Business \* 路由到其他用户。 发送到群岛用户的消息将始终路由到发送这些消息的同一客户端。

下表显示了给定模式下哪个客户端将接收来自发起方 (最左侧的三列) 的调用，具体取决于发起方的模式、选择的客户端，以及其 Skype for Business 客户端的 (位置或联机) 。

在下列表中：

- **SfB \** _ 表示以下任何模式：_SfBOnly*、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings 。  
- *Italic 文本* 突出显示互操作对话。
- **"不可能** "表示无法聊天或通话的情况。 在这种情况下，发起Skype for Business必须改为使用。 这是 Microsoft 对内部/混合客户的规范性指南使用除群岛 (外模式（通常为 SfBWithTeamsCollab) ）作为他们升级到 Teams 的起点的原因之一。

#### <a name="table-1a-in-tenant-new-chat-or-call-routing-to-an-islands-mode-recipient"></a>表 1a：租户内新聊天或呼叫路由到岛屿模式收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>SfB &nbsp; homed|<br><br>路由 -- >|收件人<br><br>孤岛|
|---|---|---|:---:|---|
|孤岛|Teams <br> Skype for Business <br> Teams <br> Skype for Business|Online <br> Online<br> 就地<br>就地|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> Skype for Business <br> Teams <br> Skype for Business|
|SfB\*|Skype for Business <br>Skype for Business|Online <br> 就地|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|Teams|
||||||

#### <a name="table-1b-in-tenant-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>表 1b：在 SfB 模式下向收件人进行租户内新聊天或呼叫 \* 路由

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>SfB &nbsp; homed|<br><br>路由 -- >|收件人<br><br>SfB\*|
|---|---|---|:---:|---|
|孤岛|Teams <br> Skype for Business <br> Teams <br> Skype for Business|Online <br> Online <br> 就地 <br> 就地|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype for Business* <br> Skype for Business <br> **不可能** <br> Skype for Business|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> 就地|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
||||||

#### <a name="table-1c-in-tenant-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 1c：租户内新聊天或呼叫路由到 TeamsOnly 模式收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>SfB &nbsp; homed|<br><br>路由 -- >|收件人<br><br>TeamsOnly|
|---|---|---|:---:|---|
|孤岛|Teams <br> Skype for Business <br> Teams <br> Skype for Business|Online <br> Online <br> 就地 <br> 就地|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> *Teams* <br> Teams <br> *Teams*|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> 就地|&boxv;<br>&boxv;|*Teams* <br> *Teams*|
|TeamsOnly|Teams|Online|&boxv;|Teams|
||||||

### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或通话的联合路由

下表捕获联合呼叫和聊天的路由，并且对于新呼叫或聊天有效。 它们描述哪个客户端将收到新的呼叫或聊天（如果由左侧用户发起）到右侧联合目标用户。

总之，如果如上文所述对话可行，发送到 TeamsOnly 用户的消息将始终位于Teams;发送给 SfB 用户的消息将始终位于Skype for Business;发送到群岛用户的消息将始终位于Skype for Business客户端，无论这些消息从 \* 哪个客户端发送。 联合聊天和呼叫的路由不同于租户内路由，因为群岛用户始终在 Skype for Business。

这是因为无法假定联合Skype for Business合作伙伴已使用Teams（如果它们位于群岛模式）。 群岛是默认模式，但无法假定所有群岛用户都Teams。 通过路由到Skype for Business，我们确保与群岛用户的通信不会失败。 如果我们路由到 Teams，则如果目标未使用 Teams，则可能会错过该Teams。 路由Skype for Business确保始终收到消息。

> [!NOTE]
> Teams 联合的当前实现基于 Skype for Business 联合，因此它利用互操作性基础结构 (它要求发起方租户是纯联机的或 Skype for Business 混合) 并且提供的功能集比本机线程少。 我们希望在将来提供本机Teams Teams联合身份验证，此时线程将是本机的并提供完整功能。

下表描述了哪个客户端将接收来自发起方 (最左侧的三列) 的调用，具体取决于发起方的模式、选择的客户端，以及其 Skype for Business 客户端的 (位置或联机) 。

#### <a name="table-2a-federated-new-chat-or-call-routing-to-an-islands-recipient"></a>表 2a：联合的新聊天或呼叫路由到群岛收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>SfB homed|<br><br>路由 -- >|收件人<br><br>孤岛|
|---|---|---|:---:|---|
|孤岛|Teams <br> Skype for Business <br> Teams <br> Skype for Business|Online <br> Online <br> 就地 <br> 就地|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype for Business* <br> Skype for Business <br> **不可能** <br> Skype for Business|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> 就地|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
|||||

#### <a name="table-2b-federated-new-chat-or-call-routing-to-a-recipient-in-an-sfb-mode"></a>表 2b：在 SfB 模式下将新聊天或呼叫路由联合到 \* 收件人

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>SfB homed|<br><br>路由 -- >|收件人<br><br> SfB\*|
|---|---|---|:---:|---|
|孤岛|Teams <br> Skype for Business <br> Teams <br> Skype for Business|Online <br> Online <br> 就地 <br> 就地|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|*Skype for Business* <br> Skype for Business <br> **不可能** <br> Skype for Business|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> 就地|&boxv;<br>&boxv;|Skype for Business <br> Skype for Business|
|TeamsOnly|Teams|Online|&boxv;|*Skype for Business*|
||||||

#### <a name="table-2c-federated-new-chat-or-call-routing-to-a-teamsonly-mode-recipient"></a>表 2c：联合到 TeamsOnly 模式收件人的新聊天或呼叫路由

<br>

|<br><br>模式|发起者<br><br>客户端|<br><br>SfB homed|<br><br>路由 -- >|收件人<br><br>TeamsOnly|
|---|---|---|:---:|---|
|孤岛|Teams <br> Skype for Business <br> Teams <br> Skype for Business|Online <br> Online <br> 就地 <br> 就地|&boxv;<br>&boxv;<br>&boxv;<br>&boxv;|Teams <br> *Teams* <br> **不可能** <br> *Teams*|
|SfB\*|Skype for Business <br> Skype for Business|Online <br> 就地|&boxv;<br>&boxv;|*Teams* <br> *Teams*|
|TeamsOnly|Teams|Online|&boxv;|Teams|
||||||

## <a name="chats-and-calls-from-pre-existing-threads"></a>来自预先存在的线程的聊天和通话

### <a name="from-teams"></a>从Teams

如果路由选项仍然可用，则从 Teams 中预先存在的持久线程启动的呼叫或聊天将按照与该线程相同的方式路由。

如果 Teams 中预先存在的持久线程是本机线程 (即路由到 Teams) ，则来自该线程的其他聊天消息和调用将转到Teams。 如果它是一个互操作线程 (即路由到 Skype for Business) ，则其他聊天消息和Skype for Business (将再次转到) 。

> [!NOTE]
> 当线程是用户之间的互操作线程时，Teams中预先存在的线程可能不再可路由，而该用户现在已升级到 Teams。 由于它是作为互操作线程创建的，因此该线程将路由到 Skype for Business，但该用户不再能够Skype for Business聊天和呼叫。 在这种情况下，线程将被禁用，不允许进一步通信。

### <a name="from-skype-for-business"></a>从 Skype for Business

Skype for Business超过 10 分钟时，会话线程不会保留。SIP 会话超时。 在 SIP 会话过期之前Skype for Business会话中的现有线程的聊天和调用将按照与线程相同的方式路由。 来自 Skype for Business 中超过 SIP 会话超时的现有线程的调用和聊天将路由到远程方 Skype for Business，不管原始线程来自另一方一侧的哪个客户端。

### <a name="availability"></a>可用性

上述租户内和联合行为均可用，具有以下限制：

- 租户位于其他 GoLocal 部署或地理位置的外部与会者在"联合"会议时不会看到 IM 聊天
- 不支持多租户 O365 与主权云之间的联合和互操作

## <a name="presence"></a>状态

如果某些用户使用 Teams 客户端，而其他用户仍在使用 Skype for Business 客户端，则可能会有许多用户同时使用这两个客户端。 你仍希望与所有用户共享状态，而不考虑单个用户拥有什么客户端。 在组织中共享此功能后，用户可以更好地确定发起聊天还是进行呼叫是合适的。

例如，如果发起方聊天或通话应位于目标的 Skype for Business 客户端上，则应该向发起方显示 Skype for Business 客户端状态。 如果它应位于目标Teams客户端上，则应该Teams客户端状态。

为了了解预期的行为，你需要了解状态是基于用户的共存模式共享的：

- 如果用户在 TeamsOnly 模式下，则任何其他用户 (无论是 Teams 还是 Skype for Business) 都将看到 TeamsOnly 用户Teams状态
- 如果用户位于任何 SfB 模式 \* (SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings) 中，则任何其他用户 (无论是 Teams 还是 Skype for Business) 都将看到该 SfB \* 用户的 Skype for Business 状态
- 如果用户位于群岛 (或旧版) 模式下，Teams 中的状态和 Skype for Business 中的状态是独立的 (这些值不需要与) 匹配，其他用户将看到一个或另一个群岛用户，具体取决于他们是在同一租户中还是联合租户中，以及他们使用哪个客户端
  - 从Teams，同一租户中的其他任何用户将看到该群岛用户Teams状态;这符合上述租户内路由表
  - 从Teams，联合租户中的其他任何用户将看到该群岛用户Skype for Business状态;这符合上面的联合路由表
  - 从Skype for Business，任何其他用户将看到该群岛用户的Skype for Business状态 (租户内和联合) ;这符合上述路由表

### <a name="in-tenant-presence"></a>租户内状态

发送给 TeamsOnly 用户的消息将始终登陆Teams。 如果可以如上所述进行聊天，则发送到 SfB 用户Skype for Business \* 始终位于该对话中。 发送到群岛用户的消息始终位于其来源客户端中。

下表描述了Publisher观察程序将看到的观察程序状态，具体取决于新线程的 Publisher 和观察程序 (客户端) 。

#### <a name="table-3-in-tenant-presence-new-thread"></a>表 3：新线程 (租户内) 

<br>

|观察程序<br><br>客户端|<br><br>路由 -- >|<br><br>孤岛|Publisher<br><br>SfB\*|<br>Teams Only|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Teams|Skype for Business|Teams|
|||||

### <a name="federated-presence"></a>联合状态

联合状态基于表 2 中所示的联合可联系性。

下表描述了Publisher观察程序将看到的 Publisher 状态，具体取决于新线程的 Publisher 模式和观察程序 (的客户端) 。 在实践中，观察程序客户端在此阶段中的联合身份验证没有任何区别。

#### <a name="table-4-federated-presence-new-thread"></a>表 4：联合状态 (新线程) 

<br>

|观察程序<br><br>客户端|<br><br>路由 -- >|<br><br>孤岛|Publisher<br><br>SfB\*|<br><br>Teams Only|
|---|:---:|---|---|---|
|Skype for Business|&boxv;|Skype for Business|Skype for Business|Teams|
|Teams|&boxv;|Skype for Business|Skype for Business|Teams|
||||||

### <a name="presence-in-pre-existing-threads"></a>预先存在的线程中是否存在

为了在预先存在的线程中对齐状态和可访问性，该线程中公开的目标状态需要与线程的路由保持一致（假设路由可行）。

具体而言，如果您以前具有持久互操作会话线程的收件人已升级到 Teams，该线程将不再反映准确的状态，并且不再可路由。 应启动一个新线程。

## <a name="related-links"></a>相关链接
[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](./migration-interop-guidance-for-teams-with-skype.md)

[视频：管理 SfB 与 Teams 之间的共存和互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
