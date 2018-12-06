---
title: Lync Server 2013：自动发现服务要求
TOCTitle: 自动发现服务要求
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690012(v=OCS.15)
ms:contentKeyID: 49311948
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的自动发现服务要求

 

_**上一次修改主题：** 2013-02-25_

Microsoft Lync Server 2013 自动发现服务在控制器池服务器和前端池服务器上运行，并且在 DNS 中发布此服务时，运行 Lync Mobile 的移动设备可使用此服务来定位 Mobility Service。您需要先修改运行自动发现服务的任何 控制器和 前端服务器上的证书使用者替代名称列表，然后运行 Lync Mobile 的移动设备才能利用自动发现服务。此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。

有关控制器、前端服务器和反向代理所需的使用者替代名称条目的详细信息，请参阅“规划移动功能”中的[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

有关在反向代理上利用使用者替代名称列表的决定基于您是在端口 80 还是端口 443 上发布自动发现服务：

  - **在端口 80 上发布**   如果在端口 80 上发起对自动发现服务的初始查询，则不需要对证书进行任何更改。这是因为，运行 Lync 的移动设备将在外部端口 80 上访问反向代理，然后在内部端口 8080 上重定向到控制器或前端服务器。有关详细信息，请参阅本主题中后面的“使用端口 80 的初始自动发现过程”一节。

  - **在端口 443 上发布**   外部 Web 服务发布规则使用的证书上的使用者替代名称列表必须为您组织中的每个 SIP 域包含一个 *lyncdiscover.\<sipdomain\>* 条目。

使用内部证书颁发结构重新颁发证书通常是一个简单的过程，但对于 Web 服务发布规则所使用的公共证书，添加多个使用者替代名称条目的成本会很高。为了解决此问题，我们支持端口 80 上的初始自动发现连接，该连接随后会重定向到 控制器或 前端服务器上的端口 8080。

例如，假定将某个运行 Lync Mobile 的移动客户端配置为通过对初始请求使用 HTTP 的自动发现功能登录 Lync Server 2013。

## 使用端口 80 的移动设备的初始自动发现过程

1.  运行 Lync Mobile 的移动设备会使用 DNS（包含 A 记录）查找 lyncdiscover.contoso.com。

2.  外部 DNS 会将外部 Web 服务的 IP 地址返回给客户端。

3.  运行 Lync Mobile 的移动设备会向反向代理发送请求 http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com。

4.  Web 发布规则将该请求从外部端口 80 桥接到内部端口 8080，后者随后将该请求路由到 控制器 或 前端服务器。
    
    由于该请求是 HTTP 而非 HTTPS，因此，无需对外部 Web 服务发布规则上的证书进行任何修改即可支持自动发现服务。

5.  自动发现服务会返回外部 Web 服务 URL（采用 HTTPS 格式）。

6.  之后，运行 Lync Mobile 的移动设备可以在端口 443 上重新连接到反向代理，并通过端口 4443 重定向到正在用户主池中运行的 Mobility Service。
    
    鉴于 HTTPS 查询是针对外部 Web 服务 URL 和自动发现服务 URL 的，因此操作会成功，原因是证书已经包含外部 Web 服务完全限定域名 (FQDN) 的使用者替代名称条目。
    
    在此方案中，不需要进行任何证书更改即可支持移动。
    
    > [!NOTE]  
    > 如果目标 Web 服务器的证书未包含针对 lyncdiscover.contoso.com 的作为使用者替代名称列表值的匹配值：<br />
    a.   Web 服务器以“Server Hello”进行响应且没有证书。<br />
    b.   运行 Lync Mobile 的移动设备会立即终止会话。<br />
    如果目标 Web 服务器的证书包含 lyncdiscover.contoso.com 作为使用者替代名称列表值：<br />
    a.   Web 服务器以“Server Hello”进行响应且有证书。<br />
    b.   运行 Lync Mobile 的移动设备验证该证书并完成握手。
    


若要支持在反向代理服务器上使用端口 80 与自动发现服务进行初始连接，您可以创建一个类似于此 Forefront Threat Management Gateway 2010 反向代理 Web 发布规则示例的 http 发布规则：

1.  创建新的 Web 发布规则（例如，**Lync Server Autodiscover (HTTP)** ）。

2.  在“公共名称”中，输入 lyncdiscover.contoso.com。

3.  在“桥接”选项卡上，仅选择用于将请求从端口 80 桥接到端口 8080 的选项。

4.  在“身份验证”选项卡上，选择“无身份验证”和“客户端无法直接进行身份验证”。

5.  提交更改，并将规则移动到 Lync 规则列表的顶部（按处理顺序排在第一位）。

## 拆分域部署的移动性

共享 SIP 地址空间也称为 *拆分域* 或 *混合部署* ，它是一种跨内部部署和在线环境部署用户的配置。期望的结果是无论用户的主服务器位于何处（内部部署还是在线），用户都能登录到部署并被重定向到其主服务器位置。若要实现此目的，需要使用 Microsoft Lync Server 2013 的自动发现功能将在线用户重定向到在线拓扑。这要通过使用 Lync Server 命令行管理程序和 cmdlet **Get-CsHostingProvider** 与 **Set-CsHostingProvider** 配置自动发现统一资源定位器 (URL) 来完成。

您需要收集和记录下列部署的属性：

  - 从 Lync Server 命令行管理程序键入
    
        Get-CsHostingProvider

  - 在结果中，查找具有属性 **ProxyFQDN** 的在线提供商。例如，sipfed.online.lync.com

  - 记录 ProxyFQDN 的值

  - 在本地 Lync Server 控制面板中启用联盟，以允许与在线提供商联盟

  - 为在线提供商启用联盟。默认情况下，对所有在线用户启用域联盟，因此在线用户可以与所有域通信

  - 如果要定义阻止域和允许域，请确定要明确允许或阻止的域

  - 对于在线联盟，您必须规划防火墙例外、证书和 DNS 主机（如使用 IPv6，则为 A 或 AAAA）记录。此外，您还必须配置联盟策略。有关详细信息，请参阅 [规划 Lync Server 和 Office Communications Server 联盟](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)

