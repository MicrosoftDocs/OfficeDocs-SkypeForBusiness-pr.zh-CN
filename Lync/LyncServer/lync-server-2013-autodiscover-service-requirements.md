---
title: Lync Server 2013：自动发现服务要求
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
ms.openlocfilehash: 777d70b20a51e5408fe9d9248028c3dbcaebeba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a>Lync Server 2013 的自动发现服务要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-25_

Microsoft Lync Server 2013 自动发现服务在 Director 和前端池服务器上运行，并且当在 DNS 中发布时，可以由运行 Lync Mobile 的移动设备使用，以找到移动服务。 在运行 Lync Mobile 的移动设备可以充分利用自动发现之前，你需要在运行自动发现服务的任何控制器和前端服务器上修改证书主题备用名称列表。 此外，可能还需要修改用于反向代理上的外部 web 服务发布规则的证书上的使用者备用名称列表。

有关董事、前端服务器和反向代理所需的主题备用名称条目的详细信息，请参阅规划移动性的[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

在反向代理上使用主题备用名称列表的决策取决于你是在端口80上还是在端口443上发布自动发现服务：

  - **已在端口 80**   上发布如果自动发现服务的初始查询通过端口80进行，则不需要进行证书更改。 这是因为运行 Lync 的移动设备将外部访问端口80上的反向代理，然后在内部将其重定向到端口8080上的 Director 或前端服务器。 有关详细信息，请参阅本主题后面的 "使用端口80的初始自动发现过程" 部分。

  - **在端口 443**   上发布在外部 web 服务发布规则使用的证书上的 "主题" 备用名称列表中必须包含*lyncdiscover。\<组织\> *中每个 SIP 域的 sipdomain 条目。

使用内部证书颁发机构重新发起证书通常是一个简单的过程，但对于 web 服务发布规则中使用的公共证书，添加多个主题可选名称条目可能会很高。 若要解决此问题，我们通过端口80支持初始自动发现连接，该连接随后将被重定向到 Director 或前端服务器上的端口8080。

例如，假设运行 Lync Mobile 的移动客户端配置为使用用于初始请求的 HTTP 的自动发现功能登录 Lync Server 2013。

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a>使用端口80的移动设备初始自动发现过程

1.  运行 Lync Mobile 的移动设备使用 DNS 查找 lyncdiscover.contoso.com，其中存在 A 记录。

2.  外部 DNS 将外部 web 服务的 IP 地址返回给客户端。

3.  运行 Lync Mobile 的移动设备将http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com请求发送到反向代理

4.  Web 发布规则将从外部端口80到内部端口8080的请求桥接该请求，然后将其路由到 Director 或前端服务器。
    
    由于请求是 HTTP 而不是 HTTPS，因此外部 web 服务发布规则上的证书不需要修改即可支持自动发现服务。

5.  自动发现服务返回外部 web 服务 Url （采用 HTTPS 格式）。

6.  运行 Lync Mobile 的移动设备可以重新连接到端口443上的反向代理，并通过4443重定向到在用户的主池中运行的移动服务。
    
    由于 HTTPS 查询指向外部 web 服务 URL 而不是自动发现服务 URL，因此它将成功，因为该证书将已包含外部 web 服务完全限定的域名（Fqdn）的主题备用名称条目。
    
    在此方案中，无需更改任何证书来支持移动性。
    
    <div>
    

    > [!NOTE]  
    > 如果目标 web 服务器具有的证书与 lyncdiscover.contoso.com 的匹配值不是 "主题备用名称" 列表值，请执行以下操作：<BR>a.&nbsp;&nbsp;&nbsp;Web 服务器使用 "服务器 Hello" 响应，没有证书。<BR>b. 运行 Lync Mobile 的&nbsp;移动设备立即终止会话。&nbsp;&nbsp;<BR>如果目标 web 服务器的证书包含 lyncdiscover.contoso.com 作为主题备用名称列表值，请执行以下操作：<BR>a.&nbsp;&nbsp;&nbsp;Web 服务器使用 "服务器 hello" 和证书进行响应。<BR>b. 运行 Lync Mobile 的&nbsp;移动设备将验证证书并完成握手。&nbsp;&nbsp;

    
    </div>

若要支持使用反向代理服务器上的端口80的自动发现服务的初始连接，你可以创建类似于 Forefront 威胁管理网关的 http 发布规则2010反向代理 web 发布规则：

1.  创建新的 web 发布规则（例如， **Lync Server 自动发现（HTTP）**）。

2.  在 "**公共名称**" 中，输入 lyncdiscover.contoso.com。

3.  在 "**桥接**" 选项卡上，仅选择将来自端口80的请求桥接到端口8080的选项。

4.  在 "**身份验证**" 选项卡上，选择 "**无身份验证**"，**客户端无法直接身份验证**。

5.  提交更改，并将规则移动到 Lync 规则列表的顶部（首先在处理顺序中）。

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>拆分域部署的移动性

共享 SIP 地址空间（也称为*拆分域*）或*混合部署*是在内部部署和联机环境中部署用户的配置。 无论其主服务器位于何处（内部部署或联机），所需的结果是让用户登录到部署并重定向到其主服务器位置。 为了实现此目的，Microsoft Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。 通过使用 Lync Server 命令行管理程序和 cmdlet **CsHostingProvider**和**Set-CsHostingProvider**配置自动发现统一资源定位器（URL）来实现此操作。

你将需要收集和记录以下已部署的属性：

  - 从 Lync Server 命令行管理程序中，键入
    
        Get-CsHostingProvider

  - 在结果中，查找具有属性**ProxyFQDN**的联机提供程序。 例如，sipfed.online.lync.com

  - 记录 ProxyFQDN 的值

  - 在本地 Lync Server "控制面板" 中启用联盟，允许与联机提供商进行联盟

  - 为联机提供程序启用联盟。 默认情况下，所有联机用户都启用了域联盟，并且可以与所有域进行通信

  - 如果你要定义阻止的域和允许的域，请确定你将明确允许或显式阻止的域

  - 对于联机联盟，你必须为防火墙例外、证书和 DNS 主机（如果使用 IPv6）记录制定计划。 此外，必须配置联合身份验证策略。 有关详细信息，请参阅[规划 Lync Server 2013 和 Office 通信服务器联合](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

