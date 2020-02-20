---
title: Lync Server 2013：为自动发现服务创建 DNS 记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe908ac48bb71beea731c742665a979d9f96182f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="9ec05-102">在 Lync Server 2013 中为自动发现服务创建 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="9ec05-102">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ec05-103">_**上次修改的主题：** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="9ec05-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="9ec05-104">你的 Lync Mobile 用户将需要启用自动发现，并且其中的一部分涉及创建一些域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-104">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="9ec05-105">根据您的需要，您需要具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="9ec05-105">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="9ec05-106">支持从组织网络内部进行连接的移动用户的内部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-106">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="9ec05-107">支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="9ec05-107">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="9ec05-108">为什么？</span><span class="sxs-lookup"><span data-stu-id="9ec05-108">Why both?</span></span> <span data-ttu-id="9ec05-109">您需要为每个 SIP 域创建一个内部 DNS 记录和一个外部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-109">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="9ec05-110">您创建的 DNS 记录可以是（主机）记录或 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-110">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="9ec05-111">为了帮助你，我们将逐步介绍如何在下面创建这些内部和外部 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-111">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="9ec05-112">如果你需要进一步阅读有关移动用户的 DNS 要求的详细信息，可以[在 Lync Server 2013 中查看移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="9ec05-112">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="9ec05-113">创建内部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="9ec05-113">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="9ec05-114">若要创建内部 DNS 记录，您需要使用作为 Domain Admins 组成员的域帐户或 DnsAdmins 组的成员登录到网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="9ec05-114">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="9ec05-115">打开 DNS 管理单元：依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\* 和“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="9ec05-116">在 DNS 服务器的控制台树中，展开要在其中安装 Lync Server 2013 控制器池和前端池的 Active Directory 域的**正向查找区域**。</span><span class="sxs-lookup"><span data-stu-id="9ec05-116">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="9ec05-117">（例如，contoso. 本地）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-117">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="9ec05-118">检查并查看是否存在适用于您的控制器池的主机 A （适用于 IPv6 的 AAAA）记录。对于您的控制器池的内部 Web 服务完全限定的域名（FQDN）（例如，lyncwebdir01），应存在主机 a 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-118">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="9ec05-119">如果不是这样，则您可能未使用控制器池，如果是你的设置，你将需要使用前端池的 FQDN，甚至是单个服务器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9ec05-119">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="9ec05-120">请注意，请查看并查看是否存在用于内部 DNS 记录的主机 A （适用于 IPv6 的 AAAA）记录，对于内部 DNS 记录，应存在主机 A （或 AAAA）记录，以便为前端池的内部 Web 服务 FQDN （例如（lyncwebpool01）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-120">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="9ec05-121">如果不是，则需要记下前端服务器或 Standard Edition Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9ec05-121">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="9ec05-122">知道存在哪个主机 A （或 AAAA）记录后，在 DNS 服务器的控制台树中，展开您的 SIP 域的**正向查找区域**（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-122">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="9ec05-123">右键单击 SIP 域名，然后单击“新建别名(CNAME)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-123">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="9ec05-124">在 "**别名名称**" 中，键入 lyncdiscoverinternal. 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="9ec05-124">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="9ec05-125">在 "**目标主机的完全限定域名（FQDN）**" 中，键入或浏览到您的控制器池的内部 WEB 服务 FQDN （例如，lyncwebdir01），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="9ec05-125">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="9ec05-126">您必须在您在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-126">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="9ec05-127">创建外部 DNS CNAME 记录</span><span class="sxs-lookup"><span data-stu-id="9ec05-127">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="9ec05-128">若要创建外部 DNS CNAME 记录，您需要连接到您的公共 DNS 提供商，然后执行我们的步骤。</span><span class="sxs-lookup"><span data-stu-id="9ec05-128">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="9ec05-129">我们无法确切描述你在 DNS 提供程序环境中所处的位置，因为可能有不同的管理外部 DNS 的方法，但我们希望这些步骤帮助。</span><span class="sxs-lookup"><span data-stu-id="9ec05-129">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="9ec05-130">使用可在该环境中创建 DNS 记录的帐户登录外部 DNS 提供程序。</span><span class="sxs-lookup"><span data-stu-id="9ec05-130">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="9ec05-131">您应该已为此环境创建了一个 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="9ec05-131">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="9ec05-132">展开此 SIP 域的**正向查找区域**，或者根据所使用的外部 DNS 接口来选择此区域。</span><span class="sxs-lookup"><span data-stu-id="9ec05-132">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="9ec05-133">您应该已经看到控制器池（如 lyncwebexdir01.contoso.com）的主机 A （适用于 IPv6 的 AAAA）记录，因此请确认是否存在。</span><span class="sxs-lookup"><span data-stu-id="9ec05-133">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="9ec05-134">如果不是，则您可能未使用控制器池。</span><span class="sxs-lookup"><span data-stu-id="9ec05-134">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="9ec05-135">如果是这种情况，您需要使用前端池的 FQDN，或者如果您为前端服务器或 Standard Edition server 执行此操作，则需要使用前端池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9ec05-135">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="9ec05-136">您还需要确认您的外部 Web 服务完全限定的域名（FQDN）的主机 A （适用于 IPv6 的 AAAA）记录对于您的前端池（如 lyncwebextpool01.contoso.com），或者如果没有前端池，则为您的单服务器 FQDN 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9ec05-136">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="9ec05-137">如前面的步骤中所述，如果没有控制器池，将需要下面的步骤。</span><span class="sxs-lookup"><span data-stu-id="9ec05-137">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="9ec05-138">现在，按照适用于外部 DNS 提供程序的格式，选择用于创建**新别名（CNAME）** 的选项（可能是菜单选项或链接，具体取决于 DNS 提供程序的格式）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-138">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="9ec05-139">应使用与内部 DNS 相同的 "**别名形式名称**" 文本框，应输入 lyncdiscover. 作为外部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="9ec05-139">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="9ec05-140">"目标主机" 文本框的**完全限定域名（FQDN）** 的形式也应该如下所示，您可以在此处输入控制器池的外部 WEB 服务 FQDN （例如，lyncwebexdir01.contoso.com），然后单击 "确定" 或执行外部 DNS 中的任何操作以接受此条目的创建。</span><span class="sxs-lookup"><span data-stu-id="9ec05-140">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="9ec05-141">如上面的步骤4中所述，如果没有控制器池，则需要使用前端池 FQDN 或已设置的单服务器 FQDN （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-141">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="9ec05-142">你需要在你的 Lync 2013 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-142">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="9ec05-143">创建内部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="9ec05-143">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="9ec05-144">若要创建内部 DNS 记录，请使用作为 Domain Admins 组成员的域帐户或 DnsAdmins 组的成员登录到网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="9ec05-144">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="9ec05-145">打开 DNS 管理单元：依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\* 和“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-145">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="9ec05-146">对于内部 DNS 记录，在 DNS 服务器的控制台树中，展开你的 Active Directory 域的**正向查找区域**（例如，contoso. local），其中安装了 Lync Server 2013 控制器池和前端池。</span><span class="sxs-lookup"><span data-stu-id="9ec05-146">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="9ec05-147">检查并查看是否存在适用于您的控制器池的主机 A （适用于 IPv6 的 AAAA）记录。对于您的控制器池的内部 Web 服务完全限定的域名（FQDN）（例如，lyncwebdir01），应存在主机 a 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-147">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="9ec05-148">如果不是这样，则您可能未使用控制器池，您需要使用您的前端池的 IP 地址，甚至是单个服务器 IP 地址（如果您设置了这样的话）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-148">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="9ec05-149">请注意，请查看并查看是否存在用于内部 DNS 记录的主机 A （适用于 IPv6 的 AAAA）记录，对于内部 DNS 记录，应存在主机 A （或 AAAA）记录，以便为前端池的内部 Web 服务 FQDN （例如（lyncwebpool01）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-149">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="9ec05-150">如果不是，则需要记下前端服务器或 Standard Edition Server 的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9ec05-150">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="9ec05-151">知道存在哪个主机 A （或 AAAA）记录后，在 DNS 服务器的控制台树中，展开您的 SIP 域的**正向查找区域**（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-151">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="9ec05-152">右键单击 SIP 域名，然后单击“新建主机(A 或 AAAA)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-152">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="9ec05-153">在 "**名称**" 中，键入 lyncdiscoverinternal. 作为内部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="9ec05-153">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="9ec05-154">在 " **IP 地址**" 中，键入控制器的内部 WEB 服务 IP 地址（或者，如果使用负载平衡器，请键入控制器负载平衡器的虚拟 IP （VIP））。</span><span class="sxs-lookup"><span data-stu-id="9ec05-154">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="9ec05-155">如上面的步骤4中所述，如果没有使用控制器，则可能需要输入前端服务器或 Standard Edition 服务器的 IP 地址，或者，如果使用负载平衡器，请键入前端池负载平衡器的 VIP。</span><span class="sxs-lookup"><span data-stu-id="9ec05-155">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="9ec05-156">单击“添加主机”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-156">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="9ec05-157">若要创建另一个或 AAAA 记录，请重复步骤8至10，记住，你需要在你的 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-157">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="9ec05-158">创建完 A 记录（对于 IPv6 为 AAAA）后，请单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-158">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="9ec05-159">创建外部 DNS A 记录</span><span class="sxs-lookup"><span data-stu-id="9ec05-159">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="9ec05-160">若要创建外部 DNS 记录，请连接到您的公共 DNS 提供商，然后按照我们的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="9ec05-160">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="9ec05-161">我们无法确切描述你在 DNS 提供程序环境中所处的位置，因为可能有不同的管理外部 DNS 的方法，但我们希望这些步骤帮助。</span><span class="sxs-lookup"><span data-stu-id="9ec05-161">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="9ec05-162">您需要以可在该环境中创建 DNS 记录的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-162">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="9ec05-163">对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-163">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="9ec05-164">对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9ec05-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="9ec05-165">您应该已经看到控制器池的主机 A （适用于 IPv6 的 AAAA）记录（如 lyncwebexdir01.contoso.com），因此请确认它在那里以及 IP 地址是什么。</span><span class="sxs-lookup"><span data-stu-id="9ec05-165">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="9ec05-166">如果不是，则您可能未使用控制器池。</span><span class="sxs-lookup"><span data-stu-id="9ec05-166">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="9ec05-167">如果是这种情况，您需要使用前端池的 IP 地址，或者如果您为前端服务器或 Standard Edition server 执行此操作，则需要使用前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="9ec05-167">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="9ec05-168">请注意，您的服务器也可能位于负载平衡器后面，或使用反向代理。</span><span class="sxs-lookup"><span data-stu-id="9ec05-168">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="9ec05-169">请记下 IP 地址，并按以下步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="9ec05-169">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="9ec05-170">您还需要确认对于您的外部 Web 服务完全限定的域名（FQDN），您的外部 Web 服务的主机 A （AAAA for IPv6）记录是否存在（如 lyncwebextpool01.contoso.com），或者您的单服务器 Lync 安装的 IP 地址（如果您没有前端池。</span><span class="sxs-lookup"><span data-stu-id="9ec05-170">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="9ec05-171">如前面的步骤中所述，如果没有控制器池，将需要下面的步骤。</span><span class="sxs-lookup"><span data-stu-id="9ec05-171">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="9ec05-172">现在，按照适用于外部 DNS 提供程序的格式，选择用于创建**新主机 a 或 AAAA**的选项（可能是菜单选项或链接，具体取决于 DNS 提供程序的格式）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-172">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="9ec05-173">应存在一个输入**名称**的位置，键入 lyncdiscover. 作为外部自动发现服务 URL 的主机名。</span><span class="sxs-lookup"><span data-stu-id="9ec05-173">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="9ec05-174">此外，还应提供**Ip 地址**文本框，此处是为您的控制器池（例如，lyncwebexdir01.contoso.com）输入 ip，还是可能为您的池的负载平衡器（或潜在的反向代理 ip）输入 ip，然后单击 "确定" 或执行外部 DNS 中的任何操作以接受此项的创建。</span><span class="sxs-lookup"><span data-stu-id="9ec05-174">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="9ec05-175">如上面的步骤4所述，如果没有控制器池，则需要使用前端池 IP 地址或已设置的单服务器 IP 地址（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="9ec05-175">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="9ec05-176">你需要在你的 Lync 2013 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。</span><span class="sxs-lookup"><span data-stu-id="9ec05-176">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

