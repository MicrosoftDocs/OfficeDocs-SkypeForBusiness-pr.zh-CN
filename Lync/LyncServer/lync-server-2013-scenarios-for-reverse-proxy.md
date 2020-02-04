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
ms.openlocfilehash: 82e1dffa55d6af8d131d3a94710c76277cfa75d9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764960"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的反向代理方案

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-21_

Lync Server 2013 中需要 "反向代理"，以便提供对服务和资源的访问权限，例如会议和电话拨入式简单 Url、通讯簿、会议内容、通讯组列表扩展、移动服务等。 Lync Server 2013 中的典型反向代理方案是允许外部客户端（例如，桌面客户端或 Lync Web App 客户端）访问 Director 或前端服务器外部 Web 服务。

**反向代理和外部 web 服务**

![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")

在计划阶段，在 Lync Server 2013 部署中定义反向代理的要求。 反向代理启用以下外部客户端的功能访问：

  - Microsoft Lync 2013 桌面客户端

  - Microsoft Lync Web App

  - Microsoft Lync Mobile

  - Lync Windows 应用商店应用

规划 Lync Server 2013 部署时，将 Lync Server 2013 的实际要求映射到反向代理功能。

1.  外部客户端将连接到端口 TCP 443 上的反向代理，并且将使用安全套接字层（SSL）或传输层安全（TLS）。 Microsoft Lync 移动客户端可以连接到 TCP 80，但仅在执行与 Lync 探索服务的初始连接时，并且管理员已配置了正确的域名系统（DNS） CNAME （或别名）记录，并接受此将不会加密通信。

2.  Lync Server 2013 外部 web 服务（部署在前端服务器和/或控制器上）期望通过端口 TCP 4443 上的反向代理建立连接，并且预期连接将是 SSL/TLS。
    
    <div>
    

    > [!IMPORTANT]  
    > 用于外部 web 服务的建议默认侦听端口为 HTTP 流量的 TCP 8080，而 TCP 流量为 TCP 4443。 拓扑生成器提供了一种替代默认设置和定义你自己的外部 web 服务侦听端口的机会。 请务必注意，反向代理与外部 web 服务进行通信，并且外部客户端与反向代理通信。 外部客户端与端口 TCP 443 上的反向代理通信，但你可以重新定义反向代理与的外部 web 服务进行通信的端口。 拓扑生成器中用于替代 web 服务的默认侦听端口的选项使你能够解决基础结构中可能出现的侦听端口冲突。

    
    </div>

3.  Lync Server 2013 外部 web 服务需要来自客户端的未修改的主机标头来标识客户端尝试使用的服务和 web 服务器目录。 请求应类似于来自反向代理的请求

4.  外部 web 服务使用已定义的 web 服务器虚拟目录（vDir），这些虚拟目录提供向客户端提供的服务。 特定的外部身份 web 服务包括：
    
      - 网络会议会议的 "会面" vDir
    
      - 手机接入和电话会议的 "拨入" vDir
    
      - Lync Windows 应用商店应用、Lync Mobile 和桌面客户端 Lync 2013 的 "自动发现" vDir。 Lync Server 2013 中的自动发现由 DNS 名称 "lyncdiscover" 识别
    
      - 未定义的服务由外部客户端通过直接调用外部 web 服务来访问。 例如，通讯组扩展（DLX）和通讯簿服务（ABS）通过直接调用外部 web 服务和关联的 vDirs 来访问。 客户端知道 vDir 的实际路径，并基于此信息构造一个统一的记录定位器（URL）。 客户端将使用类似于的 URL 访问通讯簿服务`https://externalweb.contoso.com/abs/handler`
    
      - 会议已定义并配置为 Lync Server 拓扑的一部分时的 Office Web Apps 服务器
        
        <div>
        

        > [!NOTE]  
        > Office Web Apps 服务器是单独的角色服务器，未配置为外部 Web 服务的一部分。 此服务器为客户端访问单独发布。

        
        </div>

5.  为每个服务定义 SSL 桥接。 将外部端口 TCP 443 映射到 TCP 4443 的外部 web 服务端口。 对于未加密的 HTTP，端口 TCP 80 映射到外部 web 服务端口 TCP 8080

6.  计划反向代理侦听器以发布 web 服务器资源

7.  根据将提供的服务请求和配置反向代理的证书。 如果配置了正确的主题备用名称，则该证书可以由反向代理服务器上的所有已配置侦听器共享

可用于计划反向代理部署的资源：

  - [Lync Server 2013 中的数据收集](lync-server-2013-data-collection.md)

  - [Lync Server 2013 中的证书摘要 - 反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Lync Server 2013 中的端口摘要 - 反向代理](lync-server-2013-port-summary-reverse-proxy.md)

  - [Lync Server 2013 中的 DNS 摘要 - 反向代理](lync-server-2013-dns-summary-reverse-proxy.md)

</div>

<span> </span>

</div>

</div>

</div>

