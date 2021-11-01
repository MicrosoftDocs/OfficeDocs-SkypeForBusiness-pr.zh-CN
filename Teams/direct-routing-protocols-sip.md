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
ms.openlocfilehash: 01748c0e344cbadf2d771d2ab4bf6ad1f9b14dfb
ms.sourcegitcommit: 813f1e44bd094bd997dd7423cda7e685ff61498f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2021
ms.locfileid: "60633518"
---
# <a name="direct-routing---sip-protocol"></a>直接路由 - SIP 协议

本文介绍直接路由如何在 SIP 中实现会话 (协议) 。 若要在会话边界控制器与 SBC (SBC) 之间正确路由流量，某些 SIP 参数必须具有特定值。 本文适用于负责配置本地 SBC 与 SIP 代理服务之间的连接的语音管理员。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>处理传入请求：查找租户和用户

处理传入或出站呼叫之前，在 SIP 代理和 SBC 之间交换 OPTIONS 消息。 这些 OPTIONS 消息允许 SIP 代理向 SBC 提供允许的功能。 必须成功通过 OPTIONS 协商 (200OK) ，从而在 SBC 和 SIP 代理之间进一步通信以建立呼叫。 下面提供了一个示例，在发送到 SIP 代理的 OPTIONS 消息中提供 SIP 标头：

| 参数名称 | 值的示例 | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip：sip.pstnhub.microsoft.com：5061 SIP /2.0 |
| 通过标头 | 通过：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards 标头 | 最大转发数：68 |
| 从标头 | From Header From： <sip:sbc1.adatum.biz:5058> |
| To Header | 自： <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq 标头 | CSeq：1 INVITE | 
| 联系人头 | 联系人： <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> SIP 标头在使用的 SIP URI 中不包含 userinfo。 根据 [RFC 3261 第 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)节，URI 的 userinfo 部分是可选的，当目标主机没有用户概念或当主机本身是标识的资源时，可能会不存在。 如果 SIP URI 中存在 @ 符号，则用户字段不得为空。

在传入呼叫中，SIP 代理需要查找呼叫目标为的租户，并在此租户中查找特定用户。 租户管理员可以在多个租户中配置非 DID 号码，例如 +1001。 因此，必须查找要执行数字查找的特定租户，因为非 DID 数字可能在多个组织或组织Microsoft 365相同Office 365。  

本部分介绍 SIP 代理如何查找租户和用户，以及如何对传入连接执行 SBC 身份验证。

下面是传入呼叫上的 SIP 邀请消息的示例：

| 参数名称 | 值的示例 | 
| :---------------------  |:---------------------- |
| Request-URI | 邀请 sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| 通过标头 | 通过：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards 标头 | 最大转发数：68 |
| 从标头 | 从头文件来源：<sip：+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| To Header | To： sip:+183338006777@sbc1.adatum.biz | 
| CSeq 标头 | CSeq：1 INVITE | 
| 联系人头 | 联系人：<sip：68712781@sbc1.adatum.biz：5058;transport=tls> | 

在收到邀请时，SIP 代理将执行以下步骤：

1. 检查证书。 在初始连接上，直接路由服务采用 Contact 标头中呈现的 FQDN 名称，并匹配该名称与所呈现证书的公用名称或主题可选名称。 SBC 名称必须与以下选项之一匹配：

   - 选项 1. Contact 标头中提供的完整 FQDN 名称必须与所呈现证书的公用名称/主题可选名称匹配。  

   - 选项 2. 联系人标头 (例如 FQDN 名称 sbc1.adatum.biz) 的 adatum.biz 中呈现的 FQDN 名称的域部分必须与公用名称/主题可选名称 (例如 *.adatum.biz) 中的通配符值匹配。

2. 尝试使用 Contact 标头中提供的完整 FQDN 名称查找租户。  

   检查联系人标头中的 FQDN 名称 (sbc1.adatum.biz) 注册为任何组织或组织Microsoft 365 DNS Office 365名称。 如果找到，在 SBC FQDN 已注册为域名的租户中执行用户的查找。 如果未找到，则步骤 3 适用。   

3. 步骤 3 仅适用于步骤 2 失败的情况。 

   删除主机部分 adatum.biz) 后，从联系人标头 (FQDN： sbc12.adatum.biz 中呈现的 FQDN 中删除主机部分，并检查此名称是否注册为任何 Microsoft 365 或 Office 365 组织的 DNS 名称。 如果找到，则在此租户中执行用户查找。 如果未找到，则调用会失败。

4. 使用 Request-URI 中提供的电话号码，在步骤 2 或 3 中的租户内执行反向号码查找。 将提供的电话号码与上一步找到的租户中的用户 SIP URI 匹配。

5. 应用中继设置。 查找租户管理员为此 SBC 设置的参数。

   Microsoft 不支持在 Microsoft SIP 代理和配对 SBC 之间设置第三方 SIP 代理或用户代理服务器，这可能会修改配对 SBC 创建的请求 URI。

   本文 (稍后将介绍一个 SBC 与许多租户 (运营商方案) 互连的方案所需的两个查找步骤 2 和 3) 。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>Contact 标头和 Request-URI 的详细要求

#### <a name="contact-header"></a>联系人头

对于所有传入的 SIP (OPTIONS，INVITE) 到 Microsoft SIP 代理，联系人标头必须在 URI 主机名中具有配对的 SBC FQDN，如下所示：

语法：联系人：<SBC 的 sip：phone 或 sip address@FQDN;transport=tls> 

根据 [RFC 3261 第 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)节，"联系人标题"字段可能存在于"选项"消息中。 在"直接路由"中，需要联系人标头。 对于上述格式的 INVITE 消息，对于 OPTIONS 消息，可以从 SIP URI 中删除 userinfo，并且仅按以下格式发送 FQDN：

语法：Contact：<SBC 的 sip：FQDN;transport=tls>

此名称 (FQDN) 还必须在所提供证书的"公用名称"或" (可选) 字段。 Microsoft 支持在证书的"公用 (或) 可选名称"字段中使用名称的通配符值。   

RFC [2818 第 3.1 部分介绍了对通配符的支持](https://tools.ietf.org/html/rfc2818#section-3.1)。 具体而言：

*"名称可能包含通配符 \* ，该通配符被视为匹配任何单个域名组件或组件片段。例如 \* ，.a.com 与 foo.a.com 匹配，bar.foo.a.com.com \* foo.com，bar.com。"*

如果 SBC 发送了 SIP 消息中"联系人"标头中的多个值，则只会使用"联系人"标头的第一个值的 FQDN 部分。

根据直接路由的经验法则，使用 FQDN 填充 SIP URI 而不是 IP 非常重要。 传入的 INVITE 或 OPTIONS 消息发送到包含联系人标头的 SIP 代理，其中主机名由 IP 表示，而不是 FQDN，连接将被拒绝并出现 403 禁止访问。

#### <a name="request-uri"></a>Request-URI 

对于所有传入呼叫，使用 Request-URI 将电话号码与用户匹配。   

目前电话号码必须包含加号 (+) 如以下示例所示。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>从标头

对于所有传入呼叫，"从标头"用于将呼叫者的电话号码与被呼叫者的阻止电话号码列表匹配。

电话号码必须包含 +，如以下示例所示。

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>联系人Record-Route头注意事项

SIP 代理需要计算新对话客户端事务的下一跃点 FQDN (例如 Bye 或重新邀请) ，以及答复 SIP 选项时。 使用"Record-Route联系人"或"联系人"。 

根据 [RFC 3261 第 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)部分，任何可能导致新对话的请求都需要联系人标头。 只有Record-Route想要停留在对话中未来请求的路径时，才需要该请求。 如果代理 SBC 与直接路由的本地媒体优化一同 [使用](./direct-routing-media-optimization.md)，则需要配置记录路由，因为代理 SBC 需要停留在路由中。 

如果未使用代理 SBC，Microsoft 建议仅使用 Contact 标头：

- 根据 [RFC 3261，](https://tools.ietf.org/html/rfc3261#section-20.30)如果代理想要停留在对话中未来请求的路径上，则使用第 20.30 节 Record-Route，如果没有配置代理 SBC，因为所有流量在 Microsoft SIP 代理和配对的 SBC 之间移动，则这不是必要的。 

- Microsoft SIP 代理仅使用 Contact 标头 (而不是 Record-Route) 发送出站 ping 选项时确定下一跃点。 如果代理 SBC (，) Contact (和 Record-Route) 仅配置一个参数，可简化管理。 

若要计算下一跃点，SIP 代理使用：

- 优先级 1. 顶级记录路由。 如果顶级Record-Route包含 FQDN 名称，则 FQDN 名称用于建立出站对话内连接。

- 优先级 2. 联系人头。 如果Record-Route，SIP 代理将查找 Contact 标头的值以建立出站连接。  (这是建议的配置.) 

如果使用 Contact 和 Record-Route，SBC 管理员必须保持其值相同，这会造成管理开销。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>在联系人或联系人中使用 FQDN Record-Route

在"联系人"或"联系人"中Record-Route IP 地址。 唯一支持的选项是 FQDN，它必须匹配 SBC 证书的公用名称或主题可选名称， (证书中的通配符值) 。

- 如果"记录路由"或"联系人"中显示 IP 地址，证书检查会失败，调用会失败。

- 如果 FQDN 与呈现的证书中"通用"或"主题可选名称"的值不匹配，则调用会失败。 

## <a name="inbound-call-sip-dialog-description"></a>入站呼叫：SIP 对话框说明

下表汇总了非绕过和绕过模式之间的呼叫流差异和相似性：

| 参数名称 | 非绕过模式 | 绕过模式
| :---------------------  |:---------------------- |:----------------|
| 来自 183 和 200 条消息的媒体候选者 | 媒体处理器 | 客户端 | 
| SBC 可以接收的 183 条消息数 | 每个会话一个 | 多个 | 
| 呼叫可以是使用 183 (临时)  | 是 | 是 |
| 呼叫无需 183 (临时)  | 是 | 是 |

###  <a name="non-media-bypass-flow"></a>非媒体旁路流

一Teams用户可能同时有多个终结点。 例如，Teams客户端Windows，Teams客户端iPhone，Teams 电话 (Teams Android 客户端) 。 每个终结点可能会发出 HTTP REST 信号，如下所示：

-   呼叫进度 - 由 SIP 代理转换为 SIP 消息 180。 收到消息 180 时，SBC 必须生成本地响铃。

-   媒体应答 - 由 SIP 代理转换为消息 183，在"会话说明协议"中将媒体候选项 (SDP) 。 收到消息 183 时，SBC 需要连接到在 SDP 消息中收到的媒体候选项。 

    > [!NOTE]
    > 在某些情况下，媒体应答可能未生成，并且最终点可能使用"已接受呼叫"消息进行应答。

-   已接受呼叫 – 由 SIP 代理转换为包含 SDP 的 SIP 消息 200。 收到消息 200 时，SBC 预期会向提供的 SDP 候选项发送和接收媒体。

    > [!NOTE]
    > 直接路由不支持在没有 SDP (的延迟产品/服务邀请) 。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>多个终结点使用临时答案响铃

1.  从 SBC 接收第一个邀请时，SIP 代理发送消息"SIP/2.0 100 正在尝试"，并通知所有最终用户终结点传入呼叫。 

2.  通知后，每个终结点都将开始响铃，向 SIP 代理发送"呼叫进度"消息。 由于Teams可以有多个终点，SIP 代理可能会收到多个呼叫进度消息。

3.  对于从客户端收到的每个呼叫进度消息，SIP 代理将呼叫进度消息转换为 SIP 消息"SIP/2.0 180 正在尝试"。 发送此类消息的间隔由从调用控制器接收消息的间隔定义。 下图显示了 SIP 代理生成的两条 180 条消息。 这些消息来自用户的Teams终结点。 每个客户端都有唯一的标记 ID。  来自不同终结点的每条消息都是单独的会话 ("收件人"字段中的参数"tag"与) 。 但是，终结点可能不会立即生成消息 180 并发送消息 183，如下图所示。

4.  终结点使用终结点的媒体候选项的 IP 地址生成媒体应答消息后，SIP 代理会将收到的消息转换为"SIP 183 会话进度"消息，并将来自客户端的 SDP 替换为来自媒体处理器的 SDP。 下图中，分叉 2 中的终结点应答了调用。 如果未绕过中继，则仅生成 183 SIP 消息一次 (机器人或客户端) 。 183 可能位于现有分叉上或启动新分叉。

5.  "呼叫接受"消息与接受呼叫的终结点的最终候选项一起发送。 呼叫接受消息将转换为 SIP 消息 200。 

> [!div class="mx-imgBorder"]
> ![显示多个终结点在临时应答中响铃的示意图。](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>多个终结点在无临时应答的情况下响铃

1.  从 SBC 接收第一个邀请时，SIP 代理发送消息"SIP/2.0 100 正在尝试"，并通知所有最终用户终结点传入呼叫。 

2.  通知后，每个终结点都将开始响铃，并发送消息"呼叫进度"到 SIP 代理。 由于Teams可以有多个终点，SIP 代理可能会收到多个呼叫进度消息。

3.  对于从客户端收到的每个呼叫进度消息，SIP 代理将呼叫进度消息转换为 SIP 消息"SIP/2.0 180 正在尝试"。  发送消息的间隔由从调用控制器接收消息的间隔定义。 下图显示了 SIP 代理生成的两条 180 条消息，这意味着用户登录到三个客户端Teams客户端发送呼叫进度。 每条消息将是单独的会话， ("收件人"字段中的参数"tag"不同于) 

4.  "呼叫接受"消息与接受呼叫的终结点的最终候选项一起发送。 呼叫接受消息将转换为 SIP 消息 200。 

> [!div class="mx-imgBorder"]
> ![显示多个终结点在无临时应答的情况下响铃的示意图。](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>媒体旁路流

在媒体旁路方案中 (100 尝试、180、183) 相同的消息。 

下面的架构显示了绕过调用流的一个示例。 

> [!NOTE]
> 媒体候选项可以来自不同的终结点。 

> [!div class="mx-imgBorder"]
> ![显示多个终结点在临时应答中响铃的示意图。](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>替换选项

SBC 必须支持"使用替换邀请"。

## <a name="size-of-sdp-considerations"></a>SDP 注意事项的大小

直接路由接口可能会发送超过 1，500 字节的 SIP 消息。  SDP 的大小主要会导致这种情况。 但是，如果 SBC 后面有 UDP 中继，如果消息从 Microsoft SIP 代理转发到未修改的中继，则可能会拒绝该消息。 Microsoft 建议在将消息发送到 UDP 中继时，去除 SBC 上的 SDP 中的某些值。 例如，可以删除 ICE 候选项或未使用的编解码器。

## <a name="call-transfer"></a>呼叫转移

直接路由支持两种调用传输方法：

- 选项 1. SIP 代理进程 从本地客户端引用，并充当 RfC 3892 的第 7.1 部分中所述的"代理"。

  使用此选项，SIP 代理终止传输并添加新的"邀请"。 


- 选项 2. SIP 代理发送参考 SBC，并充当 RFC 5589 第 6 节中描述的传输程序。

  使用此选项，SIP 代理发送"引用 SBC"，并期望 SBC 完全处理传输。

SIP 代理根据 SBC 报告的功能选择方法。 如果 SBC 指示它支持"参考"方法，则 SIP 代理将使用选项 2 进行呼叫转移。

下面是发送 Refer 方法受支持消息的 SBC 示例：

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

如果 SBC 未指示"引用为受支持的方法"，则直接路由将使用选项 1 (SIP 代理充当"下属) "。 SBC 还必须发出信号，表明它支持 Notify 方法：

指示不支持 Refer 方法的 SBC 示例：

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP 代理进程 从客户端本地引用，充当代理

如果 SBC 指示不支持 Refer 方法，则 SIP 代理将充当一个代理人。 

来自客户端的"引用"请求将在 SIP 代理上终止。  (图中，来自客户端的"转接"请求显示为"呼叫 Dave"。  有关详细信息，请参阅 [RFC 3892 的第 7.1 部分](https://www.ietf.org/rfc/rfc3892.txt)。 

> [!div class="mx-imgBorder"]
> ![显示多个终结点在临时应答中响铃的示意图。](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP 代理发送参考 SBC 并充当传输程序

这是呼叫转接的首选方法，对于寻求媒体绕过认证的设备，这是强制方法。 媒体旁路模式不支持在 SBC 无法处理"引用"的情况下进行呼叫转移。 

RFC 5589 的第 6 部分介绍了标准。 相关的 RFC 包括：

- [SIP 会话启动 (协议) 呼叫控制 - 传输](https://tools.ietf.org/html/rfc5589)

- [会话启动协议 (SIP) "Replaces"标头](https://tools.ietf.org/html/rfc3891)

- [会话启动协议 (SIP) "引用者"机制](https://tools.ietf.org/html/rfc3892)

此选项假定 SIP 代理充当传输程序，并将"参考"消息发送到 SBC。 SBC 充当受让方，并处理"引用"以生成要转移的新产品/服务。 有两种可能的情况：

- 呼叫将转接到外部 PSTN 参与者。 
- 该调用通过 SBC 从一Teams用户转移到Teams租户中的另一个用户。 

如果呼叫通过 SBC 从一个 Teams 用户转移到另一个用户，则 SBC 应发出新的邀请 (使用"参考"消息中收到的信息为 Teams) 用户 (启动新的对话) 。 

若要在内部填充请求事务的"To/Transferor"字段，SIP 代理需要在 REFER-TO/REFERRED-BY 标头内传达此信息。 

SIP 代理将构成引用作为 SIP URI，该 URI 由主机名中的 SIP 代理 FQDN 和以下任一项组成：

- URI 用户名部分中的 E.164 电话号码，以防转移目标是电话号码，或者

- x-m 和 x-t 参数分别编码完整传输目标 MRI 和租户 ID 

REFERRED-BY 标头是一个 SIP URI，该 URI 中编码了传输器 MRI，以及传输器租户 ID 和其他传输上下文参数，如下表所示：

| 参数 | 值 | 说明 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | 由抄送填充的传输器/传输目标的完整 MRI |
| x-t | 租户 ID | x-t 租户 ID 可选租户 ID，由 CC 填充 |
| x-ti | 传输器关联 ID | 调用传输器的相关 ID |
| x-tt | 传输目标调用 URI | 编码的呼叫替换 URI |

在这种情况下，引用标题的大小最多为 400 个符号。 SBC 必须支持处理大小最多为 400 个符号的"引用"消息。

> [!div class="mx-imgBorder"]
> ![显示多个终结点在临时应答中响铃的示意图。](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>会话计时器

SIP 代理支持 (在) 调用时始终提供会话计时器，但不在绕过呼叫时提供它。 SBC 不强制使用会话计时器。

##  <a name="use-of-request-uri-parameter-userphone"></a>使用 Request-URI 参数 user=phone

SIP 代理分析 Request-URI，如果存在参数 user=phone，服务将处理请求 URI 作为电话号码，将号码与用户匹配。 如果参数不存在，SIP 代理将应用启发法来确定请求 URI 用户类型 (电话号码或 SIP 地址) 。

Microsoft 建议始终应用 user=phone 参数以简化呼叫设置过程。

## <a name="history-info-header"></a>History-Info 标头

History-Info 标头用于重新定位 SIP 请求，"提供 (s) 用于捕获请求历史记录信息的标准机制，为网络和最终用户启用各种服务。" 有关详细信息，请参阅 [RFC 4244 – 第 1.1 部分](http://www.ietf.org/rfc/rfc4244.txt)。 对于Microsoft 电话系统，此标头用于 Simulring 和呼叫转发方案。  

如果发送，History-Info如下所示：

- SIP 代理将在组成发送到 PSTN 控制器的 History-Info 标头的单个 History-Info 中插入包含关联电话号码的参数。  仅使用具有电话号码参数的条目，PSTN 控制器将重新生成新的 History-Info 标头，并通过 SIP 代理将标头传递给 SIP 中继提供程序。

- History-Info同时拨打和呼叫转发案例添加标头。

- History-Info转接案例不会添加呼叫标头。

- 重新构造的 History-Info 标头中的单个历史记录条目将具有提供的电话号码参数与直接路由 FQDN (sip.pstnhub.microsoft.com) 设置为 URI 的主机部分;"user=phone"的参数将添加为 SIP URI 的一部分。  与原始 History-Info 标头关联的任何其他参数（手机上下文参数除外）将在重新构造的 History-Info 标头中传递。  

  > [!NOTE]
  > RFC 4244) 第 3.3 节中定义的机制确定为专用端口的条目将按如下方式转发，因为 SIP 中继提供程序是受信任的对等方。 (

- 将History-Info入站流量。

下面是 SIP 代理发送的 History-info 标头的格式：

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

如果多次重定向调用，则每个重定向的信息将按时间顺序包含相应原因。


标头示例：

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

该History-Info受强制 TLS 机制的保护。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>与直接路由和故障转移机制的 SBC 连接

请参阅直接路由计划中的 SIP 信号 [故障转移机制部分](direct-routing-plan.md#failover-mechanism-for-sip-signaling)。

## <a name="retry-after"></a>Retry-After

如果直接路由数据中心正忙，服务可以将一Retry-After一秒时间间隔的消息发送到 SBC。 当 SBC 收到包含 Retry-After 标头的 503 消息以响应 INVITE 时，SBC 必须终止该连接并尝试下一个可用的 Microsoft 数据中心。

## <a name="handling-retries-603-response"></a>处理重试 (603 响应) 
如果最终用户在拒绝传入呼叫后发现一次呼叫多次未接来电，这意味着 SBC 或 PSTN 中继提供商的重试机制配置不正确。 必须重新配置 SBC，以停止针对 603 响应的重试工作。

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 重启：转移到不支持媒体旁路的终结点的媒体旁路呼叫

SBC 必须支持 [RFC 5245 第 9.1.1.1 部分](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)中所述的 ICE 重启。

直接路由中的重启根据 RFC 的以下段落实现：

*若要重启 ICE，代理必须更改产品/服务中媒体流的 ice-pwd 和 ice-ufrag。 请注意，允许在一个产品/服务中使用会话级别属性，但提供与后续产品/服务中的媒体级别属性相同的 ice-pwd 或 ice-ufrag。 这不是密码更改，只是更改其表示形式，不会导致 ICE 重启。*

*代理为此媒体流设置 SDP 中的其余字段，就像在此媒体流的初始产品/服务中一样 (请参阅第 4.3 部分) 。 因此，候选项集"可以"包括该流的部分、无或所有以前的候选项，而"可以"包含一组完全新的候选项，如第 4.1.1 节中所述。*

如果呼叫最初是使用媒体旁路建立的，并且呼叫转移到 Skype for Business 客户端，则直接路由需要插入媒体处理器 -这是因为直接路由不能与具有媒体旁路的 Skype for Business 客户端一同使用。 直接路由通过更改 ice-pwd 和 ice-ufrag，在重新邀请中提供新的媒体候选项来启动 ICE 重启过程。
