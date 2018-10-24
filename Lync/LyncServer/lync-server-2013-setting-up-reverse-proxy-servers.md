---
title: Lync Server 2013：设置反向代理服务器
TOCTitle: 设置反向代理服务器
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398069(v=OCS.15)
ms:contentKeyID: 49311801
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 设置反向代理服务器

 

_**上一次修改主题：** 2016-12-08_

对于 Microsoft Lync Server 2013 边缘服务器部署，在外围网络中必须有 HTTPS 反向代理，外部客户端才能访问控制器和用户的主池中的 Lync Server 2013 Web 服务（在 Office Communications Server 中称为 *Web 组件*）。需要通过反向代理进行外部访问的部分功能包括：

  - 允许外部用户下载会议的会议内容。

  - 允许外部用户展开通讯组。

  - 允许远程用户从通讯簿服务下载文件。

  - 访问 Lync Web App 客户端。

  - 访问“电话拨入式会议设置”网页。

  - 允许外部设备连接到设备更新 Web 服务并获得更新。

  - 允许移动应用程序自动发现并使用来自 Internet 的移动 (Mcx) URL。

  - 允许 Lync 2013 客户端、Lync Windows 应用商店应用和 Lync 2013 移动客户端查找 Lync 发现（自动发现）URL 并使用统一通信 Web API (UCWA)。

建议配置 HTTP 反向代理以在所有池中发布所有 Web 服务。发布 https:// *ExternalFQDN*/\* 时会发布池的所有 IIS 虚拟目录。组织中的每个标准版 服务器、前端池、控制器或控制器池都需要一个发布规则。

此外，还需要发布简单 URL。如果组织中有 控制器 或 控制器池，HTTP 反向代理则会侦听对简单 URL 的 HTTP/HTTPS 请求，并且还会将它们代理到 控制器 或 控制器池 上的外部 Web 服务虚拟目录。如果尚未部署 控制器，则需要指定一个池来处理对简单 URL 的请求。（如果该池不是用户的主池，它会将这些请求重定向到用户主池上的 Web 服务。）简单 URL 可由专用 Web 发布规则进行处理，也可以将其添加到 控制器 Web 发布规则的公共名称中。您也需要发布外部自动发现服务 URL。

可使用 Microsoft Forefront Threat Management Gateway 2010、Microsoft Internet Security and Acceleration (ISA) 服务器 2006 SP1 或者带有应用程序请求路由的 Internet Information Server 7.0、7.5 或 8.0 (IIS ARR) 作为反向代理。本节中的各步骤详细介绍了如何配置 Forefront Threat Management Gateway 2010，这与配置 ISA Server 2006 的步骤几乎完全相同。也针对 IIS ARR 提供了相关指导。如果您使用的是其他反向代理，请参阅该产品的相关文档，并将此处定义的要求映射至其他反向代理中的相关功能。

> [!IMPORTANT]
> Internet Information Server 应用程序请求路由 (IIS ARR) 经过充分测试，是用于为 Lync Server 2010 和 Lync Server 2013 实施反向代理的支持选项。2012 年 11 月，Microsoft 停止了 ForeFront Threat Management Gateway 2010 (TMG) 的许可证出售。TMG 仍是完全受支持的产品，仍可供第三方在设备上销售。此外，许多第三方硬件负载平衡器和防火墙都提供反向代理支持。对于提供反向代理功能的硬件负载平衡器和防火墙，请咨询您的供应商，了解有关如何配置其产品以便为 Lync Server 提供反向代理支持的具体说明。您也可以查看第三方已提交给 Microsoft 的有关其产品的文档。第三方针对其解决方案提供支持。要查看积极提供解决方案的第三方，请参阅<a href="http://go.microsoft.com/fwlink/?linkid=268730">适合于 Microsoft Lync 的基础结构</a>。


以下主题和过程使用 Forefront Threat Management Gateway 2010 和 IIS ARR 作为部署和配置过程的基础。

  - [为 Lync Server 2013 配置 Web 场 FQDN](lync-server-2013-configure-web-farm-fqdns.md)

  - [在 Lync Server 2013 中配置网络适配器](lync-server-2013-configure-network-adapters.md)

  - [在 Lync Server 2013 中为 HTTP 反向代理请求和配置证书](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [在 Lync Server 2013 中为单个内部池配置 Web 发布规则](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [在 Lync Server 2013 中验证或配置 IIS 虚拟目录的身份验证和认证](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [在 Lync Server 2013 中为反向代理服务器创建 DNS 记录](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中验证能否通过反向代理进行访问](lync-server-2013-verify-access-through-your-reverse-proxy.md)

## 开始之前

要将 Forefront Threat Management Gateway 2010 成功部署为反向代理，您需要使用 Forefront Threat Management Gateway 2010 文档中定义的先决条件和硬件要求安装和配置一台服务器。在继续之前，请参阅以下主题集以正确配置硬件以及在该服务器上安装 Forefront Threat Management Gateway 2010。

  - [Forefront Threat Management Gateway (TMG) 2010](http://go.microsoft.com/fwlink/?linkid=291292)

  - [Forefront TMG 2010 硬件建议](http://go.microsoft.com/fwlink/?linkid=291293)

要成功地将 IIS ARR 部署为反向代理，请参阅以下主题以配置硬件和必备软件。

  - 要在 Windows Server 2008 或 Windows Server 2008 R2 上安装 IIS，请参阅[在 Windows Server 2008 或 Windows Server 2008 R2 上安装 IIS 7](http://go.microsoft.com/fwlink/?linkid=291296)

  - 要在 Windows Server 2012 上安装 IIS，请参阅[在 Windows Server 2012 上安装 IIS 8](http://go.microsoft.com/fwlink/?linkid=291297)

  - 要在 Windows Server 2012 R2 上安装 IIS，请参阅[在 Windows Server 2012 R2 上安装 IIS 8.5](http://go.microsoft.com/fwlink/?linkid=330687)

  - 要下载适用于 IIS 的应用程序请求路由扩展插件，请按照[应用程序请求路由 v2.5 下载](http://go.microsoft.com/fwlink/?linkid=291298)中的说明进行操作

  - 要安装 ARR，请按照[安装应用程序请求路由版本 2](http://go.microsoft.com/fwlink/?linkid=291299) 中的说明进行操作
    
> [!NOTE]
> 当前发布的说明适用于 ARR 2.0。对于扩展插件的安装，两个版本之间没有任何区别。

