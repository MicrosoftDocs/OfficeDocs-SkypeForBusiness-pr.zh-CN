---
title: 规划Skype for Business VDI 环境中使用
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论在连接到远程虚拟桌面Skype for Business使用远程桌面的规划注意事项。
ms.openlocfilehash: 63dbdb11abf6188cb11d5f96b54ddeb541f1b9fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864719"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>规划Skype for Business VDI 环境中使用
 
本主题讨论在连接到远程虚拟桌面Skype for Business使用远程桌面的规划注意事项。 
  
虚拟桌面基础结构 (VDI) 环境用于一些安全与合规性问题特别敏感的组织。 他们的用户使用远程桌面服务或类似的远程连接在虚拟桌面上使用其所有桌面应用程序和文件进行工作。 在Skype for Business连接上使用完整的音频和视频，这需要在虚拟桌面上的客户端上执行大量的音频和视频处理负载。 提供了其他 VDI 插件软件，用于将处理卸载到最终用户的本地计算机，并减少虚拟桌面上的负载。
  
有三种解决方案可供 Microsoft、Citrix 或 VMWare 提供的 VDI 插件组件使用。 对于新部署，Microsoft 建议使用 Citrix HDX RealTime Optimization Pack 解决方案或 VMWare Horizon Virtualization Pack。 原始 Lync VDI 插件在其剩余生命周期内仍受支持。
  
- **Lync VDI 插件** 针对 Lync 2013 开发，与在虚拟桌面上运行的 Lync 2013 或 Skype for Business 2015 客户端兼容。 它是一个独立应用程序，安装在本地计算机上，并允许将本地音频和视频设备与虚拟桌面上的客户端一同使用。 该插件不需要在本地计算机或瘦客户端上安装 Skype for Business 客户端，这些客户端必须运行 Windows 7、Windows 8 或 Windows Server 2008 操作系统。  (使用这些操作系统且受 Microsoft 支持的瘦客户端设备包括：Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e.) 此插件仍受支持，但不计划未来更新。 对于基于 Citrix 的虚拟环境，建议使用 Citrix RealTime Optimization Pack。
    
- **Citrix RealTime Optimization Pack** 基于 Lync VDI 插件构建，与虚拟桌面上的 Lync 2013 或 Skype for Business 2016 客户端一起运行。 它由 Citrix 和 Microsoft 共同开发，以改进原始 VDI 插件。 它可以安装在具有 Windows 和非 Windows 操作系统的客户端 (包括 Windows 10、Mac 和 Linux) 。 它包含两个组件：安装在虚拟桌面) 上的 RealTime 连接器 (和安装在最终用户的本地计算机) 上的 RealTime 媒体引擎 (。 这两个组件允许用户的本地计算机使用在虚拟Skype for Business上运行的客户端，同时将 A/V 处理移动到本地计算机。 对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix RealTime Optimization Pack，并且计划进一步提供支持。
    
- **VMWare Horizon Virtualization Pack** for Skype for Business 与 VMWare 协作开发，允许你在虚拟桌面中交付 Skype for Business，同时提供出色的用户体验。 解决方案的工作方式是利用客户端的媒体引擎来创建优化的解决方案，客户端终结点为音频和视频呼叫提供媒体卸载功能。 此解决方案可以直接在终结点之间传递音频和视频，进行一对一协作，或卸载到中央多点控制单元 (MCU) 进行多方电话会议或会议。
    
> [!NOTE]
> Citrix HDX RealTime Optimization Pack 或 VMWare Horizon Virtualization Pack 不支持 Skype for Business Basic 客户端。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrix 的 VDI 环境插件 (XenApp 和 XenDesktop) 的一项功能与 Lync 2013 和 Skype for Business 2015 和 2016 (完整客户端（使用任意单击即可运行安装程序）或安装在虚拟桌面上的 2017 年 1 月 PU) 客户端之后发布的 MSI 安装程序兼容。 其整体功能基于 Microsoft Lync VDI 插件，但它适用于更广泛的客户端操作系统，包括 Windows 10、Macintosh 和 Linux。
  
可在 Citrix 网站上找到功能和支持技术的完整列表，网址为将[Microsoft Skype for Business XenApp 和 XenDesktop Users。](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)
  
有关详细信息，请查看以下链接：
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business功能支持](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

VMWare 的 VDI 环境解决方案与安装在虚拟桌面上的 Skype for Business 2015 和 2016 完整版客户端兼容。 其整体功能基于 Microsoft Lync VDI 插件，但它适用于更广泛的客户端操作系统，包括 Windows 10、Macintosh 和 Linux。 
  
有关功能和支持的技术的完整讨论，可在 VMWare 网站上找到以下链接：
  
- [VMware Horizon 7.4 Horizon &amp; Client 4.7 中的新增功能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [适用于 Skype for Business 的 Horizon Virtualization Pack](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft 的 Lync VDI 插件
<a name="Citrix_RT"> </a>

使用 Microsoft Lync VDI 插件解决方案，用户必须位于 Windows 计算机或瘦客户端上，并且安装了 Microsoft 的 Lync VDI 插件来处理来自虚拟桌面上的客户端的音频/视频流。 用户将：
  
1. 连接将音频/视频设备 (耳机或相机) 本地计算机。
    
2. 连接 Lync 2013 或 Skype for Business 2015 客户端的远程虚拟桌面。
    
3. 输入虚拟Skype for Business的凭据。
    
4. 重新输入用户凭据，以与本地客户端或瘦客户端上的 Lync VDI Windows建立连接。
    
建立连接后，用户即可进行和接收音频和视频呼叫。 网络通信和虚拟桌面上的负载已最小化，因为本地计算机处理音频/视频处理。
  
Microsoft 的 Lync VDI 插件仅在某些 Windows 操作系统上受支持，并且仅支持 Lync 2013 或 Skype for Business 2015 客户端。 有关 [支持的技术和限制的](vdi-environments.md#Supported_virt) 更多详细信息，请参阅支持的虚拟化技术和已知限制。
  
有关详细信息，请查看以下链接：
  
- [支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 插件先决条件](vdi-environments.md#VDI_prereq)
    
- [将 Lync VDI 插件与 Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 知识中心文章 [CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft Lync [VDI 插件位于 Microsoft Lync VDI 2013 插件 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457)或 Microsoft Lync [VDI 2013 插件 (64 位) 。 ](https://www.microsoft.com/download/details.aspx?id=35454) 尽管该名称存在，Skype for Business 2015 客户端支持此插件。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>支持的虚拟化技术和已知限制
<a name="Supported_virt"> </a>

Lync VDI 插件允许对支持的虚拟化技术进行音频和视频呼叫。 根据标准电话法规，还包括对 E911 的支持。 以下各节介绍 Lync VDI 插件支持的虚拟化技术和已知功能限制。
  
#### <a name="support-for-virtualization-technologies"></a>对虚拟化技术的支持

Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程会话，但在远程桌面会话方案中则不支持。 这些方案可以描述如下：
  
- **支持：虚拟桌面或虚拟桌面基础结构 (VDI) 。** 在此方案中，每个用户登录到可自定义的虚拟桌面，并能够将文件保存在桌面上跨会话保留。 Microsoft 远程桌面Services 和 VMware Horizon View 是经过测试以与 Skype for Business 2015 一同使用的示例实现。 正在进行验证的其他实现包括 Citrix XenDesktop。 有关供应商特定的 VDI 环境和经 Microsoft 测试的客户端硬件的信息，请参阅适用于 [Microsoft Lync 的](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)基础结构。
    
- **不支持：远程桌面会话。** 在此方案中，每个用户登录到无法自定义的通用虚拟桌面会话。 示例包括Microsoft 远程桌面与 Citrix Receiver (RDSH) 和 Citrix XenApp 的会话。
    
Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，它允许使用应用程序，而无需在本地安装完整应用程序。 示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization (App-V) 。 应用程序流、应用程序远程处理和混合虚拟化 (例如，不支持在完整桌面远程处理) 应用程序远程处理。
  
Lync VDI 插件设计为使用独立于平台的 API，称为动态虚拟通道 (DPC) 。 对于未明确支持的方案，请参阅 VDI 解决方案提供商的支持声明。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 插件先决条件
<a name="VDI_prereq"> </a>

在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。
  
> [!NOTE]
>  虚拟化解决方案提供商可以提供有关如何安装和部署其环境的详细信息。 有关部署基于 Hyper-V 和远程桌面服务的虚拟化环境的常规信息，请参阅 Microsoft 库中的以下文章[：Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10)) [、Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10))中的远程桌面服务 
  
虚拟机必须配置有 Windows 8、Windows 7 或 Windows Server 2008 R2 以及最新的 Service Pack。
  
用户的本地计算机必须满足以下要求：
  
- 用户必须位于 Skype for Business Server Lync Server 2013 上。
    
- 本地计算机必须运行嵌入式 standard 7 sp1 Windows SP1 Windows 7 sp1 或 Windows 8。
    
- 如果使用的是远程桌面服务，请选择 32 位或 64 位 Lync VDI 插件以匹配本地计算机的操作系统。 本地计算机和虚拟机都不需要具有 32 位或 64 位操作系统。 如果你使用的是其他虚拟化解决方案或平台，请参考提供商的要求。
    
- 本地计算机必须运行 [最新版本的远程桌面客户端](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。 从 Microsoft 安装远程桌面服务客户端的最新更新，或安装虚拟化解决方案提供商提供的最新远程桌面客户端软件。 
    
- 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。 若要为远程桌面连接配置这些设置Windows，请参阅下一节"配置远程桌面连接设置"。 
    
Microsoft Lync [VDI 插件位于 Microsoft Lync VDI 2013 插件 (32 位) ](https://www.microsoft.com/download/details.aspx?id=35457)或 Microsoft Lync [VDI 2013 插件 (64 位) 。 ](https://www.microsoft.com/download/details.aspx?id=35454)
  
#### <a name="known-feature-limitations"></a>已知功能限制
<a name="VDI_prereq"> </a>

在 VDI 环境中使用 Skype for Business 2015 客户端时，存在以下已知限制：
  
对呼叫委派和响应组代理匿名化功能的支持有限。
  
不支持以下功能：
  
- 集成音频设备和视频设备优化页。
    
- 多视图视频。
    
- 录制对话。
    
- 匿名加入 (，即Skype for Business与贵组织联盟的组织主持) 。
    
- 将 Lync VDI 插件与 Lync 电话 Edition 设备一起使用。
    
- 发生网络中断时的呼叫连续性。
    
- 自定义铃声和保持音乐功能。
    
Lync VDI 插件在环境中不受Microsoft 365 Office 365支持。
  
> [!NOTE]
> Citrix RealTime Optimization Pack 不支持Microsoft 365 Office 365。 对于基于 Citrix 的虚拟环境，请查看 Citrix 的技术 [概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) 文档，了解支持的功能和版本列表。
  
## <a name="see-also"></a>另请参阅
<a name="Citrix_RT"> </a>

[将 Lync VDI 插件与 Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)