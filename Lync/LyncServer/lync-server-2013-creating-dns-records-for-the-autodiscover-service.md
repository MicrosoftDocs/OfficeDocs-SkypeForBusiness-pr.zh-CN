---
title: Lync Server 2013：为自动发现服务创建 DNS 记录
description: Lync Server 2013：为自动发现服务创建 DNS 记录。
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
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563098"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>在 Lync Server 2013 中为自动发现服务创建 DNS 记录

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-20_

你的 Lync Mobile 用户将需要启用自动发现，并且其中的一部分涉及到创建一些域名系统 (DNS) 记录。 根据您的需要，您需要具备以下条件：

  - 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。

  - 支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录

为什么？ 您需要为每个 SIP 域创建一个内部 DNS 记录和一个外部 DNS 记录。

您创建的 DNS 记录可以是 (主机) 记录或 CNAME 记录。 为了帮助你，我们将逐步介绍如何在下面创建这些内部和外部 DNS 记录。 如果你需要进一步阅读有关移动用户的 DNS 要求的详细信息，可以 [在 Lync Server 2013 中查看移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

<div>

## <a name="creating-an-internal-dns-cname-record"></a>创建内部 DNS CNAME 记录

1.  若要创建内部 DNS 记录，您需要使用作为 Domain Admins 组成员的域帐户或 DnsAdmins 组的成员登录到网络中的 DNS 服务器。

2.  打开 DNS 管理单元：依次单击“开始”****、“管理工具”**** 和“DNS”****。

3.  在 DNS 服务器的控制台树中，展开要在其中安装 Lync Server 2013 控制器池和前端池的 Active Directory 域的 **正向查找区域** 。  (例如，contoso. local) 。

4.  检查并查看是否存在针对内部 DNS 记录的控制器池的主机 A (AAAA) 记录，对于您的控制器池，主机 A 记录是否应存在对于您的控制器池的内部 Web 服务完全限定的域名 (FQDN)  (例如，lyncwebdir01) 。 如果不是这样，则您可能未使用控制器池，如果是你的设置，你将需要使用前端池的 FQDN，甚至是单个服务器 FQDN。

5.  请注意，请查看并查看主机 A (AAAA for IPv6) 记录是否存在用于内部 DNS 记录的前端池，主机 A (或 AAAA) 记录应存在于前端池的内部 Web 服务 FQDN (例如，lyncwebpool01) 。 如果不是，则需要记下前端服务器或 Standard Edition Server 的 FQDN。

6.  知道存在 (或 AAAA) 记录的主机后，在 DNS 服务器的控制台树中，展开您的 SIP 域的 **正向查找区域** (例如，contoso.com) 。

7.  右键单击 SIP 域名，然后单击“新建别名(CNAME)”****。

8.  在 " **别名名称**" 中，键入 lyncdiscoverinternal. 作为内部自动发现服务 URL 的主机名。

9.  在 " **完全限定域名" ("FQDN) 目标主机**" 中，键入或浏览到您的控制器池的内部 WEB 服务 FQDN (例如，lyncwebdir01) ，然后单击 **"确定"**。

10. 您必须在您在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>创建外部 DNS CNAME 记录

1.  若要创建外部 DNS CNAME 记录，您需要连接到您的公共 DNS 提供商，然后执行我们的步骤。 我们无法确切描述你在 DNS 提供程序环境中所处的位置，因为可能有不同的管理外部 DNS 的方法，但我们希望这些步骤帮助。

2.  使用可在该环境中创建 DNS 记录的帐户登录外部 DNS 提供程序。

3.  您应该已为此环境创建了一个 SIP 域。 展开此 SIP 域的 **正向查找区域** ，或者根据所使用的外部 DNS 接口来选择此区域。

4.  您应该已经看到主机 A (AAAA for) 控制器池的 IPv6 记录 (如 lyncwebexdir01.contoso.com) ，因此请确认存在这种情况。 如果不是，则您可能未使用控制器池。 如果是这种情况，您需要使用前端池的 FQDN，或者如果您对 Front-End server 或 Standard Edition server 执行此操作，则需要使用前端池的 FQDN。

5.  您还需要确认对于您的外部 Web 服务完全限定的域名 (FQDN) 的主机 A (AAAA) 记录是否存在，如 lyncwebextpool01.contoso.com (或单个服务器 FQDN 的 FQDN （如果没有前端池）。 如前面的步骤中所述，如果没有控制器池，将需要下面的步骤。

6.  现在，根据外部 DNS 提供程序的相应格式，选择用于创建 **新别名 (CNAME) ** 的选项 (此项可能是菜单选项或链接，具体取决于 DNS 提供程序) 的格式。

7.  应使用与内部 DNS 相同的 " **别名形式名称** " 文本框，应输入 lyncdiscover. 作为外部自动发现服务 URL 的主机名。

8.  此外，还应该有某种形式的 **完全限定的域名 (FQDN) 目标主机** "文本框中，您将在此处输入您的控制器池的外部 WEB 服务 FQDN (例如，lyncwebexdir01.contoso.com) 然后单击" 确定 "或" 执行外部 DNS 中的任何操作 "以接受此项的创建。 如上面的步骤4中所述，如果没有控制器池，则需要使用前端池 FQDN 或已设置的单服务器 FQDN （如果适用）。

9.  你需要在你的 Lync 2013 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 CNAME 记录。

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>创建内部 DNS A 记录

1.  若要创建内部 DNS 记录，请使用作为 Domain Admins 组成员的域帐户或 DnsAdmins 组的成员登录到网络中的 DNS 服务器。

2.  打开 DNS 管理单元：依次单击“开始”****、“管理工具”**** 和“DNS”****。

3.  对于内部 DNS 记录，在 DNS 服务器的控制台树中，展开 Active Directory 域的 **正向查找区域** (例如，contoso. local) 其中安装了 Lync Server 2013 控制器池和前端池。

4.  检查并查看是否存在针对内部 DNS 记录的控制器池的主机 A (AAAA) 记录，对于您的控制器池，主机 A 记录是否应存在对于您的控制器池的内部 Web 服务完全限定的域名 (FQDN)  (例如，lyncwebdir01) 。 如果不是这样，则您可能未使用控制器池，您需要使用您的前端池的 IP 地址，甚至是单个服务器 IP 地址（如果您设置了这样的话）。

5.  请注意，请查看并查看主机 A (AAAA for IPv6) 记录是否存在用于内部 DNS 记录的前端池，主机 A (或 AAAA) 记录应存在于前端池的内部 Web 服务 FQDN (例如，lyncwebpool01) 。 如果不是，则需要记下前端服务器或 Standard Edition Server 的 IP 地址。

6.  知道存在 (或 AAAA) 记录的主机后，在 DNS 服务器的控制台树中，展开您的 SIP 域的 **正向查找区域** (例如，contoso.com) 。

7.  右键单击 SIP 域名，然后单击“新建主机(A 或 AAAA)”****。

8.  在 " **名称**" 中，键入 lyncdiscoverinternal. 作为内部自动发现服务 URL 的主机名。

9.  在 " **IP 地址**" 中，键入控制器 (的内部 WEB 服务 IP 地址，或者，如果使用负载平衡器，请键入控制器负载平衡器) 的虚拟 IP (VIP) 。 如上面的步骤4中所述，如果没有使用控制器，则可能需要输入前端服务器或 Standard Edition 服务器的 IP 地址，或者，如果使用负载平衡器，请键入前端池负载平衡器的 VIP。

10. 单击“添加主机”****，然后单击“确定”****。

11. 若要创建另一个或 AAAA 记录，请重复步骤8至10，记住，你需要在你的 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。

12. 创建完 A 记录（对于 IPv6 为 AAAA）后，请单击“完成”****。

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>创建外部 DNS A 记录

1.  若要创建外部 DNS 记录，请连接到您的公共 DNS 提供商，然后按照我们的步骤进行操作。 我们无法确切描述你在 DNS 提供程序环境中所处的位置，因为可能有不同的管理外部 DNS 的方法，但我们希望这些步骤帮助。

2.  您需要以可在该环境中创建 DNS 记录的帐户身份登录。

3.  对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”****。 对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”****。

4.  您应该已经看到主机 A (AAAA for the 控制器池的 IPv6) 记录 (如 lyncwebexdir01.contoso.com) ，因此请确认是否存在以及 IP 地址是什么。 如果不是，则您可能未使用控制器池。 如果是这种情况，您需要使用前端池的 IP 地址，或者如果您对 Front-End server 或 Standard Edition server 执行此操作，则需要使用前端池的 IP 地址。 请注意，您的服务器也可能位于负载平衡器后面，或使用反向代理。 请记下 IP 地址，并按以下步骤进行操作。

5.  您还需要确认对于您的外部 Web 服务完全限定的域名 (FQDN) 的主机 A (AAAA) 记录是否存在，如 lyncwebextpool01.contoso.com (或您的单服务器 Lync 安装的 IP 地址（如果没有前端池）。 如前面的步骤中所述，如果没有控制器池，将需要下面的步骤。

6.  现在，按照适用于外部 DNS 提供程序的格式，选择用于创建 **新主机 a 或 AAAA** (的选项。这可能是一个菜单选项或一个链接，具体取决于 DNS 提供程序) 的格式。

7.  应存在一个输入 **名称**的位置，键入 lyncdiscover. 作为外部自动发现服务 URL 的主机名。

8.  此外，还应提供 **Ip 地址** 文本框。例如，您可以在此处为您的控制器池输入 ip (例如，lyncwebexdir01.contoso.com) 或可能是池的负载平衡器的 ip (或指向相同) 的反向代理 ip，然后单击 "确定" 或执行外部 DNS 中的任何操作以接受此项的创建。 如上面的步骤4所述，如果没有控制器池，则需要使用前端池 IP 地址或已设置的单服务器 IP 地址（如果适用）。

9.  你需要在你的 Lync 2013 环境支持的每个 SIP 域的正向查找区域中创建新的自动发现 A 或 AAAA 记录。

</div>

</div>

<span> </span>

</div>

</div>

</div>

