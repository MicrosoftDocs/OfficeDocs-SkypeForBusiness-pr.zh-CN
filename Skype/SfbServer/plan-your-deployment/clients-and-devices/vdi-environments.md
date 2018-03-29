---
title: 在 VDI 环境中规划 Skype for Business
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论在连接到远程虚拟桌面的同时为企业使用 Skype 的规划注意事项。
ms.openlocfilehash: facf154940b7a82ddc41ac07b87a8af1a5313f5e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>在 VDI 环境中规划 Skype for Business
 
本主题讨论在连接到远程虚拟桌面的同时为企业使用 Skype 的规划注意事项。 
  
某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 这些组织的用户在虚拟桌面上进行工作，在该虚拟桌面上，用户的所有桌面应用程序和文件均使用远程桌面服务或类似的远程连接。 使用 Skype 业务与完整的音频和视频的连接类似的需要繁重的负载的音频和视频处理的客户端上驻留在虚拟机上。 其他 VDI 插件的软件，可以转移到最终用户的本地计算机处理并降低虚拟机的负载。
  
有三种解决方案可用于提供由 Microsoft、 citrix 服务器或 VMWare VDI 插件组件。 对于新部署，Microsoft 建议使用 Citrix HDX 实时优化包解决方案或 VMWare 地平线虚拟化包。 原始的 Lync VDI 插件生命周期的其余部分仍然支持。
  
- **Lync VDI 插件**为 Lync 2013 开发和兼容 Lync 2013 或 Skype 业务 2015年客户机运行在一个虚拟机上。 它是一个安装在本地计算机上的独立应用程序，允许将本地音频设备和视频设备与虚拟桌面上的客户端结合使用。 该插件不需要为业务客户端必须运行 Windows 7，Windows 8 或 Windows Server 2008 操作系统的瘦客户端的本地计算机上安装 Skype。 (瘦客户端设备使用这些操作系统的系统和由 Microsoft 支持包括： 戴尔 Wyse Z90D7、 戴尔 Wyse R90L7、 戴尔 Wyse X90m7、 HP t610 和 HP t5740e。)仍然支持该插件，但任何未来的更新计划。 对于基于 Citrix 的虚拟环境，建议使用 Citrix RealTime Optimization Pack。
    
- **Citrix 实时优化包**Lync VDI 插件为基础并与 Lync 2013 或 Skype 业务 2016年客户端的虚拟机上。 该解决方案由 Citrix 和 Microsoft 共同开发并在原始 VDI 插件的基础上进行了改进。 该解决方案可以在安装在使用 Windows 和非 Windows 操作系统（包括 Windows 10、Mac 和 Linux）的客户端上。 它由两个组件组成： 实时连接器 （这安装在虚拟机上） 和实时媒体引擎 （这安装在最终用户的本地计算机上）。 这两个组件允许用户的本地计算机与一个虚拟桌面上运行业务客户端使用 Skype / V 处理移到本地计算机。 对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix RealTime Optimization Pack，Microsoft 计划为该解决方案提供进一步支持。
    
- **VMWare 虚拟化包范围**为 Skype 业务，与 VMWare，合作开发的可同时提供出色的用户体验提供虚拟桌面中的 Skype 的业务。 通过利用媒体引擎在客户端与客户端终结点提供媒体创建优化的解决方案，该解决方案工作卸载音频和视频呼叫的功能。 此解决方案可提供音频和视频，或者直接进行一对一的协作、 的终结点之间或将其转移到中央多点控制装置 (MCU) 的多方电话会议或会议。
    
> [!NOTE]
> Skype 业务基本 2015年或 2016年客户端不支持 Citrix HDX 实时优化包或 VMWare 地平线虚拟化包。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Citrix 的 VDI 环境插件 （XenApp 和 XenDesktop 的功能） 兼容 Lync 2013 和 Skype 业务 2015年和安装在一个虚拟的 2016年 （使用任何单击运行安装程序或在 1 月 2017 PU 之后发布的 MSI 安装程序完整客户端） 客户端桌面。 其总体的运行状况根据 Microsoft Lync VDI 插件，但在更广泛的客户端操作系统，包括 Windows 10，Macintosh，Linux 的工作原理。
  
Citrix 的网站： [XenApp 和 XenDesktop 用户业务提供 Microsoft Skype](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)上找不到的功能和受支持的技术的完整列表。
  
有关详细信息，请访问以下链接：
  
- Citrix [HDX 实时优化包 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype 业务功能支持](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>地平线 VMWare 虚拟化包
<a name="Citrix_RT"> </a>

VMWare VDI 环境解决方案是 Skype 业务 2015年和 2016年完整的客户端在一个虚拟机上安装与兼容。 其总体的运行状况根据 Microsoft Lync VDI 插件，但在更广泛的客户端操作系统，包括 Windows 10，Macintosh，Linux 的工作原理。 
  
VMWare 通过以下链接网站上找不到的功能和受支持的技术的全面讨论：
  
- [VMware 地平线 7.4 中的新&amp;客户端地平线 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [业务 Skype 的的地平线虚拟化包](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype 业务与 VMWare 地平线](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft Lync VDI 插件
<a name="Citrix_RT"> </a>

使用 Microsoft Lync VDI 插件解决方案，用户可以在 Windows 计算机或瘦客户端，并让微软 Lync VDI 插件安装来处理从虚拟机上的客户端的音频/视频流。 用户需要执行以下操作：
  
1. 将音频/视频设备（例如耳机或摄像头）连接到本地计算机。
    
2. 连接到使用 Lync 2013 或 Skype 业务 2015年客户端的远程虚拟桌面。
    
3. Skype 为企业在虚拟机上输入凭据。
    
4. 重新输入用户凭据建立与 Lync VDI 插件上的本地 Windows 计算机或瘦客户端的连接。
    
建立连接之后，用户已准备好发出和接收音频调用及视频调用。网络流量和虚拟桌面负载将会最大程度减少，因为音频/视频处理在本地计算机上进行。
  
Microsoft 的 Lync VDI 插件仅支持某些 Windows 操作系统上，仅支持客户端业务 2015年的 Lync 2013 或 Skype。 有关支持的技术和限制的更多详细信息，请参阅[支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)。
  
有关详细信息，请访问以下链接：
  
- [支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 插件先决条件](vdi-environments.md#VDI_prereq)
    
- [插件使用 Skype Lync VDI 部署业务服务器 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 的知识中心文章[CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI 插件位于[Microsoft Lync VDI 2013 插件 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[Microsoft Lync VDI 2013 插件 （64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)。 该插件支持 Skype 业务 2015年客户端，尽管该名称。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>支持的虚拟化技术和已知限制
<a name="Supported_virt"> </a>

Lync VDI 插件允许音频和视频呼吁支持虚拟化技术。 符合标准的电话法规 E911，还包含对支持。 以下各节描述了虚拟化技术所支持的插件 Lync VDI 和已知的功能限制。
  
#### <a name="support-for-virtualization-technologies"></a>虚拟化技术支持

在个人虚拟桌面方案中，但不是在远程桌面会话的情况下，插件 Lync VDI 支持完整桌面的远程会话。 这些情况说明如下：
  
- **支持：个性化虚拟桌面或虚拟桌面基础结构 (VDI)。** 在此方案中，每个用户都登录到可自定义的虚拟桌面，并且能够将文件保存到桌面上，这些文件跨会话持续存在。 远程桌面服务时 Microsoft 和 VMware 地平线视图是用于测试与业务 2015年的 Skype 的示例实现。 其他正在进行验证的实施包括 Citrix XenDesktop。 有关特定供应商的 VDI 环境和经过由 Microsoft 的客户端硬件的信息，请参阅[Microsoft Lync 为合格的基础结构](https://go.microsoft.com/fwlink/?LinkID=313435)。
    
- **不支持：远程桌面会话。** 在此方案中，每个用户都登录到无法自定义的常规虚拟桌面会话。 示例包括 Microsoft 远程桌面会话 (RDSH) 和 Citrix XenApp 结合 citrix 服务器接收器。
    
Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，而不需要完整的应用程序本地安装允许的应用程序使用。 示例实现包括 citrix 服务器 XenApp 和 Microsoft 应用程序虚拟化 (APP-V)。 不支持应用程序流、 远程处理应用程序和混合虚拟化模式 （例如，在完全的桌面远程处理应用程序远程处理）。
  
Lync VDI 插件被设计为使用独立于平台的 Api 调用动态虚拟通道 (DVCs)。 对于不显式支持的方案，请参阅支持语句从 VDI 解决方案提供商。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 插件先决条件
<a name="VDI_prereq"> </a>

在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中所述的要求。
  
> [!NOTE]
>  虚拟化解决方案提供商会提供有关如何安装和部署其环境的详细信息。 有关部署基于 Hyper-V 和远程桌面服务虚拟化的环境的一般信息，请参阅 Microsoft TechNet 库中的以下文章： [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514)， [Windows Server 2008 R2 中的远程桌面服务](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
与最新的 service pack，必须使用 Windows 8、 Windows 7 或 Windows Server 2008 R2 配置虚拟机。
  
用户的本地计算机必须满足以下要求：
  
- 用户必须驻留在 Skype 上，业务服务器 2015年或 Lync Server 2013。
    
- 本地计算机必须运行 Windows 嵌入式标准 7 使用 SP1，Windows 7 SP1，或 Windows 8。
    
- 如果您正在使用远程桌面服务，选择 32 位或 64 位 Lync VDI 插件与本地计算机的操作系统相匹配。 本地计算机和虚拟机不必都使用 32 位或 64 位操作系统。 如果使用其他虚拟化解决方案或平台，请参阅提供商的要求。
    
- 本地计算机必须运行[最新版本的远程桌面客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。 可以安装由 Microsoft 提供的最新远程桌面服务客户端更新，也可以安装由虚拟化解决方案提供商提供的最新远程桌面客户端软件。 
    
- 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。 若要在 Windows 中配置远程桌面连接的这些设置，请参阅下一节，"以配置远程桌面连接设置。 
    
Microsoft VDI 插件位于[Microsoft Lync VDI 2013 插件 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[Microsoft Lync VDI 2013 插件 （64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)。
  
#### <a name="known-feature-limitations"></a>已知功能限制
<a name="VDI_prereq"> </a>

为业务 2015 VDI 环境中的客户端使用 Skype 时，下面是已知的限制：
  
没有为调用委派和响应组代理 Anonymization 功能的有限的支持。
  
不支持以下功能：
  
- 集成音频设备和视频设备优化页。
    
- 多视图视频。
    
- 录制对话。
    
- 加入会议以匿名方式 （即，由与您的组织不会没有联盟组织承载业务会议加入 Skype）。
    
- 使用 Lync VDI 插件以及 Lync 电话版设备。
    
- 发生网络中断时的呼叫连续性。
    
- 自定义铃声和保持音乐功能。
    
在 Office 365 的环境中不支持插件 Lync VDI。
  
> [!NOTE]
> Citrix RealTime Optimization Pack 明确支持 Office 365。 对于基于 Citrix 的虚拟环境中，查看受支持的功能和版本的列表的 Citrix 的[技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)文档。
  
## <a name="see-also"></a>另请参阅
<a name="Citrix_RT"> </a>

[插件使用 Skype Lync VDI 部署业务服务器 2015](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

