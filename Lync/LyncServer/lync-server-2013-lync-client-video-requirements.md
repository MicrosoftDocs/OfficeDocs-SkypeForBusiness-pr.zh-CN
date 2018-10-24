---
title: Lync Server 2013：Lync 客户端视频要求
TOCTitle: Lync 客户端视频要求
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49888509
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的 Lync 客户端视频要求

 

_**上一次修改主题：** 2016-12-08_

本节介绍了针对 Lync 2013 视频呼叫的视频硬件支持，并说明了如何确定各种计算机、平板电脑和移动设备配置的预期视频质量。

## Windows 台式机和平板电脑视频要求和功能

Lync 2013 引入了针对基于 H.264/MPEG-4 Part 10 高级视频编码标准的视频编码和解码的硬件加速。利用此功能，CPU 时钟速度较慢的计算机可对分辨率较高的视频进行编码和解码。视频硬件要求随计算机配置和所需的视频分辨率的不同而不同。

## 视频硬件要求


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用 DirectX 视频加速 (DXVA) 的硬件加速 H.264 解码</p></td>
<td><ul>
<li><p>显卡必须支持 DirectX 9.0 且必须公开 DXVA2_ModeH264_VLD_NoFGT 解码模式。</p></li>
<li><p>必须安装最新的显卡驱动程序。</p></li>
</ul>
<div>

> [!NOTE]  
> 有关解码模式的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a>。


</div></td>
</tr>
<tr class="even">
<td><p>硬件加速 H.264 编码：芯片集要求</p></td>
<td><p>支持以下 Intel 硬件加速视频编码解决方案：</p>
<ul>
<li><p>具有集成的硬件视频编码器的第 2 代和第 3 代 Intel 高清显卡 2000、2500、3000 和 4000 芯片集（或更高版本）。需要安装 Intel 高清显卡驱动程序 15.28.9.2884 或包含以下内容的最新驱动程序：</p>
<ul>
<li><p>显示驱动程序 9.17.10.2884 或最新驱动程序</p></li>
<li><p>硬件媒体基础转换 (HMFT) 版本 3.12.10.31 或最新 HMFT</p></li>
</ul></li>
</ul>
<p>支持以下 AMD 硬件加速视频编码解决方案（需要 Lync Server 2013 的 CU1 更新）：</p>
<ul>
<li><p>AMD 视频编解码引擎，在许多不同的显卡和 AMD A 系列加速处理器的集成加速处理单元中提供。必须安装 AMD 视频编解码引擎驱动程序 9.12.0.0 或更高版本。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>硬件加速 H.264 编码：摄像机要求</p></td>
<td><p>具有符合 USB Video Class (UVC) 规格版本 1.5 的集成 H.264 硬件编码器的 USB 视频摄像机。</p>
<div>

> [!NOTE]  
> 使用 Windows 8 或 Windows 8.1 时，Lync 2013 支持 UVC 1.5 摄像机，这包括对 UVC 1.5 的支持。由于 Windows 7 不包括对 UVC 1.5 的支持，因此，Lync 2013 会将 UVC 1.5 摄像机视为没有硬件编码支持的常规摄像机。


</div></td>
</tr>
<tr class="even">
<td><p>使用 DirectX 视频加速 (DXVA) 的硬件加速 H.264 解码</p></td>
<td><ul>
<li><p>显卡必须支持 DirectX 9.0 且必须公开 DXVA2_ModeH264_VLD_NoFGT 解码模式。</p></li>
<li><p>必须安装最新的显卡驱动程序。</p></li>
</ul>
<div>

> [!NOTE]  
> 有关解码模式的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a>。


</div></td>
</tr>
<tr class="odd">
<td><p>硬件加速 H.264 编码：芯片集要求</p></td>
<td><p>支持以下 Intel 硬件加速视频编码解决方案：</p>
<ul>
<li><p>具有集成的硬件视频编码器的第 2 代和第 3 代 Intel 高清显卡 2000、2500、3000 和 4000 芯片集（或更高版本）。需要安装 Intel 高清显卡驱动程序 15.28.9.2884 或包含以下内容的最新驱动程序：</p>
<ul>
<li><p>显示驱动程序 9.17.10.2884 或最新驱动程序</p></li>
<li><p>硬件媒体基础转换 (HMFT) 版本 3.12.10.31 或最新 HMFT</p></li>
</ul></li>
</ul>
<p>支持以下 AMD 硬件加速视频编码解决方案（需要 Lync Server 2013 的 CU1 更新）：</p>
<ul>
<li><p>AMD 视频编解码引擎，在许多不同的显卡和 AMD A 系列加速处理器的集成加速处理单元中提供。必须安装 AMD 视频编解码引擎驱动程序 9.12.0.0 或更高版本。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>硬件加速 H.264 编码：摄像机要求</p></td>
<td><p>具有符合 USB Video Class (UVC) 规格版本 1.5 的集成 H.264 硬件编码器的 USB 视频摄像机。</p>
<div>

> [!NOTE]  
> 使用 Windows 8 或 Windows 8.1 时，Lync 2013 支持 UVC 1.5 摄像机，这包括对 UVC 1.5 的支持。由于 Windows 7 不包括对 UVC 1.5 的支持，因此，Lync 2013 会将 UVC 1.5 摄像机视为没有硬件编码支持的常规摄像机。


</div></td>
</tr>
</tbody>
</table>


## 确定 H.264 视频编码和解码功能

通常，存在确定特定计算机配置的最大编码和解码功能的四大因素：

  - 使用 DXVA 支持硬件加速解码

  - 支持硬件加速编码

  - 物理核心数

  - Windows 体验指数 (WEI)

Windows 系统评估工具 (WinSAT) 确定 WEI。在运行 WinSAT 工具时，它会在计算机上的 %windir%\\Performance\\WinSAT\\DataStore 目录中生成一个 Formal.Assessment XML 文档。此 XML 文件包含对于确定编码功能和解码功能非常重要的以下两项分数：

  - VideoEncodeScore 指示计算机的基于软件的视频编码功能。

  - GraphicsScore 值指示计算机的硬件加速编码功能。

以下三个表说明了不同的 PC 类型依据其支持的硬件加速所具有的最大编码功能和解码功能。对于 640x360 和更高分辨率，最大支持帧速率为 30 帧/秒 (fps)。对于低于 640x360 的分辨率，最大支持帧速率为 15 fps。

### 不带 DXVA 且不带硬件加速编码器的计算机

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支持的编码器分辨率</th>
<th>支持的解码器分辨率</th>
<th>要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240（对于仅接收方案，分辨率为 640x360，帧速率为15fps）</p></td>
<td><p>单核且 VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>双核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>双核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>四核且 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>424x240</p></td>
<td><p>424x240（对于仅接收方案，分辨率为 640x360，帧速率为15fps）</p></td>
<td><p>单核且 VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>双核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>双核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>四核且 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


### 带 DXVA 但不带硬件加速编码器的计算机

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支持的编码器分辨率</th>
<th>支持的解码器分辨率</th>
<th>要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>单核且 VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>双核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>双核且 VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 8.2</p></td>
</tr>
<tr class="even">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>单核且 VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>双核且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>双核且 VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>四核且 VideoEncodeScore ≥ 8.2</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Windows 7 上的 WinSAT 分数最高为 7.9。因此，不带硬件加速编码器的计算机的编码功能仅可在 Windows 8 或 Windows 8.1 上实现，其中最高 WinSAT 分数为 9.9。



### 带 DXVA 且带 Intel 高清显卡硬件加速编码器的计算机

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支持的编码器分辨率</th>
<th>支持的解码器分辨率</th>
<th>要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>所有第 2 代和第 3 代 Intel 高清显卡</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>第 2 代和第 3 代 Intel 高清显卡且 GraphicsScore ≥ 5.0</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>所有第 2 代和第 3 代 Intel 高清显卡</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>第 2 代和第 3 代 Intel 高清显卡且 GraphicsScore ≥ 5.0</p></td>
</tr>
</tbody>
</table>


## 移动设备视频功能

下表介绍了支持的移动设备的最大视频功能。有关移动设备支持的详细信息，请参阅[在 Lync Server 2013 中规划移动客户端](lync-server-2013-planning-for-mobile-clients.md)。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>Windows Phone</th>
<th>iPhone 和 iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264 编码最大分辨率</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 4：192x144</p>
<p>iPad 和所有其他支持的 iPhone 型号：352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="even">
<td><p>H.264 解码最大分辨率</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 和 iPad：352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="odd">
<td><p>H.264 编码最大分辨率</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 4：192x144</p>
<p>iPad 和所有其他支持的 iPhone 型号：352x288</p></td>
<td><p>320x2401</p></td>
</tr>
<tr class="even">
<td><p>H.264 解码最大分辨率</p></td>
<td><p>640x480</p></td>
<td><p>iPhone 和 iPad：352x288</p></td>
<td><p>320x2401</p></td>
</tr>
</tbody>
</table>


1对于具有使用任何 8x60 芯片集的 Qualcomm Snapdragon S3 或 S4 处理器的 Android 设备，支持采用 640x480 分辨率发送和接收。

