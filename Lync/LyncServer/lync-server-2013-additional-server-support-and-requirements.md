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
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a>Lync Server 2013 中的其他服务器支持和要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-12-09_

除了此支持文档的其他部分中介绍的软件支持，Lync Server 2013 还具有以下支持限制：

  - Lync Server 2013 支持针对特定服务器角色的域名系统（DNS）和硬件负载平衡。 它还支持中介服务器的应用程序负载平衡（如果适用）。 有关何时使用的详细信息，请参阅规划文档。

  - Lync Server 2013 使用通讯组列表扩展协议（DLX）展开通讯组列表。 此协议还指定用于获取通讯组列表成员身份的 web 服务方法。 Microsoft Exchange Server 支持没有静态分配成员的动态组。 而是存储在展开组时评估的查询。 DLX 不支持动态通讯组列表。 此 DLX 限制适用于所有版本的 Lync Server。

  - "启用用户" 向导不支持将非英语字符自动转换为 SIP 兼容的 URI，因此必须手动修改 SIP 地址。

  - 对于运行防病毒软件的服务器，请参阅[Lync Server 2013 的防病毒扫描排除](lync-server-2013-antivirus-scanning-exclusions.md)程序，了解建议的病毒排除和其他安全相关建议。

  - 如果你使用 IPsec，我们建议通过用于音频和视频流量的端口范围禁用 IPsec。 有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 IPsec 异常](lync-server-2013-ipsec-exceptions.md)。

  - 如果您的组织使用了服务质量 (QoS) 基础结构，则媒体子系统应设计为在此现有基础结构中工作。 有关实现 QoS 的详细信息，请参阅操作文档中的[Lync Server 2013 中的 "管理服务质量（QoS）](lync-server-2013-managing-quality-of-service-qos.md) "。

  - 支持使用操作系统防火墙。 Lync Server 2013 管理操作系统防火墙的防火墙例外，Microsoft SQL Server 数据库软件除外。 有关 SQL Server 防火墙要求的详细信息，请参阅 SQL Server 文档。

  - 用于实现对外部用户访问的支持的外部接口必须位于单独的子网，*而不*是在与内部接口相同的网络上。

  - Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。

  - 发布 Lync Server 2013 累积更新：年 7 2013 月，Lync Server 2013 现在支持双重身份验证。 有关详细信息，请参阅[Lync Server 2013 中的双因素身份验证](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)。

  - 大多数内部服务器都需要定义为**开放身份验证**（OAuth）的证书类型。 您需要在 "Lync Server 部署向导" 的 "**请求"、"安装和分配证书**" 阶段请求和分配 OAuth 证书。 OAuth 证书密钥的最小大小为1024位。 如果你请求的证书的密钥长度小于2048位的长度，则可能会显示一条警告。 为了避免在强制执行密钥长度为2048而不是警告的情况下出现潜在问题，强烈建议始终为 OAuth 证书使用密钥长度2048。

  - Lync Server 2013 和 Microsoft Exchange Server 2010 Service Pack 1 （SP1）操作支持联邦信息处理标准（FIPS）140-2 算法如果 Windows Server 2008 R2 操作系统配置为使用 FIPS 140-2 算法系统加密。 若要实现 FIPS 支持，必须配置运行 Lync Server 2013 的每台服务器以支持它。 有关 FIPS 兼容的算法以及如何实现 FIPS 支持的详细信息，请参阅 Microsoft 知识库文章811833： "系统加密：使用 FIPS 兼容的算法来加密、哈希和签名安全设置在 Windows XP 和 Windows 的更高版本[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)中。 有关 FIPS 140-2 支持和 Exchange 2010 中的限制的详细信息，请参阅中的 "Exchange 2010 SP1 和对 FIPS [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)兼容的算法的支持"。

Lync Server 2013 要求在部署之前或期间安装特定组件的其他软件。 这包括适用于操作系统、可下载软件和在安装 Lync Server 2013 期间自动安装的软件的软件。 下面是可能需要的其他软件的列表：

  - Windows 更新

  - Windows Identity Foundation

  - Microsoft .NET 4.5 Framework

  - Microsoft Visual c + + 2012 可再发行组件
    
    <div>
    

    > [!NOTE]  
    > 安装 Lync Server 2013 时，将自动安装 Microsoft Visual c + + 2012 可再发行组件。 不应安装和使用任何其他版本。

    
    </div>

  - URL 重写模块版本2.0 可再发行组件

  - Windows Media Format Runtime

  - Windows PowerShell 版本3。0

  - Microsoft Silverlight 4 浏览器插件（Silverlight 4.0.50524.0 或 Lync Server 控制面板的最新版本）

  - Active Directory 域服务工具

某些软件要求仅适用于特定服务器角色或组件。 有关这些软件要求的详细信息，请参阅规划文档中[Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

</div>

<span> </span>

</div>

</div>

</div>

