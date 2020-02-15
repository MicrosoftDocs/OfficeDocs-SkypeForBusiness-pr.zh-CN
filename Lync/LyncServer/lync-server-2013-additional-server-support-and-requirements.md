---
title: Lync Server 2013：其他服务器支持和要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d8eb02f0cf178807c656520787024d79ab0f09b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013 中的其他服务器支持和要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-09_

除了此可支持性文档的其他部分中所述的软件支持外，Lync Server 2013 还提供了以下支持限制：

  - Lync Server 2013 支持针对特定服务器角色的域名系统（DNS）和硬件负载平衡。 根据需要，还可针对中介服务器支持应用程序负载平衡。 有关何时使用每种支持的详细信息，请参阅规划文档。

  - Lync Server 2013 使用通讯组列表展开协议（DLX）展开通讯组列表。 此协议还指定了用于获取通讯组列表成员身份的 Web 服务方法。 Microsoft Exchange Server 不支持静态分配有成员的动态组。 而将存储扩展组时评估的查询。 DLX 不支持动态通讯组列表。 此 DLX 限制适用于所有版本的 Lync Server。

  - “启用用户向导”不支持将非英文字符自动转换为符合 SIP 的 URI，因此必须手动修改 SIP 地址。

  - 对于运行防病毒软件的服务器，请参阅[Lync Server 2013 的防病毒扫描排除](lync-server-2013-antivirus-scanning-exclusions.md)项，了解建议的病毒排除和其他安全相关建议。

  - 如果使用 IPsec，建议在用于音频和视频流量的端口范围内禁用 IPsec。 有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 IPsec 例外](lync-server-2013-ipsec-exceptions.md)。

  - 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。 有关实施 QoS 的详细信息，请参阅操作文档中的在[Lync Server 2013 中管理服务质量（QoS）](lync-server-2013-managing-quality-of-service-qos.md) 。

  - 支持使用操作系统防火墙。 Lync Server 2013 管理操作系统防火墙的防火墙例外（Microsoft SQL Server 数据库软件除外）。 有关 SQL Server 防火墙要求的详细信息，请参阅 SQL Server 文档。

  - 用于实现外部用户访问支持的外部接口必须在单独的子网中，而** 不能与内部接口位于相同的网络中。

  - Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。 对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。

  - 发布 Lync Server 2013 累积更新：6月2013，Lync Server 2013 现在支持双重身份验证。 有关详细信息，请参阅[Lync Server 2013 中的双重身份验证](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。

  - 大多数内部服务器都需要定义为**开放身份验证**（OAuth）的证书类型。 您需要在 Lync Server 部署向导的 "**请求中安装和分配证书**" 阶段请求和分配 OAuth 证书。 OAuth 证书密钥的最小大小为1024位。 如果请求密钥长度小于2048位的证书，则会显示一条警告。 为了避免在强制实施密钥长度为2048而不是警告的情况下出现潜在问题，强烈建议始终为 OAuth 证书使用密钥长度2048。

  - 如果 Windows Server 2008 R2 操作系统配置为使用 FIPS 140-2 算法，则 Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 （SP1）操作支持联邦信息处理标准（FIPS）140-2 算法系统加密。 若要实现 FIPS 支持，必须将运行 Lync Server 2013 的每台服务器配置为支持它。 有关与 FIPS 兼容的算法以及如何实施 FIPS 支持的详细信息，请参阅 Microsoft 知识库文章 811833 "系统加密：将 FIPS 兼容的算法用于加密、哈希和签名安全设置在 Windows XP 和更高版本的 Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)中。 有关 Exchange 2010 中的 FIPS 140-2 支持和限制的详细信息，请参阅中的 "Exchange 2010 SP1 和支持 FIPS [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)兼容的算法"。

在部署之前或部署过程中，Lync Server 2013 要求在特定组件上安装其他软件。 这包括可在安装 Lync Server 2013 期间自动安装的操作系统、可下载软件和软件中使用的软件。 下面列出了可能需要的其他软件：

  - Windows Update

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual c + + 2012 可再发行组件
    
    <div>
    

    > [!NOTE]  
    > 当您安装 Lync Server 2013 时，将自动安装 Microsoft Visual c + + 2012 可再发行组件。 您不应安装和使用任何其他版本。

    
    </div>

  - URL Rewrite Module 2.0 版可再发行软件包

  - Windows Media Format Runtime

  - Windows PowerShell 版本3。0

  - Microsoft Silverlight 4 浏览器插件（对于 Lync Server 控制面板，Silverlight 4.0.50524.0 或更新版本）

  - Active Directory 域服务工具

其中一些软件要求仅适用于特定服务器角色或组件。 有关这些软件要求的详细信息，请参阅规划文档中的[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

</div>

<span> </span>

</div>

</div>

</div>

