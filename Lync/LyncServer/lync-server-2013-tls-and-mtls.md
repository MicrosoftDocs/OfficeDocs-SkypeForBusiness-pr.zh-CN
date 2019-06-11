---
title: 'Lync Server 2013: TLS 和 MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 066612f08c61ad1df342b4f2dd9b61ff5a5cc286
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>Lync Server 2013 的 TLS 和 MTLS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-07_

传输层安全性 (TLS) 和相互传输层安全性 (MTLS) 协议提供 Internet 上的加密通信和终结点身份验证。 Microsoft Lync Server 2013 使用这两个协议创建受信任服务器的网络, 并确保通过该网络的所有通信均已加密。 服务器之间的所有 SIP 通信都通过 MTLS 进行。 从客户端到服务器的 SIP 通信都通过 TLS 进行。

TLS 允许用户通过其客户端软件对其连接到的 Lync Server 2013 服务器进行身份验证。 在 TLS 连接上，客户端从服务器请求有效证书。 有效证书必须满足以下条件：由受客户端信任的 CA 颁发，且服务器的 DNS 名称必须与证书上的 DNS 名称一致。 如果证书有效，则客户端使用证书中的公钥对用于通信的对称加密密钥进行加密，因此只有证书的原始所有者可以使用其私钥对通信内容进行解密。 生成的连接将会受到信任，之后再不会受到其他受信任的服务器或客户端的质询。 在此上下文中，可将用于 Web 服务的安全套接字层 (SSL) 视为是基于 TLS 的。

服务器到服务器的连接依赖 MTLS 来进行相互身份验证。 在 MTLS 连接上，发出消息的服务器和接收消息的服务器交换来自相互信任的 CA 的证书。 证书可向一台服务器证明另一台服务器的身份。 在 Lync Server 2013 部署中, 由所有内部客户端和服务器 (由于 Active Directory 域的所有成员) 在其有效期内颁发的企业 CA 颁发的证书被自动视为有效的所有内部客户端和服务器。信任该域中的企业 CA。 在联盟方案中，发证 CA 必须得到联盟伙伴双方的信任。 如果需要，任一伙伴均可以使用不同的 CA，只要该 CA 同时获得另一个伙伴的信任即可。 通过在边缘服务器的受信任的根 CA 中包含伙伴的根 CA 证书，或通过使用双方信任的第三方 CA，可以很轻松地建立此信任。

TLS 和 MTLS 有助于防止窃听攻击和中间人攻击。 在中间人攻击中，攻击者将通过其计算机重新路由两个网络实体之间的通信，而这两个网络实体对此毫不知情。 TLS 和 Lync Server 2013 规范的受信任服务器 (仅在拓扑生成器中指定的服务器) 可通过使用公钥加密协调的端到端加密来减少部分在应用程序层上受到中间人攻击的风险在两个终结点之间, 攻击者必须拥有具有相应私钥的有效且受信任的证书, 并将该证书颁发给客户进行通信的服务的名称以解密通信。 不过，最终，您还是必须遵循有关您的网络基础结构（在此示例中为企业 DNS）的最佳安全做法。 Lync Server 2013 假定 DNS 服务器的信任方式与域控制器和全局编录的信任方式相同, 但 DNS 确实提供了针对 DNS 劫持攻击的保护级别, 防止攻击者的服务器成功响应申请哄骗名称。

下图显示了 Lync Server 2013 如何使用 MTLS 创建受信任服务器网络的高级别。

**Lync Server 网络中的受信任连接**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

