---
title: Lync Server 2013：自动发现服务要求
description: Lync Server 2013：自动发现服务要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61e963bc9e921cc0a571f63d4be50f09d237c2dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572988"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Lync Server 2013 的自动发现服务要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

Microsoft Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在 DNS 中发布后，运行 Lync Mobile 的移动设备可以使用这些服务来查找移动服务。 在运行 Lync Mobile 的移动设备可以充分利用自动发现的准备工作之前，需要在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。 此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。

有关控制器、前端服务器和反向代理所需的主题替代名称条目的详细信息，请参阅规划移动性的 [Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md) 。

有关在反向代理上利用使用者替代名称列表的决定基于您是在端口 80 还是端口 443 上发布自动发现服务：

  - **已在端口 80**     上发布如果对自动发现服务的初始查询在端口80上发生，则不需要进行证书更改。 这是因为运行 Lync 的移动设备将在外部端口80上访问反向代理，然后在内部将其重定向到端口8080上的控制器或前端服务器。 有关详细信息，请参阅本主题中后面的“使用端口 80 的初始自动发现过程”一节。

  - **已在端口 443**     上发布外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含*lyncdiscover. \<sipdomain\> 。* 组织中每个 SIP 域的条目。

使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但对于 Web 服务发布规则所使用的公共证书，添加多个使用者替代名称条目的成本会很高。 若要解决此问题，我们支持通过端口80的初始自动发现连接，该连接随后将被重定向到控制器或前端服务器上的端口8080。

例如，假设运行 Lync Mobile 的移动客户端配置为使用用于初始请求的 HTTP 的自动发现功能，登录到 Lync Server 2013。

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>使用端口80的移动设备的初始自动发现过程

1.  运行 Lync Mobile 的移动设备使用 DNS 查找 lyncdiscover.contoso.com，其中存在 A 记录。

2.  外部 DNS 将外部 web 服务的 IP 地址返回给客户端。

3.  运行 Lync Mobile 的移动设备 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com 向反向代理发送请求

4.  Web 发布规则将端口80的请求从外部桥接到端口8080，然后将其路由到控制器或前端服务器。
    
    由于该请求是 HTTP 而非 HTTPS，因此，无需对外部 Web 服务发布规则上的证书进行任何修改即可支持自动发现服务。

5.  自动发现服务会返回外部 Web 服务 URL（采用 HTTPS 格式）。

6.  运行 Lync Mobile 的移动设备可以重新连接到端口443上的反向代理，并通过4443重定向到在用户的主池上运行的移动服务。
    
    鉴于 HTTPS 查询是针对外部 Web 服务 URL 和自动发现服务 URL 的，因此操作会成功，原因是证书已经包含外部 Web 服务完全限定域名 (FQDN) 的使用者替代名称条目。
    
    在此方案中，不需要进行任何证书更改即可支持移动。
    
    <div>
    

    > [!NOTE]  
    > 如果目标 Web 服务器的证书未包含针对 lyncdiscover.contoso.com 的作为使用者替代名称列表值的匹配值：<BR>a。 &nbsp; &nbsp; &nbsp;Web 服务器使用 "服务器 Hello" 进行响应，无证书。<BR>b。 &nbsp; &nbsp; &nbsp;运行 Lync Mobile 的移动设备将立即终止会话。<BR>如果目标 Web 服务器的证书包含 lyncdiscover.contoso.com 作为使用者替代名称列表值：<BR>a。 &nbsp; &nbsp; &nbsp;Web 服务器使用 "服务器 hello" 和证书进行响应。<BR>b。 &nbsp; &nbsp; &nbsp;运行 Lync Mobile 的移动设备将验证证书并完成握手。

    
    </div>

若要支持在反向代理服务器上使用端口 80 与自动发现服务进行初始连接，您可以创建一个类似于此 Forefront Threat Management Gateway 2010 反向代理 Web 发布规则示例的 http 发布规则：

1.  创建新的 Web 发布规则（例如，**Lync Server Autodiscover (HTTP)**）。

2.  在“公共名称”**** 中，输入 lyncdiscover.contoso.com。

3.  在“桥接”**** 选项卡上，仅选择用于将请求从端口 80 桥接到端口 8080 的选项。

4.  在“身份验证”**** 选项卡上，选择“无身份验证”**** 和“客户端无法直接进行身份验证”****。

5.  提交更改，并将规则移动到 Lync 规则列表的顶部， (在处理顺序) 中先进行。

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>拆分域部署的移动性

共享 SIP 地址空间也称为*拆分域* 或*混合部署*，它是一种跨内部部署和在线环境部署用户的配置。 期望的结果是无论用户的主服务器位于何处（内部部署还是在线），用户都能登录到部署并被重定向到其主服务器位置。 为实现此目的，Microsoft Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。 为此，请使用 Lync Server 命令行管理程序和 cmdlet **CsHostingProvider** And **CsHostingProvider 将**自动发现统一资源定位器配置 (URL) 。

您需要收集和记录下列部署的属性：

  - 在 Lync Server 命令行管理程序中，键入
    
        Get-CsHostingProvider

  - 在结果中，查找具有属性 **ProxyFQDN** 的在线提供商。例如，sipfed.online.lync.com

  - 记录 ProxyFQDN 的值

  - 在内部部署 Lync Server 控制面板中启用联合，以允许与联机提供程序进行联盟

  - 为在线提供商启用联盟。默认情况下，对所有在线用户启用域联盟，因此在线用户可以与所有域通信

  - 如果要定义阻止域和允许域，请确定要明确允许或阻止的域

  - 对于在线联盟，您必须规划防火墙例外、证书和 DNS 主机（如使用 IPv6，则为 A 或 AAAA）记录。 此外，您还必须配置联盟策略。 有关详细信息，请参阅 [规划 Lync Server 2013 和 Office 通信服务器联合身份验证](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

