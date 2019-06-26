---
title: 在 VDI 环境中规划 Skype for Business
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论了在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。
ms.openlocfilehash: c6bf1cea2a18920231ea4d347b8b0471cfebbba3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221237"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>在 VDI 环境中规划 Skype for Business
 
本主题讨论了在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。 
  
某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 这些组织的用户在虚拟桌面上进行工作，在该虚拟桌面上，用户的所有桌面应用程序和文件均使用远程桌面服务或类似的远程连接。 使用 Skype for Business 在连接上使用完整的音频和视频, 这需要在虚拟机上托管的客户端上进行音频和视频处理的大量加载。 可使用其他 VDI 插件软件将该处理移至最终用户的本地计算机, 并减少虚拟机的负载。
  
有三个可用于 VDI 插件组件的解决方案, 由 Microsoft、Citrix 或 VMWare 提供。 对于新部署, Microsoft 建议使用 Citrix HDX 实时优化包解决方案或 VMWare 地平线虚拟化包。 原始 Lync VDI 插件在其生命周期的其余部分仍受支持。
  
- **LYNC VDI 插件**是为 lync 2013 开发的, 并且与在虚拟桌面上运行的 Lync 2013 或 Skype for business 2015 客户端兼容。 它是一个独立的应用程序, 可在本地计算机上安装, 并允许在虚拟桌面上使用本地音频和视频设备和客户端。 插件不需要在本地计算机或瘦客户端上安装 Skype for business 客户端, 这些客户端必须运行 Windows 7、Windows 8 或 Windows Server 2008 操作系统。 (使用这些操作系统且受 Microsoft 支持的瘦客户端设备包括: Dell Wyse Z90D7、Dell Wyse R90L7、dell Wyse X90m7、HP t610 和 HP t5740e。)此插件仍受支持, 但将来没有计划更新。 对于基于 Citrix 的虚拟环境, 建议使用 Citrix 实时优化包。
    
- **Citrix 实时优化包**在 lync VDI 插件上构建, 可在虚拟机上与 Lync 2013 或 Skype for business 2016 客户端配合使用。 该解决方案由 Citrix 和 Microsoft 共同开发并在原始 VDI 插件的基础上进行了改进。 该解决方案可以在安装在使用 Windows 和非 Windows 操作系统（包括 Windows 10、Mac 和 Linux）的客户端上。 它包含两个组件: 实时连接器 (安装在虚拟机上) 和实时媒体引擎 (安装在最终用户的本地计算机上)。 这两个组件允许用户的本地计算机使用在虚拟桌面上运行的 Skype for Business 客户端, 其中 A/V 处理已移动到本地计算机。 对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix RealTime Optimization Pack，Microsoft 计划为该解决方案提供进一步支持。
    
- Skype for Business 的**VMWare 地平线虚拟化包**与 vmware 协作开发, 使您能够在虚拟桌面中提供 skype for business, 同时提供出色的用户体验。 解决方案的工作原理是利用客户端上的媒体引擎创建优化的解决方案, 并且客户端终结点提供音频和视频呼叫的媒体卸载功能。 这种解决方案可以直接在单个一对一协作的终结点之间传递音频和视频, 或将其卸载到一个用于多方电话会议或会议的中央 Multipoint 控件单元 (MCU)。
    
> [!NOTE]
> Citrix HDX 实时优化包或 VMWare 地平线虚拟化包不支持 Skype for Business 基本客户端。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrix 的 VDI 环境插件 (XenApp 和 XenDesktop 的一项功能) 与 Lync 2013 和 Skype for business 2015 和 2016 (使用任何单击以运行安装程序的完全客户端, 或在年 1 2017 月的运行时发布) 客户端上安装的 MSI 安装程序兼容机. 其整体功能基于 Microsoft Lync VDI 插件, 但适用于更广泛的客户端操作系统, 包括 Windows 10、Macintosh 和 Linux。
  
在将[Microsoft Skype For Business 交付给 XenApp 和 XenDesktop 用户](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 网站上可以找到功能和受支持技术的完整列表。
  
有关详细信息，请访问以下链接：
  
- Citrix [HDX 实时优化包 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business 功能支持](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 地平线虚拟化包
<a name="Citrix_RT"> </a>

VMWare 的 VDI 环境解决方案与安装在虚拟桌面上的 Skype for business 2015 和2016完全客户端兼容。 其整体功能基于 Microsoft Lync VDI 插件, 但适用于更广泛的客户端操作系统, 包括 Windows 10、Macintosh 和 Linux。 
  
有关功能和支持的技术的全面讨论可在 VMWare 网站上的以下链接中找到:
  
- [VMware 地平线 7.4 &amp;范围客户端4.7 中的新增功能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Skype for business 的地平线虚拟化包](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [具有 VMWare 范围的 Microsoft Skype for Business](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft Lync VDI 插件
<a name="Citrix_RT"> </a>

使用 Microsoft Lync VDI 插件解决方案, 用户必须位于 Windows 计算机或瘦客户端, 并且安装了 Microsoft 的 Lync VDI 插件以处理来自虚拟机上的客户端的音频/视频流。 用户需要执行以下操作：
  
1. 将音频/视频设备（例如耳机或摄像头）连接到本地计算机。
    
2. 使用 Lync 2013 或 Skype for business 2015 客户端连接到远程虚拟桌面。
    
3. 输入虚拟机上 Skype for Business 的凭据。
    
4. 重新输入用户凭据以在本地 Windows 计算机或瘦客户端上建立与 Lync VDI 插件的连接。
    
建立连接之后，用户已准备好发出和接收音频调用及视频调用。网络流量和虚拟桌面负载将会最大程度减少，因为音频/视频处理在本地计算机上进行。
  
Microsoft 的 Lync VDI 插件仅在某些 Windows 操作系统上受支持, 并且仅支持 Lync 2013 或 Skype for business 2015 客户端。 有关支持的技术和限制的更多详细信息，请参阅[支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)。
  
有关详细信息，请访问以下链接：
  
- [支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 插件先决条件](vdi-environments.md#VDI_prereq)
    
- [通过 Skype for Business 服务器部署 Lync VDI 插件](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 知识中心文章[CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft [LYNC vdi 2013 插件 (32 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[microsoft Lync VDI 2013 插件 (64 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)提供 microsoft VDI 插件。 尽管名称为 Skype for Business 2015 客户端支持此插件。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>支持的虚拟化技术和已知限制
<a name="Supported_virt"> </a>

Lync VDI 插件允许针对受支持的虚拟化技术进行音频和视频通话。 遵守标准电话规章, 还包括对 E911 的支持。 以下部分介绍 Lync VDI 插件支持的虚拟化技术和已知功能限制。
  
#### <a name="support-for-virtualization-technologies"></a>虚拟化技术支持

Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程会话, 但不支持远程桌面会话方案中的完整桌面远程会话。 这些方案可描述如下:
  
- **支持：个性化虚拟桌面或虚拟桌面基础结构 (VDI)。** 在此方案中，每个用户都登录到可自定义的虚拟桌面，并且能够将文件保存到桌面上，这些文件跨会话持续存在。 Microsoft 远程桌面服务和 VMware 地平线视图是已测试用于 Skype for Business 2015 的示例实现。 其他正在进行验证的实施包括 Citrix XenDesktop。 有关已由 Microsoft 测试的特定于供应商的 VDI 环境和客户端硬件的信息, 请参阅[Microsoft Lync 合格的基础结构](https://go.microsoft.com/fwlink/?LinkID=313435)。
    
- **不支持：远程桌面会话。** 在此方案中，每个用户都登录到无法自定义的常规虚拟桌面会话。 示例包括 Microsoft 远程桌面会话 (RDSH) 和 Citrix XenApp 与 Citrix 接收器结合。
    
Lync VDI 插件不支持其他虚拟化技术 (如应用程序虚拟化), 它允许在不需要本地安装完整应用程序的情况下使用应用程序。 示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization (App-v)。 不支持应用程序流、应用程序远程处理和混合虚拟化模式 (例如, 完全桌面远程处理中的应用程序远程处理)。
  
Lync VDI 插件设计为使用名为 "动态虚拟通道 (DVCs)" 的独立于平台的 Api。 对于并非明确支持的方案, 请参阅 VDI 解决方案提供商提供的支持声明。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 插件先决条件
<a name="VDI_prereq"> </a>

在 VDI 环境中, 虚拟机和用户的本地计算机必须满足本部分中概述的要求。
  
> [!NOTE]
>  虚拟化解决方案提供商会提供有关如何安装和部署其环境的详细信息。 有关基于 Hyper-v 和远程桌面服务部署虚拟化环境的一般信息, 请参阅 Microsoft Library 中的以下文章: [Windows Server 2008 R2 中](https://go.microsoft.com/fwlink/p/?linkid=247513)的[Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)、远程桌面服务 
  
虚拟机必须配置有 Windows 8、Windows 7 或 Windows Server 2008 R2 和最新服务包。
  
用户的本地计算机必须满足以下要求:
  
- 用户必须驻留在 Skype for Business 服务器或 Lync Server 2013 上。
    
- 本地计算机必须运行 Windows Embedded Standard 7 和 SP1、Windows 7 with SP1 或 Windows 8。
    
- 如果你使用的是远程桌面服务, 请选择32位或64位 Lync VDI 插件, 以匹配本地计算机的操作系统。 本地计算机和虚拟机不必都使用 32 位或 64 位操作系统。 如果使用其他虚拟化解决方案或平台，请参阅提供商的要求。
    
- 本地计算机必须运行[最新版本的远程桌面客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。 可以安装由 Microsoft 提供的最新远程桌面服务客户端更新，也可以安装由虚拟化解决方案提供商提供的最新远程桌面客户端软件。 
    
- 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。 若要为 Windows 中的 "远程桌面连接" 配置这些设置, 请参阅下一节 "配置远程桌面连接设置"。 
    
Microsoft [LYNC vdi 2013 插件 (32 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[microsoft Lync VDI 2013 插件 (64 位)](https://www.microsoft.com/en-us/download/details.aspx?id=35454)提供 microsoft VDI 插件。
  
#### <a name="known-feature-limitations"></a>已知功能限制
<a name="VDI_prereq"> </a>

在 VDI 环境中使用 Skype for Business 2015 客户端时, 以下是已知限制:
  
对呼叫委派和响应组代理匿名化功能的支持有限。
  
不支持以下功能：
  
- 集成音频设备和视频设备优化页。
    
- 多视图视频。
    
- 录制对话。
    
- 匿名加入会议 (即, 加入由不与您的组织建立联盟的组织托管的 Skype for Business 会议)。
    
- 将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。
    
- 发生网络中断时的呼叫连续性。
    
- 自定义铃声和保持音乐功能。
    
Office 365 环境中不支持 Lync VDI 插件。
  
> [!NOTE]
> Citrix RealTime Optimization Pack 明确支持 Office 365。 对于基于 Citrix 的虚拟环境, 请查看 Citrix 的[技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)文档, 了解支持的功能和版本列表。
  
## <a name="see-also"></a>另请参阅
<a name="Citrix_RT"> </a>

[通过 Skype for Business 服务器部署 Lync VDI 插件](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

