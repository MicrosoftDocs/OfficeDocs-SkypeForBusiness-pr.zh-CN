---
title: Lync Server 2013：确定外部 A/V 防火墙和端口要求
TOCTitle: 确定外部 A/V 防火墙和端口要求
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425882(v=OCS.15)
ms:contentKeyID: 49312559
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确定 Lync Server 2013 的外部 A/V 防火墙和端口要求

 

_**上一次修改主题：** 2015-03-09_

音频/视频 (A/V) 通信可能比较复杂。由于 A/V 中使用的协议的特性以及客户端和服务器使用协议的方式，需要专门一节来解释客户端和服务器版本之间的差异。

使用以下 A/V 防火墙表和端口表来确定防火墙要求和要打开的端口。然后，检查网络地址转换 (NAT) 术语，因为可以通过多种不同方式实现 NAT。有关防火墙端口设置的详细示例，请参阅 [Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)中的参考体系结构。

### 音频/视频和媒体通信中 UDP 和 TCP 的一般协议用法

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
<td><p>首选的音频和视频传输层协议</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>回退音频和视频传输层协议</p>
<p>应用程序共享到 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013 所需的传输层协议</p>
<p>文件传输到 Lync Server 2010 和 Lync Server 2013 所需的传输层协议</p></td>
</tr>
</tbody>
</table>


## 外部用户访问的外部 A/V 防火墙端口要求

无论您客户端的版本或联盟伙伴的版本如何，外部（和内部）SIP 和会议接口的防火墙端口要求都是一致的。

而音频/视频边缘外部接口却并非如此。对于与 Office Communications Server 2007 的联盟，A/V 边缘服务要求外部防火墙规则允许 50,000 到 59,999 端口范围中的 RTP/TCP 和 RTP/UDP 流量双向流动。上表假定 Lync Server 2013 是主要联盟伙伴，并将其配置为与列出的其他类型的联盟伙伴之一进行通信。

配置 50,000-59,999 的音频/视频端口范围必须考虑端口范围将包含与联盟伙伴通信的源端口。具体来说，请考虑从联盟伙伴启动通信。来自 50,000-59,999 范围中 A/V 边缘服务端口的通信将连接到合作伙伴 A/V 边缘服务的预期端口 TCP 443。相反，到 A/V 边缘服务端口 TCP 443 的入站通信将具有 50,000-59,999 范围内的源端口。

不同的防火墙和防火墙管理策略可能只需要配置目标规则，也可能需要同时配置源和目标。如果您的要求只是用于目标端口，则音频/视频要求为：


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


如果您的策略需要入站和出站防火墙规则定义，则音频/视频要求为：


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
<td><p>任意</p></td>
<td><p>A/V 边缘服务接口</p></td>
<td><p>任意</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


> [!IMPORTANT]
> Microsoft Office Communications Server 2007 所需的配置略有不同。TCP 和 UDP 的 50,000-59,999 端口范围必须对入站和出站方向开放。此要求仅针对 Office Communicator 2007。 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013 只要求 TCP 范围 50,000-59,999 对出站方向开放。


## 外部用户访问的 NAT 要求

NAT 过去通常是路由功能，但可以为 NAT 配置较新的设备（如防火墙），甚至是硬件负载平衡器。本主题介绍所需的 NAT 行为，而不是着重介绍执行 NAT 的设备。

Lync Server 2013通信软件对往返于边缘内部接口的流量不支持 NAT，但对边缘外部接口支持 NAT，需要以下 NAT 行为。

> [!IMPORTANT]
> 必须为传入和传出流量配置对称 NAT。对称 NAT 就是本主题中描述的 NAT 技术。


本文档使用表和图形中的首字母缩写词 ChangeDST 和 ChangeSRC 来定义以下所需行为：

  - **ChangeDST** 更改发送到使用 NAT 的网络的数据包的目标 IP 地址的过程，也称为透明度、端口转发、目标 NAT 模式或半 NAT 模式。

  - **ChangeSRC** 更改离开使用 NAT 的网络的数据包的源 IP 地址的过程，也称为代理、安全 NAT、状态 NAT 或全 NAT 模式。

无论使用何种命名约定，边缘服务器的外部接口所需的 NAT 行为均如下：

  - 对于从 Internet 到边缘外部接口的流量：
    
      - 将来自边缘外部接口公用 IP 地址的传入数据包的目标 IP 地址更改为边缘外部接口的转换后的 IP 地址。
    
      - 保留源 IP 地址不变，以便流量具有返回路由。

  - 对于从边缘外部接口到 Internet 的流量：
    
      - 将离开边缘外部接口的数据包的源 IP 地址从转换后的 IP 地址更改为边缘外部接口的公用 IP 地址，以便不公开内部边缘 IP 地址，这是因为该地址是不可路由的 IP 地址。
    
      - 使目标 IP 地址在传出数据包上保持不变。

下图以 A/V 边缘为例，显示了更改入站流量的目标 IP 地址 (ChangeDST) 与更改出站流量的源 IP 地址 (ChangeSRC) 之间的区别。

**更改入站流量的目标 IP 地址 (ChangeDST) 与更改源 IP 地址 (ChangeSRC)**

![更改目标/源 IP 地址](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "更改目标/源 IP 地址")

要点包括：

  - 对于运行 A/V 边缘服务的服务器的入站流量，源 IP 地址不会更改，但目标 IP 地址会从 131.107.155.30 更改为转换后的 IP 地址 10.45.16.10。

  - 对于从运行 A/V 边缘服务的服务器返回工作站的出站流量，源 IP 地址将从服务器的公用 IP 地址的源 IP 地址更改为运行 A/V 边缘服务的服务器的公用 IP 地址的源 IP 地址。目标 IP 地址仍为工作站的公用 IP 地址。数据包将第一个 NAT 设备出站后，NAT 设备上的规则会将运行 A/V 边缘服务外部接口 IP 地址 (10.45.16.10) 的服务器的源 IP 地址更改为其公用 IP 地址 (131.107.155.30)。

