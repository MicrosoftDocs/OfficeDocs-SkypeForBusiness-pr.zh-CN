---
title: Lync Server 2013：密钥安全功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55d59a6978b90db82ccf899df90b05c739e71a57
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="9409f-102">Lync Server 2013 中的关键安全功能</span><span class="sxs-lookup"><span data-stu-id="9409f-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9409f-103">_**主题上次修改时间：** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="9409f-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="9409f-104">Lync Server 2013 包含多种安全功能，包括服务器到服务器身份验证、基于角色的访问控制和配置数据的集中存储。</span><span class="sxs-lookup"><span data-stu-id="9409f-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="9409f-105">本文提供了 Lync Server 2013 安全级别的高级概述。</span><span class="sxs-lookup"><span data-stu-id="9409f-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="9409f-106">Lync Server 2013 中的关键安全功能</span><span class="sxs-lookup"><span data-stu-id="9409f-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="9409f-107">安全是一个非常广泛的主题。</span><span class="sxs-lookup"><span data-stu-id="9409f-107">Security is a very broad topic.</span></span> <span data-ttu-id="9409f-108">安全性在 Lync Server 2013 的每个功能以及组成 Lync 生态系统的数据库、服务和硬件之间达到。</span><span class="sxs-lookup"><span data-stu-id="9409f-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="9409f-109">本文概述了 Lync Server 2013 中的某些功能，尤其是针对安全设计的。</span><span class="sxs-lookup"><span data-stu-id="9409f-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="9409f-110">规划和设计工具</span><span class="sxs-lookup"><span data-stu-id="9409f-110">Planning and Design Tools</span></span>

<span data-ttu-id="9409f-111">Lync Server 2013 提供了两种工具来促进规划和设计，并减少 misconfiguring Lync 服务器组件的机率。</span><span class="sxs-lookup"><span data-stu-id="9409f-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="9409f-112">**拓扑规划工具**会自动执行大部分拓扑设计过程。</span><span class="sxs-lookup"><span data-stu-id="9409f-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="9409f-113">你可以将计划工具中的结果导出到拓扑生成器，这是安装运行 Lync Server 2013 的每台服务器所需的工具。</span><span class="sxs-lookup"><span data-stu-id="9409f-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="9409f-114">**拓扑生成器**在中央管理存储中存储所有配置信息。</span><span class="sxs-lookup"><span data-stu-id="9409f-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="9409f-115">有关这些工具的详细信息，请参阅[规划 Lync Server 2013](lync-server-2013-planning.md)。</span><span class="sxs-lookup"><span data-stu-id="9409f-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="9409f-116">中央管理存储</span><span class="sxs-lookup"><span data-stu-id="9409f-116">Central Management Store</span></span>

<span data-ttu-id="9409f-117">在 Lync Server 2013 中，有关服务器和服务的配置数据是中央管理存储的一部分。</span><span class="sxs-lookup"><span data-stu-id="9409f-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="9409f-118">中央管理存储为定义、设置、维护、管理、描述和操作 Lync Server 部署所需的数据提供了可靠的 schematized 存储。</span><span class="sxs-lookup"><span data-stu-id="9409f-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="9409f-119">它还会验证数据，以确保配置的一致性。</span><span class="sxs-lookup"><span data-stu-id="9409f-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="9409f-120">对此配置数据的所有更改都在中央管理存储上进行，这可以消除“不同步”问题。</span><span class="sxs-lookup"><span data-stu-id="9409f-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="9409f-p104">数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器和 Survivable Branch Appliance。复制过程由默认情况下在网络服务上下文下运行的服务进行管理，从而将权限缩减为计算机上的简单用户所拥有的权限。</span><span class="sxs-lookup"><span data-stu-id="9409f-p104">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances. Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="9409f-123">服务器到服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="9409f-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="9409f-124">在 Lync Server 2013 中，可通过使用开放授权（OAuth）协议在服务器之间配置身份验证。</span><span class="sxs-lookup"><span data-stu-id="9409f-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="9409f-125">例如，您可以将 Lync Server 2013 配置为使用运行 Exchange Server 2013 的服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9409f-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="9409f-126">通过使用 OAuth 协议，Lync 服务器和 Exchange 服务器可以相互信任。</span><span class="sxs-lookup"><span data-stu-id="9409f-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="9409f-127">这样做可实现无缝集成产品。</span><span class="sxs-lookup"><span data-stu-id="9409f-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="9409f-128">有关详细信息，请参阅[在 Lync server 2013 中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="9409f-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="9409f-129">基于 Windows PowerShell 的管理和基于 Web 的管理界面</span><span class="sxs-lookup"><span data-stu-id="9409f-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="9409f-130">Lync Server 2013 提供了一个功能强大的管理界面，该界面是基于 Windows PowerShell 命令行界面构建的。</span><span class="sxs-lookup"><span data-stu-id="9409f-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="9409f-131">其中包含用于管理安全性的 cmdlet，并且默认情况下会启用 Windows PowerShell 安全功能，以防止用户轻易或无意中运行脚本。</span><span class="sxs-lookup"><span data-stu-id="9409f-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="9409f-132">这意味着软件默认设置为自动帮助实现最大安全性并减少攻击事件。</span><span class="sxs-lookup"><span data-stu-id="9409f-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="9409f-133">有关 Lync Server 2013 中的 Windows PowerShell 管理支持的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序。</span><span class="sxs-lookup"><span data-stu-id="9409f-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="9409f-134">基于角色的访问控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="9409f-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="9409f-135">Microsoft Lync Server 2013 提供基于角色的访问控制（RBAC），使你能够委派管理任务，同时保持高标准的安全。</span><span class="sxs-lookup"><span data-stu-id="9409f-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="9409f-136">可以使用 RBAC 来遵守“最小特权”原则，按照该原则，用户只能获得其工作所需的管理权限。</span><span class="sxs-lookup"><span data-stu-id="9409f-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="9409f-137">Lync Server 2013 引入了创建新角色的功能，还提供了修改现有角色的功能。</span><span class="sxs-lookup"><span data-stu-id="9409f-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="9409f-138">有关详细信息，请参阅[在 Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9409f-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="9409f-139">网络地址转换 (NAT)</span><span class="sxs-lookup"><span data-stu-id="9409f-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="9409f-140">Lync Server 2013 不支持在边缘服务器的内部接口上使用网络地址转换（NAT），但它支持将访问边缘服务的外部接口、Web 会议边缘服务和 A/V 边缘服务置于为单个和缩放的合并边缘服务器拓扑执行网络地址转换（NAT）的路由器或防火墙后面。</span><span class="sxs-lookup"><span data-stu-id="9409f-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="9409f-141">硬件负载平衡器后的多台边缘服务器不能使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="9409f-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="9409f-142">如果多台边缘服务器在其外部接口上使用 NAT，将需要域名系统 (DNS) 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="9409f-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="9409f-143">反之，使用 DNS 负载平衡让你可以减少边缘服务器池中每台边缘服务器的公共 IP 地址的数量。</span><span class="sxs-lookup"><span data-stu-id="9409f-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="9409f-144">有关详细信息，请参阅[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="9409f-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9409f-145">如果你与拥有 Microsoft Office Communications Server 2007 部署的企业联盟，且需要在你的企业与联盟企业之间使用音频/视频，则端口要求就是对已部署的边缘服务器的早期版本的端口要求。</span><span class="sxs-lookup"><span data-stu-id="9409f-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="9409f-146">例如，必须为两个企业打开这些旧版本所需的端口范围，直到联盟伙伴将其 Edge 服务器升级到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9409f-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="9409f-147">此时，可以根据新配置检查并减少端口要求。</span><span class="sxs-lookup"><span data-stu-id="9409f-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="9409f-148">边缘服务器的简化证书</span><span class="sxs-lookup"><span data-stu-id="9409f-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="9409f-149">部署向导可以自动填充使用者名称 (SN) 和使用者替代名称 (SAN)，从而减少包含不必要的和可能不安全的条目的可能性。</span><span class="sxs-lookup"><span data-stu-id="9409f-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="9409f-150">可信赖计算安全开发周期 (SDL)</span><span class="sxs-lookup"><span data-stu-id="9409f-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="9409f-151">Lync Server 2013 的设计和开发符合 Microsoft 高可信计算安全开发生命周期（SDL），其介绍如下<http://go.microsoft.com/fwlink/?linkid=68761>。</span><span class="sxs-lookup"><span data-stu-id="9409f-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="9409f-152">**由设计**   获得信任在创建更安全的统一通信系统中的第一步是设计威胁模型，并测试每个功能的设计方式。</span><span class="sxs-lookup"><span data-stu-id="9409f-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="9409f-153">Microsoft 会对超出设计范围的行为进行测试，以便查找由于非预期产品行为引起的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="9409f-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="9409f-154">编码过程和做法中植入了多项与安全相关的改进。</span><span class="sxs-lookup"><span data-stu-id="9409f-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="9409f-155">生成时工具会在将代码签入到最终产品之前检测缓冲区溢出和其他潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="9409f-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="9409f-156">当然，在设计上不可能做到能够防范所有未知安全威胁。</span><span class="sxs-lookup"><span data-stu-id="9409f-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="9409f-157">任何系统都无法保证绝对的安全。</span><span class="sxs-lookup"><span data-stu-id="9409f-157">No system can guarantee complete security.</span></span> <span data-ttu-id="9409f-158">但是，由于产品开发采纳了来自开始的安全设计原则，因此 Lync Server 2013 将业界标准安全技术合并为其体系结构的一个基本部分。</span><span class="sxs-lookup"><span data-stu-id="9409f-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="9409f-159">**默认**   情况下受信任默认情况下，Lync Server 2013 中的网络通信已加密。</span><span class="sxs-lookup"><span data-stu-id="9409f-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="9409f-160">由于所有服务器使用证书和 Kerberos 身份验证、TLS、安全实时传输协议（SRTP）和其他业界标准的加密技术（包括128位高级加密标准（AES）加密），因此几乎所有 Lync服务器数据在网络上受到保护。</span><span class="sxs-lookup"><span data-stu-id="9409f-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="9409f-161">此外，基于角色的访问控制使你可以部署运行 Lync Server 2013 的服务器，以便每个服务器角色仅运行服务，并且仅具有与这些服务相关的权限，这些权限适用于服务器角色。</span><span class="sxs-lookup"><span data-stu-id="9409f-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="9409f-162">**通过部署**   获得信任所有 Lync Server 2013 文档包括最佳做法和建议，可帮助你确定和配置你的部署的最佳安全级别，并评估激活非默认选项的安全风险。</span><span class="sxs-lookup"><span data-stu-id="9409f-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

