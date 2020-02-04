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
ms.openlocfilehash: 3d5519ef37ff334ddf196e94b40aa7df14d69d25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>确定 Lync Server 2013 的外部 A/V 防火墙和端口要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

音频/视频（A/V）通信可能很复杂。 由于在 A/V 中使用的协议的性质以及客户端和服务器使用这些协议的方式，因此有一个特殊的部分可以帮助解释客户端和服务器版本之间的差异。

使用以下 A/V 防火墙和端口表确定防火墙要求和要打开的端口。 然后，查看网络地址转换（NAT）术语，因为 NAT 可以采用多种不同的方式实现。 有关防火墙端口设置的详细示例，请参阅[Lync Server 2013 中用于外部用户访问的方案](lync-server-2013-scenarios-for-external-user-access.md)中的参考体系结构。

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>音频/视频和媒体流量中的 UDP 和 TCP 的常规协议用法

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>音频/视频传输</th>
<th>使用</th>
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
<p>Office 通信服务器的应用程序共享所需的传输层协议 2007 R2、Lync Server 2010 和 Lync Server 2013</p>
<p>将文件传输到 Lync Server 2010 和 Lync Server 2013 所需的传输层协议</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>外部用户访问的外部 A/V 防火墙端口要求

无论客户端的版本或联合合作伙伴的版本如何，外部（和内部） SIP 和会议界面的防火墙端口要求都是一致的。

音频/视频边缘外部界面同样不成立。 对于使用 Office 通信服务器2007的联盟，A/V 边缘服务要求外部防火墙规则允许50000至59999端口范围内的 RTP/TCP 和 RTP/UDP 流量双向流动。 上表假设 Lync Server 2013 是主联合身份验证伙伴，并且配置为与列出的其他联合合作伙伴类型之一进行通信。

配置 50000-59999 的音频/视频端口范围必须考虑到端口范围将包含用于与联合身份验证伙伴通信的源端口。 在详细信息中，请考虑从联合身份验证伙伴发起通信。 从59999范围内的 A/V 边缘服务端口进行的通信将连接到合作伙伴的 A/V 边缘服务的预期端口 TCP 443。 相反，到 A/V 边缘服务端口 TCP 443 的入站流量将具有59999中的源端口。

防火墙管理的不同防火墙和策略可能只需要配置目标规则，也可能需要配置源和目标。 如果您的要求仅适用于目的地端口，音频/视频要求如下：


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
<td><p>任何</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


如果你的策略需要入站和出站防火墙规则定义，音频/视频要求如下：


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
<td><p>任何</p></td>
<td><p>TCP 50,000-59,999</p></td>
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
<td><p>任何</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Microsoft Office 通信服务器2007需要稍有不同的配置。 TCP 和 UDP 端口范围59999必须打开入站和出站。 此要求仅适用于 Office Communicator 2007。 Office 通信服务器 2007 R2、Lync Server 2010 和 Lync Server 2013 仅要求 TCP 范围 50000-59999 打开出站。



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Edge 服务的 NAT 要求

如果你选择为 Edge 服务配置不可路由的专用 IP 地址，则以下 NAT 要求适用：

  - NAT 仅可与 DNS 负载平衡配合使用。 NAT 不受硬件负载平衡（HLB）边缘拓扑支持。

  - NAT 仅可在外部边缘接口上使用。 NAT 在内部边缘接口上不受支持。

  - 对于传入和传出通信，NAT 必须是对称的。
    
  - 对于来自 Internet 的流量，NAT 必须将目标 IP 地址从 A/V 边缘服务的支持 NAT 的公共 IP 地址更改为其外部 IP 地址。 源 IP 地址必须保持不变，以便 A/V 边缘服务可以找到最佳媒体路径。
  
  例如，在下图中的入站方向上，公共 IP 地址131.107.155.30 已更改为外部（专用） IP 地址10.45.16.10。 源 IP 地址保持不变。
  
  - 对于从 A/V 边缘服务到 Internet 的流量，NAT 必须将源 IP 地址从 A/V 边缘服务的外部 IP 地址更改为启用 NAT 的公共 IP 地址。

例如，在下图中的出站方向上，外部（专用） IP 地址10.45.16.10 已更改为公共 IP 地址131.107.155.30。

**下图显示了 NAT 如何更改入站流量的目标 IP 地址和出站流量的源 IP 地址。**

![更改目标/源 IP 地址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "更改目标/源 IP 地址")

关键点是：

  - 入站到运行 A/V 边缘服务的服务器的通信，源 IP 地址不会更改，但目标 IP 地址会从131.107.155.30 更改为10.45.16.10 的已转换 IP 地址。

  - 从运行 A/V 边缘服务的服务器传出的流量返回到工作站，源 IP 地址从服务器的公共 IP 地址更改为运行 A/V 边缘服务的服务器的公共 IP 地址。 目标 IP 将保留工作站的公共 IP 地址。 在数据包离开第一个 NAT 设备出站后，NAT 设备上的规则会将运行 A/V 边缘服务的外部接口 IP 地址（10.45.16.10）的服务器的源 IP 地址更改为其公共 IP 地址（131.107.155.30）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

