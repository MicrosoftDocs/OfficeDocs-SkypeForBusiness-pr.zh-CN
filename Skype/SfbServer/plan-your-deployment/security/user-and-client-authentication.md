---
title: 用户和客户端身份验证的 Skype 业务服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任的用户是指其凭据已经过身份验证的 Skype 中的受信任服务器的企业服务器。 此服务器通常是 Standard Edition server，Enterprise Edition 前端服务器或控制器。 Skype 业务服务器依赖于 Active Directory 域服务的用户凭据的单一的受信任后端存储库。
ms.openlocfilehash: f8f006ac3f727553f612070ea9bdbf696d81a97e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213457"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="459ca-105">用户和客户端身份验证的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="459ca-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="459ca-106">受信任的用户是指其凭据已经过身份验证的 Skype 中的受信任服务器的企业服务器。</span><span class="sxs-lookup"><span data-stu-id="459ca-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="459ca-107">此服务器通常是 Standard Edition server，Enterprise Edition 前端服务器或控制器。</span><span class="sxs-lookup"><span data-stu-id="459ca-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="459ca-108">Skype 业务服务器依赖于 Active Directory 域服务的用户凭据的单一的受信任后端存储库。</span><span class="sxs-lookup"><span data-stu-id="459ca-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="459ca-109">身份验证是向受信任的服务器提供用户凭据的过程。</span><span class="sxs-lookup"><span data-stu-id="459ca-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="459ca-110">Skype 业务服务器使用以下身份验证协议，具体取决于状态和用户的位置。</span><span class="sxs-lookup"><span data-stu-id="459ca-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="459ca-111">**MIT Kerberos 版本 5 安全协议-用于**具有 Active Directory 凭据的内部用户。</span><span class="sxs-lookup"><span data-stu-id="459ca-111">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="459ca-112">Kerberos 要求客户端连接到 Active Directory 域服务，这是它不能用于对企业防火墙外部的客户端进行身份验证的原因。</span><span class="sxs-lookup"><span data-stu-id="459ca-112">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="459ca-113">**NTLM 协议**-用于具有 Active Directory 凭据且从企业防火墙外部的终结点进行连接的用户。</span><span class="sxs-lookup"><span data-stu-id="459ca-113">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="459ca-114">访问边缘服务将登录请求传递给 Director，如果存在此参数或前端服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="459ca-114">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="459ca-115">访问边缘服务本身不执行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="459ca-115">The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="459ca-116">与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以有些组织最大程度地减少了对 NTLM 的使用。</span><span class="sxs-lookup"><span data-stu-id="459ca-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="459ca-117">因此，访问 Skype 的业务服务器可能仅限于内部或客户端通过 VPN 或 DirectAccess 连接进行连接。</span><span class="sxs-lookup"><span data-stu-id="459ca-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="459ca-p107">**摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不用于其他客户端交互。</span><span class="sxs-lookup"><span data-stu-id="459ca-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="459ca-121">Skype 业务服务器身份验证包括两个阶段：</span><span class="sxs-lookup"><span data-stu-id="459ca-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="459ca-122">在客户端和服务器之间建立安全关联。</span><span class="sxs-lookup"><span data-stu-id="459ca-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="459ca-p108">客户端和服务器使用现有的安全关联签署它们发送的消息，以及验证所收到的消息。如果在服务器上启用了身份验证，则不会接受来自客户端的未经身份验证的消息。</span><span class="sxs-lookup"><span data-stu-id="459ca-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="459ca-p109">用户信任会附加到用户发出的每条消息，而不会附加到用户标识本身。服务器将检查每条消息是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及受信任的服务器云中的所有其他服务器都不会对消息进行质询。</span><span class="sxs-lookup"><span data-stu-id="459ca-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="459ca-128">拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。</span><span class="sxs-lookup"><span data-stu-id="459ca-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="459ca-129">ICE 和 TURN 协议也使用摘要式质询，如 IETF TURN RFC 中所述。</span><span class="sxs-lookup"><span data-stu-id="459ca-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="459ca-130">客户端证书提供用户进行身份验证的 Skype 业务服务器另一种的方法。</span><span class="sxs-lookup"><span data-stu-id="459ca-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="459ca-131">用户无需提供用户名和密码，因为他们具有证书以及解析加密质询所需的与证书对应的私钥。</span><span class="sxs-lookup"><span data-stu-id="459ca-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="459ca-132">（此证书必须使用者名称或使用者替代名称的标识用户必须由业务服务器运行 Skype 服务器信任的根 CA 颁发、 位于内的证书有效期限和不具有已吊销。）要进行身份验证，用户只需键入个人标识号 (PIN)。</span><span class="sxs-lookup"><span data-stu-id="459ca-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="459ca-133">证书对电话、移动电话和其他难以输入用户名和密码的设备特别有用。</span><span class="sxs-lookup"><span data-stu-id="459ca-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="459ca-134">由于 ASP.NET 4.5 加密要求</span><span class="sxs-lookup"><span data-stu-id="459ca-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="459ca-135">截止业务服务器 2015 CU5 的 Skype，AES 不支持 ASP.NET 4.6，这可能会导致 Skype 会议应用程序无法启动。</span><span class="sxs-lookup"><span data-stu-id="459ca-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="459ca-136">如果客户端使用的作为计算机关键验证值 AES 需要计算机密钥值重置为 sha-1 或在 IIS 上的 Skype 会议应用程序网站级别上的另一个受支持的算法。</span><span class="sxs-lookup"><span data-stu-id="459ca-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="459ca-137">如有必要，请参阅[IIS 8.0 ASP.NET 配置管理](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)说明。</span><span class="sxs-lookup"><span data-stu-id="459ca-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="459ca-138">其他支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="459ca-138">Other supported values are:</span></span>
  
- <span data-ttu-id="459ca-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="459ca-139">HMACSHA256</span></span>
    
- <span data-ttu-id="459ca-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="459ca-140">HMACSHA384</span></span>
    
- <span data-ttu-id="459ca-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="459ca-141">HMACSHA512</span></span>
    
  <span data-ttu-id="459ca-142">AES、 3DES 和 MD5 不再允许，像一次 ASP.NET 4 中的值。</span><span class="sxs-lookup"><span data-stu-id="459ca-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="459ca-143">[ASP.NET 4.5，磅 2 中的加密改进](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)具有更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="459ca-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
