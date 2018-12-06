---
title: Lync Server 2013 中的 Web 会议概述
TOCTitle: Lync Server 2013 中的 Web 会议概述
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425913(v=OCS.15)
ms:contentKeyID: 49312646
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Web 会议概述

 

_**上一次修改主题：** 2012-09-30_

通过 Web 会议，用户可以在会议期间针对文档（如 PowerPoint 演示文稿）进行共享和协作。此外，用户还可以实时地相互共享全部或部分桌面，看上去就像与会者围着同一桌子在开会一样。

## 白板和注释

白板是一个空白画布，可用于借助文本、墨迹、图形和图像进行协作。所有与会者都可看到在白板上所做的注释。白板功能使与会者能够交流想法、集体讨论、做笔记等，从而增进协作。

## 轮询

轮询功能使演示者能够快速确定参与者的偏好，从而增进协作。在联机会议和对话过程中，演示者可以使用轮询从参与者收集匿名响应。所有演示者都可以看到结果，并可以向所有与会者隐藏或显示结果。

## 应用程序共享和桌面共享

在会议期间，您可以在多监视器环境中共享整个桌面、单个应用程序或各个监视器。除了查看内容之外，其他与会者还可以请求控制您的屏幕并在获得许可的情况下交互操作内容（包括滚动和编辑）。

> [!NOTE]  
> 此外，查看会议的参与者可以在会议期间接管和开始共享内容


## PowerPoint 共享

在 Lync 2010 中，可通过两种方式之一查看 PowerPoint 演示文稿。对于运行 Lync 2010 的用户，使用 PowerPoint 97-2003 格式显示 PowerPoint 演示文稿并使用 PowerPoint Viewer 的嵌入副本查看 PowerPoint 演示文稿。对于运行 Lync Web App 的用户，PowerPoint 演示文稿已转换为动态 HTML 文件，然后使用这些自定义的 DHTML 文件和 Silverlight 的组合来查看它们。虽然此方法通常很有效，但它存在一些限制：

  - 嵌入的 PowerPoint Viewer（可提供最佳查看体验）仅适用于 Windows 平台。

  - 许多移动设备（包括某些更受欢迎的手机）都不支持 Silverlight。

  - PowerPoint Viewer 和 DHTML/Silverlight 方法不支持更新版本的 PowerPoint 中包含的所有功能（例如，幻灯片转换和嵌入视频）。

为了帮助解决这些问题，改进演示或查看 PowerPoint 演示文稿的用户的总体体验，Lync Server 2013 采用了 Office Web Apps 和 Office Web Apps Server 来处理 PowerPoint 演示文稿。除其他好处之外，此新方法还：

  - 实现了更高分辨率的显示以及对 PowerPoint 功能（例如，动画、幻灯片转换和嵌入视频）的更好支持。

  - 使其他移动设备能够访问这些演示文稿。这是因为 Lync Server 2013 使用标准 DHTML 和 JavaScript 来广播 PowerPoint 演示文稿，而不是使用自定义的 DHTML 和 Silverlight 来实现这一点。

  - 使具有适当权限的用户能够独立于 PowerPoint 演示文稿本身来浏览文稿。例如，当 Ken Myer 演示其幻灯片放映时，Pilar Ackerman 可以查看自己所需的任何幻灯片，而不会影响 Ken 所做的演示。

