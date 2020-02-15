---
title: Lync Server 2013：通知应用程序的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1da328ef485d4dcc8bdac316aa31cef8880525c5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42022443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 中通知应用程序的技术要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

本部分介绍了通知应用程序的以下技术要求：

  - 硬件要求

  - 软件要求

  - 端口要求

  - 音频文件要求

<div>

## <a name="hardware-requirements"></a>硬件要求

通知应用程序与前端服务器具有相同的硬件要求。 有关硬件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。

</div>

<div>

## <a name="software-requirements"></a>软件要求

通知应用程序与前端服务器具有相同的操作系统要求和软件先决条件。 有关软件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

运行通知应用程序的所有前端服务器或 Standard Edition 服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 的服务器安装 Microsoft Media Foundation。Windows Server 2012 R2。 对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。 对于通知和音乐，通知应用程序播放的 Windows Media 音频（.wma）文件需要 windows Media Format Runtime 或 Microsoft Media Foundation。

</div>

<div>

## <a name="port-requirements"></a>端口要求

通知应用程序使用以下端口：

  - ****   用于 SIP 侦听请求的端口5071

<div>


> [!NOTE]  
> 此端口是默认设置，可以通过使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 进行更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>音频文件要求

通知应用程序支持波形（.wav）文件格式和 Windows Media 音频（.wma）文件格式的音乐和公告。 通知应用程序的音频文件要求与响应组应用程序的音频文件要求相同。 有关详细信息，请参阅[Lync Server 2013 中响应组的技术要求](lync-server-2013-technical-requirements-for-response-group.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

