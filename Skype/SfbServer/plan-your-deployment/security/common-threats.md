---
title: 现代日常计算中的常见安全威胁
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/22/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
description: 由于Skype for Business Server是企业级通信系统，因此应注意可能会影响其基础结构和通信的常见安全攻击。
ms.openlocfilehash: 8f546ff95bec714f9ddd922b4b786d4a6bd5549c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851806"
---
# <a name="common-security-threats-in-modern-day-computing"></a>现代日常计算中的常见安全威胁
 
由于Skype for Business Server是企业级通信系统，因此应注意可能会影响其基础结构和通信的常见安全攻击。
  
## <a name="compromised-key-attack"></a>破解密钥攻击

密钥是用于加密、解密或验证机密信息的机密代码或数字。 在公钥基础结构和 PKI (有两个) ，必须考虑： 
  
- 每个证书持有者具有的私钥
    
- 通信合作伙伴成功标识和会话密钥交换后使用的会话密钥
    
破解密钥攻击是指攻击者破解私钥或会话密钥的行为。 攻击者在成功破解密钥之后，可以使用此密钥对已加密的数据进行解密，而数据的发送者对此毫不知情。
  
Skype for Business Server使用 Windows Server 操作系统中的 PKI 功能来保护用于加密传输层安全性的密钥数据 (TLS) 连接。 用于媒体加密的密钥通过 TLS 连接进行交换。
  
## <a name="network-denial-of-service-attack"></a>网络拒绝服务攻击

当攻击者阻止有效用户正常使用和运行网络时，将发生拒绝服务攻击。 这是在攻击者通过合法请求破坏服务，使合法用户使用服务不知所措时完成。 通过使用拒绝服务攻击，攻击者可以执行以下操作：
  
- 向受到攻击的网络中正在运行的应用程序和服务发送无效数据，干扰它们的正常工作。
    
- 发送大量流量以造成系统过载，直到系统停止对合理请求做出响应或对合理请求做出响应的速度变得很慢。
    
- 隐藏攻击证据。
    
- 阻止用户访问网络资源。
    
## <a name="eavesdropping-sniffing-snooping"></a>窃听 (监听、窥探) 

在攻击者获取对网络中数据路径的访问权并能够监控和读取流量内容时，会发生窃听。窃听也称为监听或窥探。如果流量内容采用纯文本形式，则攻击者在获取路径的访问权之后即可读取流量内容。例如，通过控制数据路径上的路由器进行攻击。 
  
对于内部流量的默认建议和Skype for Business Server是在受信任服务器之间 (TLS) TLS 与从客户端到服务器的 TLS 之间使用相互 TLS 协议。 这种保护措施会使在给定对话发生期间很难或不可能实现攻击。 TLS 可对各方执行身份验证，并对所有流量内容进行加密。 这样不能阻止窃听，但攻击者不能读取流量内容，除非破坏加密。
  
遍历使用中继 NAT (TURN) 协议不要求加密通信，并且它发送的信息受消息完整性保护。 尽管它会窃听，但它正在发送的信息 (即 IP 地址和端口) 只需查看数据包的源地址和目标地址，就可以直接提取。 A/V 边缘服务通过使用从几个项目（包括从不以纯文本发送的 TURN 密码）派生的密钥检查消息的消息完整性，以确保数据有效。 如果使用安全实时协议 (SRTP) ，则还会加密媒体流量。
  
## <a name="identity-spoofing-ip-address-and-caller-id-spoofing"></a>标识欺骗 (IP 地址和来电显示欺骗) 

当攻击者在未获得授权的情况下确定并使用有效用户的电话号码 (呼叫者 ID) 或网络、计算机或网络组件的 IP 地址时，会发生身份欺骗。 成功的攻击使攻击者可以像通常由电话号码（呼叫者 ID 或 IP 地址 (标识) 一样操作。

在安全Skype for Business Server，只有当管理员执行以下两项操作时，IP 地址欺骗才生效：
  
- 已配置仅支持传输控制协议 (TCP) 的连接（建议不要这样做，因为 TCP 通信未经过加密）。
    
- 将这些连接的 IP 地址标记为受信任的主机。
    
此操作对于传输层安全性 (TLS) 连接而言不成问题，因为 TLS 对所有方进行验证并加密所有通信。 使用 TLS 可防止攻击者对特定连接（例如，相互 TLS 连接）执行 IP 地址欺骗攻击。 但攻击者仍然可能会欺骗其使用的 DNS Skype for Business Server地址。 但是，由于Skype for Business身份验证是使用证书执行的，因此攻击者将没有欺骗通信中的一方所需的有效证书。

另一方面，当在提供商、PSTN 网关或其他 PBX 系统与交换机之间建立 SIP 中继时，呼叫者 ID 欺骗Skype for Business Server。 在这些情况下，Skype for Business Server不会提供任何保护来防止呼叫者 ID 欺骗。 这意味着，Skype for Business用户可以通过显示电话号码或 显示名称 (的欺骗呼叫者 ID 接收来自 SIP 中继的呼叫（如果反向号码查找适用于另一) 用户Skype for Business号码）。 应在提供程序端、PSTN 或 PBX 网关上应用对此的保护。
  
## <a name="man-in-the-middle-attack"></a>中间人攻击

当攻击者在两个通信用户不知情的情况下通过其计算机重新路由两个用户之间的通信时，会发生中间人攻击。 攻击者可以在将通信内容发送到预期接收人之前监控和读取通信内容。 通信中的每个用户在不知情的情况下向攻击者发送通信和从攻击者接收通信，还以为自己只是在与预期用户进行通信。 如果攻击者可修改 Active Directory 域服务以将他（她）的服务器添加为受信任服务器或修改域名系统 (DNS) 以让客户端在与服务器通信时通过攻击者，则会发生这种情况。 中间人攻击还可能发生在两个客户端之间的媒体流量中。 但是，在Skype for Business Server点音频、视频和应用程序共享中，流使用 SRTP 进行加密，使用在通过 TLS 的会话初始协议 (SIP) 的对等方之间协商的加密密钥。 诸如 Group Chat 的服务器使用 HTTPS 来增强 Web 通信的安全性。
  
## <a name="rtp-replay-attack"></a>RTP 重播攻击

重播攻击是指出于恶意目的截获并重新传输双方之间的有效媒体传输。通过允许接收人维护已收到的 RTP 数据包的索引并将每个新数据包与索引中已列出的数据包加以比较，安全信号协议连接中使用的 SRTP 可保护传输免受重播攻击。
  
## <a name="spim"></a>Spim

Spim 是主动提供的商业即时消息或状态订阅请求。虽然 Spim 本身并不会导致网络问题，但至少会有些烦人，占用资源和生产时间，而且可能会导致网络问题。例如，用户通过发送请求相互发送垃圾消息。用户可以相互阻止对方来防止出现这种情况，但对于联盟，如果建立了协作的 Spim 攻击，则很难防止出现这种情况，除非您禁用联盟伙伴关系。
  
## <a name="viruses-and-worms"></a>病毒和蠕虫

病毒是一个代码单元，其目的是为了复制更多类似的代码单元。 病毒需要像文件、电子邮件或程序这样的宿主才能发挥作用。 Aworm 是一个代码单元，其用途是重现其他类似的代码单元，但它不需要主机。 病毒和蠕虫主要是在客户端之间传送文件期间或从其他用户发送 URL 时出现。 例如，如果您的计算机上存在某种病毒，则该病毒可使用您的身份代表您发送即时消息。
  
## <a name="personally-identifiable-information"></a>个人身份信息

Skype for Business Server可能会通过可能链接到个人的公用网络披露信息。 这些信息类型具体可分为两大类：
  
- **增强状态数据** 增强状态数据是用户可以选择通过指向联盟伙伴的链接或与组织中联系人共享或不共享的信息。 不与公用 IM 网络上的用户共享此数据。 客户端策略和其他客户端配置可能会为系统管理员提供一些控制能力。 在 Skype for Business Server 中，可以针对单个用户配置增强状态隐私模式Skype for Business以防止不在用户的联系人列表中的 Skype for Business 用户看到该用户状态信息。 增强状态隐私模式不会阻止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的用户看到用户状态信息。 有关部署客户端和状态的详细信息，[请参阅为客户端](../../deploy/deploy-clients/deploy-clients.md)部署Skype for Business Server和在客户端部署中规划即时消息[Skype for Business Server。](../../plan-your-deployment/instant-messaging-and-presence.md)
    
- **必需数据** 服务器或客户端的正确操作需要必需数据，并且这些数据不在客户端或系统管理的控制之下。 对于路由、状态维护和信号传输而言，此信息是必需的服务器或网络级别信息。
    
下表列出了通过公共网络公开的数据。
  
**增强状态数据**

|**披露的数据**|**可能设置**|
|:-----|:-----|
|个人数据  <br/> |姓名、职务、公司、电子邮件地址、时区  <br/> |
|电话号码  <br/> |工作电话号码、手机号码、住宅电话号码  <br/> |
|日历信息  <br/> |闲/忙、外出通知、会议详细信息 (日历会议通知的联系人)   <br/> |
|状态  <br/> |离开、空闲、忙碌、请勿打扰、脱机  <br/> |
   
**必需数据**


| **披露的数据** | **示例信息**                            |
|:-------------------|:---------------------------------------------------|
| IP 地址  <br/>  | 计算机的实际地址或经过 NAT 转换的地址  <br/> |
| SIP URI  <br/>     | jeremylos@litwareinc.com  <br/>                    |

