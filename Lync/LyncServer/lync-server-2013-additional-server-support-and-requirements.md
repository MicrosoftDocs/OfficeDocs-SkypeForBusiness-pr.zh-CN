---
title: Lync Server 2013：其他服务器支持和要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f2d1a1b728fcec84f0aed70f00f1143c70c490
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="d3734-102">Lync Server 2013 中的其他服务器支持和要求</span><span class="sxs-lookup"><span data-stu-id="d3734-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3734-103">_**主题上次修改时间:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="d3734-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="d3734-104">除了此支持文档的其他部分中介绍的软件支持, Lync Server 2013 还具有以下支持限制:</span><span class="sxs-lookup"><span data-stu-id="d3734-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="d3734-105">Lync Server 2013 支持针对特定服务器角色的域名系统 (DNS) 和硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="d3734-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="d3734-106">它还支持中介服务器的应用程序负载平衡 (如果适用)。</span><span class="sxs-lookup"><span data-stu-id="d3734-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="d3734-107">有关何时使用的详细信息, 请参阅规划文档。</span><span class="sxs-lookup"><span data-stu-id="d3734-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="d3734-108">Lync Server 2013 使用通讯组列表扩展协议 (DLX) 展开通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d3734-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="d3734-109">此协议还指定用于获取通讯组列表成员身份的 web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="d3734-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="d3734-110">Microsoft Exchange Server 支持没有静态分配成员的动态组。</span><span class="sxs-lookup"><span data-stu-id="d3734-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="d3734-111">而是存储在展开组时评估的查询。</span><span class="sxs-lookup"><span data-stu-id="d3734-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="d3734-112">DLX 不支持动态通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="d3734-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="d3734-113">此 DLX 限制适用于所有版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="d3734-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="d3734-114">"启用用户" 向导不支持将非英语字符自动转换为 SIP 兼容的 URI, 因此必须手动修改 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="d3734-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="d3734-115">对于运行防病毒软件的服务器, 请参阅[Lync Server 2013 的防病毒扫描排除](lync-server-2013-antivirus-scanning-exclusions.md)程序, 了解建议的病毒排除和其他安全相关建议。</span><span class="sxs-lookup"><span data-stu-id="d3734-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="d3734-116">如果你使用 IPsec, 我们建议通过用于音频和视频流量的端口范围禁用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="d3734-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="d3734-117">有关详细信息, 请参阅规划文档中的[Lync Server 2013 中的 IPsec 异常](lync-server-2013-ipsec-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="d3734-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="d3734-118">如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。</span><span class="sxs-lookup"><span data-stu-id="d3734-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="d3734-119">有关实现 QoS 的详细信息, 请参阅操作文档中的[Lync Server 2013 中的 "管理服务质量 (QoS)](lync-server-2013-managing-quality-of-service-qos.md) "。</span><span class="sxs-lookup"><span data-stu-id="d3734-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="d3734-120">支持使用操作系统防火墙。</span><span class="sxs-lookup"><span data-stu-id="d3734-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="d3734-121">Lync Server 2013 管理操作系统防火墙的防火墙例外, Microsoft SQL Server 数据库软件除外。</span><span class="sxs-lookup"><span data-stu-id="d3734-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="d3734-122">有关 SQL Server 防火墙要求的详细信息, 请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="d3734-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="d3734-123">用于实现对外部用户访问的支持的外部接口必须位于单独的子网,*而不*是在与内部接口相同的网络上。</span><span class="sxs-lookup"><span data-stu-id="d3734-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="d3734-p106">Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。</span><span class="sxs-lookup"><span data-stu-id="d3734-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="d3734-126">发布 Lync Server 2013 累积更新: 年 7 2013 月, Lync Server 2013 现在支持双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="d3734-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="d3734-127">有关详细信息, 请参阅[Lync Server 2013 中的双因素身份验证](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="d3734-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="d3734-128">大多数内部服务器都需要定义为**开放身份验证**(OAuth) 的证书类型。</span><span class="sxs-lookup"><span data-stu-id="d3734-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="d3734-129">您需要在 "Lync Server 部署向导" 的 "**请求"、"安装和分配证书**" 阶段请求和分配 OAuth 证书。</span><span class="sxs-lookup"><span data-stu-id="d3734-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="d3734-130">OAuth 证书密钥的最小大小为1024位。</span><span class="sxs-lookup"><span data-stu-id="d3734-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="d3734-131">如果你请求的证书的密钥长度小于2048位的长度, 则可能会显示一条警告。</span><span class="sxs-lookup"><span data-stu-id="d3734-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="d3734-132">为了避免在强制执行密钥长度为2048而不是警告的情况下出现潜在问题, 强烈建议始终为 OAuth 证书使用密钥长度2048。</span><span class="sxs-lookup"><span data-stu-id="d3734-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="d3734-133">Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 操作支持联邦信息处理标准 (FIPS) 140-2 算法如果 Windows Server 2008 R2 操作系统配置为使用 FIPS 140-2 算法系统加密。</span><span class="sxs-lookup"><span data-stu-id="d3734-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="d3734-134">若要实现 FIPS 支持, 必须配置运行 Lync Server 2013 的每台服务器以支持它。</span><span class="sxs-lookup"><span data-stu-id="d3734-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="d3734-135">有关符合 FIPS 的算法以及如何实现 FIPS 支持的详细信息, 请参阅 Microsoft 知识库文章 811833 "系统加密: 使用 FIPS 兼容的算法在 Windows XP 和更高版本中加密、哈希和签名安全设置版本的 Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)。</span><span class="sxs-lookup"><span data-stu-id="d3734-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="d3734-136">有关 FIPS 140-2 支持和 Exchange 2010 中的限制的详细信息, 请参阅中的 "Exchange 2010 SP1 和对 FIPS [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)兼容的算法的支持"。</span><span class="sxs-lookup"><span data-stu-id="d3734-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="d3734-137">Lync Server 2013 要求在部署之前或期间安装特定组件的其他软件。</span><span class="sxs-lookup"><span data-stu-id="d3734-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="d3734-138">这包括适用于操作系统、可下载软件和在安装 Lync Server 2013 期间自动安装的软件的软件。</span><span class="sxs-lookup"><span data-stu-id="d3734-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="d3734-139">下面是可能需要的其他软件的列表:</span><span class="sxs-lookup"><span data-stu-id="d3734-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="d3734-140">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="d3734-140">Windows Update</span></span>

  - <span data-ttu-id="d3734-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d3734-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="d3734-142">Microsoft .NET 4.5 Framework</span><span class="sxs-lookup"><span data-stu-id="d3734-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="d3734-143">Microsoft Visual c + + 2012 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="d3734-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d3734-144">安装 Lync Server 2013 时, 将自动安装 Microsoft Visual c + + 2012 可再发行组件。</span><span class="sxs-lookup"><span data-stu-id="d3734-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="d3734-145">不应安装和使用任何其他版本。</span><span class="sxs-lookup"><span data-stu-id="d3734-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="d3734-146">URL 重写模块版本2.0 可再发行组件</span><span class="sxs-lookup"><span data-stu-id="d3734-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="d3734-147">Windows Media Format Runtime</span><span class="sxs-lookup"><span data-stu-id="d3734-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="d3734-148">Windows PowerShell 版本3。0</span><span class="sxs-lookup"><span data-stu-id="d3734-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="d3734-149">Microsoft Silverlight 4 浏览器插件 (Silverlight 4.0.50524.0 或 Lync Server 控制面板的最新版本)</span><span class="sxs-lookup"><span data-stu-id="d3734-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="d3734-150">Active Directory 域服务工具</span><span class="sxs-lookup"><span data-stu-id="d3734-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="d3734-151">某些软件要求仅适用于特定服务器角色或组件。</span><span class="sxs-lookup"><span data-stu-id="d3734-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="d3734-152">有关这些软件要求的详细信息, 请参阅规划文档中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3734-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

