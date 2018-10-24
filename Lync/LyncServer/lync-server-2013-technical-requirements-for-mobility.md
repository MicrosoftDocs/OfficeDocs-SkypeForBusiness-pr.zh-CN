---
title: Lync Server 2013：移动性技术要求
TOCTitle: 移动性技术要求
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690030(v=OCS.15)
ms:contentKeyID: 49313448
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的移动性技术要求

 

_**上一次修改主题：** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

移动用户会遇到各种需要特殊规划的移动应用程序方案。例如，当某个用户不在工作场所时，可以通过 3G 网络进行连接来开始使用移动应用程序，然后在到达工作场所后切换到企业 Wi-Fi 网络，在离开工作场所后又切换回 3G 网络。您需要规划您的环境以支持此类网络转换并确保实现一致的用户体验。本节介绍了支持移动应用程序和移动资源的自动发现必须满足的基础结构要求。

> [!NOTE]  
> 虽然移动应用程序还可以连接到其他 Lync Server 2013 服务，但将所有移动应用程序 Web 请求发送到同一外部 Web 完全限定域名 (FQDN) 这一要求仅适用于 Lync Server 2013 Mobility Service。其他移动服务不需要此配置。


如果使用随 Lync Server 2013 一起提供的 Lync Mobile，硬件负载平衡器中的 Cookie 关联的要求会显著减少，并且会替换传输控制协议 (TCP) 关联。Cookie 关联仍可使用，但 Web 服务不再需要它。

> [!IMPORTANT]
> 所有 Mobility Service 流量都会通过反向代理，无论发起点在内部还是外部都是如此。如果存在单一反向代理或反向代理场或者提供反向代理功能的设备，当内部流量通过某个接口发出并尝试立即在同一接口上进入时，可能引发问题。这通常会导致称为 TCP 数据包欺骗（或简称为欺骗）的安全规则违规。必须允许<em>发夹</em>（一个或一系列数据包发出后立即进入），移动功能才能运行。此问题的一个解决方案是使用独立于防火墙（始终会出于安全目的在防火墙处强制执行欺骗防御规则）的反向代理。发夹可能在反向代理的外部接口上而不是防火墙外部接口上发生。您可以在防火墙处检测欺骗，并在反向代理处放宽该规则，以允许移动功能所需的发夹行为。<br />
> 如果可能，请使用域名系统 (DNS) 主机或 CNAME 记录为发夹行为（而非防火墙）定义反向代理。


Lync Server 2013 支持 Lync 2010 Mobile 和 Lync 2013 移动客户端的移动功能。这两个客户端均使用 Lync Server 2013 自动发现服务查找其移动入口点，但使用的移动服务有所不同。 Lync 2010 Mobile 使用称为 *Mcx* 的移动服务，该移动服务是 2011 年 11 月版 Lync Server 2010 累积更新中引入。 Lync 2013 移动客户端使用统一通信 Web API（即 *UCWA* ）作为其移动服务提供程序。

## 内部和外部 DNS 配置

移动服务 Mcx（在 2011 年 11 月版 Lync Server 2010 累积更新中引入）和 UCWA（在 2013 年 2 月版 Lync Server 2013 累积更新中引入）以相同方式使用 DNS。

在使用自动发现时，移动设备会使用 DNS 来定位资源。在 DNS 查找期间，首先会尝试使用与内部 DNS 记录 (lyncdiscoverinternal.*\<internal domain name\>*) 关联的 FQDN 进行连接。如果无法使用内部 DNS 记录进行连接，则尝试使用外部 DNS 记录 (lyncdiscover.*\<sipdomain\>*) 进行连接。网络内部的移动设备会连接到内部自动发现服务 URL，而网络外部的移动设备会连接到外部自动发现服务 URL。外部自动发现请求将穿过反向代理。Lync Server 2013 自动发现服务将返回用户的主池的所有 Web 服务 URL，包括移动服务（Mcx 和 UCWA）URL。但是，内部移动服务 URL 和外部移动服务 URL 都与外部 Web 服务 FQDN 关联。因此，不管移动设备是位于网络的内部还是外部，该设备始终会穿过反向代理连接到外部 Lync Server 2013 移动服务。

> [!IMPORTANT]  
> 您的部署可能包括供内部和外部使用的多个不同命名空间，了解这一点很重要。您的 SIP 域名可能与内部部署域名不同。例如，您的 SIP 域可能是 <strong>contoso.com</strong>，而您的内部部署可能是 <strong>contoso.net</strong>。登录到 Lync Server 的用户将使用 SIP 域名，如 <strong>john@contoso.com</strong>。当对外部 Web 服务（在 拓扑生成器池中定义为<strong>外部 Web 服务</strong>）寻址时，域名和 SIP 域名将与 DNS 中定义的一致。当对内部 Web 服务（在 拓扑生成器池中定义为<strong>内部 Web 服务</strong>），内部 Web 服务的默认名称将为前端服务器、前端池、控制器或控制器池的 FQDN。您可以选择覆盖内部 Web 服务名称。您应该对内部 Web 服务使用内部域名（而不是 SIP 域名）并定义 DNS 主机 A（或者，对于 IPv6，则为 AAAA）记录以反映被覆盖的名称。例如，默认内部 Web 服务 FQDN 可能是 <strong>pool01.contoso.net</strong>。被覆盖的内部 Web 服务 FQDN 可能是 <strong>webpool.contoso.net</strong>。以这种方式定义 Web 服务有助于确保观测到服务的内部和外部位置（而不是使用服务的用户的位置）。<br />
> 但是，由于 Web 服务是在 拓扑生成器中定义的，且内部 Web 服务名称可以覆盖（只要生成的 Web 服务名称、用来验证该名称的证书和用来定义该名称的 DNS 记录一致），因此您可以使用所需的任何域名（包括 SIP 域名）定义内部 Web 服务。最终，IP 地址的名称解决方案由 DNS 主机记录和一致的命名空间确定。<br />
> 对于本主题和示例，内部域名用于说明拓扑和 DNS 定义。



下图说明了使用内部和外部 DNS 配置时针对移动服务和自动发现服务的移动应用程序 Web 请求流。

**使用自动发现的移动服务流程**

![移动请求流](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "移动请求流")

> [!NOTE]
> 上图演示了通用 Web 服务。名为 Mobility 的虚拟目录描绘了移动服务 Mcx 和/或 UCWA。如果您尚未应用 2013 年 2 月版 Lync Server 2013 累积更新，则您的内部和外部 Web 服务上可能已经定义了虚拟目录 Ucwa，也可能尚未定义。您将会有一个虚拟目录 Autodiscover，并且可能会有一个虚拟目录 Mcx。<br />
> 自动发现和服务发现的工作方式相同，无论您部署何种移动服务技术。


若要同时支持企业网络内部和外部的移动用户，内部和外部 Web FQDN 必须满足某些先决条件。此外，您可能需要满足其他要求，具体取决于您选择用来实现以下各项的功能：

  - 新的 DNS、CNAME 或 A（主机，如果是 IPv6，则为 AAAA）记录，针对自动发现。

  - 新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。

  - 内部服务器证书和反向代理证书上的使用者替代名称（针对自动发现）。

  - 前端服务器硬件负载平衡器配置更改源关联。

您的拓扑必须满足以下要求才能支持 Mobility Service 和自动发现服务：

  - 前端池内部 Web FQDN 必须与 前端池外部 Web FQDN 不同。

  - 内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。

  - 外部 Web FQDN 必须仅解析为 Internet 地址且仅能从 Internet 进行访问。

  - 对于企业网络内部的用户，必须将 Mobility Service URL 寻址到外部 Web FQDN。此要求针对的是 Mobility Service 且仅适用于此 URL。

  - 对于企业网络外部的用户，此请求必须转到 前端池或 控制器的外部 Web FQDN。

如果您支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：

  - 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。

  - 支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录。

应无法从网络外部对内部自动发现 URL 进行寻址。应无法从网络内部对外部自动发现 URL 进行寻址。但是，如果您无法满足外部 URL 的此要求，则可能不会影响移动客户端的功能，因为始终会先尝试内部 URL。

DNS 记录可以是 CNAME 记录或 A（主机，如果是 IPv6，则为 AAAA）记录。

> [!NOTE]
> 移动设备客户端不支持来自不同域的多个安全套接字层 (SSL) 证书。因此，不支持通过 HTTPS 对其他域进行 CNAME 重定向。例如，不支持通过 HTTPS 将 lyncdiscover.contoso.com 的 DNS CNAME 记录重定向到 director.contoso.net 地址。在此类拓扑中，移动设备客户端需要对第一个请求使用 HTTP，以便通过 HTTP 解析 CNAME 重定向。之后，后续请求会使用 HTTPS。若要支持此方案，您需要使用针对端口 80 (HTTP) 的 Web 发布规则配置反向代理。有关详细信息，请参阅<a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">在 Lync Server 2013 中配置反向代理以实现移动功能</a>中的“创建针对端口 80 的 Web 发布规则”。<br />
> 支持通过 HTTPS 对同一域的 CNAME 重定向。在这种情况下，目标域的证书涵盖了原始域。


有关您的方案所需的 DNS 记录的详细信息，请参阅 [Lync Server 2013 中的 DNS 摘要 - 自动发现](lync-server-2013-dns-summary-autodiscover.md)。

## 端口和防火墙要求

如果您支持推送通知并希望 Apple 移动设备通过 Wi-Fi 网络接收推送通知，则还需要在您的企业 Wi-Fi 网络上打开端口 5223。端口 5223 是一个由 Apple 推送通知服务 (APNS) 使用的出站 TCP 端口。该移动设备将启动连接。有关详细信息，请参阅 [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ht6175?viewlocale=zh_cn)。

> [!WARNING]
> 使用 Lync 2013 Mobile 客户端的 Apple 设备不需要推送通知。


请注意，如果用户驻留在 Survivable Branch Appliance (SBA) 上，则需要以下端口：

  - UcwaSipExternalListeningPort 需要端口 5088

  - UcwaSipPrimaryListeningPort 需要端口 5089

有关自动发现的端口和协议要求的更多详细信息及指南，请参阅[Lync Server 2013 中的端口摘要 - 自动发现](lync-server-2013-port-summary-autodiscover.md)。

## 证书要求

如果您支持 Lync 移动客户端的自动发现，则需要修改证书上的使用者替代名称列表以支持来自该移动客户端的安全连接。您需要请求和分配新的证书，并为每个运行自动发现服务的 前端服务器和 控制器添加本节中所述的使用者替代名称条目。建议的方法同样是修改反向代理的证书上的使用者替代名称列表。您需要为组织中的每个 SIP 域添加使用者替代名称条目。

使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但向反向代理所使用的公共证书中添加多个使用者替代名称条目的成本很高。如果您具有多个 SIP 域（这会导致添加使用者替代名称的成本很高），则可以将反向代理配置为在使用 HTTP 的端口 80（而非使用 HTTPS 的端口 443，这是默认配置）上发出初始自动发现服务请求。该请求随后会重定向到 控制器或 前端池上的端口 8080。当您在端口 80 上发布初始自动发现服务请求时，您无需更改反向代理的证书，因为该请求使用的是 HTTP 而非 HTTPS。虽然此方法是受支持的，但不建议使用。

## Internet Information Services (IIS) 要求

建议您使用 IIS 7.5、IIS 8.0 或 IIS 8.5 以实现移动功能。Mobility Service 安装程序在 ASP.NET 中设置了一些标志以提高性能。默认情况下，Windows Server 2008 R2 上安装 IIS 7.5，Windows Server 2012 上安装 IIS 8.0，Windows Server 2012 R2 上安装 IIS 8.5。Mobility Service 安装程序会自动更改 ASP.NET 设置。

## 硬件负载平衡器要求

在支持 前端池的硬件负载平衡器上，必须为源配置用于 Web 服务流量的外部 Web 服务虚拟 IP (VIP)。源关联有助于确保向一台服务器发送来自单个客户端的多个连接以保持会话状态。有关关联要求的详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

如果您计划仅支持内部 Wi-Fi 网络上的 Lync 移动客户端，则应为源配置内部 Web 服务 VIP，就像对外部 Web 服务 VIP 执行此操作一样。在此情况下，您应对硬件负载平衡器上的内部 Web 服务 VIP 使用 source\_addr（或 TCP）相关性。有关详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。

## 反向代理要求

如果您支持 Lync 移动客户端的自动发现，则需要更新当前发布规则，如下所示：

  - 如果您决定更新反向代理证书上的使用者替代名称列表并对初始自动发现服务请求使用 HTTPS，则必须为 lyncdiscover.*\<sipdomain\>* 更新 Web 发布规则。一般而言，这将与 前端池上的外部 Web 服务 URL 的发布规则结合。

  - 如果您决定对初始自动发现服务请求使用 HTTP，以便不需要更新反向代理证书上的使用者替代名称列表，则必须创建针对端口 HTTP/TCP 80 的新 Web 发布规则（如果尚不存在该规则）。如果 HTTP/TCP 80 的规则已存在，则可以更新该规则以包含 lyncdiscover.*\<sipdomain\>* 条目。

