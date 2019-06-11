---
title: Lync Server 2013：呼叫寄存使用的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a>Lync Server 2013 中呼叫寄存使用的组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-13_

部署企业语音时, 将自动安装呼叫寄存应用程序。 通过配置语音策略启用呼叫寄存。 以下 Lync Server 2013 组件支持调用寄存应用程序:

  - **应用程序服务**   应用程序服务提供用于部署、托管和管理统一通信应用程序 (如呼叫驻留应用程序) 的平台。 应用程序服务将自动安装在前端池和每个标准版服务器上的每个前端服务器上。

  - **呼叫驻留应用程序**   呼叫寄存应用程序是由应用程序服务托管的统一通信应用程序之一。 当您部署企业语音时, 它会自动包括在内。 呼叫公园公园和检索呼叫, 并管理呼叫寄存的轨道式。

  - **音乐暂停-文件**   如果启用了音乐, 则会在呼叫停止时播放音乐文件。 安装呼叫寄存应用程序时, 将包含默认音乐文件。

  - **文件存储**   通话寄存应用程序使用文件存储来保存自定义音频文件。

  - **Lync server 控制面板**   您可以使用 lync server 控制面板配置 "呼叫寄存轨道" 表, 并为用户启用呼叫寄存。

  - **Lync server management shell**   可以使用 Lync server management shell cmdlet 执行所有调用寄存应用程序配置。

</div>

<span> </span>

</div>

</div>

</div>

