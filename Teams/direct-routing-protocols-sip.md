---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由协议
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0756860bc6fad7a470a33e00ac8452e7977ecde0
ms.sourcegitcommit: 93c5afed49f47574f1b00305e5dfbb8a89be02a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2020
ms.locfileid: "44859647"
---
# <a name="direct-routing---sip-protocol"></a>直接路由-SIP 协议

本文介绍直接路由如何实现会话初始协议（SIP）。 若要正确路由会话边界控制器（SBC）和 SIP 代理之间的流量，某些 SIP 参数必须具有特定值。 本文面向负责配置本地 SBC 和 SIP 代理服务之间的连接的语音管理员。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>处理传入请求：查找租户和用户

在传入呼叫中，SIP 代理需要找到呼叫指向的租户，并在此租户内找到特定用户。 租户管理员可以在多个租户中配置非已完成号码（例如 + 1001）。 因此，查找要在其上执行数字查找的特定租户非常重要，因为在多个 Microsoft 365 或 Office 365 组织中的非数字可能相同。  

本部分介绍 SIP 代理如何查找租户和用户，并对传入连接执行 SBC 身份验证。

下面是一个传入呼叫的 SIP 邀请消息的示例：

| 参数名称 | 值的示例 | 
| :---------------------  |:---------------------- |
| 请求 URI | 邀请 sip:+18338006777@sip.pstnhub.microsoft.com SIP/2。0 |
| 通过页眉 | Via： SIP/2.0/TLS sbc1 biz： 5058; alias; branch = z9hG4bKac2121518978 | 
| 最大转发标题 | 最大转发：68 |
| 从页眉 | 来自以下内容的页眉： <sip： 7168712781@sbc1 biz; transport = udp; tag = 1c747237679 |
| 到页眉 | 收件人： sip:+183338006777@sbc1.adatum.biz | 
| CSeq 标头 | CSeq：1个邀请 | 
| 联系人页眉 | 联系： <sip： 68712781@sbc1 biz： 5058; transport = tls> | 

收到邀请后，SIP 代理执行以下步骤：

1. 检查证书。 在初始连接中，直接路由服务获取在联系人标头中显示的 FQDN 名称，并将其与所显示的证书的公用名或使用者备用名称相匹配。 SBC 名称必须匹配以下选项之一：

   - 选项 1. 在联系人标题中显示的完整 FQDN 名称必须与所显示的证书的通用名称/使用者备用名称相匹配。  

   - 选项 2. 在联系人标题中显示的 FQDN 名称的域部分（例如 FQDN 名称 sbc1.adatum.biz 的 adatum.biz）必须与公用名称/使用者可选名称（例如 *. adatum.biz）中的通配符相匹配。

2. 尝试使用在联系人标题中显示的完整 FQDN 名称查找租户。  

   检查联系人标题（sbc1.adatum.biz）中的 FQDN 名称是否注册为任何 Microsoft 365 或 Office 365 组织中的 DNS 名称。 如果找到，将在具有注册为域名的 SBC FQDN 的租户中执行用户查找。 如果未找到，则应用步骤3。   

3. 步骤3仅适用于步骤2失败的情况。 

   从 FQDN 中删除主机部分，显示在联系人标头（FQDN： sbc12.adatum.biz 中，删除主机部分后： adatum.biz），然后检查此名称是否注册为任何 Microsoft 365 或 Office 365 组织中的 DNS 名称。 如果找到，将在此租户中执行用户查找。 如果找不到，调用将失败。

4. 使用请求 URI 中显示的电话号码，在步骤2或3中发现的租户内执行反向号码查找。 将所提供的电话号码与上一步中找到的租户内的用户 SIP URI 相匹配。

5. 应用干线设置。 查找由租户管理员为此 SBC 设置的参数。

   Microsoft 不支持在 Microsoft SIP 代理和成对的 SBC 之间拥有第三方 SIP 代理或用户代理服务器，这可能会修改成对的 SBC 创建的请求 URI。

   本文稍后部分将介绍两个查找（步骤2和3）所需的情况（步骤2和步骤3）。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>联系人标题和请求 URI 的详细要求

#### <a name="contact-header"></a>联系人页眉

对于所有传入的 Microsoft SIP 代理呼叫，联系人头必须在 URI 主机名中具有成对的 SBC FQDN，如下所示：

语法： Contact： <sip： SBC 的电话或 sip address@FQDN; 传输 = tls> 

此名称还必须位于所显示的证书的 "公用名" 或 "主题备用名称" 字段中。 Microsoft 支持在证书的 "公用名" 或 "主题备用名称" 字段中使用名称的通配符。   

在[RFC 2818 的第3.1 节](https://tools.ietf.org/html/rfc2818#section-3.1)中介绍了对通配符的支持。 具体地说

*"名称可以包含通配符， \* 该字符被视为匹配任何单个域名组件或组件片段。例如， \* a.com 匹配 foo.a.com，而不是 bar.foo.a.com \* 匹配 foo.com，而不是 bar.com。 "*

如果由 SBC 发送 SIP 消息中显示的联系人标头中的多个值，则仅使用联系人标头第一个值的 FQDN 部分。

#### <a name="request-uri"></a>请求 URI 

对于所有传入呼叫，请求 URI 用于匹配用户的电话号码。   

当前电话号码必须包含加号（+），如以下示例中所示。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a>联系人和记录-路线标题注意事项

SIP 代理需要为新的对话客户端事务（如再见或重新邀请）和答复 SIP 选项计算下一个跃点 FQDN。 使用 "联系人" 或 "记录"-路线。 

根据 RFC 3261，任何可能导致新对话的请求都需要联系人标题。 仅当代理希望在对话框中保留未来请求的路径时，才需要记录路由。 如果代理 SBC 与[用于直接路由的本地媒体优化](https://docs.microsoft.com/MicrosoftTeams/direct-routing-media-optimization)一起使用，则需要配置记录路由，因为代理 sbc 需要保留在路由中。 

如果未使用代理 SBC，Microsoft 建议仅使用联系人标头：

- 在每个 RFC 3261 中，如果代理希望在对话框中保留未来请求的路径，并且在 Microsoft SIP 代理和成对的 SBC 之间进行所有通信时，这不是必需的，则使用记录路由。 

- Microsoft SIP 代理仅使用联系人头（而不是记录路由）来确定发送出站 ping 选项时的下一跃点。 如果代理 SBC 未使用，则仅配置一个参数（联系人），而不是两个（联系人和记录路由）可简化管理。 

要计算下一跃点，SIP 代理使用：

- 优先级1。 顶层记录-路由。 如果顶级记录路由包含 FQDN 名称或 IP，则 FQDN 名称或 IP 用于创建出站内置对话连接。

- 优先级2。 联系人标题。 如果记录路径不存在，SIP 代理将查找联系人标头的值以建立出站连接。 （这是推荐的配置。）

如果同时使用了联系人和记录路线，则 SBC 管理员必须保持其值相同，从而导致管理开销。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>在联系人或记录中使用 FQDN 名称-路由

在记录-路由或联系人中不支持使用 IP 地址。 唯一支持的选项是 FQDN，它必须与 SBC 证书的公用名称或使用者备用名称匹配（证书中的通配符受支持）。

- 如果 IP 地址显示在 "记录"-"路由" 或 "联系人" 中，则证书检查失败，并且呼叫失败。

- 如果 FQDN 与所显示的证书中的常见或主题备用名称的值不匹配，则调用将失败。 

## <a name="inbound-call-sip-dialog-description"></a>入站呼叫： SIP 对话框说明

下表总结了非绕过和绕过模式之间的通话流差异和相似性：

| 参数名称 | 非绕过模式 | 绕过模式
| :---------------------  |:---------------------- |:----------------|
| 183和200消息中的媒体候选人来自 | 媒体处理器 | 客户端 | 
| SBC 可以接收的183消息数 | 每个会话一个 | 名 | 
| 可通过临时答案进行呼叫（183） | 是 | 是 |
| 通话可能没有临时应答（183） | 是 | 是 |

###  <a name="non-media-bypass-flow"></a>非媒体旁路流

团队用户可能同时具有多个终结点。 例如，Windows 客户端团队、iPhone 客户端团队和团队手机（团队 Android 客户端）。 每个终结点可能发出 HTTP rest 的信号，如下所示：

-   呼叫进度–由 SIP 代理将其转换为 SIP 消息180。 在接收消息180时，SBC 必须生成本地震铃。

-   媒体应答–通过 SIP 代理将其转换为消息183，在会话描述协议（SDP）中使用媒体候选人。 在接收消息183时，SBC 预期连接到在 SDP 消息中接收的媒体候选人。 请注意，在某些情况下，可能不会生成媒体答案，并且终结点可能会收到 "接受通话" 消息的答案。

-   通话被接受–由 SIP 代理通过 SDP 转换到 SIP 消息200。 在接收消息200时，SBC 应在提供的 SDP 候选人中发送和接收媒体。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>多个终结点通过临时答案进行铃声

1.  收到来自 SBC 的第一个邀请后，SIP 代理会发送消息 "SIP SIP/2.0 100 尝试"，并通知所有最终用户终结点的传入呼叫。 

2.  收到通知后，每个终结点将开始向 SIP 代理发送 "呼叫进度" 消息。 由于团队用户可以有多个终结点，因此 SIP 代理可能会收到多个呼叫进度消息。

3.  对于从客户收到的每个呼叫进度消息，SIP 代理将呼叫进度消息转换为 SIP 消息 "SIP SIP/2.0 180 尝试"。 发送此类消息的间隔由来自呼叫控制器的接收邮件的间隔定义。 在下图中，SIP 代理生成了 2 180 封邮件。 这些消息来自用户的两个团队终结点。 每个客户都有一个唯一的标记 ID。  来自不同终结点的每条消息将是一个单独的会话（"收件人" 字段中的参数 "tag" 将不同）。 但是，终结点可能不会生成消息180并立即发送消息183，如下图中所示。

4.  一旦终结点生成带有终结点媒体候选人的 IP 地址的媒体答案消息，SIP 代理会将收到的消息转换为 "SIP 183 会话进度" 消息，该消息包含客户端从媒体处理器替换的来自客户端的 sdp。 在下图中，派生2的终结点应答呼叫。 如果主干是非绕过的，则 183 SIP 消息仅生成一次（即环机器人或客户端终结点）。 183可能会产生一个现有的分叉或开始一个新的分叉。

5.  将使用接受呼叫的终结点的最终候选项发送呼叫接受消息。 通话接受消息将转换为 SIP 消息200。 

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>多个终结点在没有临时应答的情况下响铃

1.  收到来自 SBC 的第一个邀请后，SIP 代理会发送消息 "SIP SIP/2.0 100 尝试"，并通知所有最终用户终结点的传入呼叫。 

2.  收到通知后，每个终结点将开始向 SIP 代理发送消息 "呼叫进度"。 由于团队用户可以有多个终结点，因此 SIP 代理可能会收到多个呼叫进度消息。

3.  对于从客户收到的每个呼叫进度消息，SIP 代理将呼叫进度消息转换为 SIP 消息 "SIP SIP/2.0 180 尝试"。  发送消息的间隔由接收来自呼叫控制器的邮件的间隔定义。 在下面的图片中，SIP 代理生成 2 180 消息，这意味着用户登录到三个团队客户和每个客户端发送呼叫进度。 每封邮件都将是单独的会话（"收件人" 字段中的参数 "标记" 不同）

4.  将使用接受呼叫的终结点的最终候选项发送呼叫接受消息。 通话接受消息将转换为 SIP 消息200。 

![图表显示多个终结点在没有临时应答的情况下响铃](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>媒体绕过流

媒体绕过方案中使用的消息（100尝试、180、183）相同。 

下面的架构显示了绕过通话流的示例。 请注意，媒体候选人可以来自不同的终结点。 

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>替换选项

SBC 必须支持替换的邀请。

## <a name="size-of-sdp-considerations"></a>SDP 注意事项的大小

直接路由接口可能会发送超过1500字节的 SIP 消息。  SDP 的大小主要是导致这种情况。 但是，如果在 SBC 后面有一个 UDP 主干，则它可能会在从 Microsoft SIP 代理转发到未修改的中继时拒绝该消息。 Microsoft 建议在 SBC 上将消息发送到 UDP 中继时，在 SBC 上去除一些值。 例如，可以删除 ICE 候选人或未使用的编解码器。

## <a name="call-transfer"></a>呼叫转接

直接路由支持呼叫转接的两种方法：

- 选项 1. SIP 代理进程从本地引用客户端，并充当 RFC 3892 第7.1 节中所述的 Referee。

  使用此选项，SIP 代理将终止传输并添加新邀请。 


- 选项 2. SIP 代理发送对 SBC 的引用并充当 Transferor，如 RFC 5589 的第6节中的描述所述。

  使用此选项，SIP 代理会发送一个指向 SBC 的参考，并期望 SBC 完全处理传输。

SIP 代理根据 SBC 所报告的功能选择该方法。 如果 SBC 指示它支持方法 "参阅"，则 SIP 代理将对呼叫转移使用选项2。

下面是一个 SBC 的示例，该示例发送消息指出支持引用方法：

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

如果 SBC 未指示引用为受支持的方法，直接路由将使用选项1（SIP 代理充当 Referee）。 SBC 还必须发出支持 Notify 方法的信号：

SBC 的示例（指示不支持参考方法）：

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP 代理进程在本地引用客户端并充当 Referee

如果 SBC 指示不支持参阅方法，则 SIP 代理充当 Referee。 

来自客户端的引用请求将在 SIP 代理上终止。 （客户端的引用请求在下图中显示为 "呼叫转接至 Dave"。  有关详细信息，请参阅[RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)的7.1 节。 

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP 代理发送对 SBC 的引用并充当 Transferor

这是呼叫转接的首选方法，对于寻找媒体绕过证书的设备是必需的。 在媒体绕过模式下不支持 SBC 能够处理引用的呼叫转接。 

标准将在 RFC 5589 的第6节中介绍。 相关 Rfc 包括：

- [会话初始协议（SIP）呼叫控制-转移](https://tools.ietf.org/html/rfc5589)

- [会话初始协议（SIP） "替换" 标头](https://tools.ietf.org/html/rfc3891)

- [会话初始协议（SIP） "被指" 机制](https://tools.ietf.org/html/rfc3892)

此选项假定 SIP 代理充当 Transferor，并向 SBC 发送一条参考消息。 SBC 充当 Transferee 并处理用于传输的新优惠的参考。 有两种可能的情况：

- 将呼叫转移到外部 PSTN 参与者。 
- 通过 SBC 将呼叫从一个团队用户转移到同一租户中的另一个团队用户。 

如果通过 SBC 将呼叫从一个团队用户转移到另一个团队，则 SBC 应使用参考消息中接收的信息为传输目标（团队用户）发出新的邀请（开始新的对话框）。 

要为请求的内部事务填充 "收件人/Transferor" 字段，SIP 代理需要将此信息传达在 "引用"/"引用方" 标题内。 

SIP 代理将作为 SIP URI （由主机名中的 SIP 代理 FQDN 和下列任一项之一）组成的 "引用为 SIP URI"：

- URI 的用户名部分中的 E.i 电话号码，如果转移目标是电话号码，则为

- 每个 x-m 和 x t 参数分别编码完整的传输目标 MRI 和租户 ID 

被引用的标头是 transferor MRI 编码的 SIP URI，以及 transferor 租户 ID 和其他传输上下文参数，如下表所示：

| 参数 | 值 | 说明 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | Transferor 的所有 MRI/转移目标（由 CC 填充） |
| x-t | 租户 ID | x-t 租户 ID 由 CC 填充的可选租户 Id |
| x-ti | Transferor 相关性 Id | 对 transferor 的调用的相关 Id |
| x-tt | 传输目标呼叫 URI | 已编码的调用替换 URI |

在这种情况下，引用页眉的大小最多可以为400符号。 SBC 必须支持处理引用的消息大小最多为400个符号。

![显示多个终结点和临时应答的图表](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>会话计时器

SIP 代理支持（始终提供）在非绕过呼叫中的会话计时器，但不在绕过呼叫时提供。 SBC 使用会话计时器不是必需的。

##  <a name="use-of-request-uri-parameter-userphone"></a>使用请求 URI 参数 user = phone

SIP 代理分析请求 URI，如果参数 user = phone 存在，服务会将请求 URI 作为电话号码处理，并将该号码与用户相匹配。 如果参数不存在，SIP 代理会应用试探法来确定请求 URI 用户类型（电话号码或 SIP 地址）。

Microsof 建议始终应用 user = phone 参数以简化呼叫设置过程。

## <a name="history-info-header"></a>历史记录-信息标题

历史记录信息标头用于 retargeting SIP 请求和 "提供一种用于捕获请求历史记录信息的标准机制，以便为网络和最终用户提供多种服务。" 有关详细信息，请参阅[RFC 4244 –第1.1 部分](http://www.ietf.org/rfc/rfc4244.txt)。 对于 Microsoft Phone 系统，在 Simulring 和呼叫转发方案中使用此标题。  

如果发送，则将启用历史记录信息，如下所示：

- SIP 代理将在包含历史记录信息头（已发送到 PSTN 控制器）的单个历史记录信息条目中插入一个包含相关电话号码的参数。  PSTN 控制器仅使用具有电话号码参数的条目，它将重建新的历史记录信息标头，并通过 SIP 代理将其传递到 SIP 中继提供程序。

- 将为同时拨打和呼叫转移案例添加历史记录-信息标题。

- 将不会为呼叫转移案例添加历史记录-信息标题。

- 已重建历史记录-信息标头中的单个历史记录项将提供与直接路由 FQDN （sip.pstnhub.microsoft.com）组合的电话号码参数，该参数设置为 URI 的主机部分;"user = phone" 的参数将作为 SIP URI 的一部分添加。  除了手机上下文参数外，与原始历史记录信息标题关联的任何其他参数都将在重新构建的历史记录信息标题中传递。  请注意，专用项（由 RFC 4244 的3.3 中定义的机制确定）将按原样转发，因为 SIP 中继提供程序是受信任的对等。

- 入站历史记录-信息被忽略。

以下是 SIP 代理发送的历史记录信息头的格式：

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

如果多次呼叫被重定向，则有关每次重定向的信息都包含在按时间顺序排列的相应原因中。


页眉示例：

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

历史记录-信息受强制 TLS 机制的保护。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>与直接路由和故障转移机制的 SBC 连接

请参阅[计划中用于直接路由](direct-routing-plan.md#failover-mechanism-for-sip-signaling)的 SIP 信号的故障转移机制部分。

## <a name="retry-after"></a>重试-在

如果直接路由数据中心正忙，则该服务可以向 SBC 发送一秒钟间隔后的重试消息。 当 SBC 收到503消息，并且使用重试头响应某个邀请时，SBC 必须终止该连接并尝试下一个可用的 Microsoft 数据中心。 

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 重启：转到不支持媒体绕过的终结点的媒体旁路呼叫。

SBC 必须支持["9.1.1.1" 部分中的 RFC 5245](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)中所述的 ICE 重启。

直接路由中的重启按照 RFC 的以下段落实现：

*若要重新启动 ICE，工程师必须在优惠中更改媒体流的冰密码和 ice ufrag。 请注意，允许在一个提供中使用会话级属性，但在后续优惠中提供与媒体级属性相同的 ice pwd 或 ice ufrag。 这不是密码更改，而是对其表示形式的更改，并且不会导致 ICE 重启。*

*在此媒体流的初始提供中，代理将此媒体流的其他字段设置为该媒体流的其他字段（请参阅4.3 节）。 因此，候选集可能包含该流的部分、全部或所有候选项，并且可能包括一组全新的候选项，如4.1.1 节中所述。*

如果呼叫最初是使用 "媒体绕过" 建立的，并且呼叫转移到 Skype for business 客户端，直接路由需要插入媒体处理器-这是因为直接路由无法与具有媒体旁路的 Skype for Business 客户端配合使用。 直接路由通过更改 ice-pwd 和 ice ufrag 并在 reinvite 中提供新的媒体候选人来启动 ICE 重启过程。 


