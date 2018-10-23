---
title: Lync Server 2013 中的媒体流量的网络带宽要求
TOCTitle: Lync Server 2013 中的媒体流量的网络带宽要求
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49888491
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的媒体流量的网络带宽要求

 

_**上一次修改主题：** 2015-09-24_

网站规划的一个重要方面就是确保网络可处理 Lync Server 生成的媒体流量。本节帮助您规划媒体流量。

## 媒体流量网络使用情况

媒体流量带宽使用量可能由于不同变量（如编解码器使用、分辨率和活动级别）的数量而难于计算。带宽使用量是使用的编解码器和流活动的一种功能，这两者在不同的方案中各不相同。下表列出了 Lync Server 2013 方案中常用的音频编解码器。

### 音频编解码器带宽

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
<th>音频负载比特率 (KBPS)</th>
<th>仅限于带宽音频负载和 IP 标头 (Kbps)</th>
<th>带宽音频负载、IP 标头、UDP、RTP 和 SRTP (Kbps)</th>
<th>带宽音频负载、IP 标头、UDP、RTP、SRTP 和前向纠错 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio 宽带</p></td>
<td><p>点对点</p></td>
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
<td><p>G0.722</p></td>
<td><p>会议</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>G.722 立体声</p></td>
<td><p>对等，会议</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G0.711</p></td>
<td><p>PSTN</p></td>
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


上表中的带宽数值基于 Siren 和 G.722 的 20 毫秒数据分包（每秒 50 个数据包），其中包含其他安全实时传输协议 (SRTP) 开销（在会议方案中），并假定流是 100% 活动的。如果链接上出现数据包丢失，则会以动态方式使用前向纠错 (FEC) 以帮助维护音频流的质量。

G.722 编解码器的立体声版本由基于 Lync Room System 的系统使用，Lync Room System 启用立体声耳机捕获以允许收听者更好地辨别会议室中的多个讲话人。

对于视频，默认的编解码器为 H.264/MPEG-4 Part 10 高级视频编码标准及其可缩放的用于临时可伸缩性的视频编码扩展。若要维护与 Lync 2010 或 Office Communicator 2007 R2 客户端的互操作性，RTVideo 编解码器仍用于 Lync 2013 和旧客户端之间的对等呼叫。在使用 Lync 2013 和旧客户端这二者的会议会话中，Lync 2013 终结点可能使用视频编解码器编码视频并将 H.264 比特流发送至 Lync 2013，将 RTVideo 比特流发送至 Lync 2010 或 Office Communicator 2007 R2 客户端。

所需的带宽取决于分辨率、质量和帧速率。每种分辨率都有两个相关的比特率：

  - **最大负载比特率**Lync 2013 终结点将此比特率用于该分辨率所能支持的最大帧速率的分辨率。此值可提供最高质量和最高帧速率的视频，因此十分重要。

  - **最小负载比特率**   当低于此比特率时，Lync 2013 终结点将切换至下一个更低的分辨率。为了保证特定分辨率，可用的视频负载比特率不得低于该分辨率的此最低比特率。利用此值，您可以了解在最大比特率不可用或不切实际时可能实现的最低值，因此它很值得关注。对于部分用户，此低比特率视频体验可能被视为无法接受的视频体验，因此在考虑使用这些最低视频负载比特率时应十分谨慎。请注意，对于用户移动很少或无用户移动的视频场景，实际比特率也还可能暂时低于此最小比特率。

Lync 2013 支持的分辨率更多。这使您可更好地调整到不同的网络带宽和接收客户端功能。此外，Lync 2013 的默认纵横比已更改为 16:9。网络摄像机仍支持 4:3 的纵横比，它不允许以 16:9 的纵横比进行捕获。

### 视频分辨率带宽

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
<th>最大视频负载比特率 (Kbps)</th>
<th>最小视频负载比特率 (Kbps)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15</p></td>
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
<td><p>15</p></td>
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


使用视频负载比特率时，其中包含视频 FEC，因此使用或不使用视频 FEC 值都相同。

终结点不会持续流出音频或视频数据包。根据不同的方案，流活动的级别也不同，这些级别指示为流发送数据包的频率。流活动取决于媒体和方案，而不依赖使用的编解码器。在对等方案中：

  - 仅当用户通话时终结点才发送音频流。

  - 参与双方都会接收到音频流。

  - 如果使用视频，则双方终结点都会在整个呼叫过程中发送和接收视频流。

  - 对于少或无移动的视频场景，实际位率在视频编解码器未进行更改的情况下跳过视频的编码区域时可能会暂时非常低。

在会议方案中：

  - 仅当用户通话时终结点才发送音频流。

  - 所有参与者都会接收到音频流。

  - 如果使用视频，则所有参与者最多将收到 5 个接收视频流和 1 个全景（例如，纵横比 20:3）视频流。默认情况下，5 个接收视频流是基于当前发言人历史记录的，但用户还可手动选择要从其接收视频流的参与者。

  - 每个启用用户的发送视频流的参与者将发送一个或多个视频流。Lync 2013 新增了最多发送 5 个视频流的功能以优化所有接收客户端的视频质量。将发送的视频流的实际数量由发送方根据 CPU 容量、可用上行链路带宽和请求特定视频流的接收客户端的数量确定。最常见的情况是，在旧客户端加入会议的情况下发送 1 个 H.264 和 1 个 RTVideo 视频流。另一常见方案是，发送若干 H.264 视频流（例如，使用不同视频分辨率）以适应不同的接收方请求。

除音频和视频媒体的实时传输协议 (RTP) 流量所需的带宽之外，实时传输控制协议 (RTCP) 也需要带宽。RTCP 用于报告 RTP 流的统计信息和带外控制。规划时，请使用下表中的带宽数值规划 RTCP 流量。这些值代表用于 RTCP 的最大带宽，并且因控制数据不同，音频流和视频流的这些值也有所不同。

### RTCP 带宽

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
<td><p>15</p></td>
</tr>
</tbody>
</table>


出于容量规划的目的，以下两种带宽很重要：

  - **不使用 FEC 的最大带宽** 流将使用的最大带宽，包括不使用 FEC 的方案中的典型流活动和使用的典型编解码器。这是流处于 100% 活动状态，且没有因丢失数据包而触发使用 FEC 时的带宽。它对于计算为允许给定的方案使用编解码器而必须分配的带宽数量而言，十分重要。

  - **使用 FEC 的最大带宽** 流使用的最大带宽，包括使用 FEC 的方案中的典型流活动和使用的典型编解码器。这是流处于 100% 活动状态，且因丢失数据包而触发使用 FEC 以提高质量时的带宽。这对于计算为允许给定的方案使用编解码器，并且允许在数据包丢失的条件下使用 FEC 来维护质量而必须分配的带宽数量而言，十分重要。

下面的表中还列出了另一个带宽值，“典型带宽”。这是流使用的平均带宽，包括方案中的典型流活动和使用的典型编解码器。此带宽可用于估计给定时间内媒体流量使用的带宽量，但不应用于容量规划，因为活动级别高于平均水平时，个别呼叫会超过该值。下表中的典型视频流带宽基于在测得的客户数据中观察到的不同视频分辨率的组合。例如，在对等会话中，大部分用户将使用默认视频呈现窗口，但有一定百分比的用户将增加或最大程度地增加 Lync 应用程序以实现更高的视频分辨率。

下面的表提供了不同方案中的这三个带宽值。

### 对等会话的音频/视频容量规划

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
<td><p>调用 Lync 2013 终结点时的主视频</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010（用于最大分辨率 1920x1080）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>调用 Lync 2010 或 Office Communicator 2007 R2 终结点时的主视频</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510（用于最大分辨率 1280x720）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>调用 Lync 2013 终结点时的全景视频</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010（用于最大分辨率 1920x288）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>调用 Lync 2010 或 Office Communicator 2007 R2 终结点时的全景视频</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510（用于最大分辨率 960x144）</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


### 会议的音频/视频容量规划

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
<td><p>G0.722</p></td>
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
<td><p>H.264 和/或 RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>主视频发送</p></td>
<td><p>H.264 和/或 RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>全景视频接收</p></td>
<td><p>H.264 和/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010（用于最大分辨率 1920x288）</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>全景视频发送</p></td>
<td><p>H.264 和/或 RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515（用于使用多个分辨率/编解码器发送比特流）</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


对于主视频，典型和最大流带宽分别是用于所有收到的视频流和所有发送视频流的聚合带宽。即使对于多个视频流，典型视频带宽也小于对等方案，因为很多视频会议使用了内容共享，这会导致视频窗口小很多，从而使视频分辨率更低。例如，如果存在两个传入 1920x1080p 视频流，则将使用的发送和接收流二者支持的最大聚合视频负载带宽为 8000 Kbps。

全景视频的典型流带宽基于当前可用的设备，这些设备仅流式传输最大 960x144 的全景视频。一旦使用 1920x288 全景视频的设备变得可用，典型流带宽就应增大。

### PSTN 的音频容量规划

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
<td><p>G0.711</p></td>
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


这些表中的网络带宽数值仅代表单向流量，其中包括分配给每个流的 5 Kbps 的 RTCP 流量开销。对于视频，最大视频比特率用于计算最大流。

