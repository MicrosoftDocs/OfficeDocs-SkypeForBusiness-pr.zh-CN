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
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由协议
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5a05dbc6519c4f90cf0cc0d49e996467bf10230
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414720"
---
# <a name="direct-routing---sip-protocol"></a>直接路由 - SIP 协议

本文介绍直接路由如何实现会话初始协议 (SIP) 。 若要在会话边界控制器 (SBC) 和 SIP 代理之间正确路由流量，某些 SIP 参数必须具有特定值。 本文适用于负责配置本地 SBC 与 SIP 代理服务之间的连接的语音管理员。

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>处理传入请求：查找租户和用户

在处理传入或出站呼叫之前，SIP 代理和 SBC 之间交换 OPTIONS 消息。 这些 OPTIONS 消息允许 SIP 代理向 SBC 提供允许的功能。 OPTIONS 协商必须成功 (200OK 响应) ，从而允许 SBC 和 SIP 代理之间进一步通信以建立呼叫。 向 SIP 代理发送 OPTIONS 消息中的 SIP 标头作为示例提供：

| 参数名称 | 值示例 | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip：sip.pstnhub.microsoft.com：5061 SIP /2.0 |
| 通过标头 | 通过：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards标头 | Max-Forwards：68 |
| From Header | 发件人标头： <sip:sbc1.adatum.biz:5058> |
| To Header | 自： <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq 标头 | CSeq：1 个邀请 | 
| 联系人标头 | 联系： <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> SIP 标头不包含正在使用的 SIP URI 中的 userinfo。 根据 [RFC 3261 第 19.1.1 节](https://tools.ietf.org/html/rfc3261#section-19.1.1)，URI 的 userinfo 部分是可选的，当目标主机没有用户概念或主机本身是被标识的资源时，可能不存在。 如果 SIP URI 中存在 @ 符号，则用户字段不得为空。
> 请注意，SIPS URI 不应与直接路由一起使用，因为它不受支持。
> 检查会话边界控制器配置，并确保未在 SIP 请求中使用“替换”标头。 直接路由将拒绝定义了替换标头的 SIP 请求。

在传入呼叫上，SIP 代理需要查找呼叫目标租户，并查找此租户中的特定用户。 租户管理员可以在多个租户中配置非 DID 号码，例如 +1001。 因此，必须查找要对其执行数字查找的特定租户，因为非 DID 号码在多个Microsoft 365 或Office 365组织中可能相同。  

本部分介绍 SIP 代理如何查找租户和用户，以及如何对传入连接执行 SBC 身份验证。

下面是传入呼叫上的 SIP 邀请消息示例：

| 参数名称 | 值示例 | 
| :---------------------  |:---------------------- |
| Request-URI | 邀请 sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| 通过标头 | 通过：SIP/2.0/TLS sbc1.adatum.biz：5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards标头 | Max-Forwards：68 |
| From Header | From Header From： <sip：+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| To Header | 目标：sip:+183338006777@sbc1.adatum.biz | 
| CSeq 标头 | CSeq：1 个邀请 | 
| 联系人标头 | 联系： <sip:+17168712781@sbc1.adatum.biz:5058;transport=tls> | 

收到邀请后，SIP 代理将执行以下步骤：

1. 检查证书。 在初始连接上，直接路由服务采用“联系人”标头中显示的 FQDN 名称，并将其与所提供证书的“公用名”或“使用者备用名称”相匹配。 SBC 名称必须与以下选项之一匹配：

   - 选项 1. 联系人标头中显示的完整 FQDN 名称必须与所提供证书的公用名/使用者可选名称匹配。  

   - 选项 2. 例如，在联系人标头 (显示的 FQDN 名称的域部分 sbc1.adatum.biz) FQDN 名称 adatum.biz 必须与公用名/使用者可选名称中的通配符值匹配， (例如 *.adatum.biz) 。

2. 尝试使用联系人标头中显示的完整 FQDN 名称查找租户。  

   检查联系人标头 (sbc1.adatum.biz) 中的 FQDN 名称是否在任何Microsoft 365 或Office 365组织中注册为 DNS 名称。 如果找到，则会在 SBC FQDN 注册为域名的租户中查找用户。 如果未找到，则应用步骤 3。   

3. 仅当步骤 2 失败时，步骤 3 才适用。 

   删除主机部分 adatum.biz) 后，从 FQDN（联系人标头 (FQDN： sbc12.adatum.biz）中删除主机部分，并检查此名称是否在任何Microsoft 365 或Office 365组织中注册为 DNS 名称。 如果找到，则在此租户中执行用户查找。 如果未找到，则调用失败。

4. 使用请求 URI 中显示的电话号码，在步骤 2 或步骤 3 中找到的租户中执行反向号码查找。 将提供的电话号码与在上一步骤中找到的租户中的用户 SIP URI 匹配。

5. 应用中继设置。 查找租户管理员为此 SBC 设置的参数。

   Microsoft不支持在Microsoft SIP 代理和配对的 SBC 之间拥有第三方 SIP 代理或用户代理服务器，这可能会修改配对 SBC 创建的请求 URI。

   本文稍后将介绍两个查找 (步骤 2 和 3) ，其中一个 SBC 与多个租户互连， (运营商方案) 。

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>联系人标头和请求 URI 的详细要求

#### <a name="contact-header"></a>联系人标头

对于 (选项、INVITE) 到Microsoft SIP 代理的所有传入 SIP 消息，联系人标头必须在 URI 主机名中具有配对的 SBC FQDN，如下所示：

语法：联系人：<sBC 的 sip：phone 或 sip address@FQDN;transport=tls> 

根据 [RFC 3261 第 11.1 节](https://tools.ietf.org/html/rfc3261#section-11.1)，OPTIONS 消息中可能存在联系人标头字段。 在“直接路由”中，需要联系人标头。 对于上述格式的 INVITE 消息，对于 OPTIONS 消息，可以从 SIP URI 中删除 userinfo，并且只能按如下所示的格式发送 FQDN：

语法：Contact： <sip：FQDN of the SBC;transport=tls>

此名称 (FQDN) 也必须位于“公用名”或“使用者可选名称”字段中， () 提供的证书。 Microsoft支持在证书的“公用名”或“使用者可选名称”字段中使用名称 () 的通配符值。   

[RFC 2818 第 3.1 节](https://tools.ietf.org/html/rfc2818#section-3.1)介绍了对通配符的支持。 特别：

*“名称可能包含通配符，该通配符 \* 被视为与任何单个域名组件或组件片段匹配。例如， \*.a.com 匹配 foo.a.com 但不 bar.foo.a.com。f.com\* 匹配 foo.com 但不 bar.com。*

如果 SIP 消息中显示的联系人标头中的多个值由 SBC 发送，则仅使用联系人标头的第一个值的 FQDN 部分。

作为直接路由的经验法则，使用 FQDN 来填充 SIP URI 而不是 IP 非常重要。 一条传入的 INVITE 或 OPTIONS 消息发到带有联系人标头的 SIP 代理，其中主机名由 IP 表示，而不是 FQDN，连接将被拒绝并显示 403 禁止访问。

#### <a name="request-uri"></a>Request-URI 

对于所有传入呼叫，请求 URI 用于将电话号码与用户匹配。   

目前，电话号码必须包含加号 (+) ，如以下示例所示。 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>From Header

对于所有传入呼叫，“发件人标头”用于将呼叫者的电话号码与被呼叫者的阻止电话号码列表进行匹配。

电话号码必须包含 +，如以下示例所示。

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>联系人和Record-Route标头注意事项

SIP 代理需要计算新的对话内客户端事务的下一跃点 FQDN， (例如 Bye 或 Re-Invite) ，以及回复 SIP 选项时。 使用联系人或Record-Route。 

根据 [RFC 3261 第 8.1.1.8 节](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)，任何可能导致新对话框的请求都需要联系人标头。 仅当代理希望在对话中保持未来请求的路径时，才需要Record-Route。 如果代理 SBC 与 [用于直接路由的本地媒体优化](./direct-routing-media-optimization.md)一起使用，则需要配置记录路由，因为代理 SBC 需要保留在路由中。 

如果未使用代理 SBC，Microsoft建议仅使用联系人标头：

- 根据 [RFC 3261 第 20.30 节](https://tools.ietf.org/html/rfc3261#section-20.30)Record-Route，如果代理希望在对话中保持未来请求的路径，则这一点并不重要，如果没有配置代理 SBC，因为所有流量都在Microsoft SIP 代理和配对 SBC 之间传输。 

- Microsoft SIP 代理仅使用联系人标头 (不使用记录路由) 来确定发送出站 ping 选项时的下一跃点。 如果未使用代理 SBC，则仅配置一个参数 (Contact) 而不是两个 (Contact 和 Record-Route) 可以简化管理。 

若要计算下一跃点，SIP 代理使用：

- 优先级 1。 顶级记录路由。 如果顶级Record-Route包含 FQDN 名称，则 FQDN 名称用于建立出站对话内连接。

- 优先级 2。 联系人标头。 如果不存在Record-Route，SIP 代理将查找 Contact 标头的值以建立出站连接。  (这是建议的配置。) 

如果使用 Contact 和 Record-Route，SBC 管理员必须保持其值相同，这会导致管理开销。 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>在联系人或Record-Route中使用 FQDN 名称

Record-Route 或 Contact 不支持使用 IP 地址。 唯一受支持的选项是 FQDN，它必须与 SBC 证书的公用名或使用者可选名称匹配， () 支持证书中的通配符值。

- 如果在“记录路由”或“联系人”中显示 IP 地址，则证书检查失败，并且调用失败。

- 如果 FQDN 与提供的证书中“公用名称”或“使用者可选名称”的值不匹配，则调用失败。 

## <a name="inbound-call-sip-dialog-description"></a>入站呼叫：SIP 对话框说明

下表总结了非旁路模式和旁路模式之间的调用流差异和相似之处：

| 参数名称 | 非旁路模式 | 绕过模式
| :---------------------  |:---------------------- |:----------------|
| 来自 183 和 200 条消息的媒体候选人 | 媒体处理器 | 客户端 | 
| SBC 可以接收的 183 条消息数 | 每个会话一个 | 多个 | 
| 呼叫可以是临时应答 (183)  | 是 | 是 |
| 呼叫可能没有临时应答 (183)  | 是 | 是 |

###  <a name="non-media-bypass-flow"></a>非媒体旁路流

Teams 用户可能同时具有多个终结点。 例如，Teams for Windows 客户端、Teams for iPhone 客户端和 Teams Phone (Teams Android 客户端) 。 每个终结点可能会发出 HTTP rest 信号，如下所示：

-   呼叫进度 - 由 SIP 代理转换为 SIP 消息 180。 在接收消息 180 时，SBC 必须生成本地响铃。

-   媒体应答 - 由 SIP 代理转换为消息 183，其中包含会话描述协议 (SDP) 中的媒体候选项。 在接收消息 183 时，SBC 应连接到在 SDP 消息中收到的媒体候选项。 

    > [!NOTE]
    > 在某些情况下，可能不会生成媒体应答，并且终结点可能会应答“已接受呼叫”消息。

-   已接受呼叫 - SIP 代理使用 SDP 转换为 SIP 消息 200。 在接收消息 200 时，SBC 应向提供的 SDP 候选人发送和接收媒体。

    > [!NOTE]
    > 直接路由不支持无 SDP) 的延迟产品/服务邀请 (邀请。

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>具有临时答案的多个终结点响铃

1.  收到来自 SBC 的第一个邀请后，SIP 代理发送消息“SIP SIP/2.0 100 正在尝试”，并通知所有最终用户终结点有关传入呼叫的信息。 

2.  收到通知后，每个终结点将开始响铃并向 SIP 代理发送“呼叫进度”消息。 由于 Teams 用户可以有多个终结点，因此 SIP 代理可能会收到多个呼叫进度消息。

3.  对于从客户端接收的每个呼叫进度消息，SIP 代理会将呼叫进度消息转换为 SIP 消息“SIP SIP/2.0 180 响铃”。 发送此类消息的间隔由从调用控制器接收消息的间隔定义。 在下图中，SIP 代理生成了两个 180 条消息。 这些消息来自用户的两个 Teams 终结点。 每个客户端都有唯一的标记 ID。  来自不同终结点的每条消息都是一个单独的会话， (“To”字段中的参数“标记”将是不同的) 。 但终结点可能不会生成消息 180 并立即发送消息 183，如下图所示。

4.  终结点生成具有终结点候选媒体的 IP 地址的媒体应答消息后，SIP 代理会将收到的消息转换为“SIP 183 会话进度”消息，客户端的 SDP 替换为来自媒体处理器的 SDP。 在下图中，分叉 2 的终结点接听了呼叫。 如果未绕过中继，则仅 (环形机器人或客户端终结点) 生成一次 183 SIP 消息。 183 可能位于现有分支上或启动新分支。

5.  呼叫接受消息与接受呼叫的终结点的最终候选项一起发送。 呼叫接受消息转换为 SIP 消息 200。 

> [!div class="mx-imgBorder"]
> ![显示具有临时答案的多个终结点响铃的关系图。](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>没有临时答案的多个终结点响铃

1.  收到来自 SBC 的第一个邀请后，SIP 代理发送消息“SIP SIP/2.0 100 正在尝试”，并通知所有最终用户终结点有关传入呼叫的信息。 

2.  收到通知后，每个终结点将开始响铃并将消息“呼叫进度”发送到 SIP 代理。 由于 Teams 用户可以有多个终结点，因此 SIP 代理可能会收到多个呼叫进度消息。

3.  对于从客户端接收的每个呼叫进度消息，SIP 代理会将呼叫进度消息转换为 SIP 消息“SIP SIP/2.0 180 正在尝试”。  发送消息的间隔由从呼叫控制器接收消息的间隔定义。 下图中显示了 SIP 代理生成的两条 180 条消息，这意味着用户已登录到三个 Teams 客户端，每个客户端发送呼叫进度。 每条消息都是单独的会话， (“To”字段中的参数“tag”是不同的) 

4.  呼叫接受消息与接受呼叫的终结点的最终候选项一起发送。 呼叫接受消息转换为 SIP 消息 200。 

> [!div class="mx-imgBorder"]
> ![显示没有临时答案的多个终结点响铃的关系图。](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>媒体旁路流

媒体旁路方案中使用相同的消息 (100 尝试、180、183) 。 

下面的架构显示了绕过调用流的示例。 

> [!NOTE]
> 媒体候选项可以来自不同的终结点。 

> [!div class="mx-imgBorder"]
> ![显示具有临时答案的多个终结点响铃的关系图。](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>替换选项

SBC 必须支持带替换的邀请。

## <a name="size-of-sdp-considerations"></a>SDP 的大小注意事项

直接路由接口可能会发送超过 1，500 字节的 SIP 消息。  SDP 的大小主要导致此问题。 但是，如果 SBC 后面有 UDP 中继，如果消息从 Microsoft SIP 代理转发到未修改的中继，则可能会拒绝该消息。 Microsoft建议在将消息发送到 UDP 中继时，在 SBC 上剥离 SDP 中的一些值。 例如，可以删除 ICE 候选项或未使用的编解码器。

## <a name="call-transfer"></a>呼叫转移

直接路由支持两种呼叫转移方法：

- 选项 1. SIP 代理进程 从客户端本地引用，并充当 RFC 3892 第 7.1 节中所述的裁判。

  使用此选项，SIP 代理将终止传输并添加新的邀请。 


- 选项 2. SIP 代理发送引用 SBC，并充当 RFC 5589 第 6 节中所述的转让方。

  使用此选项，SIP 代理发送引用 SBC，并期望 SBC 完全处理传输。

SIP 代理根据 SBC 报告的功能选择方法。 如果 SBC 指示它支持方法“Refer”，则 SIP 代理将使用选项 2 进行呼叫转移。

下面是发送支持 Refer 方法的消息的 SBC 示例：

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

如果 SBC 未指示 Refer 作为受支持的方法，则直接路由将使用选项 1 (SIP 代理充当引用) 。 SBC 还必须发出信号，表示它支持 Notify 方法：

指示不支持 Refer 方法的 SBC 示例：

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP 代理进程 从客户端本地引用并充当裁判

如果 SBC 指示不支持 Refer 方法，则 SIP 代理将充当“引用者”。 

来自客户端的引用请求将在 SIP 代理上终止。  (下图中，来自客户端的“引用”请求显示为“呼叫转接到 Dave”。  有关详细信息，请参阅 [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 第 7.1 节。 

> [!div class="mx-imgBorder"]
> ![显示具有临时答案的多个终结点响铃的关系图。](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP 代理发送引用 SBC 并充当传输方

这是呼叫转接的首选方法，对于寻求媒体旁路认证的设备，此方法是必需的。 在媒体旁路模式下，不支持在没有 SBC 能够处理 Refer 的情况下进行呼叫转移。 

RFC 5589 的第 6 节介绍了该标准。 相关的 RFC 包括：

- [会话初始协议 (SIP) 呼叫控制 - 转移](https://tools.ietf.org/html/rfc5589)

- [会话初始协议 (SIP) “替换”标头](https://tools.ietf.org/html/rfc3891)

- [会话启动协议 (SIP) “引用依据”机制](https://tools.ietf.org/html/rfc3892)

此选项假定 SIP 代理充当传输方，并向 SBC 发送“引用”消息。 SBC 充当受让人并处理引用以生成新的转让产品/服务。 有两种可能的情况：

- 呼叫将转接到外部 PSTN 参与者。 
- 呼叫通过 SBC 从一个 Teams 用户转移到同一租户中的另一个 Teams 用户。 

如果呼叫通过 SBC 从一个 Teams 用户转移到另一个，则 SBC 应发出新的邀请， (使用“引用”消息中收到的信息为转移目标 (Teams 用户) 启动新的对话) 。 

若要在内部填充请求事务的“To/Transferor”字段，SIP 代理需要在 REFER-TO/REFERRED-BY 标头中传达此信息。 

SIP 代理将构成 SIP URI，该 URI 由主机名中的 SIP 代理 FQDN 和以下任一项组成：

- 如果传输目标为电话号码，则 URI 用户名部分的 E.164 电话号码，或

- x-m 和 x-t 参数分别编码完整传输目标 MRI 和租户 ID 

REFERRED-BY 标头是一个 SIP URI，其中包含编码的传输程序 MRI，以及传输方租户 ID 和其他传输上下文参数，如下表所示：

| 参数 | 值 | 说明 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | Mri | 由 CC 填充的传输方/传输目标的完整 MRI |
| x-t | 租户 ID | x-t 租户 ID 可选租户 ID（由 CC 填充） |
| x-ti | 传输方关联 ID | 对传输方调用的相关 ID |
| x-tt | 转移目标呼叫 URI | 编码的呼叫替换 URI |

在这种情况下，引用标头的大小最多可为 400 个符号。 SBC 必须支持处理最大为 400 个符号的引用消息。

> [!div class="mx-imgBorder"]
> ![显示具有临时答案的多个终结点响铃的关系图。](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>会话计时器

SIP 代理支持 (始终在非旁路呼叫上提供) 会话计时器，但不在旁路呼叫上提供它。 SBC 不强制使用会话计时器。

##  <a name="use-of-request-uri-parameter-userphone"></a>Request-URI 参数 user=phone 的使用

SIP 代理分析 Request-URI，如果存在参数 user=phone，则服务会将 Request-URI 作为电话号码进行处理，并将该号码与用户匹配。 如果没有参数，SIP 代理将应用启发法来确定请求 URI 用户类型 (电话号码或 SIP 地址) 。

Microsoft建议始终应用 user=phone 参数来简化呼叫设置过程。

## <a name="history-info-header"></a>History-Info标头

History-Info标头用于重新定位 SIP 请求，并“提供 () 用于捕获请求历史记录信息的标准机制，以便为网络和最终用户启用各种服务”。 有关详细信息，请参阅 [RFC 4244 - 第 1.1 节](http://www.ietf.org/rfc/rfc4244.txt)。 对于Microsoft电话系统，此标头用于模拟和呼叫转接方案。  

如果发送，则启用History-Info，如下所示：

- SIP 代理将在单个History-Info条目中插入一个参数，其中包含发送到 PSTN 控制器的History-Info标头。  仅使用具有电话号码参数的条目，PSTN 控制器将重新生成新的History-Info标头，并通过 SIP 代理将其传递给 SIP 中继提供商。

- 将为同时响铃和呼叫转接情况添加History-Info标头。

- 不会为呼叫转移案例添加History-Info标头。

- 重新构造的 History-Info 标头中的单个历史记录条目会将提供的电话号码参数与直接路由 FQDN (sip.pstnhub.microsoft.com) 设置为 URI 的主机部分;“user=phone”参数将添加为 SIP URI 的一部分。  与原始History-Info标头关联的任何其他参数（电话上下文参数除外）将在重新构造的History-Info标头中传递。  

  > [!NOTE]
  > 由 RFC 4244) 第 3.3 节中定义的机制确定的专用 (条目将按原样转发，因为 SIP 中继提供程序是受信任的对等方。

- 忽略入站History-Info。

以下是 SIP 代理发送的 History-info 标头的格式：

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

如果多次重定向调用，则每个重定向的相关信息将按时间顺序包含相应的原因。


标头示例：

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

History-Info受强制 TLS 机制的保护。 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>SBC 连接到直接路由和故障转移机制

请参阅 [规划直接路由](direct-routing-plan.md#failover-mechanism-for-sip-signaling)中的 SIP 信号故障转移机制部分。

## <a name="retry-after"></a>Retry-After

如果直接路由数据中心繁忙，该服务可以每隔一秒向 SBC 发送Retry-After消息。 当 SBC 收到包含Retry-After标头以响应 INVITE 的 503 消息时，SBC 必须终止该连接，并尝试下一个可用的数据中心Microsoft。

## <a name="handling-retries-603-response"></a>处理 603 响应)  (重试
如果最终用户在拒绝传入呼叫后观察到一个呼叫的多个未接来电，则意味着 SBC 或 PSTN 中继提供商的重试机制配置错误。 必须重新配置 SBC 以停止针对 603 响应的重试工作。

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 重启：将媒体旁路调用转移到不支持媒体旁路的终结点

SBC 必须支持 [RFC 5245 第 9.1.1.1 节](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)中所述的 ICE 重启。

直接路由中的重启根据 RFC 的以下段落实现：

*若要重启 ICE，代理必须更改产品/服务中媒体流的 ice-pwd 和 ice-ufrag。 请注意，允许在一个产品/服务中使用会话级别属性，但在后续产品/服务中提供与媒体级别属性相同的 ice-pwd 或 ice-ufrag。 这不是密码的更改，只是其表示形式的更改，不会导致 ICE 重启。*

*代理为此媒体流设置 SDP 中的其余字段，就像在此媒体流的初始产品/服务中一样 (请参阅第 4.3 节) 。 因此，候选人集可能包括该流的一些、没有或所有以前的候选人，并且可能包括一组全新的候选人，如第 4.1.1 节所述。*

如果最初使用媒体旁路建立呼叫，并且呼叫被转移到Skype for Business客户端，则直接路由需要插入媒体处理器 -- 这是因为直接路由不能与具有媒体旁路的Skype for Business客户端一起使用。 直接路由通过更改 ice-pwd 和 ice-ufrag 并在重新邀请中提供新的媒体候选项来启动 ICE 重启过程。
