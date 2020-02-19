---
title: Lync Server 2013：确定外部 A/V 防火墙和端口要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30492bed8deeb2a24dd136355e8f21f82e28a903
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42132565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>确定 Lync Server 2013 的外部 A/V 防火墙和端口要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

音频/视频（A/V）通信可能是一种复杂的。 由于在 A/V 中使用的协议的性质以及客户端和服务器使用这些协议的方式，因此有一个特殊的部分来说明客户端和服务器版本之间的差异。

使用下面的 A/V 防火墙和端口表来确定防火墙要求以及要打开的端口。 然后，检查网络地址转换 (NAT) 术语，因为可以通过多种不同方式实现 NAT。 有关防火墙端口设置的详细示例，请参阅[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)中的参考体系结构。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>音频/视频和媒体流量中的 UDP 和 TCP 的常规协议用法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>音频/视频传输</th>
<th>用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>音频和视频的首选传输层协议</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>音频和视频的回退传输层协议</p>
<p>适用于 Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 的应用程序共享所需的传输层协议</p>
<p>文件传输到 Lync Server 2010 和 Lync Server 2013 所需的传输层协议</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部用户访问的外部 A/V 防火墙端口要求

外部（和内部） SIP 和会议接口的防火墙端口要求是一致的，而不考虑客户端的版本或联合合作伙伴的版本。

而音频/视频边缘外部接口却并非如此。 对于使用 Office 通信服务器2007的联盟，A/V 边缘服务要求外部防火墙规则允许在50000至59999端口范围内的 RTP/TCP 和 RTP/UDP 通信在两个方向流动。 上表假定 Lync Server 2013 是主联合身份验证伙伴，并且将其配置为与列出的其他联合合作伙伴类型之一进行通信。

若要配置59999的音频/视频端口范围，必须考虑端口范围将包含用于与联合身份验证伙伴通信的源端口。 在详细情况下，请考虑从联合身份验证合作伙伴启动通信。 从59999范围内的 A/V 边缘服务端口进行的通信将连接到合作伙伴的 A/V 边缘服务的预期端口 TCP 443。 相反，到 A/V 边缘服务端口 TCP 443 的入站通信的源端口范围为 50000-59999。

防火墙管理的不同防火墙和策略可能只需要配置目标规则，或者可能需要配置源和目标。 如果您的要求仅适用于目标端口，音频/视频要求为：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>源 IP</th>
<th>目标 IP</th>
<th>目标端口</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任意</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任意</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


如果您的策略需要入站和出站防火墙规则定义，音频/视频要求为：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>源 IP</th>
<th>目标 IP</th>
<th>源端口</th>
<th>目标端口</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>TCP 50000-59999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>任意</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>任意</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office 通信服务器2007需要略有不同的配置。 TCP 和 UDP 端口范围为 50000-59999 必须打开入站和出站。 此要求仅适用于 Office Communicator 2007。 Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 仅要求 TCP 范围 50000-59999 打开出站。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>边缘服务的 NAT 要求

如果您选择为边缘服务配置不可路由的专用 IP 地址，则以下 NAT 要求适用：

  - NAT 仅可用于 DNS 负载平衡。 NAT 在硬件负载平衡（HLB）边缘拓扑中不受支持。

  - NAT 只能在外部边缘接口上使用。 内部边缘接口上不支持 NAT。

  - 对于传入和传出流量，NAT 必须是对称的。
    
  - 对于来自 Internet 的流量，NAT 必须将目标 IP 地址从 A/V 边缘服务的已启用 NAT 的公共 IP 地址更改为其外部 IP 地址。 源 IP 地址必须保持不变，以便 A/V 边缘服务可以找到最佳媒体路径。
  
  例如，在下图中的入站方向上，公用 IP 地址131.107.155.30 已更改为外部（专用） IP 地址10.45.16.10。 源 IP 地址保持不变。
  
  - 对于从 A/V 边缘服务到 Internet 的流量，NAT 必须将源 IP 地址从 A/V 边缘服务的外部 IP 地址更改为启用了 NAT 的公共 IP 地址。

例如，在下图中的出站方向上，外部（专用） IP 地址10.45.16.10 已更改为公用 IP 地址131.107.155.30。

**下图显示了 NAT 如何更改入站流量的目标 IP 地址和出站流量的源 IP 地址。**

![更改目标/源 IP 地址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "更改目标/源 IP 地址")

要点包括：

  - 入站到运行 A/V 边缘服务的服务器的通信，源 IP 地址不会发生更改，但目标 IP 地址将从131.107.155.30 更改为10.45.16.10 的转换 IP 地址。

  - 从运行 A/V 边缘服务的服务器出站的流量返回到工作站，源 IP 地址将从服务器的公共 IP 地址更改为运行 A/V 边缘服务的服务器的公共 IP 地址。 目标 IP 仍为工作站的公共 IP 地址。 在数据包离开第一个 NAT 设备出站后，NAT 设备上的规则会将运行 A/V 边缘服务的服务器的源 IP 地址更改为其公共 IP 地址（131.107.155.30）的服务器的 IP 地址（10.45.16.10）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

