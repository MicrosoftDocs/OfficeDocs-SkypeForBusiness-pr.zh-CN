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
ms.openlocfilehash: 9628248922742ce46037c94f8257823e4484d168
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的移动性技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-07-24_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

移动用户会遇到各种需要特殊规划的移动应用程序方案。 例如，通过3G 网络连接时，某人可能会开始使用移动应用程序，然后在工作到达时切换到公司 Wi-fi 网络，然后在离开大楼时切换回3G。 您需要规划您的环境以支持此类网络转换并确保实现一致的用户体验。 本节介绍了为支持移动应用程序和自动发现移动资源而必须具备的基础结构要求。

<div>


> [!NOTE]  
> 尽管移动应用程序也可以连接到其他 Lync Server 2013 服务，但将所有移动应用程序 web 请求发送到相同外部 web 完全限定的域名（FQDN）的要求仅适用于 Lync Server 2013 移动服务。 其他移动服务不需要此配置。



</div>

硬件负载平衡器中的 cookie 关联要求大大减少，如果使用 lync Mobile 提供的 Lync Server 2013，则替换了传输控制协议（TCP）关联。 Cookie 相关性仍然可以使用，但 web 服务不再需要它。

<div>


> [!IMPORTANT]  
> 所有移动服务流量都通过反向代理，而不管来源点是内部还是外部。 如果是单个反向代理或反向代理服务器场或提供反向代理功能的设备，则通过接口附近内部流量并尝试立即进入同一接口时，可能会出现问题。 这通常会导致违反 TCP 数据包欺骗或仅哄骗的安全规则。 若要使移动功能正常工作，必须允许使用<EM>头发钉住</EM>（数据包或数据包系列的出口和直接入站）。 解决此问题的一种方法是使用独立于防火墙的反向代理（哄骗预防规则应始终在防火墙上强制实施，出于安全目的）。 发夹可以在反向代理的外部接口（而不是防火墙外部接口）发生。 在防火墙中检测到欺骗，并在反向代理中放松该规则，从而允许移动性所需的发夹。<BR>使用域名系统（DNS）主机或 CNAME 记录为发夹行为（而不是防火墙）定义反向代理（如果可能）。



</div>

Lync Server 2013 支持 Lync 2010 移动和 Lync 2013 移动客户端的移动服务。 这两个客户端都使用 Lync Server 2013 自动发现服务来查找其移动入口点，但在其使用的移动服务上有所不同。 Lync 2010 Mobile 使用移动服务（称为 " *Mcx*"），随 Lync Server 2010 的累积更新引入：11月2011。 Lync 2013 移动客户端使用统一通信 Web API 或*UCWA*作为其移动服务提供程序。

<div>

## <a name="internal-and-external-dns-configuration"></a>内部和外部 DNS 配置

移动服务 Mcx （随 Lync Server 2010：11月2011的累积更新引入）和 UCWA （在 Lync Server 2013 的累积更新中引入：二月份2013）以相同的方式使用 DNS。

当您使用自动发现时，移动设备将使用 DNS 查找资源。 在 DNS 查找过程中，首先尝试连接到与内部 DNS 记录（lyncdiscoverinternal.）相关联的 FQDN。\<内部域名称\>）。 如果无法使用内部 DNS 记录建立连接，则使用外部 DNS 记录（lyncdiscover.）尝试连接。\<sipdomain\>）。 网络内部的移动设备会连接到内部自动发现服务 URL，而网络外部的移动设备会连接到外部自动发现服务 URL。 外部自动发现请求会经历反向代理。 Lync Server 2013 自动发现服务返回用户主池的所有 Web 服务 Url，包括移动服务（Mcx 和 UCWA） Url。 但是，内部 Mobility Service URL 和外部 Mobility Service URL 都与外部 Web 服务 FQDN 关联。 因此，无论移动设备是在网络内部还是外部，设备都将始终通过反向代理从外部连接到 Lync Server 2013 移动服务。

<div>


> [!NOTE]  
> 您的部署可以由多个不同的命名空间组成，以供内部和外部使用，这一点非常重要。 您的 SIP 域名可能不同于内部部署域名称。 例如，您的 SIP 域可能是<STRONG>contoso.com</STRONG>，而内部部署可能是<STRONG>contoso.net</STRONG>。 登录到 Lync Server 的用户将使用 SIP 域名，如<STRONG>john@contoso.com</STRONG>。 在将外部 web 服务（在拓扑生成器中定义为<STRONG>外部 web 服务</STRONG>）寻址时，域名和 SIP 域名将保持一致，如 DNS 中所定义。 在为内部 web 服务（在拓扑生成器中定义为<STRONG>内部 web 服务</STRONG>）寻址时，内部 web 服务的默认名称将是前端服务器、前端池、控制器或控制器池的 FQDN。 你可以选择替代内部 web 服务名称。 应使用内部 web 服务的内部域名（而不是 SIP 域名），并定义 DNS 主机 A （或 IPv6、AAAA）记录以反映覆盖的名称。 例如，默认的内部 web 服务 FQDN 可能为<STRONG>pool01.contoso.net</STRONG>。 重写的内部 web 服务 FQDN 可能是<STRONG>webpool.contoso.net</STRONG>的。 以这种方式定义 web 服务有助于确保服务的内部和外部位置（而不是使用它们的用户的位置）遵守。<BR>但是，由于 web 服务是在拓扑生成器中定义的，并且可以重写内部 web 服务名称，因此只要生成的 web 服务名称、用于验证它的证书以及用于定义它的 DNS 记录，它们就是一致的。您可以定义包含您所需的任何域名（包括 SIP 域名）的内部 web 服务。 最终，名称到 IP 地址的解析由 DNS 主机记录和一致的命名空间确定。<BR>出于本主题和示例的目的，内部域名用于说明拓扑和 DNS 定义。



</div>

下图说明了在使用内部和外部 DNS 配置时移动服务和自动发现服务的移动应用程序 web 请求流。

**使用自动发现的移动服务流**

![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")

<div>


> [!NOTE]  
> 该图说明了通用 web 服务。 名为 "移动性" 的虚拟目录描述了移动服务 Mcx 和/或 UCWA。 如果尚未应用 Lync Server 2013 的累积更新：2月2013，则您的内部和外部 Web 服务上可能有也可能没有定义虚拟目录 Ucwa。 您将拥有一个虚拟目录自动发现，并且您可能有一个虚拟目录 Mcx。<BR>无论您部署了何种移动服务技术，自动发现和服务发现的工作方式都是相同的。



</div>

若要同时支持企业网络内部和外部的移动用户，内部和外部 Web FQDN 必须满足某些先决条件。此外，您可能需要满足其他要求，具体取决于您选择用来实现以下各项的功能：

  - 用于自动发现的新 DNS、CNAME 或 A （主机，如果是 IPv6、AAAA）记录。

  - 新的防火墙规则（如果要通过 Wlan 网络支持推送通知）。

  - 内部服务器证书上的使用者替代名称和反向代理证书（用于自动发现）。

  - 前端服务器硬件负载平衡器配置更改源关联。

您的拓扑必须满足以下要求才能支持移动服务和自动发现服务：

  - 前端池内部 web FQDN 必须与前端池外部 web FQDN 不同。

  - 内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。

  - 外部 web FQDN 必须仅解析到并可从 Internet 访问。

  - 对于企业网络内部的用户，必须将 Mobility Service URL 寻址到外部 Web FQDN。此要求针对的是 Mobility Service 且仅适用于此 URL。

  - 对于公司网络外部的用户，该请求必须转到前端池或控制器的外部 web FQDN。

如果您支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：

  - 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。

  - 支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录。

应无法从网络外部对内部自动发现 URL 进行寻址。 应无法从网络内部对外部自动发现 URL 进行寻址。 但是，如果您无法满足外部 URL 的此要求，则可能不会影响移动客户端的功能，因为最初总是会尝试内部 URL。

DNS 记录可以是 CNAME 记录，也可以是（主机，如果是 IPv6，AAAA）记录。

<div>


> [!NOTE]  
> 移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。 因此，不支持通过 HTTPS 对其他域进行 CNAME 重定向。 例如，不支持通过 HTTPS 将 lyncdiscover.contoso.com 的 DNS CNAME 记录重定向到 director.contoso.net 地址。 在此类拓扑中，移动设备客户端需要对第一个请求使用 HTTP，以便通过 HTTP 解析 CNAME 重定向。 之后，后续请求会使用 HTTPS。 若要支持此方案，您需要使用针对端口 80 (HTTP) 的 Web 发布规则配置反向代理。 有关详细信息，请参阅在<A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013 中配置反向代理以实现移动性的反向代理</A>中的 "为端口80创建 web 发布规则"。<BR>支持通过 HTTPS 对同一域的 CNAME 重定向。 在这种情况下，目标域的证书将覆盖源域。



</div>

有关您的方案所需的 DNS 记录的详细信息，请参阅[Lync Server 2013 中的 dns 摘要-自动发现](lync-server-2013-dns-summary-autodiscover.md)。

</div>

<div>

## <a name="port-and-firewall-requirements"></a>端口和防火墙要求

如果您支持推送通知并希望 Apple 移动设备通过 Wi-Fi 网络接收推送通知，则还需要在您的企业 Wi-Fi 网络上打开端口 5223。 端口 5223 是一个由 Apple 推送通知服务 (APNS) 使用的出站 TCP 端口。 移动设备启动连接。 有关详细信息， [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629)请参阅。

<div>


> [!WARNING]  
> 使用 Lync 2013 移动客户端的 Apple 设备不需要推送通知。



</div>

请注意，如果用户驻留在 Survivable 分支设备（SBA）上，则需要以下端口：

  - UcwaSipExternalListeningPort 需要端口5088

  - UcwaSipPrimaryListeningPort 需要端口5089

有关自动发现的端口和协议要求的其他详细信息和指导，请参阅[Lync Server 2013 中的端口摘要-自动发现](lync-server-2013-port-summary-autodiscover.md)。

</div>

<div>

## <a name="certificate-requirements"></a>证书要求

如果您支持 Lync 移动客户端的自动发现，则需要修改证书上的使用者替代名称列表以支持来自该移动客户端的安全连接。 对于运行自动发现服务的每台前端服务器和控制器，您需要请求和分配新证书，并为每个前端服务器和控制器添加此部分中介绍的使用者可选名称条目。 建议的方法同样是修改反向代理的证书上的使用者替代名称列表。 您需要为组织中的每个 SIP 域添加使用者替代名称条目。

使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但向反向代理所使用的公共证书中添加多个使用者替代名称条目的成本很高。 如果您具有多个 SIP 域（这会导致添加使用者替代名称的成本很高），则可以将反向代理配置为在使用 HTTP 的端口 80（而非使用 HTTPS 的端口 443，这是默认配置）上发出初始自动发现服务请求。 然后，将该请求重定向到控制器或前端池上的端口8080。 当您在端口 80 上发布初始自动发现服务请求时，您无需更改反向代理的证书，因为该请求使用的是 HTTP 而非 HTTPS。 此方法受支持，但我们不建议这样做。

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a>Internet Information Services (IIS) 要求

建议使用 IIS 7.5、IIS 8.0 或 IIS 8.5 进行移动。 移动服务安装程序在 ASP.NET 中设置标志以提高性能。 默认情况下，IIS 7.5 安装在 Windows server 2008 R2 上，IIS 8.0 安装在 windows Server 2012 上，而 IIS 8.5 安装在 Windows server 2012 R2 上。 移动服务安装程序会自动更改 ASP.NET 设置。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬件负载平衡器要求

在支持前端池的硬件负载平衡器上，必须为源配置 Web 服务流量的外部 Web 服务虚拟 Ip （Vip）。 源关联有助于确保将来自单个客户端的多个连接发送到一台服务器，以维护会话状态。 有关相关性要求的详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

如果计划仅通过内部 Wlan 网络支持 Lync 移动客户端，则应为源配置内部 Web 服务 VIP，如外部 Web 服务 Vip 所述。 在这种情况下，应将\_源地址（或 TCP）关联用于硬件负载平衡器上的内部 Web 服务 vip。 有关详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向代理要求

如果您支持 Lync 移动客户端的自动发现，则需要更新当前发布规则，如下所示：

  - 如果您决定在反向代理证书上更新 "主题备用名称" 列表并对初始自动发现服务请求使用 HTTPS，则必须更新 lyncdiscover. 的 web 发布规则。\<sipdomain\>。 通常情况下，这与前端池上的外部 Web 服务 URL 的发布规则结合在一起。

  - 如果您决定对初始自动发现服务请求使用 HTTP，以便不需要更新反向代理证书上的 "主题备用名称" 列表，则必须为 "端口 HTTP/TCP 80" 创建一个新的 web 发布规则（如果尚不存在）。 如果 HTTP/TCP 80 的规则已存在，则可以将该规则更新为包含 lyncdiscover.。\<sipdomain\>条目。

</div>

</div>

<span> </span>

</div>

</div>

</div>

