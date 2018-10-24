---
title: Lync Server 2013：响应组的技术要求
TOCTitle: 响应组的技术要求
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204863(v=OCS.15)
ms:contentKeyID: 49312726
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中响应组的技术要求

 

_**上一次修改主题：** 2016-12-08_

本节介绍了响应组应用程序的下列技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

  - 响应组配置工具要求

## 硬件要求

响应组应用程序具有与前端服务器相同的硬件要求。有关硬件要求的详细信息，请参阅可支持性文档中的[适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

## 软件要求

响应组应用程序具有与前端服务器相同的操作系统要求和软件要求。有关软件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

如果您对响应组音乐和通知使用 Windows Media 音频 (.wma) 文件，则运行响应组应用程序的所有前端服务器或 Standard Edition 服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime 或为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft 媒体基础。对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。

有关音频要求的详细信息，请参阅下文中的“音频文件要求”。

## 端口要求

响应组应用程序使用下列端口：

  - **端口 5071**   用于 SIP 侦听请求

  - **端口 8404**   用于在服务器之间通信
    
    > [!NOTE]
    > 此端口用于 Match Making 服务，且在拥有多台 前端服务器的池中部署 响应组应用程序时，该端口是必需的。


> [!NOTE]  
> 这些端口是默认设置，您可以使用 <strong>Set-CsApplicationServer</strong> cmdlet 更改。有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。


## 音频文件要求

响应组应用程序支持 wave (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式的响应组消息、保持音乐或互动语音响应 (IVR) 问题。

Windows Media 音频文件格式要求 Windows Media Format Runtime 安装在运行 Windows Server 2008 R2 和 Windows Server 2008 的前端服务器上。有关详细信息，请参阅上文中的“软件要求”。

## 支持的 Wave 文件格式

所有 wave 文件必须符合以下要求：

  - 8 位或 16 位文件

  - 线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式

  - 单声道或立体声

  - 4 MB 或更小

为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。

## 支持的 Windows Media 音频文件格式

如果使用 Windows Media 音频文件，请考虑使用较低的比特率，并验证负载下的系统性能。

您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。若要下载 Expression Encoder 4，请参阅 [http://go.microsoft.com/fwlink/?linkid=202843\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=202843%26clcid=0x804)。

## 响应组配置工具要求

响应组配置工具支持下表所述的操作系统和 Web 浏览器的组合。

> [!NOTE]  
> 支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。


### 支持的操作系统和 Web 浏览器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>操作系统</th>
<th>Web 浏览器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
<tr class="even">
<td><p></p>
<p></p>
<p></p>
<p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
</tbody>
</table>


## 响应组代理控制台

此代理控制台支持下表所述的操作系统和 Web 浏览器的组合。

> [!NOTE]  
> 支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。


### 支持的操作系统和 Web 浏览器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>操作系统</th>
<th>Web 浏览器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td></td>
</tr>
</tbody>
</table>

