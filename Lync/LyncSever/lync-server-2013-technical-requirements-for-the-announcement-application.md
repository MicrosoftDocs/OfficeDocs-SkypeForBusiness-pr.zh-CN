---
title: Lync Server 2013：通知应用程序的技术要求
TOCTitle: 通知应用程序的技术要求
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205413(v=OCS.15)
ms:contentKeyID: 49314831
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中通知应用程序的技术要求

 

_**上一次修改主题：** 2013-11-07_

本节介绍了通知应用程序的下列技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

## 硬件要求

通知应用程序具有与前端服务器相同的硬件要求。有关硬件要求的详细信息，请参阅可支持性文档中的[适用于 Lync Server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

## 软件要求

通知应用程序具有与前端服务器相同的操作系统要求和软件要求。有关软件要求的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

所有运行通知应用程序的前端服务器或 Standard Edition Server 必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft 媒体基础。对于 Windows Server 2008 R2，作为 Windows Desktop Experience 的一部分安装 Windows Media Format Runtime。通知应用程序为通知和音乐播放的 Windows Media Audio (.wma) 文件需要 Windows Media Format Runtime 或 Microsoft 媒体基础。

## 端口要求

通知应用程序 使用下列端口：

  - **端口 5071**   用于 SIP 侦听请求

> [!NOTE]  
> 此端口是默认设置，可以通过使用 <strong>Set-CsApplicationServer</strong> cmdlet 进行更改。有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序 文档。


## 音频文件要求

通知应用程序支持用于音乐和通知的 Wave (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式。 通知应用程序的音频文件要求与对 响应组应用程序的要求相同。有关详细信息，请参阅 [Lync Server 2013 中响应组的技术要求](lync-server-2013-technical-requirements-for-response-group.md)。

