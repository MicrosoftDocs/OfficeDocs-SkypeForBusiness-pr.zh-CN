---
title: 'Lync Server 2013: 用户和客户端身份验证'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Lync Server 2013 的用户和客户端身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-11_

受信任的用户是其凭据已由 Microsoft Lync Server 2013 中的受信任服务器进行身份验证的用户。 此服务器通常是标准版服务器、企业版前端服务器或控制器。 Lync Server 2013 依赖 Active Directory 域服务作为用户凭据的单个受信任的后端存储库。

身份验证是向受信任的服务器提供用户凭据的过程。 Lync Server 2013 使用以下身份验证协议, 具体取决于用户的状态和位置。

  - 对具有 Active Directory 凭据的内部用户的**Kerberos 版本5安全协议的 MIT** 。 Kerberos 需要与 Active Directory 域服务的客户端连接, 这就是为什么无法使用它来对公司防火墙外部的客户端进行身份验证。

  - 使用 Active Directory 凭据连接到公司防火墙外部终结点的用户的**NTLM 协议**。 Access Edge 服务将登录请求传递到 Director (如果存在) 或前端服务器进行身份验证。 访问边缘服务本身不执行身份验证。
    
    <div>
    

    > [!NOTE]  
    > 与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以有些组织最大程度地减少了对 NTLM 的使用。 因此, 对 Lync Server 2013 的访问可能仅限于内部或通过 VPN 或 DirectAccess 连接连接的客户端。

    
    </div>

  - **摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。

Lync Server 2013 身份验证包含两个阶段:

1.  在客户端和服务器之间建立安全关联。

2.  客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。

用户信任会附加到用户发出的每条消息，而不会附加到用户标识本身。服务器将检查每条消息是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及受信任的服务器云中的所有其他服务器都不会对消息进行质询。

拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。

ICE 和 TURN 协议也使用摘要式质询，如 IETF TURN RFC 中所述。

客户端证书为用户提供了另一种通过 Lync Server 2013 进行身份验证的方法。 用户无需提供用户名和密码，因为他们具有证书以及解析加密质询所需的与证书对应的私钥。 (此证书必须具有标识用户的主题名称或主题备用名称, 并且必须由运行 Lync Server 2013 的服务器信任的根 CA 发出, 在证书的有效期内, 并且未被吊销。)若要进行身份验证, 用户只需键入个人识别码 (PIN)。 证书对于运行 Microsoft Lync 2013 Phone Edition 的电话和其他设备尤其有用, 在这种情况下, 很难输入用户名和/或密码。

</div>

<span> </span>

</div>

</div>

</div>

