---
title: Lync Server 2013：其他服务器支持和要求
TOCTitle: 其他服务器支持和要求
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398577(v=OCS.15)
ms:contentKeyID: 49313291
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的其他服务器支持和要求

 

_**上一次修改主题：** 2016-12-08_

除了本可支持性文档其他节中介绍的软件支持之外， Lync Server 2013 还有下列支持限制：

  - Lync Server 2013 针对特定服务器角色支持域名系统 (DNS) 和硬件负载平衡。根据需要，还可针对中介服务器支持应用程序负载平衡。有关何时使用每种支持的详细信息，请参阅规划文档。

  - Lync Server 2013 使用通讯组列表扩展协议 (DLX) 扩展通讯组列表。此协议还指定了用于获取通讯组列表成员身份的 Web 服务方法。 Microsoft Exchange Server 支持不包括静态分配的成员的动态组。而将存储扩展组时评估的查询。DLX 不支持动态通讯组列表。

  - “启用用户向导”不支持将非英文字符自动转换为符合 SIP 的 URI，因此必须手动修改 SIP 地址。

  - 对于运行防病毒软件的服务器，请参阅 [Lync Server 2013 的病毒扫描排除](lync-server-2013-antivirus-scanning-exclusions.md)，了解建议的病毒排除和其他安全相关的建议。

  - 如果使用 IPsec，建议在用于音频和视频流量的端口范围内禁用 IPsec。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)。

  - 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。有关实施 QoS 的详细信息，请参阅操作文档中的 [在 Lync Server 2013 中管理服务质量 (QoS)](lync-server-2013-managing-quality-of-service-qos.md)。

  - 支持使用操作系统防火墙。 Lync Server 2013 管理操作系统防火墙的防火墙异常，Microsoft SQL Server 数据库软件除外。有关 SQL Server 防火墙要求的详细信息，请参阅 SQL Server 文档。

  - 用于实现外部用户访问支持的外部接口必须在单独的子网中，而不能与内部接口位于相同的网络中。

  - Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。

  - 2013 年 7 月 Lync Server 2013 累积更新发布后，Lync Server 2013 现在支持双重身份验证。有关详细信息，请参阅[在 Lync Server 2013 中规划和部署双重身份验证](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。

  - 大多数内部服务器都需要定义为 **开放式身份验证** (OAuth) 的证书类型。在 Lync Server 部署向导的 **请求、安装和分配证书**阶段，您将需要请求和分配 OAuth 证书。OAuth 证书密匙的最小大小为 1024 位。如果请求的证书的密匙长度小于 2048 位，则可能会显示一条警告。为了避免在强制而非提醒您使用 2048 位的密匙长度的情况下可能出现的问题，强烈建议您始终对 OAuth 证书使用 2048 位的密钥长度。

  - 如果将 Windows Server 2008 R2 操作系统配置为使用美国联邦信息处理标准 (FIPS) 140-2 算法进行系统加密，则 Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 支持 FIPS 140-2 算法。若要实现 FIPS 支持，则必须将每个运行 Lync Server 2013 的服务器配置为支持它。有关 FIPS 兼容算法和如何实现 FIPS 支持的详细信息，请参阅 Microsoft 知识库文章 811833“系统加密：在 Windows XP 和 Windows 的更高版本中使用 FIPS 兼容的算法来加密、散列和签名安全设置”，网址为 <http://support.microsoft.com/kb/811833>。有关 Exchange 2010 中的 FIPS 140-2 支持和限制的详细信息，请参阅“Exchange 2010 SP1 和对 FIPS 兼容算法的支持”，网址为<http://go.microsoft.com/fwlink/?linkid=205335>。

在部署之前或期间， Lync Server 2013 需要在特定组件上安装其他软件。这包括操作系统、可下载的软件以及在安装 Lync Server 2013 期间自动安装的软件可用的软件。下面列出了可能需要的其他软件：

  - Windows 更新

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual C++ 2012 可再发行软件包
    
    > [!NOTE]  
    > 安装 Lync Server 2013 时将自动安装 Microsoft Visual C++ 2012 可再发行软件包。不应安装和使用任何其他版本。
    


  - URL Rewrite Module 2.0 版可再发行软件包

  - Windows Media Format Runtime

  - Windows PowerShell 3.0 版

  - Microsoft Silverlight 4 浏览器插件（对于 Lync Server 控制面板，Silverlight 4.0.50524.0 或更新版本）

  - Active Directory 域服务 工具

其中一些软件要求仅适用于特定服务器角色或组件。有关这些软件要求的详细信息，请参阅规划文档中的 [Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

