---
title: Skype for Business Server 2015 的用户和客户端身份验证
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的用户是其凭据已经过身份验证通过 Skype 在受信任的服务器的业务服务器 2015年。 此服务器通常是标准版，企业版前端服务器或服务器主管。 Skype 业务服务器依赖于 Active Directory 域服务单一、 信任后端存储库的用户凭据。
ms.openlocfilehash: d8fa9265a4c27432dd4c2dba6e15c07e39f348b8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-and-client-authentication-for-skype-for-business-server-2015"></a><span data-ttu-id="afb93-105">Skype for Business Server 2015 的用户和客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="afb93-105">User and client authentication for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="afb93-106">受信任的用户是其凭据已经过身份验证通过 Skype 在受信任的服务器的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="afb93-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server 2015.</span></span> <span data-ttu-id="afb93-107">此服务器通常是标准版，企业版前端服务器或服务器主管。</span><span class="sxs-lookup"><span data-stu-id="afb93-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="afb93-108">Skype 业务服务器依赖于 Active Directory 域服务单一、 信任后端存储库的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="afb93-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="afb93-109">身份验证是向受信任的服务器提供用户凭据的过程。</span><span class="sxs-lookup"><span data-stu-id="afb93-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="afb93-110">Skype 业务服务器将使用下列身份验证协议，具体取决于状态和用户的位置。</span><span class="sxs-lookup"><span data-stu-id="afb93-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="afb93-111">对于内部用户使用 Active Directory 凭据**MIT Kerberos 版本 5 的安全协议**。</span><span class="sxs-lookup"><span data-stu-id="afb93-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="afb93-112">Kerberos 需要与 Active Directory 域服务，这是为什么它不能用于身份验证客户端在公司防火墙外部的客户端连接。</span><span class="sxs-lookup"><span data-stu-id="afb93-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="afb93-113">使用 Active Directory 凭据连接从公司防火墙外的终结点用户的**NTLM 协议**。</span><span class="sxs-lookup"><span data-stu-id="afb93-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="afb93-114">访问边缘服务传递给主管，（如果存在） 或前端服务器进行身份验证的登录请求。</span><span class="sxs-lookup"><span data-stu-id="afb93-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="afb93-115">访问边缘服务本身执行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="afb93-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="afb93-116">与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以有些组织最大程度地减少了对 NTLM 的使用。</span><span class="sxs-lookup"><span data-stu-id="afb93-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="afb93-117">结果是，Skype 业务服务器 2015年的访问可能仅限于内部或客户端通过 VPN 或 DirectAccess 连接进行连接。</span><span class="sxs-lookup"><span data-stu-id="afb93-117">As a result, access to Skype for Business Server 2015 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="afb93-p107">**摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。</span><span class="sxs-lookup"><span data-stu-id="afb93-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="afb93-121">Skype 业务服务器 2015年身份验证包括两个阶段：</span><span class="sxs-lookup"><span data-stu-id="afb93-121">Skype for Business Server 2015 authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="afb93-122">在客户端和服务器之间建立安全关联。</span><span class="sxs-lookup"><span data-stu-id="afb93-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="afb93-p108">客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。</span><span class="sxs-lookup"><span data-stu-id="afb93-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="afb93-p109">用户信任会附加到用户发出的每条消息，而不会附加到用户标识本身。服务器将检查每条消息是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及受信任的服务器云中的所有其他服务器都不会对消息进行质询。</span><span class="sxs-lookup"><span data-stu-id="afb93-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="afb93-128">拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。</span><span class="sxs-lookup"><span data-stu-id="afb93-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="afb93-129">ICE 和 TURN 协议也使用摘要式质询，如 IETF TURN RFC 中所述。</span><span class="sxs-lookup"><span data-stu-id="afb93-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="afb93-130">客户端证书提供对用户进行身份验证通过 Skype 业务服务器 2015年的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="afb93-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server 2015.</span></span> <span data-ttu-id="afb93-131">用户无需提供用户名和密码，因为他们具有证书以及解析加密质询所需的与证书对应的私钥。</span><span class="sxs-lookup"><span data-stu-id="afb93-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="afb93-132">（此证书主题名称或者主题备用名称标识用户和必须由受信任的服务器运行 Skype 业务服务器 2015年由根 CA 颁发，可以在证书的有效期内，并不被吊销时必须有）要进行身份验证，用户只需输入个人识别码 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="afb93-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server 2015, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="afb93-133">证书对电话、移动电话和其他难以输入用户名和密码的设备特别有用。</span><span class="sxs-lookup"><span data-stu-id="afb93-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  

