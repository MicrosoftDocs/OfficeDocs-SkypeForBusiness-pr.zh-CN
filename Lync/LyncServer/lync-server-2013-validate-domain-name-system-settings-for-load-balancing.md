---
title: 'Lync Server 2013: 验证用于负载平衡的域名系统设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d56219dc36859eb37a766a94f827fb0c28a9909
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>验证 Lync Server 2013 中的负载平衡的域名系统设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-02_

若要支持 DNS 负载平衡使用的 FQDN, 必须预配 DNS 以将池 FQDN (如 pool01.contoso.com) 解析为池中所有服务器的 IP 地址 (例如192.168.1.1、192.168.1.2 等)。 应仅包含当前已部署的服务器的 IP 地址。

此外, 如果你正在为 Edge 池使用 DNS 负载平衡, 则需要以下 DNS 条目:

  - 对于 Lync Server Access Edge 服务, 池中的每个服务器都必须有一个条目。 每个条目都必须将 Lync Server Access Edge 服务 (例如, sip.contoso.com) 的 FQDN 解析为池中的一个边缘服务器上的 Lync Server 访问边缘服务的 IP 地址。

  - 对于 Lync Server Web 会议 Edge 服务, 池中的每个服务器都必须有一个条目。 每个条目都必须将 Lync Server Web 会议 Edge 服务 (例如, webconf.contoso.com) 的 FQDN 解析为池中的一个边缘服务器上的 Lync Server Web 会议边缘服务的 IP 地址。

  - 对于 Lync Server 音频/视频边缘服务, 池中的每个服务器都必须有一个条目。 每个条目都必须将 Lync Server 音频/视频边缘服务 (例如, av.contoso.com) 的 FQDN 解析为池中的一个边缘服务器上的 Lync Server 音频/视频边缘服务的 IP 地址。

  - 如果要在 Edge 池的内部接口上使用 DNS 负载平衡, 则必须添加一个 DNS 记录, 这会将边缘池的内部 FQDN 解析为池中每个服务器的 IP 地址。

若要验证 DNS 是否为 DNS 负载平衡返回正确的值, 应使用 nslookup 工具。 若要使用 nslookup 返回 DNS 记录的所有值, 请运行命令:

`nslookup <FQDN >`

你可以针对 DNS 负载平衡配置中使用的每个 FQDN 运行此命令, 以验证 DNS 负载平衡的每个记录集是否返回了所有正确的条目。

</div>

<span> </span>

</div>

</div>

</div>

