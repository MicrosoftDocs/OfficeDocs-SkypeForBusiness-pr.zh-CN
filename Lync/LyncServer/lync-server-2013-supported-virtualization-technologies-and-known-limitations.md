---
title: Lync Server 2013：支持的虚拟化技术和已知限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0968f79b8c9aedc3dc2d2318a2e8abf5c51531d7
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013 中支持的虚拟化技术和已知限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-02-06_

Lync VDI 插件允许音频和视频呼叫支持的虚拟化技术。 这在[Microsoft lync 2010 白皮书的客户端虚拟化](https://go.microsoft.com/fwlink/?linkid=330447)中扩展了为 Microsoft lync Server 2010 概述的功能。 在遵守标准电话法规的情况下，还包括对 E911 的支持。 以下各节介绍了 Lync VDI 插件支持的虚拟化技术和已知的功能限制。

<div>

## <a name="support-for-virtualization-technologies"></a>对虚拟化技术的支持

Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程，但在远程桌面会话方案中不支持。 可以按如下所述描述这些方案：

  - **支持：个性化虚拟桌面或虚拟桌面基础结构（VDI）。**    在这种情况下，每个用户都登录到可自定义的虚拟桌面，并且能够在桌面上保存跨会话保留的文件。 Microsoft 远程桌面服务、VMware 地平线视图和 Citrix XenDesktop 是已经过测试可与 Lync 配合使用的实现。 有关已由 Microsoft 测试的供应商特定的 VDI 环境和客户端硬件的信息，请参阅[适用于 Microsoft Lync 的基础结构限定](https://go.microsoft.com/fwlink/?linkid=313435)。

  - **不支持：远程桌面会话。**    在这种情况下，每个用户登录到无法自定义的通用虚拟桌面会话。 示例实现包括 Microsoft 远程桌面会话（RDSH）和与 Citrix 接收器组合的 Citrix XenApp。

Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，它允许使用应用程序，而无需在本地安装完整应用程序。 示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。 不支持应用程序流式处理、应用程序远程处理和混合虚拟化模式（例如，在完整桌面远程处理中进行应用程序远程处理）。

为允许可扩展性，Lync VDI 插件旨在使用称为 "动态虚拟通道" （Dvc）的独立于平台的 Api。 对于不是由 Lync 显式支持的方案，请参阅 VDI 解决方案提供商提供的支持声明。

</div>

<div>

## <a name="known-feature-limitations"></a>已知功能限制

在 VDI 环境中使用 Lync 2013 时，有以下已知限制：

  - 对呼叫委派和响应组代理 Anonymization 功能的支持有限。

  - 不支持以下功能：
    
      - 集成音频设备和视频设备优化页。
    
      - 多视图视频。
    
      - 录制对话。
    
      - 远程桌面服务（RDS）。
    
      - 匿名加入会议（即，加入由不与您的组织联合的组织托管的 Lync 会议）。
    
      - 将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。
    
      - 发生网络中断时的呼叫连续性。
    
      - 自定义铃声和保持音乐功能。

  - Microsoft 365 或 Office 365 环境中不支持 Lync VDI 插件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

