---
title: Lync Server 2013：反向代理方案
TOCTitle: 反向代理方案
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204691(v=OCS.15)
ms:contentKeyID: 49312072
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的反向代理方案

 

_**上一次修改主题：** 2013-01-21_

反向代理是 Lync Server 2013 中必需的，用于提供对服务和资源的访问，例如会议和电话拨入式简单 URL、通讯簿、会议内容、通讯组列表扩展、移动服务等。 Lync Server 2013 中典型的反向代理方案是允许外部客户端（例如桌面客户端或 Lync Web App 客户端）访问 控制器或 前端服务器外部 Web 服务。

**反向代理和外部 Web 服务**

![反向代理和外部 Web 服务](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "反向代理和外部 Web 服务")

在规划阶段，您在 Lync Server 2013 部署中定义反向代理的要求。反向代理支持访问下列外部客户端的功能：

  - Microsoft Lync 2013 桌面客户端

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows 应用商店应用

规划 Lync Server 2013 部署时，将 Lync Server 2013 的实际要求映射到反向代理功能。

1.  外部客户端将连接至端口 TCP 443 上的反向代理，并将使用安全套接字层 (SSL) 或传输层安全性 (TLS)。仅当执行至 Lync 发现服务的初始连接，并且管理员已配置正确的域名系统 (DNS) CNAME（或别名）记录并同意此通信将不会被加密时， Microsoft Lync Mobile 客户端才可以连接端口 TCP 80。

2.  Lync Server 2013 外部 Web 服务（部署在 前端服务器和/或 控制器上）将连接至端口 TCP 4443 上的反向代理，并将使用 SSL/TLS 连接。
    
    > [!IMPORTANT]
    > 建议对于 HTTP 流量，默认的外部 Web 服务侦听端口为 TCP 8080，而对于 HTTPS 流量则为 TCP 4443。您可以使用 拓扑生成器覆盖默认设置并定义自己的外部 Web 服务侦听端口。务必注意，反向代理与外部 Web 服务通信，而外部客户端与反向代理通信。外部客户端与端口 TCP 443 上的反向代理通信，但您可以重新定义反向代理与外部 Web 服务通信所在的端口。通过 拓扑生成器中覆盖默认的 Web 服务侦听端口的选项，您可以解决基础结构中可能产生的侦听端口冲突。


3.  Lync Server 2013 外部 Web 服务将从客户端中获得未经修改的主机头，用于识别客户端正在尝试使用的服务和 Web 服务器目录。请求应看似来自反向代理

4.  外部 Web 服务使用定义的 Web 服务器虚拟目录 (vDir) 提供客户端服务。特定的外部可识别的 Web 服务包括：
    
      - 用于 Web 会议的“Meet”vDir
    
      - 用于电话访问和电话会议的“Dialin”vDir
    
      - 用于 Lync Windows 应用商店应用、Lync Mobile 和桌面客户端 Lync 2013 的“Autodiscover”vDir。Lync Server 2013 中的自动发现是因 DNS 名称“lyncdiscover”而为大家所熟知
    
      - 未定义的服务由外部客户端通过将呼叫定向到外部 Web 服务进行访问。例如，通过将呼叫定向到外部 Web 服务和关联的 vDir 来访问通讯组扩展 (DLX) 和通讯簿服务 (ABS)。客户端知道 vDir 的实际路径，并基于此信息构造一个统一记录定位器 (URL)。客户端将使用类似于 `https://externalweb.contoso.com/abs/handler` 的 URL 访问通讯簿服务
    
      - Office Web Apps Server，当会议被定义并配置为 Lync Server 拓扑的一部分时
        
        > [!NOTE]  
		> Office Web Apps Server 是一个单独的角色服务器，并未被配置为外部 Web 服务的一部分。此服务器单独发布用于客户端访问。
        


5.  定义每个服务的 SSL 桥接。外部端口 TCP 443 映射到 TCP 4443 的外部 Web 服务端口。对于未加密的 HTTP，端口 TCP 80 映射到外部 Web 服务端口 TCP 8080

6.  规划反向代理侦听器来发布 Web 服务器资源

7.  基于将提供的服务，请求并配置反向代理的证书。如果配置有正确的使用者替代名称，则此证书可由反向代理服务器上所有已配置的侦听器共享

可用于规划反向代理部署的资源：

  - [Lync Server 2013 中的数据收集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 中的证书摘要 - 反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Lync Server 2013 中的端口摘要 - 反向代理](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013 中的 DNS 摘要 - 反向代理](lync-server-2013-dns-summary-reverse-proxy.md)

