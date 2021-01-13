---
title: Skype for Business Server 的用户和客户端身份验证
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: 受信任用户是其凭据已由 Skype for Business Server 中的受信任服务器进行身份验证的用户。 此服务器通常是 Standard Edition Server、Enterprise Edition 前端服务器或控制器。 Skype for Business Server 依赖 Active Directory 域服务作为用户凭据的单一受信任后端存储库。
ms.openlocfilehash: bf0bde8478cd6c4e2eb068ffade7fba7fac14d56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832002"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a><span data-ttu-id="8944a-105">Skype for Business Server 的用户和客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="8944a-105">User and client authentication for Skype for Business Server</span></span>
 
<span data-ttu-id="8944a-106">受信任用户是其凭据已由 Skype for Business Server 中的受信任服务器进行身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="8944a-106">A trusted user is one whose credentials have been authenticated by a trusted server in Skype for Business Server.</span></span> <span data-ttu-id="8944a-107">此服务器通常是 Standard Edition Server、Enterprise Edition 前端服务器或控制器。</span><span class="sxs-lookup"><span data-stu-id="8944a-107">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="8944a-108">Skype for Business Server 依赖 Active Directory 域服务作为用户凭据的单一受信任后端存储库。</span><span class="sxs-lookup"><span data-stu-id="8944a-108">Skype for Business Server relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>
  
<span data-ttu-id="8944a-109">身份验证是向可信服务器提供用户凭据的过程。</span><span class="sxs-lookup"><span data-stu-id="8944a-109">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="8944a-110">Skype for Business Server 使用下列身份验证协议，具体取决于用户的状态和位置。</span><span class="sxs-lookup"><span data-stu-id="8944a-110">Skype for Business Server uses the following authentication protocols, depending on the status and location of the user.</span></span>
  
- <span data-ttu-id="8944a-p104">**MIT Kerberos 版本 5 安全协议** - 用于具有 Active Directory 凭据的内部用户。Kerberos 要求客户端与 Active Directory 域服务连接，这就是此协议不能用于对企业防火墙外部的客户端进行身份验证的原因。</span><span class="sxs-lookup"><span data-stu-id="8944a-p104">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>
    
- <span data-ttu-id="8944a-p105">**NTLM 协议** - 用于具有 Active Directory 凭据且从企业防火墙外部的终结点进行连接的用户。访问边缘服务将登录请求传递给控制器（如果存在）或前端服务器以进行身份验证。而访问边缘服务本身不执行任何身份验证。</span><span class="sxs-lookup"><span data-stu-id="8944a-p105">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8944a-116">与 Kerberos 相比，NTLM 协议提供的攻击保护较弱，所以某些组织最大程度地降低对 NTLM 的使用。</span><span class="sxs-lookup"><span data-stu-id="8944a-116">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="8944a-117">因此，对 Skype for Business Server 的访问可能仅限于内部或通过 VPN 或 DirectAccess 连接连接的客户端。</span><span class="sxs-lookup"><span data-stu-id="8944a-117">As a result, access to Skype for Business Server might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span> 
  
- <span data-ttu-id="8944a-p107">**摘要式协议** - 用于所谓的匿名用户。匿名用户是指满足以下条件的外部用户：这些用户虽然不具备认可的 Active Directory 凭据，但已被邀请参与内部会议并且拥有有效的会议密钥。摘要式身份验证不能用于其他客户端交互活动。</span><span class="sxs-lookup"><span data-stu-id="8944a-p107">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>
    
<span data-ttu-id="8944a-121">Skype for Business Server 身份验证包含两个阶段：</span><span class="sxs-lookup"><span data-stu-id="8944a-121">Skype for Business Server authentication consists of two phases:</span></span>
  
1. <span data-ttu-id="8944a-122">在客户端和服务器之间建立安全关联。</span><span class="sxs-lookup"><span data-stu-id="8944a-122">A security association is established between the client and the server.</span></span>
    
2. <span data-ttu-id="8944a-p108">客户端和服务器使用现有的安全关联签署它们发送的消息并验证接收到的消息。如果在服务器上启用身份验证，则不会接受来自客户端的未经身份验证的消息。</span><span class="sxs-lookup"><span data-stu-id="8944a-p108">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>
    
<span data-ttu-id="8944a-p109">用户信任将会附加在用户发出的每条消息上，而不是附加在用户标识本身上。服务器检查每条消息，查看是否具有有效的用户凭据。如果用户凭据有效，则接收消息的第一台服务器以及可信服务器云中的所有其他服务器都不会对消息进行质询。</span><span class="sxs-lookup"><span data-stu-id="8944a-p109">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>
  
<span data-ttu-id="8944a-128">拥有联盟伙伴颁发的有效凭据的用户会受到信任，但其他限制可能会阻止这些用户享有与内部用户相同的全部权限。</span><span class="sxs-lookup"><span data-stu-id="8944a-128">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>
  
<span data-ttu-id="8944a-129">ICE 和 TURN 协议也会使用摘要式质询，如 IETF TURN RFC 中所述。</span><span class="sxs-lookup"><span data-stu-id="8944a-129">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>
  
<span data-ttu-id="8944a-130">客户端证书为用户提供了通过 Skype for Business Server 进行身份验证的替代方法。</span><span class="sxs-lookup"><span data-stu-id="8944a-130">Client certificates provide an alternate way for users to be authenticated by Skype for Business Server.</span></span> <span data-ttu-id="8944a-131">无需提供用户名和密码，用户具有证书以及解析加密质询所需的与证书对应的私钥。</span><span class="sxs-lookup"><span data-stu-id="8944a-131">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="8944a-132"> (此证书必须具有标识用户的使用者名称或使用者替代名称，并且必须由运行 Skype for Business Server 的服务器信任的根 CA 颁发，且在证书有效期内且尚未吊销。) 若要进行身份验证，用户只需键入个人标识号 (PIN) 。</span><span class="sxs-lookup"><span data-stu-id="8944a-132">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Skype for Business Server, be within the certificate's validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="8944a-133">证书对于电话、移动电话和其他难以输入用户名和密码的设备特别有用。</span><span class="sxs-lookup"><span data-stu-id="8944a-133">Certificates are particularly useful for telephones, mobile phones, and other devices where it is difficult to enter a user name and password.</span></span>
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a><span data-ttu-id="8944a-134">ASP .NET 4.5 的加密要求</span><span class="sxs-lookup"><span data-stu-id="8944a-134">Cryptographic requirements due to ASP .NET 4.5</span></span> 

<span data-ttu-id="8944a-135">自 Skype for Business Server 2015 CU5 起，ASP.NET 4.6 不支持 AES，这可能会导致 Skype 会议应用无法启动。</span><span class="sxs-lookup"><span data-stu-id="8944a-135">As of Skype for Business Server 2015 CU5, AES is not supported for ASP.NET 4.6 and this may cause Skype Meetings App to fail to start.</span></span> <span data-ttu-id="8944a-136">如果客户端使用 AES 作为计算机密钥验证值，则需要将计算机密钥值重置为 SHA-1 或 IIS 上 Skype 会议应用站点级别支持的另一算法。</span><span class="sxs-lookup"><span data-stu-id="8944a-136">If a client is using AES as the machine key validation value you will need to reset the machine key value to SHA-1 or another supported algorithm on the Skype Meetings App site level on IIS.</span></span> <span data-ttu-id="8944a-137">如有必要，请参阅 [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) 了解说明。</span><span class="sxs-lookup"><span data-stu-id="8944a-137">If necessary, see [IIS 8.0 ASP.NET Configuration Management](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) for instructions.</span></span>
  
<span data-ttu-id="8944a-138">其他支持的值包括：</span><span class="sxs-lookup"><span data-stu-id="8944a-138">Other supported values are:</span></span>
  
- <span data-ttu-id="8944a-139">HMACSHA256</span><span class="sxs-lookup"><span data-stu-id="8944a-139">HMACSHA256</span></span>
    
- <span data-ttu-id="8944a-140">HMACSHA384</span><span class="sxs-lookup"><span data-stu-id="8944a-140">HMACSHA384</span></span>
    
- <span data-ttu-id="8944a-141">HMACSHA512</span><span class="sxs-lookup"><span data-stu-id="8944a-141">HMACSHA512</span></span>
    
  <span data-ttu-id="8944a-142">不再允许值 AES、3DES 和 MD5，因为它们曾经在 ASP.NET 4 中。</span><span class="sxs-lookup"><span data-stu-id="8944a-142">The values AES, 3DES, and MD5 are no longer allowed, as they once were in ASP.NET 4.</span></span> <span data-ttu-id="8944a-143">[ASP.NET 4.5 pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) 中的加密改进具有更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8944a-143">[Cryptographic Improvements in ASP.NET 4.5, pt. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) has more details.</span></span>
  
