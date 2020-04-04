---
title: 与 Skype for Business 共存
author: kenwith
ms.author: kenwith
manager: Serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: francoid
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
description: 团队 & Skype for business 之间的共存行为，包括路线参数、聊天 & 呼叫路线、聊天 & 来自预先存在的线程的通话 & 状态。
ms.openlocfilehash: ff5e94b16cd55374ec0aeb45aaffdda41fbe0498
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137302"
---
# <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 共存

Skype for Business 和团队客户端和用户之间的共存和互操作性由 TeamsUpgrade 模式定义，这些模式由[使用团队与 Skype For business 一起使用的组织的迁移和互操作性指南](migration-interop-guidance-for-teams-with-skype.md)中所述。

任何给定用户都将始终被指定为 TeamsUpgrade 模式，默认情况下为管理员。 默认值为 "*岛*"。 升级到团队的用户具有*TeamsOnly*模式。 *SfBOnly*、 *SfBWithTeamsCollab*和*SfBWithTeamsCollabAndMeetings*也是可能的模式。


## <a name="routing-parameters"></a>路由参数

收件人的 TeamsUpgrade 模式是租户内和联合租户中确定聊天、调用和状态的行为的关键。

如果发件人正在使用团队，则会在创建新的对话线索时做出路由决定。 团队中的现有对话线程始终保留在创建线程时确定的路由方法：团队支持永久线程。

 线程路由方法为：  

- 团队成员在租户中的*本地*对话
- 团队到租户中的 Skype for business 对话的*互操作*
- 针对租户间的联盟对话的*联合*

确定线程路由方法的参数如下所示：

- 收件人的 TeamsUpgrade 模式
- 发件人使用的客户端
- 对话是新的还是某个现有线程的一部分
- 对话是否在租户内或联合
- 是否可以进行对话
    - *租户内*互操作要求租户为纯在线或 Skype for business 混合。 纯粹的内部租户不能有内部互操作性。
    - *跨租户联盟*始终需要正确的 Skype for business 联合身份验证配置以及来自这两个租户的正确团队联合身份验证配置。 任何一种租户都不需要 Skype for business 混合。
    - 如果始发者的 Skype for Business 帐户位于本地托管，则该用户不能使用团队客户端进行租户互操作性或联合身份验证。 该用户只能使用 Skype for Business 客户端进行互操作性和联盟。
    - 团队到团队的通信始终可以在租户中实现。

> [!NOTE]
> 如果接收方和发件人都在 TeamsOnly 升级模式中，则对话将是一个本机聊天体验，包括所有丰富的消息传递和呼叫功能。 若要了解详细信息，请阅读[团队中外部（联合）用户的本机聊天体验](native-chat-for-external-users.md)。 如果其中一个对话参与者未处于 TeamsOnly 升级模式，则对话将保持带有纯文本消息的互操作体验。

## <a name="chat-and-call-routing"></a>聊天和呼叫路由

### <a name="in-tenant-routing-for-new-chats-or-calls"></a>用于新聊天或通话的租户内路由 

下表捕获租户内聊天和通话的路由，并且对于不是从预先存在的线程开始的新通话或聊天有效。 它介绍了向右侧的租户收件人用户发出的新呼叫或聊天（如果由左侧的用户发起）。

发送给 TeamsOnly 用户的邮件将始终路由到团队。 发送给 SfB\*用户的邮件将始终路由到 Skype for business，前提是您可以按照上述说明进行对话。 发送给孤岛用户的消息将始终路由到其发送到的同一客户端。

下表显示给定模式下的客户端将接收来自始发者的呼叫（三个最左侧的列），具体取决于发起方的模式、所选客户端以及其 Skype for Business 客户端的托管位置（本地或 online）。

在下面的表中： 
- **SfB\* **表示以下任何模式： *SfBOnly*、 *SfBWithTeamsCollab*、 *SfBWithTeamsCollabAndMeetings*。

- *斜体文本*突出显示互操作对话。

- **不可能**表示不可能聊天或呼叫的情况。 在这些情况下，发信方必须使用 Skype for Business。 这是 Microsoft 对本地/混合客户的说明性指导的原因之一是使用孤岛（通常是 SfBWithTeamsCollab）以外的其他模式（通常是）作为升级到团队的升级起点。

**表1a：租户新聊天或呼叫路由到孤岛模式收件人**

| <br/><br/> 众 | 创 <br/><br/> 客户端 | <br/><br/> SfB&nbsp;托管 | | 收信 <br/><br/> 孤岛  |
|--- |--- |--- |--- |--- |
| 孤岛 | Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business| Online<br/> Online<br/> 本地<br/>本地| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|Teams <br/> Skype for Business<br/> Teams<br/> Skype for Business|
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> 本地<br/> |&boxv;<br/>&boxv;|Skype for Business<br/>Skype for Business<br/>|
|TeamsOnly |Teams| Online<br/>|&boxv;<br/>|Teams|
| | | | | |

**表1b：在 SfB\*模式下的租户新聊天或呼叫路由到收件人**

| <br/><br/> 众   | 创 <br/><br/> 客户端 | <br/><br/> SfB&nbsp;托管 | |   收信 <br/><br/> SfB\*   |
|--- |--- |--- |---   |--- |
| 孤岛 |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> 本地<br/> 本地<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business<br/> **不可能** <br/>Skype for Business<br/> |
|SfB\* <br/> | Skype for Business<br/>Skype for Business<br/> | Online<br/> 本地<br/> |&boxv;<br/>&boxv; |  Skype for Business<br/>Skype for Business<br/> |
|TeamsOnly |Teams| Online<br/>|&boxv;<br/> |  *Skype for Business* <br/>| 
| | | | | |

**表1c：租户新聊天或呼叫路由到 TeamsOnly 模式的收件人**

| <br/><br/> 众   | 创 <br/><br/> 客户端 | <br/><br/> SfB&nbsp;托管 | |   收信 <br/><br/> TeamsOnly  |
|--- |--- |--- |--- | --- |
| 孤岛   |Teams<br/>Skype for Business<br/>Teams <br/>Skype for Business<br/>|Online<br/> Online<br/> 本地<br/> 本地<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;|  Teams <br/>*Teams* <br/>Teams <br/>*Teams*  |
|SfB\*  | Skype for Business<br/>Skype for Business<br/> | Online<br/> 本地<br/> | &boxv;<br/>&boxv; | *Teams*  <br/>*Teams*   |
|TeamsOnly  | Teams | Online |  &boxv; |Teams   |
|  |  |  | | |

### <a name="federated-routing-for-new-chats-or-calls"></a>新聊天或呼叫的联盟路由
  
下表捕获联合呼叫和聊天的路由，并且适用于新的通话或聊天。 它们描述了向右侧的联合目标用户发起的新呼叫或聊天（如果由左侧的用户发起）。

总而言之，如果可以按上述方式进行对话，则发送给 TeamsOnly 用户的邮件将始终位于团队中;发送给 SfB\*用户的邮件将始终位于 Skype for business 中，发送给孤岛用户的邮件将始终位于 Skype for Business 中，而不考虑发送给他们的客户。 联合聊天和呼叫的路由与该孤岛中的租户内路由不同，该孤岛中的用户将始终在 Skype for Business 中接收联合通信。

这是因为我们无法假定联合的 Skype for business 合作伙伴已使用团队（如果他们处于孤岛模式）。 岛是默认模式，但无法假设所有孤岛用户运行团队。 通过路由到 Skype for Business，我们确保没有与孤岛用户进行通信失败。 如果我们路由到团队，则如果目标未使用团队，则可能会错过通信。 将邮件路由到 Skype for Business 可确保始终收到邮件。  

> [!NOTE]
> 团队联合身份验证的当前实现基于 Skype for business federation，因此它利用互操作性基础结构（要求发起人的租户为纯在线或 Skype for business 混合），并提供与本机线程相比的一组精简的功能。 我们预计将来会向团队联盟提供本机团队，此时该线程将是本机团队并提供完整功能。

下表描述了哪些客户端将接收来自始发者的呼叫（三个最左侧的列），具体取决于发起方的模式、所选客户端以及其 Skype for Business 客户端的驻留位置（本地或 online）。

**表2a：联合新聊天或呼叫路由到岛的收件人**

| <br/><br/>众   | 创<br/><br/> 客户端| <br/><br/>SfB 托管| | 收信<br/><br/> 孤岛 |
|--- |--- |--- |--- |--- |
| 孤岛 |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business  |Online<br/> Online<br/> 本地<br/> 本地<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **不可能**   <br/> Skype for Business |
| SfB\* |Skype for Business <br/>Skype for Business |Online<br/> 本地<br/> | &boxv;<br/>&boxv;|Skype for Business <br/>Skype for Business |
| TeamsOnly |Teams |Online| &boxv;|*Skype for Business* |
|  | | | | 

**表2b：联合新聊天或呼叫在 SfB\*模式下路由到收件人**

| <br/><br/>众   | 创<br/><br/> 客户端| <br/><br/>SfB 托管| |  收信<br/><br/> SfB\* |  
|--- |--- |--- |--- |--- |
| 孤岛 |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> 本地<br/> 本地<br/> | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *Skype for Business* <br/> Skype for Business <br/> **不可能** <br/>Skype for Business <br/> |  
| SfB\* |Skype for Business <br/>Skype for Business  |Online<br/> 本地<br/>  |&boxv;<br/>&boxv; | Skype for Business <br/>Skype for Business  |
| TeamsOnly | Teams|Online |&boxv; |*Skype for Business*  |
|  | | | | |

**表2c：联合新聊天或呼叫路由到 TeamsOnly 模式的收件人**

| <br/><br/>众 | 创<br/><br/> 客户端| <br/><br/>SfB 托管| |  收信<br/>  <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |
| 孤岛  |Teams<br/>Skype for Business <br/>Teams <br/>Skype for Business <br/>|Online<br/> Online<br/> 本地<br/> 本地<br/>  | &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;| Teams <br/>*Teams* <br/>**不可能** <br/>*Teams* |
| SfB\* |Skype for Business <br/>Skype for Business  | Online<br/> 本地| &boxv;<br/>&boxv;|*Teams* <br/>*Teams*   |
| TeamsOnly |Teams |Online |&boxv; |Teams |
|  | | | | |

## <a name="chats-and-calls-from-pre-existing-threads"></a>来自预先存在的线程的聊天和通话

### <a name="from-teams"></a>从团队

从团队中预先存在的持久线程开始的通话或聊天将以与该线程相同的方式进行路由，如果该路由选项仍然可用。

如果团队中预先存在的持久线程是本机线程（即路由到团队），则其他聊天消息和来自该线程的调用将转到团队。 如果是互操作线程（即路由到 Skype for business），则其他聊天消息和呼叫将转到 Skype for business （也可再次假设路由选项可用）。

> [!NOTE]
> 团队中的预先存在的线程可能无法再路由，例如当该线程是指向现在已升级到团队的用户的互操作线程时。 由于它是作为互操作线程创建的，该线程将路由到 Skype for business，但该用户不再可以使用 Skype for business 进行聊天和通话。 在这种情况下，该线程将被禁用，并且不允许进一步通信。

### <a name="from-skype-for-business"></a>从 Skype for Business

Skype for business 线程不会保留超过10分钟的 SIP 会话超时。 在 SIP 会话到期之前，Skype for business 中的现有线程的聊天和呼叫将以与线程相同的方式进行路由。 除了 SIP 会话超时之外，Skype for business 中的现有线程的通话和聊天将路由到远程方的 Skype for business，无论原始线程来自另一方的哪一个客户端。

### <a name="availability"></a>可用性

上面介绍的租户和联合行为均可用，并且具有以下限制：

- 租户位于不同 GoLocal 部署或地理位置的外部与会者在 "联盟" 会议中看不到即时消息聊天
- 不支持多租户 O365 和主权云之间的联盟和互操作

## <a name="presence"></a>状态

如果你有一些用户使用团队客户端，而其他用户仍在使用 Skype for Business 客户端，则你可能会有大量使用客户端的用户。 你仍希望在不考虑单个用户拥有的客户端的情况下与所有用户共享状态状态。 当在组织内共享此功能时，用户可以更好地确定它是否适合发起聊天或进行呼叫。

例如，如果发起人的聊天或呼叫应位于目标的 Skype for business 客户端上，则是 Skype for business 客户端的状态，应显示给始发者。 如果它应位于目标的团队客户端上，则表示团队客户端的状态应为 "已显示"。

为了了解所需的行为，您需要了解基于用户的共存模式共享状态：

* 如果用户处于 TeamsOnly 模式，则任何其他用户（无论是在团队中还是在 Skype for business 中）都将看到 TeamsOnly 用户的团队是否存在
* 如果用户处于 SfB\*模式（SfbOnly、SfbWithTeamsCollab、SfbWithTeamsCollabAndMeetings）中，则任何其他用户（无论是在团队中还是在 Skype for business 中）都将看到 SfB\*用户的 Skype for business 存在
* 如果用户使用的是 "岛（或旧版）" 模式，则团队中的联机状态和 Skype for business 中的状态是独立的（值不需要匹配），并且其他用户将看到孤岛用户的一个或另一个状态，具体取决于它们是位于同一租户中还是在联合租户中以及使用的客户端
    * 来自团队，同一租户中的任何其他用户将看到孤岛用户的团队状态;这与上面的租户内路由表对齐
    * 从团队中，联合租户中的任何其他用户将看到孤岛用户的 Skype for business 状态;这与上面的联盟路由表对齐
    * 在 Skype for Business 中，任何其他用户将看到孤岛用户的 Skype for business 联机状态（租户和联合）;这与上面的路由表对齐


### <a name="in-tenant-presence"></a>租户内状态

发送给 TeamsOnly 用户的邮件将始终位于团队中。 发送给 SfB\*用户的邮件将始终位于 Skype for business 中，如果可以按上述说明进行对话。 发送给孤岛用户的消息将始终位于发起它们的客户端中。

下表介绍了将由观察者查看的发布者的状态，具体取决于发布者的模式和观察者的客户端（对于新线程）。

**表3：租户内状态（新线程）**

|观察 <br/><br/>客户端| |<br/><br/>孤岛 |Publisher <br/><br/>SfB\* |<br/>仅限团队|
|--- |--- |--- |--- |---|
|Skype for Business |&boxv;|Skype for Business | Skype for Business | Teams|
|Teams |&boxv; |Teams |Skype for Business |Teams |
| | | | |

### <a name="federated-presence"></a>联合状态

联合状态基于表2中所示的联合可访问性。

下表介绍了将由观察者查看的发布者的状态，具体取决于发布者的模式和观察者的客户端（对于新线程）。 在实践中，观察程序的客户在此阶段不会有任何不同的联盟。

**表4：联合状态（新线程）**

|观察 <br/><br/> 客户端 | |<br/><br/> 孤岛  |Publisher <br/><br/> SfB\* |<br/><br/> 仅限团队 |
|--- |--- |--- |--- |---|
|Skype for Business |&boxv; |Skype for Business  | Skype for Business  | Teams  |
|Teams | &boxv;|Skype for Business |Skype for Business |Teams|
| | | | ||

### <a name="presence-in-pre-existing-threads"></a>存在于预先存在的线程中

为了在预先存在的线程中对齐状态和可访问性，在该线程中公开的目标状态需要与线程的路由进行对齐，假设路由是可能的。

特别是，如果收件人以前拥有已升级到团队的永久互操作对话线程，该线程将不再反映精确的状态，并且将无法再进行路由。 应启动新线程。

## <a name="related-links"></a>相关链接
[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[视频：管理 SfB 和团队之间的共存和互操作性](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
