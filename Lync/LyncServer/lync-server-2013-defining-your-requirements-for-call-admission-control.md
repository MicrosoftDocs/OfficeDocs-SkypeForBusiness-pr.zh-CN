---
title: Lync Server 2013：定义呼叫允许控制的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc067156647a748aaccffeafa97b932e123fbfe
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中定义呼叫允许控制的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-28_

规划呼叫允许控制（CAC）需要有关企业网络拓扑的详细信息。 若要帮助规划呼叫允许控制策略，请执行以下步骤。

1.  确定企业网络中的集线器/中枢（称为*网络区域*）。

2.  标识每个网络区域中的办公室或位置（称为 "*网络站点*"）。

3.  确定每对网络区域之间的网络路由。

4.  确定每个 WAN 链路的带宽限制。
    
    <div>
    

    > [!NOTE]  
    > 带宽限制是指 WAN 链路上的多少带宽分配给企业语音和音频/视频流量。 当 WAN 链路被描述为 "带宽受限" 时，WAN 链路的带宽限制低于该链路上预期的峰值流量。

    
    </div>

5.  确定分配给每个网络站点的 IP 子网。

为了说明这些概念，我们将使用下图中所示的示例网络拓扑。

**呼叫允许控制的示例拓扑**

![Litware 的网络拓扑示例](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware 的网络拓扑示例")

<div>


> [!NOTE]  
> 所有网络站点都与一个网络区域相关联。 例如，"里诺" 和 "阿尔伯克基" 包含在北美区域中。 在此图中，仅显示了已应用 CAC 策略的 WAN 链接，其中包含带宽限制。 芝加哥、纽约和底特律的网络站点在北美地区椭圆中显示，因为它们不受带宽限制，因此不需要 CAC 策略。



</div>

以下各节介绍了此示例拓扑的组件。 若要详细了解如何规划此拓扑（包括带宽限制），请参阅[示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div>

## <a name="identify-network-regions"></a>标识网络区域

网络区域代表网络中枢或网络中心。

网络主干或集线器是用于互连网络不同部分的计算机网络基础结构的一部分，它提供了在不同 Lan 或子网之间交换信息的路径。 主干可将较小位置的各种网络与大地理区域关联起来。 主干的容量通常大于连接到它的网络的容量。

示例拓扑具有三个网络区域：北美、EMEA 和 APAC。 网络区域包含网络站点的集合（请参阅本主题后面的网络站点的定义）。 与您的网络运营团队合作，以确定您的网络区域。

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a>将中央站点与每个网络区域相关联

CAC 要求为每个网络区域定义 Lync Server 中心网站。 将选择中央网站，并将最佳网络连接和最大带宽用于该网络区域中的所有其他网站。 上面的网络拓扑示例显示三个网络区域，每个区域都有一个管理 CAC 决策的中央站点。 在上面的示例中，相应的关联如下表所示。

<div>


> [!NOTE]  
> 中心站点并不一定对应于网络站点。 在本文档的示例中，一些中央站点（芝加哥、伦敦和北京）与网络站点共享相同的名称。 但是，即使中央站点和网络站点共享相同的名称，中心站点也是 Lync Server 拓扑的一个元素，而网络站点是 Lync Server 拓扑所驻留的整个网络的一部分。



</div>

### <a name="network-regions-central-sites-and-network-sites"></a>网络区域、中央站点和网络站点

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
<td><p>Chicago</p></td>
<td><p>Chicago</p>
<p>纽约</p>
<p>底特律</p>
<p>波特兰</p>
<p>里诺</p>
<p>阿尔伯克基</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>南京</p></td>
<td><p>南京</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>首都</p></td>
<td><p>首都</p>
<p>Manila</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a>标识网络站点

网络站点代表组织具有物理场所（例如，办公室、一组建筑物或校园）的位置。 具有 LAN 且具有与其他站点的 WAN 连接的物理场所被视为网络站点。 首先，清点你的组织的所有办公室。 在我们的示例拓扑中，北美网络区域由以下网络站点组成：纽约、芝加哥、底特律、上海、里诺和阿尔伯克基。

您必须将每个网络站点与一个网络区域相关联。 根据网络站点是否具有受约束的 WAN 链路，带宽策略与网络站点相关联。 有关 CAC 策略和使用它们分配的带宽的详细信息，请参阅本主题后面的 "定义带宽策略"。 若要配置 CAC，请将网络站点与网络区域相关联，然后创建分配带宽的策略，以应用于给定站点或区域之间的带宽限制的连接以及站点和区域之间的 WAN 连接。

</div>

<div>

## <a name="identify-network-links"></a>标识网络链接

网络链接代表与链接不同区域和站点的物理 WAN 的连接。 在我们的示例拓扑中，有两个区域网络链接、区域和网站之间有五个网络链接以及两个站点之间的一个网络链接。

这两个区域链接介于北美和 EMEA 之间，表示为 NA-EMEA 链接，在 APAC 和 EMEA 之间，表示为 EMEA-APAC-链接。

站点链接由连接上海、里诺和阿尔伯克基到北美地区、Manila 到 APAC 地区和 Cologne 到 EMEA 地区的线路指示。 里诺和阿尔伯克基之间的线显示这两个站点之间的直接网络链接。

</div>

<div>

## <a name="define-bandwidth-policies"></a>定义带宽策略

与您的网络运营团队合作，以确定可用于组织中的 WAN 链接的实时音频和视频流量的 WAN 带宽量。 带宽策略通常适用于 WAN 链路（如果带宽使用受到限制）;也就是说，如果它应大于可为音频和视频形式分配的带宽。

CAC*带宽策略*定义可为实时音频和视频形式预留的最大带宽。 由于 CAC 不会限制其他流量的带宽，因此不能阻止其他数据流量（如大型文件传输、音乐流）使用所有网络带宽。

CAC 带宽策略可以定义以下任一或所有内容：

  - 为音频分配的最大总带宽。

  - 为视频分配的最大总带宽。

  - 为单个音频呼叫（会话）分配的最大带宽。

  - 为单个视频呼叫（会话）分配的最大带宽。

<div>


> [!NOTE]  
> 所有 CAC 带宽值表示最大<EM>单向</EM>带宽限制。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 语音策略功能可以替代对用户传入呼叫的带宽策略检查（不适用于用户发出的传出呼叫）。 在建立会话之后，将准确地考虑带宽消耗。 应慎用此设置。 有关详细信息，请参阅部署文档中的在 lync <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">server 2013 中创建语音策略和配置 pstn 用法记录</A>或在<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync Server 2013 中修改语音策略和配置 pstn 用法记录</A>。



</div>

若要基于每个会话优化带宽使用率，请考虑将使用的音频和视频编码解码器的类型。 特别是，避免为您预计经常使用的编解码器分配足够的带宽。 相反，如果要阻止媒体使用需要更多带宽的编解码器，则应将每个会话的最大带宽设置得足够低以防止此类使用。 对于音频，并不是每个方案都提供了每个编解码器。 例如：

  - 当你考虑编解码器的带宽和优先顺序时，Lync 终结点之间的对等音频呼叫将使用 RTAudio （8kHz）或 RTAudio （16kHz）。

  - Lync 终结点和 A/V 会议服务之间的会议呼叫将使用 g.722 或 Siren。

  - 从 Lync 终结点到公共交换电话网络（PSTN）的呼叫将使用 g.711 或 RTAudio （8kHz）。

使用下表可帮助优化每个会话的最大带宽设置。

### <a name="bandwidth-utilization-by-codecs"></a>通过编解码器的带宽利用率

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>编解码器</th>
<th>无转发错误纠正的带宽要求（FEC）</th>
<th>带前向纠错（FEC）的带宽要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio （8kHz）</p></td>
<td><p>49.8 kbps</p></td>
<td><p>61.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTAudio （16kHz）</p></td>
<td><p>67 kbps</p></td>
<td><p>96 kbps</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57.6 kbps</p></td>
<td><p>73.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>G. g.711</p></td>
<td><p>102 kbps</p></td>
<td><p>166 kbps</p></td>
</tr>
<tr class="odd">
<td><p>G. g.722</p></td>
<td><p>105.6 kbps</p></td>
<td><p>169.6 kbps</p></td>
</tr>
<tr class="even">
<td><p>RTVideo （CIF 15 fps）</p></td>
<td><p>260 kbps</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo （VGA 30 fps）</p></td>
<td><p>610 kbps</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 带宽要求考虑以下方面的开销：以太网 II、IP、用户数据报协议（UDP）、RTP （实时传输协议）和 SRTP （安全实时传输协议）。 它们还包括 10 kbps 的 RTCP 开销。



</div>

722.1 和 Siren 编解码器类似，但它们提供不同的比特率。

G.722 （Lync Server 会议的默认编解码器）与722.1 和 Siren 编解码器完全不同。

在下列情况下，在 Lync Server 中使用 Siren 编解码器：

  - 如果将 g.722 的带宽策略设置得太低，则无法使用。

  - 如果通信服务器2007或通信服务器 2007 R2 客户端连接到 Lync Server 会议服务（因为这些客户端不支持 g.722 编解码器）。

### <a name="bandwidth-utilization-by-scenario"></a>按方案的带宽使用情况

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
<th>为数量优化的带宽要求（kbps）</th>
<th>平衡模式的带宽要求（kbps）</th>
<th>针对质量优化的带宽要求（kbps）</th>
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
<td><p>会议呼叫</p></td>
<td><p>53 kbps</p></td>
<td><p>101 kbps</p></td>
<td><p>165 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 呼叫（在 Lync 2013 和 PSTN 网关之间，使用媒体旁路）</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>PSTN 呼叫（在 Lync 2013 和中介服务器之间，不使用媒体旁路）</p></td>
<td><p>45 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="odd">
<td><p>PSTN 呼叫（在中介服务器和 PSTN 网关之间，不使用媒体旁路）</p></td>
<td><p>97 kbps</p></td>
<td><p>97 kbps</p></td>
<td><p>161 kbps</p></td>
</tr>
<tr class="even">
<td><p>Lync-Polycom 呼叫</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
<td><p>101 Kbps</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您将需要与您的网络管理员合作，以确定分配给每个网络站点的 IP 子网。 如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

在我们的示例中，向北美地区的纽约站点分配了以下 IP 子网： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。 假设小明在底特律中工作的小明传播到纽约办公室进行培训。 当他打开计算机并连接到网络时，他的计算机将在为纽约保留的四个区域之一中获取 IP 地址，例如172.29.80.103。

<div>


> [!WARNING]  
> 在服务器上的网络配置过程中指定的 IP 子网必须与客户端计算机提供的格式相匹配，以便能够正确地用于媒体旁路。 Lync 客户端获取其本地 IP 地址，并使用关联的子网掩码屏蔽 IP 地址。 在确定与每个客户端关联的绕过 ID 时，注册器会将与每个网络站点关联的 IP 子网的列表与客户端提供的子网进行比较，以实现精确匹配。 因此，在服务器上的网络配置过程中输入的子网是实际的子网而不是虚拟子网，这一点非常重要。 （如果您部署了呼叫允许控制，但没有媒体旁路，则即使您配置了虚拟子网，呼叫允许控制也能正常运行。<BR>例如，如果客户端登录到 IP 地址为 172.29.81.57 ip 子网掩码为255.255.255.0 的计算机，Lync 2013 将请求与子网172.29.81.0 关联的绕过 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此，管理员应完全按照 Lync 客户端提供的方式输入子网，这一点很重要（在静态或通过 DHCP 在网络配置期间为子网预配）。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

