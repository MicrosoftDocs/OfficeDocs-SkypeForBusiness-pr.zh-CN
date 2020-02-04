---
title: Lync Server 2013：Lync Server 中影响边缘服务器规划的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a><span data-ttu-id="b982b-102">Lync Server 2013 中影响边缘服务器规划的更改</span><span class="sxs-lookup"><span data-stu-id="b982b-102">Changes in Lync Server 2013 that affect Edge Server planning</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b982b-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b982b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b982b-104">Lync Server 2013 引入了新功能，可为你的用户扩展功能和通信方法。</span><span class="sxs-lookup"><span data-stu-id="b982b-104">Lync Server 2013 introduces new features that extend the features and communications methods for your users.</span></span> <span data-ttu-id="b982b-105">此外，Lync Server 2013 引入了对现有服务的更改，以便更好地集成和扩展你的组织可使用的服务。</span><span class="sxs-lookup"><span data-stu-id="b982b-105">Also, Lync Server 2013 introduces changes to existing services to better integrate and extend the services that are available to your organization.</span></span> <span data-ttu-id="b982b-106">下面是可能影响您规划和部署 Lync Server 2013 Edge 服务器服务的更改的摘要。</span><span class="sxs-lookup"><span data-stu-id="b982b-106">Following is a summary of changes that may affect your planning and deployment of Lync Server 2013 Edge Server services.</span></span>

<div>

## <a name="support-for-ipv6-addressing"></a><span data-ttu-id="b982b-107">对 IPv6 寻址的支持</span><span class="sxs-lookup"><span data-stu-id="b982b-107">Support for IPv6 Addressing</span></span>

<span data-ttu-id="b982b-108">Lync Server 2013 支持所有 Edge 服务器服务的 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="b982b-108">Lync Server 2013 supports IPv6 addressing for all Edge Server services.</span></span> <span data-ttu-id="b982b-109">如果你已通过 Windows Server 中的配置为接口提供 IPv6 地址，则可以在 Edge 服务器配置中通过拓扑生成器中的 IP 地址配置使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="b982b-109">If you have provided IPv6 addresses for the interfaces through configuration in Windows Server, you can use IPv6 addresses in your Edge Server configuration through the IP address configuration in Topology Builder.</span></span> <span data-ttu-id="b982b-110">此外，可扩展消息和状态协议（XMPP）支持 IPv6。</span><span class="sxs-lookup"><span data-stu-id="b982b-110">Additionally, the extensible messaging and presence protocol (XMPP) supports IPv6.</span></span> <span data-ttu-id="b982b-111">不需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="b982b-111">No additional configuration is required.</span></span> <span data-ttu-id="b982b-112">如果在拓扑中配置了 IPv6，XMPP 将使用 IPv6 （如果需要）。</span><span class="sxs-lookup"><span data-stu-id="b982b-112">If IPv6 is configured in the topology, XMPP will use IPv6 (where required).</span></span>

<span data-ttu-id="b982b-113">对在 Lync Server 2013 中支持 IPv6 的增加的要求是为必须发现和解析为 IPv6 地址的记录创建域名系统记录。</span><span class="sxs-lookup"><span data-stu-id="b982b-113">An added requirement to support IPv6 in Lync Server 2013 is to create domain name system records for records that must be discovered and resolved to an IPv6 address.</span></span> <span data-ttu-id="b982b-114">IPv6 DNS 使用定义为**AAAA**的主机记录和名为 "quad A" 的主机记录。</span><span class="sxs-lookup"><span data-stu-id="b982b-114">IPv6 DNS uses host records that are defined as **AAAA** and called “quad-A”.</span></span> <span data-ttu-id="b982b-115">其他记录类型与它们的 IPv4 对应项一致。</span><span class="sxs-lookup"><span data-stu-id="b982b-115">Other record types are consistent with their IPv4 counterparts.</span></span>

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a><span data-ttu-id="b982b-116">对可扩展消息和状态协议（XMPP）部署的支持</span><span class="sxs-lookup"><span data-stu-id="b982b-116">Support for Extensible Messaging and Presence Protocol (XMPP) Deployment</span></span>

<span data-ttu-id="b982b-117">Edge 服务器引入了完全集成的 XMPP 代理（部署在 Edge 服务器上）和 XMPP 网关（部署在前端服务器上）。</span><span class="sxs-lookup"><span data-stu-id="b982b-117">Edge Server introduces a fully integrated XMPP proxy (deployed on the Edge Servers) and an XMPP gateway (deployed on your Front End Servers).</span></span> <span data-ttu-id="b982b-118">你可以将 XMPP 联盟部署为可选组件。</span><span class="sxs-lookup"><span data-stu-id="b982b-118">You can deploy XMPP federation as an optional component.</span></span> <span data-ttu-id="b982b-119">通过添加和配置 XMPP 代理和 XMPP 网关，你可以允许 Microsoft Lync 2013 用户添加来自基于 XMPP 的合作伙伴的联系人，以便发送即时消息（IM）和状态。</span><span class="sxs-lookup"><span data-stu-id="b982b-119">By adding and configuring the XMPP proxy and XMPP gateway, you can enable your Microsoft Lync 2013 users to add contacts from XMPP-based partners for instant messaging (IM) and presence.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b982b-120">目前，Edge 服务器中的 XMPP 服务仅在 Lync Server 客户端和基于 XMPP 的联系人之间提供即时消息和状态。</span><span class="sxs-lookup"><span data-stu-id="b982b-120">Currently, the XMPP services in Edge Server only provide IM and presence between Lync Server clients and XMPP-based contacts.</span></span> <span data-ttu-id="b982b-121">此外，XMPP 仅托管在一个网站中。</span><span class="sxs-lookup"><span data-stu-id="b982b-121">Additionally, XMPP is hosted in only one site.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b982b-p106">Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="b982b-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a><span data-ttu-id="b982b-124">支持将音频/视频身份验证和服务器滚动到服务器身份验证证书</span><span class="sxs-lookup"><span data-stu-id="b982b-124">Support for Rolling Audio/Video Authentication and Server to Server Authentication Certificates</span></span>

<span data-ttu-id="b982b-125">证书用于生成颁发给客户和 A/V 身份验证服务的其他使用者以及服务器到服务器身份验证的令牌。</span><span class="sxs-lookup"><span data-stu-id="b982b-125">A certificate is used to generate tokens that are issued to clients and other consumers of the A/V Authentication service and for server to server authentication.</span></span> <span data-ttu-id="b982b-126">音频/视频身份验证证书的类型为*AudioVideoAuthentication* ，服务器到服务器身份验证证书的类型为*OAuthTokenIssuer*。</span><span class="sxs-lookup"><span data-stu-id="b982b-126">The Audio/Video Authentication certificate is of type *AudioVideoAuthentication* and the Server to Server Authentication certificate is of type *OAuthTokenIssuer*.</span></span>

<span data-ttu-id="b982b-127">对于音频/视频身份验证，令牌用于对端口分配请求进行身份验证，令牌缓存最多8小时-令牌的默认生存期。</span><span class="sxs-lookup"><span data-stu-id="b982b-127">For Audio/Video Authentication, tokens are used to authenticate port allocation requests, and the tokens are cached for up to 8 hours – the default lifetime of the token.</span></span> <span data-ttu-id="b982b-128">在 "正常操作" 下，这是创建并将身份验证材料分发给 A/V 消费者的非常可靠的方法。</span><span class="sxs-lookup"><span data-stu-id="b982b-128">Under normal operation, this is a very reliable method to create and distribute authentication material to the A/V consumers.</span></span> <span data-ttu-id="b982b-129">但是，证书具有有限的生命周期，并在预定义的日期和时间（基于创建证书的证书颁发机构（通常是两年），这种类型的证书的创建日期和策略过期。</span><span class="sxs-lookup"><span data-stu-id="b982b-129">However, certificates have a finite lifetime and expire on a predefined date and time (based on creation date and the policies enforced at the certification authority that created the certificate, typically 2 years for this type of certificate).</span></span> <span data-ttu-id="b982b-130">当证书到期时，由过期证书创建并由使用者缓存的任何令牌均无效。</span><span class="sxs-lookup"><span data-stu-id="b982b-130">When the certificate expires, any tokens created by the expired certificate and cached by consumers become not valid.</span></span> <span data-ttu-id="b982b-131">任何使用已过期证书创建的令牌的尝试都将导致媒体中继分配失败，并且所有当前音频/视频会话将失败。</span><span class="sxs-lookup"><span data-stu-id="b982b-131">Any attempts to use a token created with an expired certificate would result in failed Media Relay allocations and any current Audio/Video sessions will fail.</span></span> <span data-ttu-id="b982b-132">客户端需要获取有效证书创建的新令牌才能恢复正常的音频和视频功能。</span><span class="sxs-lookup"><span data-stu-id="b982b-132">The client would need to acquire a new token created by a valid certificate to resume normal Audio and Video functionality.</span></span>

<span data-ttu-id="b982b-133">服务器到服务器身份验证由请求和应用于部署中所有服务器的全局证书管理。</span><span class="sxs-lookup"><span data-stu-id="b982b-133">Server to Server Authentication is managed by a global certificate that is requested and applied to all servers in the deployment.</span></span> <span data-ttu-id="b982b-134">证书负责在 Lync Server 2013 中验证服务器以及对 Exchange 2013 和 Microsoft SharePoint Server 2013 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b982b-134">The certificate is responsible for authenticating servers in Lync Server 2013 as well as authenticating to Exchange 2013 and Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="b982b-135">有关服务器到服务器身份验证的工作方式的详细信息，请参阅[在 Lync server 2013 中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="b982b-135">For more information on how Server to Server Authentication works, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).</span></span> <span data-ttu-id="b982b-136">音频/视频身份验证过程与服务器到服务器身份验证过程之间的一个非常重要的区别是身份验证或令牌的生命周期。</span><span class="sxs-lookup"><span data-stu-id="b982b-136">One very important difference between the Audio/Video Authentication process and the Server to Server Authentication process is the lifetime of the authentication, or tokens.</span></span> <span data-ttu-id="b982b-137">对于音频/视频身份验证，身份验证将在八个小时后到期。</span><span class="sxs-lookup"><span data-stu-id="b982b-137">For Audio/Video Authentication, the authentication expires after eight hours.</span></span> <span data-ttu-id="b982b-138">服务器到服务器身份验证的生命周期为24小时。</span><span class="sxs-lookup"><span data-stu-id="b982b-138">Server-to-Server Authentication has a lifetime of 24 hours.</span></span> <span data-ttu-id="b982b-139">您必须针对每种证书类型进行相应规划。</span><span class="sxs-lookup"><span data-stu-id="b982b-139">You must plan accordingly for each of the certificate types.</span></span>

<span data-ttu-id="b982b-140">Lync Server 2013 的新增功能是在当前证书到期之前将替换音频/视频身份验证证书和服务器转移到服务器身份验证证书的功能。</span><span class="sxs-lookup"><span data-stu-id="b982b-140">New for Lync Server 2013 is the ability to stage a replacement Audio/Video Authentication certificate and Server to Server Authentication certificate in advance of the expiration of the current certificate.</span></span> <span data-ttu-id="b982b-141">然后，新证书用于生成新的令牌或新的身份验证请求。</span><span class="sxs-lookup"><span data-stu-id="b982b-141">The new certificate is then used for generating new tokens or new authentication requests.</span></span> <span data-ttu-id="b982b-142">但保留用于验证当前会话和身份验证的旧证书。</span><span class="sxs-lookup"><span data-stu-id="b982b-142">but retains the old certificate for verifying the current sessions and authentications..</span></span> <span data-ttu-id="b982b-143">完成此操作的目标是有效地避免因令牌和证书到期而导致几乎所有失败。</span><span class="sxs-lookup"><span data-stu-id="b982b-143">What this accomplishes is to effectively prevent nearly all failures due to token and certificate expirations.</span></span> <span data-ttu-id="b982b-144">有关此功能的详细信息以及如何配置它，请参阅[在 CsCertificate 中使用-滚在 Lync Server 2013 中暂存 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span><span class="sxs-lookup"><span data-stu-id="b982b-144">For details of this feature and how to configure it, see [Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)</span></span>

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a><span data-ttu-id="b982b-145">减少了对基于 Cookie 的相似性的依赖</span><span class="sxs-lookup"><span data-stu-id="b982b-145">Reduced Reliance on Cookie-based Affinity</span></span>

<span data-ttu-id="b982b-146">在早期版本的 Lync Server 和 Office 通信服务器中，Web 服务使用基于 cookie 的相关性以确保客户端和 Web 服务会话状态已维护。</span><span class="sxs-lookup"><span data-stu-id="b982b-146">In previous versions of Lync Server and Office Communications Server, cookie-based affinity was used by the Web services to ensure that the client and Web services session state was maintained.</span></span> <span data-ttu-id="b982b-147">Lync Server 2013 Web 服务使用内置的关联机制，可消除基于 cookie 的相似性的大多数要求。</span><span class="sxs-lookup"><span data-stu-id="b982b-147">Lync Server 2013 Web services use a built in affinity mechanism that eliminates most of the requirements for cookie-based affinity.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b982b-148">Microsoft Lync 2010 移动客户端仍然必须使用基于 cookie 的相似性，并且需要配置基于 cookie 的相似性，直到将所有客户端迁移到即将发布的 Microsoft Lync 移动客户端（尚未确定的发布日期）。</span><span class="sxs-lookup"><span data-stu-id="b982b-148">The Microsoft Lync 2010 Mobile client must still use cookie-based affinity and will require configuration of cookie-based affinity until you have migrated all clients to the upcoming Microsoft Lync Mobile client (Date of release not yet determined).</span></span>



</div>

<span data-ttu-id="b982b-149">有关 Lync Server 2013 中基于 cookie 的相关性的详细信息，请参阅[Lync server 2013 中的外部用户访问所需的组件](lync-server-2013-components-required-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b982b-149">For details about cookie-based affinity in Lync Server 2013, see [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

</div>

<div>

## <a name="autodiscover-enhancements"></a><span data-ttu-id="b982b-150">自动发现增强</span><span class="sxs-lookup"><span data-stu-id="b982b-150">AutoDiscover Enhancements</span></span>

<span data-ttu-id="b982b-151">Lync Server 2013 中的自动发现功能使客户能够找到可用于通信的附加功能。</span><span class="sxs-lookup"><span data-stu-id="b982b-151">The autodiscover feature in Lync Server 2013 enables clients to locate additional features that are made available for communication.</span></span> <span data-ttu-id="b982b-152">自动发现功能是 Lync Server 2010 的累积更新中第一次引入的2011：移动版和 Microsoft Lync 2010 移动版的累积更新。</span><span class="sxs-lookup"><span data-stu-id="b982b-152">Autodiscover was first introduced in the cumulative update for Lync Server 2010: November 2011 for Mobility and Microsoft Lync 2010 Mobile.</span></span> <span data-ttu-id="b982b-153">自动发现功能（也称为 DNS 记录名称 LyncDiscover 和 LyncDiscoverInternal）允许客户查找和使用移动服务（适用于 Microsoft Lync 2010 移动客户端）、Microsoft Lync Web App 和 Lync Web 计划程序以及与 Microsoft Exchange Server 和 SharePoint Server 的通信。</span><span class="sxs-lookup"><span data-stu-id="b982b-153">The autodiscover feature (also known by the DNS record names LyncDiscover and LyncDiscoverInternal) allows clients to locate and use mobility services (for Microsoft Lync 2010 Mobile clients), the Microsoft Lync Web App, and the Lync Web scheduler, as well as communications with Microsoft Exchange Server and SharePoint Server.</span></span> <span data-ttu-id="b982b-154">自动发现作为基础结构和 Lync Server 2013 服务器的设置和部署的正常部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="b982b-154">Autodiscover is installed as normal part of the setup and deployment of your infrastructure and Lync Server 2013 servers.</span></span> <span data-ttu-id="b982b-155">拓扑生成器和 Lync Server 部署向导可消除 Lync Server 2010 的累积更新中所需的大部分配置任务：2011年11月。</span><span class="sxs-lookup"><span data-stu-id="b982b-155">The Topology Builder and Lync Server Deployment Wizard eliminate most of the configuration tasks that were required in cumulative update for Lync Server 2010: November 2011.</span></span>

</div>

<div>

## <a name="services-for-mobile-clients"></a><span data-ttu-id="b982b-156">适用于移动客户端的服务</span><span class="sxs-lookup"><span data-stu-id="b982b-156">Services for Mobile Clients</span></span>

<span data-ttu-id="b982b-157">在 Lync Server 2010 的累积更新中引入：年 11 2011 月，Lync Server 中的移动服务2013启用使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备运行 Lync Mobile 和平板电脑设备的移动电话活动，例如发送和接收即时消息、查看联系人和查看状态。</span><span class="sxs-lookup"><span data-stu-id="b982b-157">Introduced in the cumulative update for Lync Server 2010: November 2011, mobility services in Lync Server 2013 enable mobile phones running Lync Mobile and tablet devices using supported Apple iOS, Android, Windows Phone, or Nokia mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="b982b-158">此外，移动设备支持某些企业语音功能，例如单击以加入会议、通过工作、单号码到达、语音邮件和错过的呼叫通知进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="b982b-158">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed call notification.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b982b-159">移动服务使用部署在前端服务器上的反向代理和发布的服务。</span><span class="sxs-lookup"><span data-stu-id="b982b-159">The mobility services use the reverse proxy and published services that are deployed on your Front End Servers.</span></span> <span data-ttu-id="b982b-160">不需要对边缘服务器进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="b982b-160">No changes are required to Edge Servers.</span></span> <span data-ttu-id="b982b-161">您最少需要出站 SIP/TCP/5061from 运行 Lync Server Access Edge 服务的服务器。</span><span class="sxs-lookup"><span data-stu-id="b982b-161">Minimally you need outbound SIP/TCP/5061from the server running the Lync Server Access Edge service.</span></span>



</div>

</div>

<div>

## <a name="director-role-is-optional"></a><span data-ttu-id="b982b-162">主管角色是可选的</span><span class="sxs-lookup"><span data-stu-id="b982b-162">Director Role is Optional</span></span>

<span data-ttu-id="b982b-163">Lync Server 2013 拓扑中 Director 服务器的角色未更改。</span><span class="sxs-lookup"><span data-stu-id="b982b-163">The role of the Director server in the Lync Server 2013 topology has not changed.</span></span> <span data-ttu-id="b982b-164">它仍托管 web 服务，preauthenticates 传入的用户请求，并将外部用户定向到其主池。</span><span class="sxs-lookup"><span data-stu-id="b982b-164">It still hosts web services, preauthenticates incoming user requests, and directs external users to their home pool.</span></span> <span data-ttu-id="b982b-165">通过将 Director 从推荐的角色更改为可选角色，Microsoft 不打算降低 Director 的价值。</span><span class="sxs-lookup"><span data-stu-id="b982b-165">By changing the Director from a recommended role to an optional role, Microsoft does not intend to diminish the value of the Director.</span></span> <span data-ttu-id="b982b-166">目的是减少服务器数量和其他硬件要求（例如，控制器的硬件负载平衡器），而不影响功能和功能。</span><span class="sxs-lookup"><span data-stu-id="b982b-166">The intention is to reduce server count and other hardware requirements (for example, hardware load balancers for the Director) without compromising features and functionality.</span></span> <span data-ttu-id="b982b-167">由于前端服务器可以执行与提供的服务不受影响的控制器相同的作业，因此，如果你选择，则可以部署控制器。</span><span class="sxs-lookup"><span data-stu-id="b982b-167">Because the Front End Servers can do the same job as the Director with no impact to services provided, you can deploy Directors if you choose to.</span></span> <span data-ttu-id="b982b-168">您可以放心地排除 Director，前端服务器将提供相同的服务来代替 Director。</span><span class="sxs-lookup"><span data-stu-id="b982b-168">You can safely exclude the Director with confidence that the Front End Servers will provide the same services in place of a Director.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

