---
title: Lync Server 2013：常见安全威胁在现代日计算中
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dffff9cfbc501a8e6a9a79439183966ef0a1956
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a>现代的日期计算中的常见安全威胁

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-10_

由于 Lync Server 2013 是企业级通信系统，因此应注意可能影响其基础结构和通信的常见安全攻击。

<div>

## <a name="compromised-key-attack"></a>破解密钥攻击

密钥是用于加密、解密或验证机密信息的机密代码或数字。 必须考虑在公钥基础结构（PKI）中使用两个敏感密钥：。

  - 每个证书持有者拥有的私钥

  - 在通信合作伙伴成功进行身份验证和会话密钥交换之后使用的会话密钥

破解密钥攻击是指攻击者破解私钥或会话密钥的行为。 攻击者在成功破解密钥之后，可以使用此密钥对已加密的数据进行解密，而数据的发送者对此毫不知情。

Lync Server 2013 使用 Windows Server 操作系统中的 PKI 功能来保护用于加密传输层安全性（TLS）连接的密钥数据。 用于媒体加密的密钥通过 TLS 连接进行交换。

</div>

<div>

## <a name="network-denial-of-service-attack"></a>网络拒绝服务攻击

当攻击者阻止正常网络使用和有效用户正常运行时，会发生*拒绝服务攻击*。 这是在攻击者使用严重请求使服务与合法用户一起使用服务的合法请求一起完成时实现的。 通过使用拒绝服务攻击，攻击者可以执行以下操作：

  - 向受到攻击的网络中正在运行的应用程序和服务发送无效数据，干扰它们的正常工作。

  - 发送大量流量以造成系统过载，直到系统停止对合理请求做出响应或对合理请求做出响应的速度变得很慢。

  - 隐藏攻击证据。

  - 阻止用户访问网络资源。

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a>窃听（嗅探、窥探）

当攻击者获得对网络中数据路径的访问权限并能够监控和读取流量时，可能会发生*窃听*。 这也称为 "*嗅探*" 或 "*窥探*"。 如果流量内容采用纯文本形式，则攻击者在获取路径的访问权之后即可读取流量内容。 例如，通过控制数据路径上的路由器进行攻击。

Microsoft Lync Server 2013 中的流量的默认建议和设置是在受信任的服务器和从客户端到服务器之间的 TLS 之间使用相互 TLS （MTLS）。 此保护措施将使得攻击非常困难，或者在给定对话发生的时间段内无法实现。 TLS 可对各方执行身份验证，并对所有流量内容进行加密。 这样不能阻止窃听，但攻击者不能读取流量内容，除非破坏加密。

使用中继 NAT （TURN）协议的遍历不会要求加密通信，并且要发送的信息受消息完整性保护。 尽管它是开放的，但它发送的信息（即 IP 地址和端口）可以直接提取，只需查看数据包的源地址和目标地址即可。 A/V 边缘服务可确保数据有效，方法是使用从少数几个项目派生的密钥检查邮件的消息完整性，包括密码（从不以明文形式发送）。 如果使用安全实时协议（SRTP），则媒体流量也会进行加密。

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a>身份欺骗（IP 地址欺骗）

当攻击者在未经授权的情况下确定和使用网络、计算机或网络组件的 IP 地址时，会发生*欺骗*。 一旦攻击成功，攻击者便可以假借 IP 地址通常标识的实体的身份执行操作。 在 Microsoft Lync Server 2013 的上下文中，仅当管理员已执行以下两项操作时，才会发生这种情况：

  - 已配置仅支持传输控制协议 (TCP) 的连接（建议不要这样做，因为 TCP 通信未经过加密）。

  - 将这些连接的 IP 地址标记为受信任的主机。

此操作对于传输层安全性 (TLS) 连接而言不成问题，因为 TLS 对所有方进行验证并加密所有通信。 使用 TLS 可防止攻击者对特定连接（例如，相互 TLS 连接）执行 IP 地址欺骗攻击。 但是，攻击者仍然可以哄骗 Lync Server 2013 使用的 DNS 服务器的地址。 但是，因为 Lync 中的身份验证是通过证书执行的，所以攻击者将没有欺骗通信中的任何一方所需的有效证书。

</div>

<div>

## <a name="man-in-the-middle-attack"></a>中间人攻击

当攻击者在发生通信的两个用户不知情的情况下，通过自己的计算机重新路由这两个用户之间的通信时，就会发生中间人攻击。 攻击者可以在将通信内容发送到预期接收人之前监控和读取通信内容。 通信中的每个用户在不知情的情况下向攻击者发送通信和从攻击者接收通信，还以为自己只是在与预期用户进行通信。 如果攻击者可修改 Active Directory 域服务以将他（她）的服务器添加为受信任服务器或修改域名系统 (DNS) 以让客户端在与服务器通信时通过攻击者，则会发生这种情况。 在两个客户端之间的媒体通信也会发生中间人攻击。 但是，在 Microsoft Lync Server 2013 点到点音频、视频和应用程序共享中，流使用 SRTP 进行了加密，在使用通过 TLS 的会话初始协议（SIP）的对等方之间协商的加密密钥。 诸如 Group Chat 的服务器使用 HTTPS 来增强 Web 通信的安全性。

</div>

<div>

## <a name="rtp-replay-attack"></a>RTP 重播攻击

当两方之间的有效媒体传输因恶意目的而被截取和重新传输时，会发生*重播攻击*。 通过允许接收人维护已收到的 RTP 数据包的索引并将每个新数据包与索引中已列出的数据包加以比较，安全信号协议连接中使用的 SRTP 可保护传输免受重播攻击。

</div>

<div>

## <a name="spim"></a>Spim

*Spim*是未经请求的商业即时消息或状态订阅请求。 虽然 Spim 本身并不会导致网络问题，但至少会有些烦人，占用资源和生产时间，而且可能会导致网络问题。 例如，用户通过发送请求相互发送垃圾消息。 用户可以相互阻止对方来防止出现这种情况，但对于联盟，如果建立了协作的 Spim 攻击，则很难防止出现这种情况，除非您禁用联盟伙伴关系。

</div>

<div>

## <a name="viruses-and-worms"></a>病毒和蠕虫

*病毒*是一种代码单元，其目的是复制其他类似的代码单元。 病毒需要像文件、电子邮件或程序这样的宿主才能发挥作用。 *蠕虫*是一种代码单元，其目的是复制其他类似的代码单元，但它不需要主机。 病毒和蠕虫主要是在客户端之间传送文件期间或从其他用户发送 URL 时出现。 例如，如果您的计算机上存在某种病毒，则该病毒可使用您的身份代表您发送即时消息。

</div>

<div>

## <a name="personally-identifiable-information"></a>个人身份信息

Microsoft Lync Server 2013 可能会泄露可链接到个人的公共网络的信息。 这些信息类型具体可分为两大类：

  - **增强状态数据**增强状态数据是指用户可以选择共享或不共享到联盟伙伴或组织内联系人的链接的信息。 不与公用 IM 网络上的用户共享此数据。 客户端策略和其他客户端配置可能会为系统管理员提供一些控制能力。 在 Lync Server 2013 中，可为单个用户配置 "增强状态" 隐私模式，以防止 Lync 用户不在用户的 "联系人" 列表中查看用户的状态信息。 增强状态隐私模式不会阻止 Microsoft Office Communicator 2007 和 Microsoft Office Communicator 2007 R2 的用户看到用户的状态信息。 有关详细信息，请参阅部署文档中的入门文档和[在 Lync server 2013 中配置增强状态隐私模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)中的[客户端的新增功能： lync server 2013](lync-server-2013-what-s-new-for-clients.md) 。

  - **必需数据**必需的数据是服务器或客户端的正确操作所必需的，不受客户端或系统管理的控制。 对于路由、状态维护和信号传输而言，此信息是必需的服务器或网络级别信息。

下表列出了通过公用网络公开的数据。

### <a name="enhanced-presence-data"></a>增强状态数据

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>数据泄露</th>
<th>可能的设置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>个人数据</p></td>
<td><p>名称、职务、公司、电子邮件地址、时区</p></td>
</tr>
<tr class="even">
<td><p>电话号码</p></td>
<td><p>工作电话号码、手机号码、住宅电话号码</p></td>
</tr>
<tr class="odd">
<td><p>日历信息</p></td>
<td><p>忙/闲、不在城镇通知、会议详细信息（对具有日历访问权限的用户）</p></td>
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
<th>数据泄露</th>
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

