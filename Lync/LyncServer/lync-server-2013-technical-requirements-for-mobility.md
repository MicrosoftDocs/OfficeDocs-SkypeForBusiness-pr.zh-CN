---
title: Lync Server 2013：移动性技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4eef2cb185653446627fe6ccec2d49538e1162b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的移动性技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

移动用户遇到需要特殊规划的各种移动应用方案。 例如，通过3G 网络连接时，某人可能开始使用移动应用程序，而不是通过3G 网络连接，然后在工作时切换到公司 Wi-fi 网络，然后在离开大楼时切换回3G。 你需要规划你的环境以支持此类网络转换，并保证一致的用户体验。 本部分介绍了为支持移动应用程序和自动发现移动资源而必须具备的基础结构要求。

<div>


> [!NOTE]  
> 虽然移动应用程序也可以连接到其他 Lync Server 2013 服务，但需要将所有移动应用程序 web 请求发送到相同的外部 web 完全限定的域名（FQDN）才会应用于 Lync Server 2013 移动服务。 其他移动服务不需要此配置。



</div>

硬件负载平衡器中的 cookie 相关性要求大大减少，如果你使用的是使用 Lync Server 2013 发送的 Lync Mobile，则替换传输控制协议（TCP）关系。 Cookie 相关性仍可使用，但 web 服务不再需要它。

<div>


> [!IMPORTANT]  
> 无论来源点位于何处（内部或外部），所有移动服务流量都将经历反向代理。 如果是单个反向代理或反向代理服务器场或提供反向代理功能的设备，则通过接口 egressing 内部流量并尝试立即进入同一接口时，可能会出现问题。 这通常会导致安全规则被称为 "TCP 数据包欺骗" 或 "仅欺骗"。 要使移动正常运行，必须允许 "<EM>头发钉</EM>" （数据包或数据包的出口和直接输入）。 解决此问题的一种方法是使用独立于防火墙的反向代理（应始终在防火墙上强制执行欺骗性的阻止规则，出于安全目的）。 Hairpin 可以出现在反向代理的外部接口上，而不是防火墙外部接口。 你可以在防火墙上检测欺骗，并在反向代理服务器上放松规则，从而允许移动性所需的 hairpin。<BR>使用域名系统（DNS）主机或 CNAME 记录定义 hairpin 行为（而非防火墙）的反向代理（如果可能）。



</div>

Lync Server 2013 支持 Lync 2010 移动版和 Lync 2013 移动客户端的移动服务。 两个客户端都使用 Lync Server 2013 自动发现服务来查找其移动入口点，但其使用的移动服务有所不同。 Lync 2010 Mobile 使用名为*Mcx*的移动服务，该服务由 Lync Server 2010 的累积更新引入：11月2011。 Lync 2013 移动客户端将统一通信 Web API （或*UCWA*）用作其移动服务提供商。

<div>

## <a name="internal-and-external-dns-configuration"></a>内部和外部 DNS 配置

移动服务 Mcx （使用 Lync Server 2010：11月2011的累积更新引入）和 UCWA （在 Lync Server 2013 的累积更新中引入：2月2013）以同样的方式使用 DNS。

使用自动发现时，移动设备使用 DNS 查找资源。 在 DNS 查找过程中，首先尝试连接到与内部 DNS 记录（lyncdiscoverinternal）相关联的 FQDN。\<内部域名\>）。 如果使用内部 DNS 记录无法建立连接，则使用外部 DNS 记录（lyncdiscover）尝试连接。\<sipdomain\>）。 网络内部的移动设备连接到内部自动发现服务 URL，并且网络外部的移动设备连接到外部自动发现服务 URL。 外部自动发现请求经过反向代理。 Lync Server 2013 自动发现服务返回用户的主池的所有 Web 服务 Url，包括移动服务（Mcx 和 UCWA） Url。 但是，内部移动服务 URL 和外部移动服务 URL 均与外部 Web 服务 FQDN 相关联。 因此，无论移动设备是网络内部还是外部设备，设备都将始终通过反向代理连接到外部的 Lync Server 2013 移动服务。

<div>


> [!NOTE]  
> 了解你的部署可以包含多个不同的命名空间以供内部和外部使用，这一点很重要。 您的 SIP 域名可能与内部部署域名不同。 例如，你的 SIP 域可能是<STRONG>contoso.com</STRONG>，而内部部署可能是<STRONG>contoso.net</STRONG>。 登录 Lync Server 的用户将使用 SIP 域名，例如<STRONG>john@contoso.com</STRONG>。 当为外部 web 服务（在拓扑生成器中定义为<STRONG>外部 web 服务</STRONG>）寻址时，域名和 SIP 域名将保持一致，如 DNS 中所定义。 当寻址内部 Web 服务（在拓扑生成器中定义为<STRONG>内部 web 服务</STRONG>）时，内部 web 服务的默认名称将是前端服务器、前端池、控制器或控制器池的 FQDN。 你可以选择替代内部 web 服务名称。 你应该为内部 web 服务使用内部域名（而不是 SIP 域名），并定义 DNS 主机 A （或 IPv6、AAAA）记录以反映替代名称。 例如，默认内部 web 服务 FQDN 可能为<STRONG>pool01.contoso.net</STRONG>。 已覆盖内部 web 服务 FQDN 可能为<STRONG>webpool.contoso.net</STRONG>。 以这种方式定义 web 服务有助于确保服务的内部和外部位置（而不是使用它们的用户的位置）被遵守。<BR>但是，由于 web 服务在拓扑生成器中定义且内部 web 服务名称可以被重写，因此只要生成的 web 服务名称、验证它的证书以及定义它的 DNS 记录是一致的，您就可以定义包含你所需的任何域名（包括 SIP 域名）的内部 web 服务。 最终，名称到 IP 地址的解析由 DNS 主机记录和一致的命名空间确定。<BR>出于本主题和示例的目的，内部域名用于说明拓扑和 DNS 定义。



</div>

下图显示了在使用内部和外部 DNS 配置时移动服务和自动发现服务的移动应用程序 web 请求的流程。

**使用自动发现的移动服务流程**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> 图表显示了通用 web 服务。 名为 "移动" 的虚拟目录描述了移动服务 Mcx 和/或 UCWA。 如果尚未应用 Lync Server 2013 的累积更新：2月2013，则你的内部和外部 Web 服务上可能有也可能没有定义虚拟目录 Ucwa。 你将拥有虚拟目录自动发现，并且你可能具有虚拟目录 Mcx。<BR>无论您部署了何种移动服务技术，自动发现和服务的发现的工作方式都相同。



</div>

为了支持来自公司网络内部和外部的移动用户，内部和外部 web Fqdn 必须满足某些先决条件。 此外，你可能需要满足其他要求，具体取决于你选择要实现的功能：

  - 新的 DNS、CNAME 或 A （host，if IPv6，AAAA）记录，用于自动发现。

  - 新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。

  - 内部服务器证书上的使用者备用名称和反向代理证书，用于自动发现。

  - 前端服务器硬件负载平衡器配置更改了源关联。

拓扑必须满足以下要求才能支持移动服务和自动发现服务：

  - 前端池内部 web FQDN 必须与前端池外部 web FQDN 不同。

  - 内部 web FQDN 必须仅解析到企业网络内部并可访问。

  - 外部 web FQDN 必须仅解析到并可从 Internet 访问。

  - 对于位于企业网络内部的用户，移动服务 URL 必须寻址到外部 web FQDN。 此要求适用于移动服务，并且仅适用于此 URL。

  - 对于公司网络外部的用户，请求必须转到前端池或控制器的外部 web FQDN。

如果你支持自动发现，你需要为每个 SIP 域创建以下 DNS 记录：

  - 一个内部 DNS 记录，用于支持从你的组织的网络中连接的移动用户。

  - 支持从 Internet 连接的移动用户的外部 DNS 记录或公共 DNS 记录。

内部自动发现 URL 不应从您的网络外部寻址。 外部自动发现 URL 不应从你的网络中寻址。 但是，如果您无法满足外部 URL 的此要求，则移动客户端功能可能不会受到影响，因为内部 URL 总是首先尝试。

DNS 记录可以是 CNAME 记录，也可以是 A （host，if IPv6、AAAA）记录。

<div>


> [!NOTE]  
> 移动设备客户端不支持来自不同域的多个安全套接字层（SSL）证书。 因此，不支持通过 HTTPS 对不同域进行 CNAME 重定向。 例如，不支持通过 HTTPS 重定向到 director.contoso.net 地址的 lyncdiscover.contoso.com 的 DNS CNAME 记录。 在此类拓扑中，移动设备客户端需要对第一个请求使用 HTTP，以便 CNAME 重定向通过 HTTP 进行解析。 随后的请求将使用 HTTPS。 若要支持此方案，你需要使用端口80（HTTP）的 web 发布规则配置反向代理。 有关详细信息，请参阅在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中配置反向代理</A>中的 "为端口80创建 web 发布规则"。<BR>通过 HTTPS 支持到同一域的 CNAME 重定向。 在这种情况下，目标域的证书覆盖了始发域。



</div>

有关你的方案所需的 DNS 记录的详细信息，请参阅[在 Lync Server 2013 中的 dns 摘要自动发现](lync-server-2013-dns-summary-autodiscover.md)。

</div>

<div>

## <a name="port-and-firewall-requirements"></a>端口和防火墙要求

如果你支持推送通知，并且希望 Apple 移动设备通过 Wi-fi 网络接收推送通知，你还需要在企业 Wi-fi 网络上打开端口5223。 端口5223是 Apple 推送通知服务（APNS）使用的出站 TCP 端口。 移动设备将启动连接。 有关详细信息， [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629)请参阅。

<div>


> [!WARNING]  
> 使用 Lync 2013 移动客户端的 Apple 设备不需要推送通知。



</div>

请注意，如果用户托管在 Survivable 分支装置（SBA）上，则需要以下端口：

  - UcwaSipExternalListeningPort 需要端口5088

  - UcwaSipPrimaryListeningPort 需要端口5089

有关自动发现的端口和协议要求的其他详细信息和指导，请参阅[在 Lync Server 2013 中自动发现的端口摘要](lync-server-2013-port-summary-autodiscover.md)。

</div>

<div>

## <a name="certificate-requirements"></a>证书要求

如果你支持 Lync 移动客户端的自动发现，你需要修改证书上的使用者备用名称列表以支持来自移动客户端的安全连接。 对于运行自动发现服务的每个前端服务器和控制器，你需要请求和分配新证书，并为每个前端服务器和控制器添加本部分中所述的主题备用名称条目。 建议的方法也是在反向代理证书上修改 "主题备用名称" 列表。 您需要为组织中的每个 SIP 域添加主题备用名称条目。

通过使用内部证书颁发机构重新发起证书通常是一个简单的过程，但向反向代理使用的公共证书添加多个主题备用名称条目可能会很高。 如果您有多个 SIP 域，增加了使用者备用名称的费用，则可以通过使用 HTTP 配置反向代理以通过端口80进行初始自动发现服务请求，而不是使用 HTTPS （默认配置）的端口443。 然后，该请求将被重定向到 Director 或前端池中的端口8080。 在端口80上发布初始自动发现服务请求时，不需要更改反向代理的证书，因为该请求使用 HTTP 而不是 HTTPS。 此方法受支持，但我们不建议这样做。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services （IIS）要求

我们建议你使用 IIS 7.5、IIS 8.0 或 IIS 8.5 进行移动。 移动服务安装程序在 ASP.NET 中设置标志以提高性能。 默认情况下，IIS 7.5 安装在 Windows server 2008 R2 上，IIS 8.0 安装在 windows Server 2012 上，而 IIS 8.5 安装在 Windows Server 2012 R2 上。 移动服务安装程序会自动更改 ASP.NET 设置。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬件负载平衡器要求

在支持前端池的硬件负载平衡器上，必须为源配置外部 Web 服务虚拟 IPs （Vip）用于 Web 服务流量。 源相关性有助于确保将单个客户端的多个连接发送到一台服务器以维护会话状态。 有关相关性要求的详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

如果你计划仅在你的内部 Wlan 网络上支持 Lync 移动客户端，你应该为源配置内部 Web 服务 VIP，如外部 Web 服务 Vip 所述。 在这种情况下，你应该\_对硬件负载平衡器上的内部 Web 服务 vip 使用源地址（或 TCP）关联。 有关详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向代理要求

如果你支持 Lync 移动客户端的自动发现，你需要更新当前发布规则，如下所示：

  - 如果你决定在反向代理证书上更新 "主题备用名称" 列表，并对初始自动发现服务请求使用 HTTPS，则必须更新 lyncdiscover 的 web 发布规则。\<sipdomain\>。 通常，此功能与前端池中的外部 Web 服务 URL 的发布规则相结合。

  - 如果你决定将 HTTP 用于初始自动发现服务请求，以便你不需要更新反向代理证书上的 "主题备用名称" 列表，则必须为端口 HTTP/TCP 80 创建新的 web 发布规则（如果尚不存在）。 如果 HTTP/TCP 80 的规则已存在，则可以将该规则更新为包含 lyncdiscover。\<sipdomain\>条目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

