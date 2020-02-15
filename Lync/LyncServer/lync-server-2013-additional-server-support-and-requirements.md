---
title: Lync Server 2013：其他服务器支持和要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8eb02f0cf178807c656520787024d79ab0f09b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="c51be-102">Lync Server 2013 中的其他服务器支持和要求</span><span class="sxs-lookup"><span data-stu-id="c51be-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c51be-103">_**上次修改的主题：** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="c51be-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="c51be-104">除了此可支持性文档的其他部分中所述的软件支持外，Lync Server 2013 还提供了以下支持限制：</span><span class="sxs-lookup"><span data-stu-id="c51be-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="c51be-105">Lync Server 2013 支持针对特定服务器角色的域名系统（DNS）和硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="c51be-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="c51be-106">根据需要，还可针对中介服务器支持应用程序负载平衡。</span><span class="sxs-lookup"><span data-stu-id="c51be-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="c51be-107">有关何时使用每种支持的详细信息，请参阅规划文档。</span><span class="sxs-lookup"><span data-stu-id="c51be-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="c51be-108">Lync Server 2013 使用通讯组列表展开协议（DLX）展开通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c51be-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="c51be-109">此协议还指定了用于获取通讯组列表成员身份的 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="c51be-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="c51be-110">Microsoft Exchange Server 不支持静态分配有成员的动态组。</span><span class="sxs-lookup"><span data-stu-id="c51be-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="c51be-111">而将存储扩展组时评估的查询。</span><span class="sxs-lookup"><span data-stu-id="c51be-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="c51be-112">DLX 不支持动态通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="c51be-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="c51be-113">此 DLX 限制适用于所有版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="c51be-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="c51be-114">“启用用户向导”不支持将非英文字符自动转换为符合 SIP 的 URI，因此必须手动修改 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="c51be-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="c51be-115">对于运行防病毒软件的服务器，请参阅[Lync Server 2013 的防病毒扫描排除](lync-server-2013-antivirus-scanning-exclusions.md)项，了解建议的病毒排除和其他安全相关建议。</span><span class="sxs-lookup"><span data-stu-id="c51be-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="c51be-116">如果使用 IPsec，建议在用于音频和视频流量的端口范围内禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="c51be-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="c51be-117">有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="c51be-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="c51be-118">如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。</span><span class="sxs-lookup"><span data-stu-id="c51be-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="c51be-119">有关实施 QoS 的详细信息，请参阅操作文档中的在[Lync Server 2013 中管理服务质量（QoS）](lync-server-2013-managing-quality-of-service-qos.md) 。</span><span class="sxs-lookup"><span data-stu-id="c51be-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="c51be-120">支持使用操作系统防火墙。</span><span class="sxs-lookup"><span data-stu-id="c51be-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="c51be-121">Lync Server 2013 管理操作系统防火墙的防火墙例外（Microsoft SQL Server 数据库软件除外）。</span><span class="sxs-lookup"><span data-stu-id="c51be-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="c51be-122">有关 SQL Server 防火墙要求的详细信息，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="c51be-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="c51be-123">用于实现外部用户访问支持的外部接口必须在单独的子网中，而\*\* 不能与内部接口位于相同的网络中。</span><span class="sxs-lookup"><span data-stu-id="c51be-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="c51be-124">Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。</span><span class="sxs-lookup"><span data-stu-id="c51be-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="c51be-125">对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="c51be-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="c51be-126">发布 Lync Server 2013 累积更新：6月2013，Lync Server 2013 现在支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c51be-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="c51be-127">有关详细信息，请参阅[Lync Server 2013 中的双重身份验证](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="c51be-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="c51be-128">大多数内部服务器都需要定义为**开放身份验证**（OAuth）的证书类型。</span><span class="sxs-lookup"><span data-stu-id="c51be-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="c51be-129">您需要在 Lync Server 部署向导的 "**请求中安装和分配证书**" 阶段请求和分配 OAuth 证书。</span><span class="sxs-lookup"><span data-stu-id="c51be-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="c51be-130">OAuth 证书密钥的最小大小为1024位。</span><span class="sxs-lookup"><span data-stu-id="c51be-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="c51be-131">如果请求密钥长度小于2048位的证书，则会显示一条警告。</span><span class="sxs-lookup"><span data-stu-id="c51be-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="c51be-132">为了避免在强制实施密钥长度为2048而不是警告的情况下出现潜在问题，强烈建议始终为 OAuth 证书使用密钥长度2048。</span><span class="sxs-lookup"><span data-stu-id="c51be-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="c51be-133">如果 Windows Server 2008 R2 操作系统配置为使用 FIPS 140-2 算法，则 Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 （SP1）操作支持联邦信息处理标准（FIPS）140-2 算法系统加密。</span><span class="sxs-lookup"><span data-stu-id="c51be-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="c51be-134">若要实现 FIPS 支持，必须将运行 Lync Server 2013 的每台服务器配置为支持它。</span><span class="sxs-lookup"><span data-stu-id="c51be-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="c51be-135">有关与 FIPS 兼容的算法以及如何实施 FIPS 支持的详细信息，请参阅 Microsoft 知识库文章 811833 "系统加密：将 FIPS 兼容的算法用于加密、哈希和签名安全设置在 Windows XP 和更高版本的 Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)中。</span><span class="sxs-lookup"><span data-stu-id="c51be-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="c51be-136">有关 Exchange 2010 中的 FIPS 140-2 支持和限制的详细信息，请参阅中的 "Exchange 2010 SP1 和支持 FIPS [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)兼容的算法"。</span><span class="sxs-lookup"><span data-stu-id="c51be-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="c51be-137">在部署之前或部署过程中，Lync Server 2013 要求在特定组件上安装其他软件。</span><span class="sxs-lookup"><span data-stu-id="c51be-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="c51be-138">这包括可在安装 Lync Server 2013 期间自动安装的操作系统、可下载软件和软件中使用的软件。</span><span class="sxs-lookup"><span data-stu-id="c51be-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="c51be-139">下面列出了可能需要的其他软件：</span><span class="sxs-lookup"><span data-stu-id="c51be-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="c51be-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="c51be-140">Windows Update</span></span>

  - <span data-ttu-id="c51be-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="c51be-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="c51be-142">Microsoft .NET 4.5 Framework</span><span class="sxs-lookup"><span data-stu-id="c51be-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="c51be-143">Microsoft Visual c + + 2012 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="c51be-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c51be-144">当您安装 Lync Server 2013 时，将自动安装 Microsoft Visual c + + 2012 可再发行组件。</span><span class="sxs-lookup"><span data-stu-id="c51be-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="c51be-145">您不应安装和使用任何其他版本。</span><span class="sxs-lookup"><span data-stu-id="c51be-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="c51be-146">URL Rewrite Module 2.0 版可再发行软件包</span><span class="sxs-lookup"><span data-stu-id="c51be-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="c51be-147">Windows Media Format Runtime</span><span class="sxs-lookup"><span data-stu-id="c51be-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="c51be-148">Windows PowerShell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="c51be-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="c51be-149">Microsoft Silverlight 4 浏览器插件（对于 Lync Server 控制面板，Silverlight 4.0.50524.0 或更新版本）</span><span class="sxs-lookup"><span data-stu-id="c51be-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="c51be-150">Active Directory 域服务工具</span><span class="sxs-lookup"><span data-stu-id="c51be-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="c51be-151">其中一些软件要求仅适用于特定服务器角色或组件。</span><span class="sxs-lookup"><span data-stu-id="c51be-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="c51be-152">有关这些软件要求的详细信息，请参阅规划文档中的[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c51be-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

