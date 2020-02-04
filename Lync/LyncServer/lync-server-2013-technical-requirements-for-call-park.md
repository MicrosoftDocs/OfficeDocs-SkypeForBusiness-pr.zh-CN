---
title: Lync Server 2013：呼叫寄存的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742d6ef62068e3e6e3bbd953e078b186e86bb497
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中呼叫寄存的技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

本部分介绍呼叫寄存的以下技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

<div>

## <a name="hardware-requirements"></a>硬件要求

通话寄存应用程序与前端服务器具有相同的硬件要求。 有关硬件要求的详细信息，请参阅支持文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>软件要求

呼叫驻留应用程序具有与前端服务器相同的操作系统要求和软件先决条件。 有关软件要求的详细信息，请参阅支持文档中的[Lync server 2013 中的 "服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)"。

部署呼叫驻留应用程序的所有前端服务器和标准版服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 的服务器安装 Microsoft Media FoundationWindows Server 2012 R2。 对于 Windows Server 2008 R2，Windows Media 格式运行时作为 Windows 桌面体验的一部分进行安装。 Windows media 音频（.wma）文件需要 windows Media 格式运行时或 Microsoft Media Foundation，这些文件用于调用处于暂停状态的所有音乐的寄存播放。

</div>

<div>

## <a name="port-requirements"></a>端口要求

呼叫驻留应用程序使用以下端口：

  - ****   用于 SIP 侦听请求的端口5075。

<div>


> [!NOTE]  
> 此端口是默认设置，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 对其进行更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音频文件要求

通话寄存应用程序仅支持 Windows Media 音频（.wma）文件用于保留音乐。 您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。 若要下载表达式编码器4，请参阅中的[http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)"Expression 编码器 4"。 使用该工具可将文件转换为 .wma 格式。 呼叫寄存音乐保留文件的推荐格式是媒体音频9、44 kHz、16位、单声道、CBR、32 kbps。

<div>


> [!NOTE]  
> 转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

