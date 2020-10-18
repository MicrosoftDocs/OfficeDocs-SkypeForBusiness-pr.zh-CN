---
title: Lync Server 2013：呼叫寄存使用的组件
description: Lync Server 2013：呼叫寄存使用的组件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 285af316fa2d49e8bebf68e11de6d9526e12ae29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576768"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a>Lync Server 2013 中呼叫寄存使用的组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-13_

当您部署企业语音时，呼叫寄存应用程序将自动安装。 通过配置语音策略启用呼叫寄存。 以下 Lync Server 2013 组件支持呼叫寄存应用程序：

  - **应用程序服务**    应用程序服务提供了用于部署、托管和管理统一通信应用程序（如呼叫寄存应用程序）的平台。 应用程序服务将自动安装在前端池和每个 Standard Edition 服务器上的每台前端服务器上。

  - **呼叫寄存应用程序**    呼叫寄存应用程序是由应用程序服务承载的统一通信应用程序之一。 在部署企业语音时，它会自动包含在内。 呼叫寄存公园和检索呼叫并管理呼叫寄存轨道式。

  - **音乐保留-文件**    如果启用了音乐，则会在呼叫暂停时播放音乐文件。 安装呼叫寄存应用程序时，会包含一个默认的音乐文件。

  - **文件存储**    呼叫寄存应用程序使用文件存储来保存自定义音频文件。

  - **Lync Server 控制面板**    您可以使用 Lync Server 控制面板配置呼叫寄存通道表，并为用户启用呼叫寄存。

  - **Lync Server 命令行**     管理程序可以使用 Lync Server 命令行管理程序 cmdlet 执行所有呼叫寄存应用程序配置。

</div>

<span> </span>

</div>

</div>

</div>

