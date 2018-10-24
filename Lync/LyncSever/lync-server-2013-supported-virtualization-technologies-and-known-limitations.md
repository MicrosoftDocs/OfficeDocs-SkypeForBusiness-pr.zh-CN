---
title: Lync Server 2013：支持的虚拟化技术和已知限制
TOCTitle: 支持的虚拟化技术和已知限制
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204982(v=OCS.15)
ms:contentKeyID: 49313171
ms.date: 02/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中支持的虚拟化技术和已知限制

 

_**上一次修改主题：** 2017-02-06_

Lync VDI 插件对于支持的虚拟化技术允许音频和视频呼叫。这将扩展 [Client Virtualization in Microsoft Lync 2010](http://go.microsoft.com/fwlink/?linkid=330447) 白皮书中针对 Microsoft Lync Server 2010 概述的功能。为遵循标准电话法规，也包括 E911 支持。以下部分介绍了 Lync VDI 插件支持的虚拟化技术和已知功能限制。

## 虚拟化技术支持

Lync VDI 插件在个人虚拟桌面方案中支持完整的桌面远程，但是在远程桌面会话方案中不支持。这些方案可以如下描述：

  - **支持：个性化虚拟桌面或虚拟桌面基础结构 (VDI)。**   在此方案中，每个用户都将登录到可自定义的虚拟桌面，并且能够将文件保存到桌面上，这些文件跨会话持续存在。Microsoft 远程桌面服务、VMware Horizon View 和 Citrix XenDesktop 是已经过测试可与 Lync 一起使用的实施。有关 Microsoft 已测试的供应商特定的 VDI 环境和客户端软件的信息，请参阅[适合于 Microsoft Lync 的基础结构](http://go.microsoft.com/fwlink/?linkid=313435)。

  - **不支持：远程桌面会话。**   在此方案中，每个用户都登录到可自定义的常规虚拟桌面会话。示例实施包括 Microsoft 远程桌面会话 (RDSH) 和与 Citrix Receiver 组合的 Citrix XenApp。

Lync VDI 插件不支持其他虚拟化技术（例如应用程序虚拟化），它们允许使用某应用程序，无需在本地安装完整的应用程序。示例实施包括 Citrix XenApp 和Microsoft Application Virtualization (App-V)。不支持应用程序流式传输、应用程序远程处理和混合虚拟化模式（例如远程桌面远程处理中的应用程序远程处理）。

为支持可扩展性，Lync VDI 插件设计为使用独立于平台的 API，称为动态虚通道 (DVC)。对于 Lync 未显式支持的方案，请来自 VDI 解决方案提供商的支持声明。

## 已知功能限制

在 VDI 环境中使用 Lync 2013 时，存在以下已知限制：

  - 对呼叫委派和 响应组代理匿名处理功能的支持是有限的。

  - 不支持以下功能：
    
      - 集成音频设备和视频设备优化页。
    
      - 多视图视频。
    
      - 录制对话。
    
      - 以匿名方式加入会议（即，加入由您的组织召开的 Lync 会议但不与您的组织联盟）。
    
      - 将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。
    
      - 发生网络中断时的呼叫连续性。
    
      - 自定义铃声和保持音乐功能。

  - Office 365 环境中不支持 Lync VDI 插件。

