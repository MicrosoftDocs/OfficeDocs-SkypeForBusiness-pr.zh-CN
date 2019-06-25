---
title: 'Lync Server 2013: 现代日期计算中的常见安全威胁'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2446ee0755f4544f17f6c04c6059d70576a466f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>现代日常计算中的常见安全威胁

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-09-10_

由于 Lync Server 2013 是企业级通信系统, 因此你应该知道可能会影响其基础结构和通信的常见安全攻击。

<div>

## <a name="compromised-key-attack"></a>破解密钥攻击

密钥是用于加密、解密或验证机密信息的机密代码或数字。必须考虑以下两种在公钥基础结构 (PKI) 中使用的机密密钥：

  - 每个证书持有者都拥有的私钥

  - 在成功识别身份后使用的会话密钥和通信双方交换的会话密钥

破解密钥攻击是指攻击者破解私钥或会话密钥的行为。攻击者在成功破解密钥之后，可以使用此密钥对已加密的数据进行解密，而数据的发送者对此毫不知情。

Lync Server 2013 使用 Windows Server 操作系统中的 PKI 功能保护用于加密传输层安全 (TLS) 连接的密钥数据。 用于媒体加密的密钥通过 TLS 连接进行交换。

</div>

<div>

## <a name="network-denial-of-service-attack"></a>网络拒绝服务攻击

当攻击者阻止有效用户正常使用和运行网络时，将发生*拒绝服务攻击*。这是攻击者通过合法请求淹没服务并且让合法用户无法使用服务来完成的。使用拒绝服务攻击，攻击者可以执行以下操作：

  - 向受到攻击的网络中正在运行的应用程序和服务发送无效数据，干扰它们的正常工作。

  - 发送大量流量以造成系统过载，直到系统停止对合理请求做出响应或对合理请求做出响应的速度变得很慢。

  - 隐藏攻击证据。

  - 阻止用户访问网络资源。

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>窃听（监听、窥探）

在攻击者获取对网络中数据路径的访问权并能够监控和读取流量内容时，会发生*窃听*。窃听也称为*监听*或*窥探*。如果流量内容采用纯文本形式，则攻击者在获取路径的访问权之后即可读取流量内容。例如，通过控制数据路径上的路由器进行攻击。

Microsoft Lync Server 2013 中的流量的默认建议和设置是在受信任的服务器之间使用相互 TLS (MTLS), 从客户端到服务器使用 TLS。 这种保护措施使得在发生给定对话的时间段内很难实现或不可能实现攻击。 TLS 可对各方执行身份验证，并对所有流量内容进行加密。 这样不能阻止窃听，但攻击者不能读取流量内容，除非破坏加密。

使用中继 NAT (TURN) 协议不要求对流量内容进行加密，其发送的信息受消息完整性保护。尽管其发送的信息易受到窃听攻击，但只需通过查看数据包的源地址和目标地址即可直接提取该信息（即 IP 地址和端口）。A/V 边缘服务可通过检查消息的消息完整性来确保数据有效，方法是使用从少数几项（包括从不以明文格式发送的 TURN 密码）派生的密钥。如果使用安全实时协议 (SRTP)，则还要对媒体流量内容进行加密。

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>身份欺骗（IP 地址欺骗）

当攻击者在未经授权的情况下确定和使用网络、计算机或网络组件的 IP 地址时，会发生*欺骗*。 一旦攻击成功，攻击者便可以假借 IP 地址通常标识的实体的身份执行操作。 在 Microsoft Lync Server 2013 的上下文中, 仅当管理员已执行以下两项操作时, 才会播放此情况:

  - 已配置仅支持传输控制协议 (TCP) 的连接（建议不要这样做，因为 TCP 通信未经过加密）。

  - 将这些连接的 IP 地址标记为受信任的主机。

此操作对于传输层安全性 (TLS) 连接而言不成问题，因为 TLS 对所有方进行验证并加密所有通信。 使用 TLS 可防止攻击者对特定连接（例如，相互 TLS 连接）执行 IP 地址欺骗攻击。 但是, 攻击者仍然可以欺骗 Lync Server 2013 使用的 DNS 服务器的地址。 但是, 由于 Lync 中的身份验证是使用证书执行的, 因此攻击者没有必要的有效证书来欺骗其中的一方通信。

</div>

<div>

## <a name="man-in-the-middle-attack"></a>中间人攻击

当攻击者在发生通信的两个用户不知情的情况下，通过自己的计算机重新路由这两个用户之间的通信时，就会发生中间人攻击。 攻击者可以在将通信内容发送到预期接收人之前监控和读取通信内容。 通信中的每个用户在不知情的情况下向攻击者发送通信和从攻击者接收通信，还以为自己只是在与预期用户进行通信。 如果攻击者可修改 Active Directory 域服务以将他（她）的服务器添加为受信任服务器或修改域名系统 (DNS) 以让客户端在与服务器通信时通过攻击者，则会发生这种情况。 攻击者可以对两个客户端之间的媒体通信实施中间人攻击。 但是, 在 Microsoft Lync Server 2013 的点到点音频、视频和应用程序共享中, 流使用 SRTP 进行了加密, 这些密钥在通过 TLS 使用会话初始协议 (SIP) 的对等方之间进行协商。 诸如 Group Chat 的服务器使用 HTTPS 来增强 Web 通信的安全性。

</div>

<div>

## <a name="rtp-replay-attack"></a>RTP 重播攻击

*重播攻击*是指出于恶意目的截获并重新传输双方之间的有效媒体传输。通过允许接收人维护已收到的 RTP 数据包的索引并将每个新数据包与索引中已列出的数据包加以比较，安全信号协议连接中使用的 SRTP 可保护传输免受重播攻击。

</div>

<div>

## <a name="spim"></a>SPIM

*Spim* 是主动提供的商业即时消息或状态订阅请求。虽然 Spim 本身并不会导致网络问题，但至少会有些烦人，占用资源和生产时间，而且可能会导致网络问题。例如，用户通过发送请求相互发送垃圾消息。用户可以相互阻止对方来防止出现这种情况，但对于联盟，如果建立了协作的 Spim 攻击，则很难防止出现这种情况，除非你禁用联盟伙伴关系。

</div>

<div>

## <a name="viruses-and-worms"></a>病毒和蠕虫

*病毒*是一个代码单元，其目的是为了复制更多类似的代码单元。病毒需要像文件、电子邮件或程序这样的宿主才能发挥作用。*蠕虫*是用于复制更多类似代码单元的代码单元，但它不需要宿主。病毒和蠕虫主要是在客户端之间传送文件期间或从其他用户发送 URL 时出现。例如，如果你的计算机上存在某种病毒，则该病毒可使用你的身份代表你发送即时消息。

</div>

<div>

## <a name="personally-identifiable-information"></a>个人身份信息

Microsoft Lync Server 2013 可能会通过可能会链接到个人的公共网络泄漏信息。 这些信息类型具体可分为两大类：

  - **增强的状态数据**增强的状态数据是指用户可以选择共享或不共享到联盟伙伴或组织内联系人的链接的信息。 不与公用 IM 网络上的用户共享此数据。 客户端策略和其他客户端配置可能会为系统管理员提供一些控制能力。 在 Lync Server 2013 中, 可以为单个用户配置增强的状态隐私模式, 以防止 Lync 用户查看用户的 "联系人" 列表中的用户状态信息。 增强的状态隐私模式不会阻止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的用户看到用户的状态信息。 有关详细信息, 请参阅在 "入门" 文档中的 "入门" 文档和[配置增强状态隐私模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)(位于部署文档中的 lync server 2013) 中的[适用于 lync server 2013 中的客户端](lync-server-2013-what-s-new-for-clients.md)。

  - **必需数据**必需数据是服务器或客户端的正常操作所必需的, 不受客户端或系统管理的控制。 这是服务器或网络级别所必需的信息, 用于路由、状态维护和发送信号。

下表列出了通过对公用网络公开的数据。

### <a name="enhanced-presence-data"></a>增强状态数据

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>披露的数据</th>
<th>可能的设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>个人数据</p></td>
<td><p>姓名、职务、公司、电子邮件地址、时区</p></td>
</tr>
<tr class="even">
<td><p>电话号码</p></td>
<td><p>工作电话号码、手机号码、住宅电话号码</p></td>
</tr>
<tr class="odd">
<td><p>日历信息</p></td>
<td><p>空闲/忙碌、出城通知、会议详细信息（显示给有权访问你的日历的用户）</p></td>
</tr>
<tr class="even">
<td><p>状态</p></td>
<td><p>离开、空闲、忙碌、请勿打扰、脱机</p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a>必需数据

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>披露的数据</th>
<th>示例信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IP 地址</p></td>
<td><p>计算机的实际地址或经过 NAT 转换的地址</p></td>
</tr>
<tr class="even">
<td><p>SIP URI</p></td>
<td><p>jeremylos@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

