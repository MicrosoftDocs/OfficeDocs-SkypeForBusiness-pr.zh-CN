---
title: Lync Server 2013 媒体流量的网络带宽要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765923"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Lync Server 2013 中媒体流量的网络带宽要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-09-24_

网络规划的一个重要部分是确保你的网络可以处理 Lync Server 生成的媒体流量。 本节帮助您规划媒体流量。

<div>

## <a name="media-traffic-network-usage"></a>媒体流量网络使用情况

媒体流量带宽使用量可能由于不同变量（如编解码器使用、分辨率和活动级别）的数量而难于计算。 "带宽使用" 是所使用的编解码器和流的活动的功能，这两者在不同的方案之间有所不同。 下表列出了 Lync Server 2013 方案中常用的音频编解码器。

### <a name="audio-codec-bandwidth"></a>音频编解码器带宽

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>音频编解码器</th>
<th>方案</th>
<th>音频有效载荷比特率（KBPS）</th>
<th>仅限于带宽音频负载和 IP 标头 (Kbps)</th>
<th>带宽音频负载、IP 标头、UDP、RTP 和 SRTP (Kbps)</th>
<th>带宽音频负载、IP 标头、UDP、RTP、SRTP 和前向纠错 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio 宽带</p></td>
<td><p>对等</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>RTAudio 窄带</p></td>
<td><p>对等，PSTN</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>网络会议</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G.722 立体声</p></td>
<td><p>对等、会议</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>PSTN，会议</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>会议</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


上表中的带宽数字基于 20ms packetization （每秒50数据包）和 Siren 和 G。722包括来自会议方案的其他安全实时传输协议（SRTP）开销，并假设流的活动量为100%。 当链接上存在数据包丢失时，将动态使用转发错误纠正（FEC），以帮助保持音频流的质量。

722编解码器的立体声版本由基于 Lync 房间系统的系统使用，这将启用立体声麦克风捕获，使侦听器能够更好地区分会议室中的多个 talkers。

对于视频，默认编解码器是一个 "H-p/MPEG-4" 第10部分高级视频编码标准，它具有可缩放的视频编码扩展功能，用于实现时态可伸缩性。 为保持与 Lync 2010 或 Office Communicator 2007 R2 客户端的互操作，RTVideo 编解码器仍用于 Lync 2013 与旧客户端之间的对等调用。 在同时使用 Lync 2013 和旧式客户端的会议会话中，Lync 2013 终结点可以使用视频编解码器对视频进行编码，并向 Lync 2013 和 RTVideo bitstream 发送对 Lync 2010 或 Office Communicator 2007 R2 客户端的 bitstream。

所需带宽取决于分辨率、质量和帧速率。 对于每个分辨率，有两个有趣的比特率：

  - **最高有效负载比**   特率这是 Lync 2013 终结点将在此分辨率支持的最大帧速率下用于解析的比特率。 此值很有趣，因为它允许最高质量和帧速率视频。

  - **最低负载比特率**   这是 Lync 2013 终结点将切换到下一个较低分辨率的比特率。 为了保证特定的解决方案，可用的视频有效载荷比特率不得低于该分辨率的最低比特率。 此值是有趣的，以便你可以在最大比特率不可用或不切实际的情况下了解最小值。 对于某些用户，此类低比特率视频可能被视为不可接受的视频体验，因此在考虑这些最低的视频负载比特率时，请务必小心。 请注意，对于只有少量或没有用户移动的视频场景，实际比特率也会暂时降到最低比特率以下。

Lync 2013 支持更多分辨率。 这使你能够更好地调整到不同的网络带宽和接收客户端功能。 此外，Lync 2013 的默认纵横比已更改为16:9。 对于不允许在16:9 纵横比中捕获的网络摄像头，仍然支持4:3 纵横比。

### <a name="video-resolution-bandwidth"></a>视频分辨率带宽

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>视频编解码器</th>
<th>分辨率和纵横比</th>
<th>视频有效负载最高比特率（Kbps）</th>
<th>最小视频负载比特率（Kbps）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>岁</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>岁</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


视频 FEC 在使用时包含在视频有效负载比特率，因此不会使用视频 FEC 的不同值，也不带视频 FEC。

终结点不会持续流出音频或视频数据包。根据不同的方案，流活动的级别也不同，这些级别指示为流发送数据包的频率。流活动取决于媒体和方案，而不依赖使用的编解码器。在对等方案中：

  - 仅当用户通话时终结点才发送音频流。

  - 参与双方都会接收到音频流。

  - 如果使用视频，则两个终结点在整个通话期间发送和接收视频流。

  - 对于只有很少或没有移动的视频场景，实际比特率可能会暂时很低，因为视频编解码器将跳过视频的编码区域而不进行更改。

在会议方案中：

  - 仅当用户通话时终结点才发送音频流。

  - 所有参与者都会接收到音频流。

  - 如果使用视频，则所有参与者最多将收到 5 个接收视频流和 1 个全景（例如，纵横比 20:3）视频流。 默认情况下，5 个接收视频流是基于当前发言人历史记录的，但用户还可手动选择要从其接收视频流的参与者。

  - 每个启用用户的发送视频流的参与者将发送一个或多个视频流。 Lync 2013 添加最多可发送五个视频流的功能，以优化所有接收客户端的视频质量。 将发送的视频流的实际数量由发送方根据 CPU 容量、可用上行链路带宽和请求特定视频流的接收客户端的数量确定。 最常见的情况是，在旧客户端加入会议的情况下发送 1 个 H.264 和 1 个 RTVideo 视频流。 另一常见方案是，发送若干 H.264 视频流（例如，使用不同视频分辨率）以适应不同的接收方请求。

除音频和视频媒体的实时传输协议 (RTP) 流量所需的带宽之外，实时传输控制协议 (RTCP) 也需要带宽。 RTCP 用于报告 RTP 流的统计信息和带外控制。 规划时，请使用下表中的带宽数值规划 RTCP 流量。 这些值表示用于 RTCP 的最大带宽和音频和视频流之间的最大带宽，因为控制数据的差异

### <a name="rtcp-bandwidth"></a>RTCP 带宽

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>媒体</th>
<th>RTCP 最大带宽 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>视频（仅正在发送/接收的 H.264 或 RTVideo）</p></td>
<td><p>10</p></td>
</tr>
<tr class="odd">
<td><p>视频（正在发送/接收的 H.264 和 RTVideo）</p></td>
<td><p>岁</p></td>
</tr>
</tbody>
</table>


为了实现容量规划，以下两个带宽是非常重要的：

  - **最大带宽没有 FEC**   流将占用的最大带宽，包括流的典型活动和方案中使用的典型编解码器，而不 FEC。这是当流处于100% 活动且没有数据包丢失触发 FEC 使用时的带宽。这对计算必须分配多少带宽以允许在给定方案中使用编解码器非常有趣。 

  - **最大带宽为 FEC**   流所消耗的最大带宽，包括流的典型活动和 FEC 方案中使用的典型编解码器。 这是流达到100% 活动时的带宽，有数据包丢失触发使用 FEC 以提高质量。 这对计算必须分配多少带宽以允许在给定方案中使用编解码器，并允许在数据包丢失情况下使用 FEC 来保持质量。 

下表中还列出了另一个带宽值，**典型带宽**。 这是流占用的平均带宽，包括流的典型活动和方案中使用的典型编解码器。 此带宽可用于 approximating 任何给定时间由媒体流量占用的带宽量，但不适用于容量规划，因为当活动级别高于平均值时，单个调用将超出此值。 下表中的典型视频流带宽基于在测量的客户数据中看到的不同视频分辨率的混合。 例如，在对等会话中，大多数用户都将使用默认视频呈现窗口，而某些部分的用户会增加或最大化 Lync 应用程序，以允许更高的视频分辨率。

下表提供了各种方案的三个带宽值。

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>对等会话的音频/视频容量规划

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>媒体</th>
<th>编解码器</th>
<th>典型流带宽 (Kbps)</th>
<th>不使用 FEC 的最大流带宽</th>
<th>使用 FEC 的最大流带宽</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>RTAudio 宽带</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>音频</p></td>
<td><p>RTAudio 窄带</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>呼叫 Lync 2013 终结点时的主视频</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010（用于最大分辨率 1920x1080）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>呼叫 Lync 2010 或 Office Communicator 2007 R2 终结点时的主视频</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510（用于最大分辨率 1280x720）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>呼叫 Lync 2013 终结点时的全景视频</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010（用于最大分辨率 1920x288）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>呼叫 Lync 2010 或 Office Communicator 2007 R2 终结点时的全景视频</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510（用于最大分辨率 960x144）</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>会议的音频/视频容量规划

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>媒体</th>
<th>典型的编解码器</th>
<th>典型流带宽 (Kbps)</th>
<th>不使用 FEC 的最大流带宽</th>
<th>使用 FEC 的最大流带宽</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>G.722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>音频</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>主视频接收</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>主视频发送</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>全景视频接收</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010（用于最大分辨率 1920x288）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>全景视频发送</p></td>
<td><p>H-p 和/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515（用于使用多个分辨率/编解码器发送 bitstreams</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


对于主视频，"典型" 和 "最大流带宽" 是所有已接收视频流和所有发送视频流的聚合带宽。 即使使用多个视频流，通常也比对等方案中的视频带宽更小，因为许多视频会议使用的内容共享导致视频窗口较多，因此视频分辨率更小。 支持的最大聚合视频负载带宽为 8000 Kbps，可用于发送和接收流，例如，如果有两个传入1920x1080p 视频流。

全景视频的典型流带宽基于当前可用的仅最高960x144 全景视频传输的设备。 一旦具有1920x288 全景视频的设备可用，典型的流带宽将会增加。

### <a name="audio-capacity-planning-for-pstn"></a>PSTN 的音频容量规划

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>媒体</th>
<th>典型的编解码器</th>
<th>典型流带宽 (Kbps)</th>
<th>不使用 FEC 的最大流带宽</th>
<th>使用 FEC 的最大流带宽</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>G. 711 （这包括会议中的 PSTN 参与者）</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>音频</p></td>
<td><p>RTAudio 窄带</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


这些表中的网络带宽数值仅代表单向流量，其中包括分配给每个流的 5 Kbps 的 RTCP 流量开销。 对于视频，最大视频比特率用于计算最大流。

</div>

</div>

<span> </span>

</div>

</div>

</div>

