---
title: Lync Server 2013：反向代理方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for reverse proxy
ms:assetid: 13108f59-a660-4ff1-8404-079d1cb646f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204691(v=OCS.15)
ms:contentKeyID: 48183468
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 767df1e427cd29e9437b4bd04d2859b382b48267
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510829"
---
# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向代理方案

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-21_

Lync Server 2013 中需要反向代理，以提供对服务和资源（如会议和拨入式简单 Url、通讯簿、会议内容、通讯组列表展开、移动服务等）的访问权限。 Lync Server 2013 中的典型反向代理方案是允许外部客户端 (例如，桌面客户端或 Lync Web App 客户端) 对控制器或前端服务器外部 Web 服务的访问权限。

**反向代理和外部 web 服务**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

在规划阶段，在 Lync Server 2013 部署中定义反向代理的要求。 反向代理启用对以下外部客户端的功能的访问：

  - Microsoft Lync 2013 桌面客户端

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows 应用商店应用

在规划 Lync Server 2013 部署时，您需要将 Lync Server 2013 的实际要求映射到反向代理功能。

1.  外部客户端将连接到端口 TCP 443 上的反向代理，并将使用安全套接字层 (SSL) 或传输层安全性 (TLS) 。 Microsoft Lync 移动客户端可以在端口 TCP 80 上进行连接，但仅当执行到 Lync 发现服务的初始连接时，管理员已将正确的域名系统配置 (DNS) CNAME (或别名) 记录，并接受此通信不会加密。

2.  Lync Server 2013 在前端服务器和/或) 控制器上部署的外部 web 服务 (预期从端口 TCP 4443 上的反向代理进行连接，并且预期该连接将为 SSL/TLS。
    
    <div>
    

    > [!IMPORTANT]  
    > 推荐的外部 web 服务的默认侦听端口为 TCP 8080，用于 HTTP 流量，TCP 4443 用于 HTTPS 流量。 拓扑生成器提供了重写默认值并为外部 web 服务定义您自己的侦听端口的机会。 请务必注意，反向代理与外部 web 服务通信，而外部客户端与反向代理通信。 外部客户端与端口 TCP 443 上的反向代理通信，但您可以重新定义反向代理与中的外部 web 服务进行通信的端口。 拓扑生成器中用于替代 web 服务的默认侦听端口的选项允许您解决基础结构中可能出现的侦听端口冲突。

    
    </div>

3.  Lync Server 2013 外部 web 服务需要来自客户端的未修改的主机标头，以标识客户端尝试使用的服务和 web 服务器目录。 请求应像来自反向代理一样显示

4.  外部 web 服务使用已定义的 web 服务器虚拟目录 (vDir) ，提供向客户端提供的服务。 特定的外部身份 web 服务包括：
    
      - "开会" vDir for web 会议会议
    
      - "拨入" vDir 用于电话访问和电话会议
    
      - Lync Windows 应用商店应用、Lync Mobile 和桌面客户端 Lync 2013 的 "自动发现" vDir。 Lync Server 2013 中的自动发现由 DNS 名称 "lyncdiscover." 识别
    
      - 未定义的服务通过直接调用外部 web 服务的外部客户端进行访问。 例如，通讯组扩展 (DLX) 和通讯簿服务 (ABS) 通过直接调用外部 web 服务和关联的 vDirs 来访问。 客户端知道 vDir 的实际路径，并根据此信息构造一个统一的记录定位器 (URL) 。 客户端将使用类似于的 URL 访问通讯簿服务 `https://externalweb.contoso.com/abs/handler`
    
      - 会议被定义并配置为 Lync Server 拓扑的一部分时的 Office Web Apps Server
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps Server 是一个单独的角色服务器，不是作为外部 Web 服务的一部分进行配置的。 此服务器单独发布，以供客户端访问。

        
        </div>

5.  为每个服务定义 SSL 桥接。 将外部端口 TCP 443 映射到 TCP 4443 的外部 web 服务端口。 对于未加密的 HTTP，端口 TCP 80 映射到外部 web 服务端口 TCP 8080

6.  规划反向代理侦听程序以发布 web 服务器资源

7.  根据将提供的服务，为反向代理请求和配置证书。 如果配置了正确的主题备用名称，则此证书可以由反向代理服务器上的所有已配置侦听器共享

可用于规划反向代理部署的资源：

  - [Lync Server 2013 中的数据收集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 中的证书摘要-反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Lync Server 2013 中的端口摘要-反向代理](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013 中的 DNS 摘要-反向代理](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

