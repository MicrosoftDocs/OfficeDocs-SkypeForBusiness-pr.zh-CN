---
title: Lync Server 2013：呼叫寄存的技术要求
description: Lync Server 2013：呼叫寄存的技术要求。
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
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577128"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中呼叫寄存的技术要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

本部分介绍呼叫寄存的以下技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

<div>

## <a name="hardware-requirements"></a>硬件要求

呼叫寄存应用程序与前端服务器具有相同的硬件要求。 有关硬件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md) 。

</div>

<div>

## <a name="software-requirements"></a>软件要求

呼叫寄存应用程序与前端服务器具有相同的操作系统要求和软件先决条件。 有关软件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md) 。

在部署呼叫寄存应用程序的所有前端服务器和 Standard Edition 服务器上，必须为运行 windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。 对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。 Windows Media 音频需要 windows Media Format Runtime 或 Microsoft Media Foundation () 呼叫寄存的文件。在保留时播放的音乐。

</div>

<div>

## <a name="port-requirements"></a>端口要求

呼叫寄存应用程序使用以下端口：

  - **端口 5075**    用于 SIP 侦听请求。

<div>


> [!NOTE]  
> 此端口是默认设置，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 对其进行更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音频文件要求

呼叫寄存应用程序仅支持对处于保留状态的音乐 ( .wma) 文件的 Windows Media 音频。 您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。 若要下载表达式编码器4，请参阅中的 "Expression 编码器 4" [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。 使用此工具将文件转换为 .wma 格式。 呼叫寄存保持音乐文件的建议格式为 Media Audio 9，44 kHz，16 位，单声道，CBR，32 kbps。

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

