---
title: Lync Server 2013：通知应用程序使用的组件
TOCTitle: 通知应用程序使用的组件
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398608(v=OCS.15)
ms:contentKeyID: 49313359
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的通知应用程序使用的组件

 

_**上一次修改主题：** 2012-09-13_

在 Lync Server 2013 中， 通知应用程序是 响应组应用程序的一个组件。部署 企业语音时，将与 响应组应用程序一起自动安装并激活 通知应用程序。本节描述支持 通知应用程序的组件。

## 通知应用程序组件

以下 Lync Server 组件支持 通知应用程序：

  - **应用程序服务**应用程序服务为部署、托管和管理统一通信应用程序提供了一个平台。 应用程序服务会在 前端池中的每台前端服务器以及每台 Standard Edition Server 上自动安装。

  - **响应组应用程序**响应组应用程序是由 应用程序服务承载的统一通信应用程序之一。如果将某个未分配电话号码范围配置为路由到通知，则需要使用 响应组应用程序路由向电话号码发出的呼叫。（如果将所有范围都配置为路由到 Exchange 统一消息 (UM)，则不必使用 响应组应用程序。）

  - **音频文件** 音频文件用于通知。

  - **文件存储**通知应用程序使用文件存储来存储其音频文件。

  - **Lync Server 控制面板** 可以使用 Lync Server 控制面板来配置未分配号码表。

  - **Lync Server 命令行管理程序** 可以使用 Lync Server 命令行管理程序 cmdlet 来配置通知设置和未分配号码表。

