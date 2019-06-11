---
title: 'Lync Server 2013: 反向代理的配置要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuration requirements for reverse proxy
ms:assetid: c37d688a-28e4-4822-80cc-6add59c71052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945651(v=OCS.15)
ms:contentKeyID: 51541518
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0367ea79a0f3de6ad716f18aab980e9d9442e148
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuration-requirements-for-reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中反向代理的配置要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-05_

Lync Server 2013 对来自外部客户端的通信的一些要求, 这些要求随后传递到托管在 Director、Director 池、前端服务器或前端池上的外部 Web 服务。 如果你向用户提供会议, 则反向代理还负责发布 Office Web Apps 服务器。

<div>


> [!NOTE]  
> Lync Server 2013 不指定必须使用的特定反向代理。 Lync Server 2013 仅定义反向代理必须能够执行的操作要求。 通常, 你的基础结构中已部署的反向代理可能能够满足这些要求。



</div>

<div>

## <a name="reverse-proxy-requirements"></a>反向代理要求

Lync Server 2013 预期执行反向代理的功能操作是:

  - 使用安全套接字层 (SSL) 和传输层安全性 (TLS), 使用从公共证书颁发机构获取的证书连接到 Director、Director pool、前端服务器或前端池的已发布外部 Web 服务。 控制器和前端服务器可以使用硬件负载平衡器在负载平衡的池中。

  - 可以使用证书进行加密来发布内部网站, 或通过未加密的方式发布它们 (如果需要)。

  - 可以通过使用完全限定的域名 (FQDN) 在外部发布内部托管的网站。

  - 能够发布托管网站的所有内容。 默认情况下, 你可以使用** / **该指令, 大多数 web 服务器可以识别该指令, 这意味着 "在 web 服务器上发布所有内容"。 您也可以修改指令, 例如 **/Uwca/\***, 这意味着 "在虚拟目录 Ucwa 下发布所有内容"。

  - 必须可配置为需要安全套接字层 (SSL) 和/或传输层安全 (TLS) 连接, 客户端从已发布的网站请求内容。

  - 必须接受带有主题备用名称 (SAN) 条目的证书。

  - 必须能够允许将证书绑定到侦听器或接口, 外部 web 服务 FQDN 将解析该侦听器。 侦听器配置优于接口配置。 可在一个接口上配置多个侦听器。

  - 必须允许进行主机头处理的配置。 通常, 发出请求的客户端发送的原始主机标头必须透明地传递, 而不是由反向代理进行修改。

  - 将 SSL 和 TLS 流量从一个外部定义的端口 (例如 TCP 443) 桥接到另一个已定义的端口 (例如 TCP 4443)。 反向代理可能会在接收时解密数据包, 然后在发送时 reencrypt 数据包。

  - 将未加密的 TCP 流量从一个端口 (例如 TCP 80) 桥接到另一个端口 (例如 TCP 8080)。

  - 允许配置或接受 NTLM 身份验证, 无身份验证和传递身份验证。

</div>

</div>

<span> </span>

</div>

</div>

</div>

