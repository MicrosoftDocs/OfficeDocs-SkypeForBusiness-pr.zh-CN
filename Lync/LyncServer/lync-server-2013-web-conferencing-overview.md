---
title: Lync Server 2013 web 会议概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6287b5edd711df845b862b49bc15adb8405e8587
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535359"
---
# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 web 会议概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

通过 Web 会议，用户可以在会议期间针对文档（如 PowerPoint 演示文稿）进行共享和协作。此外，用户还可以实时地相互共享全部或部分桌面，看上去就像与会者围着同一桌子在开会一样。

<div>

## <a name="whiteboard-and-annotations"></a>白板和注释

白板是一个空白画布，可用于借助文本、墨迹、图形和图像进行协作。所有与会者都可看到在白板上所做的注释。白板功能使与会者能够交流想法、集体讨论、做笔记等，从而增进协作。

</div>

<div>

## <a name="polling"></a>轮询

轮询功能使演示者能够快速确定参与者的偏好，从而增进协作。在联机会议和对话过程中，演示者可以使用轮询从参与者收集匿名响应。所有演示者都可以看到结果，并可以向所有与会者隐藏或显示结果。

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>应用程序共享和桌面共享

在会议期间，您可以在多个监视器环境中共享整个桌面、单个应用程序或单个监视器。 除了查看内容之外，其他与会者还可以请求控制您的屏幕并在获得许可的情况下交互操作内容（包括滚动和编辑）。

<div>


> [!NOTE]  
> 此外，查看会议的参与者可以在会议期间接管和开始共享内容



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>PowerPoint 共享

在 Lync 2010 中，以两种方式之一查看 PowerPoint 演示文稿。 对于运行 Lync 2010 的用户，PowerPoint 演示文稿使用 PowerPoint 97-2003 格式显示，并使用 PowerPoint viewer 的嵌入副本进行查看。 对于运行 Lync Web App 的用户，PowerPoint 演示文稿转换为动态 HTML 文件，然后使用这些自定义 DHTML 文件和 Silverlight 的组合进行查看。 虽然此方法通常很有效，但它存在一些限制：

  - 仅在 Windows 平台上提供了 (提供最佳观看体验) 的嵌入式 PowerPoint Viewer。

  - 许多移动设备 (包括一些较常见的移动电话) 不支持 Silverlight。

  - PowerPoint Viewer 和 DHTML/Silverlight 方法不支持在 PowerPoint 的较新版本中找到的所有功能 (此类幻灯片切换和嵌入视频) 。

为了帮助解决这些问题，并提高演示或查看 PowerPoint 演示文稿的用户的整体体验，Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 服务器来处理 PowerPoint 演示文稿。 除其他好处之外，此新方法还：

  - 实现了更高分辨率的显示以及对 PowerPoint 功能（例如，动画、幻灯片转换和嵌入视频）的更好支持。

  - 使其他移动设备能够访问这些演示文稿。 这是因为 Lync Server 2013 使用标准 DHTML 和 JavaScript 来广播 PowerPoint 演示文稿，而不是自定义的 DHTML 和 Silverlight。

  - 使具有适当权限的用户能够独立于 PowerPoint 演示文稿本身来浏览文稿。例如，当 Ken Myer 演示其幻灯片放映时，Pilar Ackerman 可以查看自己所需的任何幻灯片，而不会影响 Ken 所做的演示。

</div>

</div>

<span> </span>

</div>

</div>

</div>

