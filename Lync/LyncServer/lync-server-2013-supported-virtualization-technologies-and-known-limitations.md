---
title: Lync Server 2013：支持的虚拟化技术和已知限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845773"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a>Lync Server 2013 中支持的虚拟化技术和已知限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2017-02-06_

Lync VDI 插件允许针对受支持的虚拟化技术进行音频和视频通话。 这将在[Microsoft lync 2010 白皮书的客户端虚拟化](https://go.microsoft.com/fwlink/?linkid=330447)中扩展 Microsoft Lync Server 2010 所示的功能。 遵守标准电话规章, 还包括对 E911 的支持。 以下部分介绍 Lync VDI 插件支持的虚拟化技术和已知功能限制。

<div>

## <a name="support-for-virtualization-technologies"></a>虚拟化技术支持

Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程处理, 但不支持远程桌面会话方案中的完整桌面远程处理。 这些方案可描述如下:

  - **支持: 个性化的虚拟桌面或虚拟桌面基础结构 (VDI)。**   在此方案中, 每个用户都登录到一个可自定义的虚拟桌面, 并且能够保存桌面上跨会话保留的文件。 Microsoft 远程桌面服务、VMware 地平线视图和 Citrix XenDesktop 是已测试用于 Lync 的实现。 有关已由 Microsoft 测试的特定于供应商的 VDI 环境和客户端硬件的信息, 请参阅[Microsoft Lync 合格的基础结构](https://go.microsoft.com/fwlink/?linkid=313435)。

  - **不支持: 远程桌面会话。**   在此方案中, 每个用户登录到无法自定义的一般虚拟桌面会话。 示例实施包括 Microsoft 远程桌面会话 (RDSH) 和与 Citrix Receiver 组合的 Citrix XenApp。

Lync VDI 插件不支持其他虚拟化技术 (如应用程序虚拟化), 它允许在不需要本地安装完整应用程序的情况下使用应用程序。 示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization (App-v)。 不支持应用程序流、应用程序远程处理和混合虚拟化模式 (例如, 完全桌面远程处理中的应用程序远程处理)。

为了允许扩展性, Lync VDI 插件设计为使用名为 "动态虚拟通道 (DVCs)" 的独立于平台的 Api。 对于不是由 Lync 明确支持的方案, 请参阅来自 VDI 解决方案提供商的支持声明。

</div>

<div>

## <a name="known-feature-limitations"></a>已知功能限制

在 VDI 环境中使用 Lync 2013 时, 以下是已知限制:

  - 对呼叫委派和响应组代理匿名化功能的支持有限。

  - 不支持以下功能：
    
      - 集成音频设备和视频设备优化页。
    
      - 多视图视频。
    
      - 录制对话。
    
      - 远程桌面服务 (RDS)。
    
      - 匿名加入会议 (即, 加入由不与您的组织联盟的组织托管的 Lync 会议)。
    
      - 将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。
    
      - 发生网络中断时的呼叫连续性。
    
      - 自定义铃声和保持音乐功能。

  - Office 365 环境中不支持 Lync VDI 插件。

</div>

</div>

<span> </span>

</div>

</div>

</div>

