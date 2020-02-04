---
title: Lync Server 2013：设置反向代理服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbc6e0aee918d08f47c6df88f91493cd62ae6a3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>为 Lync Server 2013 设置反向代理服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-05-08_

对于 Microsoft Lync Server 2013 Edge 服务器部署，外部客户端可以使用外围网络中的 HTTPS 反向代理访问 Lync Server 2013 Web 服务（称为 Office 通信服务器中的*Web 组件*）和用户的主池。 需要通过反向代理进行外部访问的一些功能包括以下内容：

  - 允许外部用户为你的会议下载会议内容。

  - 使外部用户能够展开通讯组。

  - 使远程用户能够从通讯簿服务下载文件。

  - 访问 Lync Web App 客户端。

  - 访问 "电话拨入式会议设置" 网页。

  - 启用外部设备连接到设备更新 web 服务并获取更新。

  - 使移动应用程序能够自动发现和使用来自 Internet 的移动（Mcx） Url。

  - 启用 Lync 2013 客户端、Lync Windows 应用商店应用和 Lync 2013 移动客户端以找到 Lync 发现（自动发现） Url 和使用统一通信 Web API （UCWA）。

我们建议你将 HTTP 反向代理配置为发布所有池中的所有 Web 服务。 发布 https://ExternalFQDN/\*发布池的所有 IIS 虚拟目录。 您的组织中的每个标准版服务器、前端池或控制器或控制器池都需要一个发布规则。

此外，你需要发布简单的 Url。 如果组织具有 Director 或控制器池，则 HTTP 反向代理将侦听对简单 Url 的 HTTP/HTTPS 请求，并将它们代理到 Director 或 Director 池中的外部 Web 服务虚拟目录。 如果尚未部署 Director，则需要指定一个池来处理简单 Url 的请求。 （如果这不是用户的主池，它将向前重定向到用户主池中的 Web 服务）。 简单 Url 可以由专用的 web 发布规则处理，也可以将其添加到 Director web 发布规则的公共名称中。 你还需要发布外部自动发现服务 URL。

你可以使用 Microsoft Forefront 威胁管理网关2010、Microsoft Internet 安全和加速（ISA） Server 2006 SP1 或 Internet Information Server 7.0、7.5 或8.0，使用应用程序请求路由（IIS ARR）作为反向代理。 本部分中的详细步骤介绍了如何配置 Forefront 威胁管理网关2010，以及配置 ISA 服务器2006的步骤几乎完全相同。 还提供了有关 IIS ARR 的指南。 如果你使用的是不同的反向代理，请参阅该产品的文档，并将此处定义的要求映射到其他反向代理中的关联功能。

<div>


> [!IMPORTANT]  
> Internet 信息服务器应用程序请求路由（IIS ARR）是一种经过完全测试且受支持的选项，可用于实现 Lync Server 2010 和 Lync Server 2013 的反向代理。 在2012年11月，Microsoft 对 ForeFront 威胁管理网关2010或 TMG 的许可证的销售不会不复存在。 TMG 仍是完全受支持的产品，仍可在第三方销售的装置上销售。 另外，许多第三方硬件负载平衡器和防火墙提供反向代理支持。 对于提供反向代理功能的硬件负载平衡器和防火墙，请咨询您的供应商，了解有关如何配置其产品以提供 Lync 服务器的反向代理支持的具体说明。 您还可以查看已向 Microsoft 提交其产品文档的第三方。 支持由第三方提供，供其解决方案使用。 若要查看提供解决方案时处于活动状态的第三方，请参阅<A href="http://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 合格的基础结构</A>。



</div>

以下主题和过程将 Forefront 威胁管理网关2010和 IIS ARR 用作部署和配置过程的基础。

  - [为 Lync Server 2013 配置 Web 场 FQDN](lync-server-2013-configure-web-farm-fqdns.md)

  - [在 Lync Server 2013 中配置网络适配器](lync-server-2013-configure-network-adapters.md)

  - [在 Lync Server 2013 中为 HTTP 反向代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [在 Lync Server 2013 中为单个内部池配置 Web 发布规则](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和认证](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [在 Lync Server 2013 中为反向代理服务器创建 DNS 记录](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中验证能否通过反向代理进行访问](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>开始之前

若要成功将 Forefront 威胁管理网关2010作为反向代理部署，你需要使用 Forefront 威胁管理网关2010文档中定义的先决条件和硬件要求设置和配置服务器。 在继续操作之前，请参阅以下主题设置以正确配置硬件并在服务器上安装 Forefront 威胁管理网关2010。

  - <span></span>  
    [Forefront 威胁管理网关（TMG）2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 硬件建议](http://go.microsoft.com/fwlink/?linkid=291293)

若要将 IIS ARR 成功部署为反向代理服务器，请参阅以下主题以配置硬件和必备软件。

  - <span></span>  
    若要在 Windows Server 2008 或 Windows Server 2008 R2 上安装 IIS，请参阅[在 Windows server 2008 或 Windows server 2008 r2 上安装 iis 7](http://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    若要在 Windows Server 2012 上安装 IIS，请参阅[在 Windows server 2012 上安装 iis 8](http://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    若要在 Windows Server 2012 R2 上安装 IIS，请参阅[在 Windows server 上安装 iis 8.5 2012 R2](http://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    若要下载 IIS 的应用程序请求路由扩展，请按照[应用程序请求路由选择 v 2.5 下载](http://go.microsoft.com/fwlink/?linkid=291298)中的说明进行操作。

  - <span></span>  
    若要安装 ARR，请参阅[安装应用程序请求路由版本 2](http://go.microsoft.com/fwlink/?linkid=291299)中的说明
    
    <div>
    

    > [!NOTE]  
    > 当前发布的说明适用于 ARR 2.0。 对于扩展的安装，两个版本之间没有区别。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

