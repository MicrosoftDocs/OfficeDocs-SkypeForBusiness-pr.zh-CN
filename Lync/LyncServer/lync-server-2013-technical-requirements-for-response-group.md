---
title: Lync Server 2013：响应组的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ab381a70a8a6d69170959fbaf488982887d765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中响应组的技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

本部分介绍响应组应用程序的以下技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

  - 响应组配置工具要求

<div>

## <a name="hardware-requirements"></a>硬件要求

响应组应用程序具有与前端服务器相同的硬件要求。 有关硬件要求的详细信息，请参阅支持文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>软件要求

响应组应用程序具有与前端服务器相同的操作系统要求和软件先决条件。 有关软件要求的详细信息，请参阅支持文档中的[Lync server 2013 中的 "服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)"。

如果将 Windows Media 音频（.wma）文件用于响应组音乐和通知，则所有前端服务器或运行响应组应用程序的标准版服务器必须为运行 Windows 的服务器安装 Windows Media 格式运行时服务器 2008 R2 或 Microsoft Media Foundation for 运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器。 对于 Windows Server 2008 R2，Windows Media 格式运行时作为 Windows 桌面体验的一部分进行安装。

有关音频要求的更多详细信息，请参阅本部分后面部分的 "音频文件要求"。

</div>

<div>

## <a name="port-requirements"></a>端口要求

响应组应用程序使用以下端口：

  - ****   用于 SIP 侦听请求的端口5071

  - ****   用于 interserver 通信的端口8404
    
    <div>
    

    > [!NOTE]  
    > 此端口用于匹配 "正在进行" 服务，并且当响应组应用程序部署在具有多个前端服务器的池中时，此端口是必需的。

    
    </div>

<div>


> [!NOTE]  
> 这些端口是默认设置，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音频文件要求

响应组应用程序支持波形（.wav）文件格式和 Windows Media 音频（.wma）文件格式，用于响应组消息、保留音乐或交互式语音响应（IVR）问题。

Windows Media 音频文件格式要求 Windows Media 格式运行时安装在运行 Windows Server 2008 R2 和 Windows Server 2008 的前端服务器上。 有关详细信息，请参阅上文中的“软件要求”。

<div>

## <a name="supported-wave-file-formats"></a>支持的 Wave 文件格式

所有 wave 文件必须符合以下要求：

  - 8 位或 16 位文件

  - 线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式

  - 单声道或立体声

  - 4 MB 或更小

为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>支持的 Windows Media 音频文件格式

如果使用 Windows Media 音频文件，请考虑使用较低的比特率，并验证负载下的系统性能。

您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。 若要下载表达式编码器4， [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)请参阅。

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>响应组配置工具要求

"响应组配置" 工具支持下表中所述的操作系统和 web 浏览器的组合。

<div>


> [!NOTE]  
> 支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支持的操作系统和 Web 浏览器

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
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8（本机模式）</p>
<p>Internet Explorer 9（本机模式）</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>响应组代理控制台

此代理控制台支持下表所述的操作系统和 Web 浏览器的组合。

<div>


> [!NOTE]  
> 支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>支持的操作系统和 Web 浏览器

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
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

