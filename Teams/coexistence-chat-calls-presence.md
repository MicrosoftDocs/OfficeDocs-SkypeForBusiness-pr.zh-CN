---
title: 与 Skype for Business 的共存
author: jambirk
ms.author: francoid
manager: Serdars
ms.date: 11/7/2018
ms.topic: article
ms.service: msteams
ms.reviewer: francoid
description: 本文档介绍了基于分配 TeamsUpgrade 模式的聊天、 呼叫路由和团队的用户和业务，在租户和联盟的 Skype 之间的状态的行为。 它包括路由优化、 状态行为，以及从*旧**群岛*到默认 TeamsUpgrade 模式的更改和*旧*即将退休。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0d6e4ad171ffc99e1f0aaa1c3b93e0fd61443bc
ms.sourcegitcommit: 42143176c46ba9496a0fd401c8e4774075106b98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238103"
---
# <a name="coexistence-with-skype-for-business"></a>与 Skype for Business 的共存

由 TeamsUpgrade 模式、[迁移和互操作性指南组织使用团队一起 Skype for Business](migration-interop-guidance-for-teams-with-skype.md)中所述定义共存和 Skype for Business 和团队之间的互操作性。

任何给定的用户将始终分配 TeamsUpgrade 模式，默认情况下或显式由管理员。 默认值是*群岛*。 升级到团队的用户具有*TeamsOnly*的模式。

> [!NOTE]
> 已弃用*旧*模式;2018 年 11 月 15 之后，剩余*旧*模式的用户将被转换为*群岛*模式。

## <a name="routing-parameters"></a>路由参数

收件人的 TeamsUpgrade 模式是中确定的聊天、 呼叫和状态，是租户内兼跨联盟租户行为键。

如果发件人使用的团队，创建一个新的对话线程时进行做出路由决定。 团队中的现有对话线程始终保留确定创建线程时的路由方法。 团队支持持久线程。

 线程路由方法是：  
* *本机*到团队对话中的租户团队
* *互操作*的 Skype 团队业务对话中的租户
* 跨租户联盟对话的*联盟*。

确定线程路由方法的参数为：
* 收件人的 TeamsUpgrade 模式
* 发件人使用的客户端
* 对话是否新或现有的线程的一部分
* 对话是否在租户或联盟
* 是否可能对话
    * 在租户互操作性和联合身份验证从团队需要，则发起者的租户是纯联机或业务混合的 Skype。 向工作组的联合身份验证或租户中互操作性，则不能具有完全内部租户。
    * 如果业务帐户发起方的 Skype，本地驻留的用户无法使用团队客户端租户中的互操作性和联合身份验证。 该用户必须改用业务客户端 Skype 的互操作性和联合身份验证。
    * 团队团队通信始终是可能的租户。

# <a name="chat-and-call-routing"></a>聊天和呼叫路由

## <a name="in-tenant-routing-for-new-chats-or-calls"></a>租户中为新的聊天或呼叫路由 

下表捕获当前做法租户中聊天和呼叫路由。 此表是有效的新呼叫或未启动从预先存在现有线程的聊天。 它介绍哪些客户端的新呼叫 （或聊天） 将路由到，如果产生左侧到右侧的租户中目标用户的用户。

向 TeamsOnly 用户发送的邮件将始终位于工作组中。 如上所述可能对话时，始终将在 Skype for Business，位于向 SfB * 用户发送消息。 向群岛用户发送的邮件将始终位于已产生的客户端中。

**表 1： 租户中新的聊天或呼叫路由**

| <br/> 模式   | 从&nbsp;原始发件人 <br/> 客户端 | <br/> SfB&nbsp;驻留 | | <br/> 群岛  | 到&nbsp;目标 <br/> SfB\*   | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |--- |
| 群岛 <br/>群岛 <br/>群岛 <br/>群岛<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Teams<br/>SfB <br/>Teams <br/>SfB <br/>SfB <br/>SfB <br/>Teams|Online<br/> Online<br/> 在 prem<br/> 在 prem<br/> Online<br/> 在 prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>|Teams <br/> SfB <br/> Teams <br/> SfB <br/>  SfB <br/> SfB <br/> Teams | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>*SfB* <br/>  | Teams <br/>*Teams* <br/>Teams <br/>*Teams* <br/> *Teams*  <br/>*Teams* <br/>Teams <br/> |
|  | | | | | | |

在表中，SfB * 代表任何以下模式： *SfBOnly*， *SfBWithTeamsCollab*， *SfBWithTeamsCollabAndMeetings*。

*斜体文本*表中指示的互操作的对话。

表中的**加粗**表示在其聊天或呼叫不是可能的情况。 这是因为互操作性基础结构仅联机可用，需要 Skype 的团队帐户为 online 帐户相关联的业务帐户。 原始发件人必须使用 Skype for Business 改为在这些情况下。 这是 Microsoft 的说明性指导信息，以便上-prem/混合客户为何要比群岛 (通常为*SfBWithTeamsCollab*) 使用另一种模式的原因之一向工作组其升级旅程的起始点。

## <a name="federated-routing-for-new-chats-or-calls"></a>联盟路由进行呼叫或新的聊天
  
下表捕获当前联盟的呼叫 （和聊天） 路由做法。 此表是有效的新呼叫或聊天。 它介绍哪些客户端的新呼叫 （或聊天） 将路由到，如果产生左侧到右侧联盟的目标用户的用户。

总之，如果可能，上面所述的对话就 TeamsOnly 用户发送的邮件将始终位于中团队;邮件发送给 SfB * 用户将始终位于在 Skype 的业务需要。向群岛用户发送的邮件将始终位于 Skype for Business 中而不考虑所产生的客户端。 路由联盟聊天和呼叫不同租户中路由，群岛用户始终将 Skype for Business 中收到联盟的通信。

此最后一个点的原因是，我们不能假定业务合作伙伴的联盟的 Skype 已使用团队，如果群岛模式。 群岛是默认模式中，但我们不能假定所有群岛用户都运行团队。 通过传送至 for Business 的 Skype 我们确保向群岛用户没有通信失败。 如果我们传送给团队，如果目标不使用团队，可能会丢失的通信。 传送到 for Business 的 Skype 可确保始终接收邮件。  

> [!NOTE]
> 当前实现团队联合身份验证基于 Skype 业务联盟，因此它利用互操作性基础结构 (这要求发起方的租户应是纯联机或 SfB 混合)，并提供了一组缩减的功能与本机线程进行比较。 我们希望提供本机团队团队联盟将来，此时线程本机并提供完整的功能。

**表 2： 联合新聊天或呼叫路由**

| <br/>模式   | 从原始发件人<br/> 客户端| <br/>SfB 驻留| | <br/> 群岛 | 若要确定目标<br/> SfB\* | <br/> TeamsOnly  |
|--- |--- |--- |--- |--- |--- |---|
| 群岛 <br/>群岛 <br/>群岛 <br/>群岛<br/> SfB\*<br/> SfB\* <br/> TeamsOnly |Teams<br/>SfB <br/>Teams <br/>SfB <br/>SfB <br/>SfB <br/>Teams|Online<br/> Online<br/> 在 prem<br/> 在 prem<br/> Online<br/> 在 prem<br/> Online| &boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>&boxv;<br/>| *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/> | *SfB* <br/> SfB <br/> **NA** <br/>SfB <br/> SfB <br/>SfB <br/>SfB <br/>  | Teams <br/>Teams <br/>**NA** <br/>*团队<br/>团队<br/>团队* <br/>Teams <br/> |
|  | | | | | |

在表中，SfB * 代表任何以下模式： *SfBOnly*， *SfBWithTeamsCollab*， *SfBWithTeamsCollabAndMeetings*。

*斜体文本*突出显示的互操作的对话。

**加粗**表示在其聊天或呼叫不是可能的情况。 原始发件人必须使用 Skype for Business 改为在这些情况下。 这是 Microsoft 的说明性指导信息，以便上-prem/混合客户为何要比群岛 (通常 SfBWithTeamsCollab) 使用另一种模式的原因之一向工作组其升级旅程的起始点。

## <a name="chats-and-calls-from-pre-existing-threads"></a>聊天并调用从事先线程

### <a name="from-teams"></a>从工作组

调用或聊天启动从预先存在持久线程中团队将路由中相同的方式的线程，如果该路由选项仍可用。 

如果团队中的前现有持久线程本机线程 （即路由至团队），其他聊天消息和从该线程的呼叫将转到团队。 如果它 （即路由至 for Business 的 Skype） 互操作性线程，其他聊天消息和呼叫将转到 Skype for Business （再次假定路由选项才可用）。

> [!NOTE]
> 团队中的前现有线程可能不再可路由。 这可能例如线程是否向用户立即升级到团队的互操作的线程。 由于互操作的线程，线程会将路由到 for Business 的 Skype 但用户不再可以使用 Skype for Business 的聊天和呼叫。 在这种情况下，线程将被禁用，不允许进一步进行通信。

### <a name="from-skype-for-business"></a>从 Skype for Business

Skype for Business 没有线程持久性之外的 SIP 会话超时值 （10 分钟）。 聊天和从之前的 SIP 会话的过期 Skype for Business 中现有的线程的呼叫将路由线程的方式相同。 会向业务，无论哪些客户端的原始线程来自另一方的一侧的远程用户的 Skype 路由呼叫和从超出 SIP 会话超时 Skype for Business 中现有的线程的聊天室。

## <a name="availability"></a>可用性

上述中租户行为与在今天生产中可用。

上述的联盟的行为主要是立即生产中可用的。 下列元素仍对于正在推出和仅供前期应用上的租户： 
* 联合身份验证与本地租户具有状态可见性
* 团队客户端的联系人列表中的迁移联盟联系人的显示
* 若要使用的 SIP URI 或 SMTP 地址来发现联盟的联系人的能力。

推出的这些已开始，和常规可用性预期之前年 11 月 2018年的末尾。

# <a name="presence"></a>状态

如果您有其中某些用户使用的团队客户端和其他人仍在使用 Skype for Business 客户端的情况，您可以使用两个客户端的用户数。 您仍希望与而不考虑单个用户具有哪些客户端的所有用户共享的状态。 当这在组织内共享时，用户可以更好地确定它是否适合启动聊天或进行呼叫。

例如，如果在目标的 Skype 业务客户端上应位于发信的聊天或呼叫，则应显示为原始发件人的业务客户端的状态 Skype。 如果它应位于的目标团队客户端上，则应显示的团队客户端的状态。

为了知道哪些行为的情况，您需要了解状态共享基于用户的共存模式：

* 如果用户是在 TeamsOnly 模式中，则 （团队或 Skype for Business 中是否） 的任何其他用户将看到该 TeamsOnly 用户团队状态
* 如果用户是在任何 SfB\*模式 (SfbOnly，SfbWithTeamsCollab，SfbWithTeamsCollabAndMeetings)，然后 （团队或 Skype for Business 中是否） 的任何其他用户会看到该 SfB\*业务状态的用户的 Skype
* 如果用户是在群岛 （或旧） 模式时，团队中的状态和 Skype for Business 中的状态是独立于 （值不需要匹配） 和其他用户将看到一条或其他状态的群岛用户，具体取决于是否位于同一租户或 federated 租户和他们使用的客户端
    * 从工作组，同一租户中的任何其他用户将看到群岛用户团队状态;这与上面的租户中路由表对齐
    * 从团队看到业务状态; 群岛用户的 Skype 联合租户中的任何其他用户。这与上面的联盟路由表对齐
    * 从 for Business 的 Skype，任何其他用户将看到群岛用户的 Skype 业务状态 （在租户和联盟）;这与上面的路由表对齐

> [!NOTE]
> 这是从以前的实现 （称为统一状态） 的业务客户端中显示的目标的团队和 Skype 组合、 聚合状态的最新更改。 事实证明，经常会导致在准确状态，即用户未访问即使其状态显示它们 online 中显示为向用户令人费解的前面的方法。

## <a name="in-tenant-presence"></a>租户状态

向 TeamsOnly 用户发送的邮件将始终位于工作组中。 邮件发送到 SfB\*可能如上所述对话时，用户始终将位于中的业务，Skype。 向群岛用户发送的邮件将始终位于已产生的客户端中。

下表描述了将会看到的观察程序，具体取决于发行者的模式和 （对于新的线程） 观察程序的客户端的发布者的状态。

**表 3： 在租户状态 （新线程）**

|观察程序 <br/>客户端| |<br/>群岛 |Publisher <br/>SfB\* |<br/>仅团队|
|--- |--- |--- |--- |---|
|SfB <br/> Teams|&boxv;<br/>&boxv;<br/> |SfB <br/>Teams | SfB <br/>SfB | Teams  <br/> Teams |
| | | | |

## <a name="federated-presence"></a>联盟的状态

联盟的状态基于表 2 所示联盟可访问性。

下表描述了将会看到的观察程序，具体取决于发行者的模式和 （对于新的线程） 观察程序的客户端的发布者的状态。 实际上客户端的观察程序将在此阶段的联合身份验证中没有区别。

**表 4： 联合的状态 （新线程）**

|观察程序 <br/> 客户端 | |<br/> 群岛  |Publisher <br/> SfB\* |<br/> 仅团队  |
|--- |--- |--- |--- |---|
|SfB <br/> Teams|&boxv;<br/>&boxv; |SfB <br/> SfB | SfB <br/> SfB | Teams <br/> Teams |
| | | | ||

## <a name="presence-in-pre-existing-threads"></a>事先线程中的状态

为了对齐状态和事先线程，目标的状态公开，需要使用，路由对齐线程中可访问性假定路由是线程的可能的。

特别是，如果收件人先前必须与持久的互操作性会话线索随后升级到团队线程将不再反映准确的状态，并将不再可路由。 您应开始新的线程。
