---
title: Lync Server 2013：用户和客户端身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21f2fa918acf01d9d13e44e0731825dd51b3d918
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033961"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="22487-102">Lync Server 2013 的用户和客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="22487-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22487-103">_**上次修改的主题：** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="22487-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="22487-104">受信任用户是指其凭据已由 Microsoft Lync Server 2013 中的受信任服务器进行身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="22487-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="22487-105">此服务器通常是 Standard Edition Server、Enterprise Edition 前端服务器或控制器。</span><span class="sxs-lookup"><span data-stu-id="22487-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="22487-106">Lync Server 2013 依赖 Active Directory 域服务作为用户凭据的单个受信任的后端存储库。</span><span class="sxs-lookup"><span data-stu-id="22487-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="22487-107">身份验证是向可信服务器提供用户凭据的过程。</span><span class="sxs-lookup"><span data-stu-id="22487-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="22487-108">Lync Server 2013 使用以下身份验证协议，具体取决于用户的状态和位置。</span><span class="sxs-lookup"><span data-stu-id="22487-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="22487-p103">**MIT Kerberos 版本 5 安全协议** - 用于具有 Active Directory 凭据的内部用户。Kerberos 要求客户端与 Active Directory 域服务连接，这就是此协议不能用于对企业防火墙外部的客户端进行身份验证的原因。</span><span class="sxs-lookup"><span data-stu-id="22487-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="22487-p104">**NTLM 协议** - 用于具有 Active Directory 凭据且从企业防火墙外部的终结点进行连接的用户。访问边缘服务将登录请求传递给控制器（如果存在）或前端服务器以进行身份验证。而访问边缘服务本身不执行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="22487-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22487-114">与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以某些组织最大程度地降低对 NTLM 的使用。</span><span class="sxs-lookup"><span data-stu-id="22487-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="22487-115">因此，对 Lync Server 2013 的访问可能仅限于内部或通过 VPN 或 DirectAccess 连接连接的客户端。</span><span class="sxs-lookup"><span data-stu-id="22487-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="22487-p106">**摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不能用于其他客户端交互活动。</span><span class="sxs-lookup"><span data-stu-id="22487-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="22487-119">Lync Server 2013 身份验证包含两个阶段：</span><span class="sxs-lookup"><span data-stu-id="22487-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="22487-120">在客户端和服务器之间建立安全关联。</span><span class="sxs-lookup"><span data-stu-id="22487-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="22487-p107">客户端和服务器使用现有的安全关联签署它们发送的消息并验证接收到的消息。如果在服务器上启用身份验证，则不会接受来自客户端的未经身份验证的消息。</span><span class="sxs-lookup"><span data-stu-id="22487-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="22487-p108">用户信任将会附加在用户发出的每条消息上，而不是附加在用户标识本身上。服务器检查每条消息，查看是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及可信服务器云中的所有其他服务器都不会对消息进行质询。</span><span class="sxs-lookup"><span data-stu-id="22487-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="22487-126">拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。</span><span class="sxs-lookup"><span data-stu-id="22487-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="22487-127">ICE 和 TURN 协议也会使用摘要式质询，如 IETF TURN RFC 中所述。</span><span class="sxs-lookup"><span data-stu-id="22487-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="22487-128">客户端证书为用户提供了另一种通过 Lync Server 2013 进行身份验证的方法。</span><span class="sxs-lookup"><span data-stu-id="22487-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="22487-129">无需提供用户名和密码，用户具有证书以及解析加密质询所需的与证书对应的私钥。</span><span class="sxs-lookup"><span data-stu-id="22487-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="22487-130">（此证书必须具有标识用户的使用者名称或使用者替代名称，并且必须由运行 Lync Server 2013 的服务器信任的根 CA 颁发，在证书的有效期内，且未被吊销。）若要进行身份验证，用户只需键入个人标识号（PIN）。</span><span class="sxs-lookup"><span data-stu-id="22487-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="22487-131">证书对于运行 Microsoft Lync 2013 Phone Edition 的电话和其他设备尤其有用，在这种情况下，很难输入用户名和/或密码。</span><span class="sxs-lookup"><span data-stu-id="22487-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

