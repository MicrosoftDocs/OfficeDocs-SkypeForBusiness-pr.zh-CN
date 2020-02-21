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
ms.openlocfilehash: 9f4ff853e3f31804e4bca55bd6a4576e25702b6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a>为 Lync Server 2013 设置反向代理服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-08_

对于 Microsoft Lync Server 2013 边缘服务器部署，外部客户端必须具有外围网络中的 HTTPS 反向代理，才能访问 Director 和用户的主池上的 Lync Server 2013 Web 服务（称为 Office 通信服务器中的*Web 组件*）。 需要通过反向代理进行外部访问的部分功能包括：

  - 允许外部用户下载会议的会议内容。

  - 允许外部用户展开通讯组。

  - 允许远程用户从通讯簿服务下载文件。

  - 访问 Lync Web App 客户端。

  - 访问“电话拨入式会议设置”网页。

  - 允许外部设备连接到设备更新 Web 服务并获得更新。

  - 使移动应用程序能够自动发现和使用来自 Internet 的移动（Mcx） Url。

  - 启用 Lync 2013 客户端、Lync Windows 应用商店应用和 Lync 2013 移动客户端，以找到 Lync 发现（自动发现） Url 并使用统一通信 Web API （UCWA）。

建议配置 HTTP 反向代理以在所有池中发布所有 Web 服务。 发布 https://ExternalFQDN/\*发布池的所有 IIS 虚拟目录。 组织中每个 Standard Edition Server、前端池、控制器或控制器池都需要一个发布规则。

此外，还需要发布简单 URL。 如果组织中有控制器或控制器池，HTTP 反向代理则会侦听对简单 URL 的 HTTP/HTTPS 请求，并且还会将它们代理到控制器或控制器池上的外部 Web 服务虚拟目录。 如果尚未部署控制器，则需要指定一个池来处理连接简单 URL 的请求。 （如果该池不是用户的主池，它会将这些请求重定向到用户主池上的 Web 服务。 ）简单 URL 可由专用 Web 发布规则进行处理，也可以将其添加到控制器 Web 发布规则的公共名称中。 此外，还需要发布外部自动发现服务 URL。

您可以使用 Microsoft Forefront 威胁管理网关2010、Microsoft Internet 安全和加速（ISA） Server 2006 SP1 或 Internet Information Server 7.0、7.5 或8.0，并使用应用程序请求路由（IIS ARR）作为反向代理。 本节中的详细步骤介绍了如何配置 Forefront 威胁管理网关2010，以及配置 ISA Server 2006 的步骤几乎完全相同。 还为 IIS ARR 提供了指南。 如果使用的是其他反向代理，请参阅该产品的文档，并将此处定义的要求映射到其他反向代理中的关联功能。

<div>


> [!IMPORTANT]  
> Internet Information Server 应用程序请求路由（IIS ARR）是为 Lync Server 2010 和 Lync Server 2013 实施反向代理的经过完全测试且受支持的选项。 在11月，2012，Microsoft 停止了 ForeFront 威胁管理网关2010或 TMG 的许可证销售。 TMG 仍是完全受支持的产品，仍可用于第三方销售的设备上的销售。 此外，许多第三方硬件负载平衡器和防火墙提供反向代理支持。 对于提供反向代理功能的硬件负载平衡器和防火墙，请与您的供应商联系，以获取有关如何配置其产品以为 Lync Server 提供反向代理支持的具体说明。 您还可以查看已将其产品的文档提交给 Microsoft 的第三方。 由第三方为其解决方案提供支持。 若要查看在提供解决方案时处于活动状态的第三方，请参阅<A href="https://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 的基础结构限定</A>。



</div>

下面的主题和过程将 Forefront 威胁管理网关2010和 IIS ARR 用作部署和配置过程的基础。

  - [为 Lync Server 2013 配置 web 场 Fqdn](lync-server-2013-configure-web-farm-fqdns.md)

  - [在 Lync Server 2013 中配置网络适配器](lync-server-2013-configure-network-adapters.md)

  - [在 Lync Server 2013 中为您的反向 HTTP 代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [在 Lync Server 2013 中为单个内部池配置 web 发布规则](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和证书](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [在 Lync Server 2013 中为反向代理服务器创建 DNS 记录](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [通过你在 Lync Server 2013 中的反向代理验证访问权限](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a>开始之前

若要成功部署 Forefront 威胁管理网关2010作为反向代理，您需要使用 Forefront 威胁管理网关2010文档中定义的先决条件和硬件要求设置和配置服务器。 在继续之前，请参阅以下主题设置为正确配置硬件并在服务器上安装 Forefront 威胁管理网关2010。

  - <span></span>  
    [Forefront Threat Management Gateway (TMG) 2010](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [Forefront TMG 2010 硬件建议](https://go.microsoft.com/fwlink/?linkid=291293)

若要成功地将 IIS ARR 部署为反向代理，请查看以下主题以配置硬件和必备软件。

  - <span></span>  
    若要在 Windows Server 2008 或 Windows Server 2008 R2 上安装 IIS，请参阅[在 Windows server 2008 或 Windows server 2008 r2 上安装 iis 7](https://go.microsoft.com/fwlink/?linkid=291296)

  - <span></span>  
    若要在 Windows Server 2012 上安装 IIS，请参阅[在 Windows server 上安装 iis 8 2012](https://go.microsoft.com/fwlink/?linkid=291297)

  - <span></span>  
    若要在 Windows Server 2012 R2 上安装 IIS，请参阅[在 Windows server 上安装 iis 8.5 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)

  - <span></span>  
    若要下载 IIS 的应用程序请求路由扩展插件，请按照[应用程序请求路由](https://go.microsoft.com/fwlink/?linkid=291298)中的说明下载

  - <span></span>  
    若要安装 ARR，请参阅[安装应用程序请求路由版本 2](https://go.microsoft.com/fwlink/?linkid=291299)中的说明
    
    <div>
    

    > [!NOTE]  
    > 当前发布的说明适用于 ARR 2.0。 对于扩展安装，两个版本之间没有区别。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

