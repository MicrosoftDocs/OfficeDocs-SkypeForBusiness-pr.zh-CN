---
title: Lync Server 2013 web 会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0b85bc97f5737f980c83c992a6a21eaeaca4e40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的网络会议概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-30_

通过网络会议, 用户可以在会议期间共享和协作处理文档, 如 PowerPoint 演示文稿。 此外, 用户可以实时共享其所有或部分桌面, 使其看起来好像是会议中的同一个表周围收集的人员。

<div>

## <a name="whiteboard-and-annotations"></a>白板和注释

白板是一个空白画布，可用于借助文本、墨迹、图形和图像进行协作。 所有与会者都可看到在白板上所做的注释。 白板功能使与会者能够交流想法、集体讨论、做笔记等，从而增进协作。

</div>

<div>

## <a name="polling"></a>轮询

投票功能使演示者能够快速确定参与者的偏好，从而增进协作。 在联机会议和对话过程中，演示者可以使用投票从参与者收集匿名响应。 所有演示者都可以看到结果，并可以向所有与会者隐藏或显示结果。

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>应用程序共享和桌面共享

在会议期间, 您可以在多监视器环境中共享您的整个桌面、单个应用程序或单个监视器。 除了只查看内容之外, 会议中的其他参与者还可以请求对你的屏幕进行控制, 并通过权限与内容进行交互 (包括滚动和编辑)。

<div>


> [!NOTE]  
> 正在查看会议的参与者还可以在会议期间接管和开始共享内容



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 共享

在 Lync 2010 中, PowerPoint 演示文稿以两种方式之一查看。 对于运行 Lync 2010 的用户, PowerPoint 演示文稿使用 PowerPoint 97-2003 格式显示, 并使用 PowerPoint viewer 的嵌入副本进行查看。 对于运行 Lync Web App 的用户, PowerPoint 演示文稿转换为动态 HTML 文件, 然后使用这些自定义 DHTML 文件和 Silverlight 的组合进行查看。 虽然通常有效, 但此方法确实有一些限制:

  - 嵌入的 PowerPoint Viewer (提供最佳的观看体验) 仅在 Windows 平台上可用。

  - 许多移动设备 (包括一些更常见的移动电话) 不支持 Silverlight。

  - PowerPoint Viewer 和 DHTML/Silverlight 方法不支持在最新版本的 PowerPoint 中找到的所有功能 (如幻灯片切换和嵌入视频)。

为了帮助解决这些问题, 并改善用户演示或查看 PowerPoint 演示文稿的整体体验, Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 服务器来处理 PowerPoint 演示文稿。 除了其他优点之外, 此新方法支持:

  - 更高分辨率显示和更好地支持 PowerPoint 功能, 例如动画、幻灯片切换和嵌入的视频。

  - 用于访问这些演示文稿的其他移动设备。 这是因为 Lync Server 2013 使用标准 DHTML 和 JavaScript 来广播 PowerPoint 演示文稿, 而不是自定义的 DHTML 和 Silverlight。

  - 具有适当权限的用户滚动浏览演示文稿本身的 PowerPoint 演示文稿。 例如, Ken Myer 正在演示他的幻灯片放映, Pilar Ackerman 可以查看她想要的任何幻灯片, 而不会影响 Ken 的演示文稿。

</div>

</div>

<span> </span>

</div>

</div>

</div>

