---
title: Lync Server 2013：呼叫寄存的技术要求
TOCTitle: 呼叫寄存的技术要求
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204818(v=OCS.15)
ms:contentKeyID: 49312537
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中呼叫寄存的技术要求

 

_**上一次修改主题：** 2016-12-08_

本节介绍 呼叫寄存的以下技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

## 硬件要求

呼叫寄存应用程序具有与前端服务器相同的硬件要求。有关硬件要求的详细信息，请参阅可支持性文档中的[适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

## 软件要求

呼叫寄存应用程序具有与前端服务器相同的操作系统要求和软件要求。有关软件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

在其中部署了呼叫寄存应用程序的所有前端服务器和 Standard Edition 服务器都必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft 媒体基础。对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。Windows Media Format Runtime 或 Microsoft 媒体基础是呼叫寄存播放的保持音乐 Windows Media 音频 (.wma) 文件所必需的。

## 端口要求

呼叫寄存应用程序 使用下列端口：

  - **端口 5075**   用于 SIP 侦听请求。

> [!NOTE]  
> 此端口是默认设置，您可以使用 <strong>Set-CsApplicationServer</strong> cmdlet 对其进行更改。有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。


## 音频文件要求

呼叫寄存应用程序仅支持保持音乐的 Windows Media 音频 (.wma) 文件。您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。若要下载 Expression Encoder 4，请参阅“Expression Encoder 4”（网址为 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)）。使用该工具可将文件转换为 .wma 格式。呼叫寄存保持音乐文件的建议格式为 Media Audio 9，44 kHz，16 位，单声道，CBR，32 kbps。

> [!NOTE]  
> 转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。

