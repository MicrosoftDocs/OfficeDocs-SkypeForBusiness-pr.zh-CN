---
title: Lync Server 2013：定义呼叫允许控制要求
TOCTitle: 定义组织的呼叫允许控制要求
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398334(v=OCS.15)
ms:contentKeyID: 49312835
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义呼叫允许控制要求

 

_**上一次修改主题：** 2015-03-09_

规划呼叫允许控制 (CAC) 需要有关企业网络拓扑的详细信息。为了帮助您规划呼叫允许控制策略，请执行以下步骤。

1.  确认企业网络中的中心/中枢（称为 *网络区域* ）。

2.  确认每个网络区域中的办公室或位置（称为 *网络站点* ）。

3.  确定每对网络区域之间的网络路由。

4.  确定对每个 WAN 链路的带宽限制。
    
    > [!NOTE]  
    > 带宽限制是指 WAN 链路分配给企业语音和音频/视频流量的带宽量。当 WAN 链路被描述为“带宽受限”时，表示该 WAN 链路具有低于链接上预期高峰流量的带宽限制。
    


5.  标识分配给每个网络站点的 IP 子网。

下面，我们将通过下图所示示例网络拓扑来解释这些概念。

**呼叫允许控制的示例拓扑**

![Litware Inc. 网络拓扑示例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 网络拓扑示例")

> [!NOTE]  
> 所有网络站点都与一个网络区域关联。例如，波特兰、里诺和阿尔伯克基包括在北美区域中。在此图中，只显示应用了 CAC 策略、具有带宽限制的 WAN 链路。芝加哥、纽约和底特律的网络站点在北美区域椭圆中显示，因为这些区域没有带宽限定，因此不需要 CAC 策略。



以下各节将介绍此示例拓扑的组件。有关如何规划此拓扑（包括带宽限制）的详细信息，请参阅 [示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

## 确认网络区域

网络区域代表网络中枢或网络中心。

网络中枢或中心是计算机网络基础结构的一部分，它将网络的不同部分相互连接起来，为不同 LAN 或子网间的信息交换提供路径。网络中枢可以将各种网络关联在一起，适用范围从较小区域到广阔的地理区域。网络中枢的容量通常大于与其连接的网络的容量。

示例拓扑具有三个网络区域：北美、EMEA 和 APAC。网络区域是网络站点的集合（请参阅本主题后面的网络站点定义）。与您的网络运营团队一起确认网络区域。

## 将中央站点与每个网络区域相关联

CAC 要求为每个网络区域定义一个 Lync Server 中央站点。从该网络区域中的所有站点中选择具有最佳网络连接性和最高带宽的站点作为中央站点。前面的网络拓扑示例显示了三个网络区域，每个网络区域都有一个管理 CAC 决策的中央站点。前面示例中的相应关联如下表所示。

> [!NOTE]  
> 中央站点不一定与网络站点对应。在本文档的示例中，某些中央站点（芝加哥、伦敦和北京）与网络站点共享同一名称。但是，即使中央站点和网络站点共享同一名称，中央站点也是 Lync Server 拓扑的一个元素，而网络站点是 Lync Server 拓扑所在的完整网络的一部分。



### 网络区域、中央站点和网络站点

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>网络区域</th>
<th>中央站点</th>
<th>网络站点</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>北美</p></td>
<td><p>芝加哥</p></td>
<td><p>芝加哥</p>
<p>纽约</p>
<p>底特律</p>
<p>波特兰</p>
<p>里诺</p>
<p>阿尔伯克基</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>伦敦</p></td>
<td><p>伦敦</p>
<p>科隆</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>北京</p></td>
<td><p>北京</p>
<p>马尼拉</p></td>
</tr>
</tbody>
</table>


## 确认网络站点

网络站点是指为组织提供了实际场地（如办公室、建筑群或校园）的位置。具有 LAN 并与其他站点建立 WAN 连接的实际场地被视为网络站点。从清点组织的所有办公室开始。在我们的示例拓扑中，北美网络区域包括以下网络站点：纽约、芝加哥、底特律、波特兰、里诺和阿尔伯克基。

必须将每个网络站点与某个网络区域关联。根据网络站点是否具有受限 WAN 链路，将带宽策略与网络站点相关联。有关 CAC 策略以及使用这些策略分配的带宽的详细信息，请参阅本主题后面介绍的“定义带宽策略”。要配置 CAC，请将网络站点与网络区域相关联，然后创建应用于给定站点或区域之间的带宽受限连接以及站点和区域之间的 WAN 连接的带宽分配策略。

## 确认网络链接

网络链接是指与链接不同区域和站点的物理 WAN 的连接。我们的示例拓扑中包括两个区域网络链接，区域和站点之间的五个网络链接，以及两个站点之间的一个网络链接。

两个区域链接分别为北美和 EMEA 之间的链接以及 APAC 和 EMEA 之间的链接，分别表示为 NA-EMEA-LINK 和 EMEA-APAC-LINK。

站点链接由将波特兰、里诺和阿尔伯克基连接到北美区域、将马尼拉连接到 APAC 区域、以及将科隆连接到 EMEA 区域的线路表示。里诺和阿尔伯克基之间的线路显示了这两个站点之间的直接网络链接。

## 定义带宽策略

与您的网络运营团队一起确定可用于组织中跨 WAN 链路的实时音频和视频流量的带宽。如果带宽使用量受限；即，如果预期使用的带宽大于可为音频和视频形式分配的带宽，则带宽策略通常应用于 WAN 链路。

CAC *带宽策略* 定义可为实时音频和视频形式保留的最大带宽。由于 CAC 不限制其他流量的带宽，因此它无法阻止其他数据流量（如大型文件传输、音乐流）占用所有网络带宽。

CAC 带宽策略可定义下列任何内容或所有内容：

  - 分配给音频的最大带宽总量。

  - 分配给视频的最大带宽总量。

  - 分配给单个音频呼叫（会话）的最大带宽。

  - 分配给单个视频呼叫（会话）的最大带宽。

> [!NOTE]  
> 所有 CAC 带宽值均表示最大“单向”带宽限制。



> [!NOTE]  
> Lync Server 2013 语音策略功能能够替代针对用户传入呼叫（而非用户发起的传出呼叫）的带宽策略检查。建立会话后，将准确计算带宽消耗。应慎用此设置。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录</a>或 <a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录</a>。



要基于每个会话优化带宽用量，请考虑将要使用的音频和视频编解码器的类型。特别要避免出现为预期要频繁使用的编解码器分配的带宽不足的情况。相反，如果要阻止媒体使用需要更多带宽的编解码器，则应将每个会话的最大带宽设置为足以阻止此类使用的较低值。对于音频，并不是每一种编解码器都适用于每一种方案。例如：

  - 将编解码器的带宽和优先顺序作为因素考虑时， Lync 终结点之间的对等音频呼叫将使用 RTAudio (8kHz) 或 RTAudio (16kHz)。

  - Lync 终结点之间的电话会议和 A/V 会议服务将使用 G.722 或 Siren。

  - Lync 终结点的传入/传出公用电话交换网 (PSTN) 呼叫将使用 G.711 或 RTAudio (8kHz)。

借助下表优化每个会话的最大带宽设置。

### 不同编解码器的带宽用量要求

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>编解码器</th>
<th>不带前向纠错 (FEC) 的带宽要求</th>
<th>带前向纠错 (FEC) 的带宽要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49.8 kbps</p></td>
<td><p>61.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16kHz)</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57.6 kbps</p></td>
<td><p>73.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G0.711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>105.6 kbps</p></td>
<td><p>169.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 fps)</p></td>
<td><p>260 kbps</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 fps)</p></td>
<td><p>610 kbps</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 带宽要求考虑以下几项的开销：以太网 II、IP、用户数据报协议 (UDP)、RTP（实时传输协议）和 SRTP（安全实时传输协议）。其中还包括 RTCP 开销 (10 kbps)。



G.722.1 和 Siren 编解码器类似，但是它们提供不同的比特率。

Lync Server 会议的默认编解码器 G.722 完全不同于 G.722.1 和 Siren 编解码器。

在以下情形中 Siren 编解码器用于 Lync Server 中：

  - 带宽策略设置太低而无法使用 G.722 时。

  - Communications Server 2007 或 Communications Server 2007 R2 客户端连接到 Lync Server 会议服务时（因为这些客户端不支持 G.722 编解码器）。

### 不同方案的带宽用量要求

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>方案</th>
<th>针对量优化的带宽要求 (kbps)</th>
<th>平衡模式下的带宽要求 (kbps)</th>
<th>针对质优化的带宽要求 (kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>对等音频呼叫</p></td>
<td><p>45 kbps</p></td>
<td><p>62 kbps</p></td>
<td><p>91 kbps</p></td>
</tr>
<tr class="even">
<td><p>电话会议</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 呼叫（ Lync 2013 和 PSTN 网关之间，存在媒体旁路）</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>PSTN 呼叫（ Lync 2013 和 中介服务器之间，不存在媒体旁路）</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 呼叫（ 中介服务器和 PSTN 网关之间，不存在媒体旁路）</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Lync - Polycom 呼叫</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
</tr>
</tbody>
</table>


## 标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

在我们的示例中，为北美区域中的纽约站点分配了以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。假设通常在底特律工作的 Bob 到纽约办事处出差进行培训。当他打开计算机并连接到网络时，他的计算机将获取为纽约预留的四个范围之一中的 IP 地址，例如 172.29.80.103。

> [!WARNING]  
> 网络配置期间服务器上指定的 IP 子网必须与客户端计算机提供的格式匹配，这样才能正确地用于媒体旁路。 Lync 客户端将占用其本地 IP 地址并使用关联子网掩码屏蔽 IP 地址。确定与每个客户端相关联的绕过 ID 时，注册器将与每个网络站点相关联的 IP 子网列表和客户端提供的子网进行对比，以检查是否完全匹配。因此，网络配置期间应在服务器上输入实际子网而非虚拟子网，这一点十分重要。（如果是部署呼叫允许控制而非媒体旁路，那么即使配置虚拟子网，呼叫允许控制也将正常工作。）<br />
> 例如，如果客户端登录到 IP 地址为 172.29.81.57、IP 子网掩码为 255.255.255.0 的计算机上， Lync 2013 将需要与子网 172.29.81.0 关联的绕过 ID。如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。因此，管理员精确输入 Lync 客户端提供的子网（网络配置期间静态或通过 DHCP 为子网设置的）十分重要。

