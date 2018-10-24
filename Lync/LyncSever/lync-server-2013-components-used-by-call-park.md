---
title: Lync Server 2013：呼叫寄存使用的组件
TOCTitle: 呼叫寄存使用的组件
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398824(v=OCS.15)
ms:contentKeyID: 49314217
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中呼叫寄存使用的组件

 

_**上一次修改主题：** 2012-09-13_

部署企业语音时，会自动安装 呼叫寄存应用程序。可通过配置语音策略启用 呼叫寄存。以下 Lync Server 2013 组件支持 呼叫寄存应用程序：

  - **应用程序服务**应用程序服务为部署、承载和管理统一通信应用程序（例如 呼叫寄存应用程序）提供了一个平台。 应用程序服务会在 前端池中的每台前端服务器以及每台 Standard Edition Server 上自动安装。

  - **呼叫寄存应用程序**呼叫寄存应用程序是由 应用程序服务承载的统一通信应用程序之一。部署企业语音时会自动将其包含在内。 呼叫寄存会寄存和取回呼叫，并管理呼叫寄存通道。

  - **保持音乐文件** 如果启用音乐，则会在呼叫寄存时播放音乐文件。安装 呼叫寄存应用程序时会包含默认的音乐文件。

  - **文件存储**呼叫寄存应用程序使用文件存储保存自定义的音频文件。

  - **Lync Server 控制面板** 您可以使用 Lync Server 控制面板配置呼叫寄存通道表，以及为用户启用 呼叫寄存。

  - **Lync Server 命令行管理程序** 所有的 呼叫寄存应用程序配置都可以通过使用 Lync Server 命令行管理程序 cmdlet 来执行。

