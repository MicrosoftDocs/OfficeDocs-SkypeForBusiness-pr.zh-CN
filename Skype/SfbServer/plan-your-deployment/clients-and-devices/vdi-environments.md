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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。
ms.openlocfilehash: 6886eab8a13db852e0aa86b63d08aa33f82fdaed
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219522"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>在 VDI 环境中规划 Skype for Business
 
本主题讨论在连接到远程虚拟桌面时使用 Skype for Business 的规划注意事项。 
  
在某些组织中，在安全和合规性问题尤其敏感的组织中使用虚拟桌面基础结构（VDI）环境。 他们的用户使用远程桌面服务或类似的远程连接在虚拟机上完成其所有桌面应用程序和文件的工作。 在连接上使用 Skype for Business （如这样的连接）需要大量在虚拟机上托管客户端上的音频和视频处理负载。 另外还提供了其他 VDI 插件软件，用于将该处理降到最终用户的本地计算机上，并减少了虚拟机上的负载。
  
Microsoft、Citrix 或 VMWare 提供了三个可用于 VDI 插件组件的解决方案。 对于新的部署，Microsoft 建议使用 Citrix HDX 实时优化包解决方案或 VMWare 地平线虚拟化包。 原始 Lync VDI 插件仍支持在其生命周期的剩余部分中。
  
- **LYNC VDI 插件**是为 lync 2013 开发的，并且与运行在虚拟桌面上的 Lync 2013 或 Skype for business 2015 客户端兼容。 它是一个独立的应用程序，在本地计算机上安装，允许在虚拟桌面上将本地音频和视频设备与客户端一起使用。 该插件不需要在本地计算机或瘦客户端上安装 Skype for Business 客户端，该客户端必须运行 Windows 7、Windows 8 或 Windows Server 2008 操作系统。 （使用这些操作系统并受 Microsoft 支持的瘦客户端设备包括： Dell Wyse Z90D7、Dell Wyse R90L7、Dell Wyse X90m7、HP t610 和 HP t5740e。）此插件仍受支持，但不计划将来的任何更新。 对于基于 Citrix 的虚拟环境，建议使用 Citrix 实时优化包。
    
- **Citrix 实时优化包**建立在 lync VDI 插件之上，可在虚拟机上与 Lync 2013 或 Skype for business 2016 客户端配合使用。 它由 Citrix 和 Microsoft 共同开发，可在原始 VDI 插件上进行改进。 它可以安装在具有 Windows 和非 Windows 操作系统（包括 Windows 10、Mac 和 Linux）的客户端上。 它包含两个组件：实时连接器（安装在虚拟机上）和实时媒体引擎（安装在最终用户的本地计算机上）。 这两个组件允许用户的本地计算机使用在虚拟桌面上运行的 Skype for Business 客户端，并将 A/V 处理移动到本地计算机。 对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix 实时优化包，并规划进一步的支持。
    
- 适用于 Skype for business 的**VMWare 地平线虚拟化包**（与 VMWare 协作开发）使您能够在虚拟桌面中提供 Skype for business，同时提供极好的用户体验。 此解决方案的工作原理是，在客户端上利用媒体引擎创建优化的解决方案，客户端终结点为音频和视频呼叫提供媒体卸载功能。 这种解决方案可以直接在终结点之间直接传递单一单一协作的音频和视频，也可以将其卸载到多方会议呼叫或会议的中央 Multipoint 控制单元（MCU）。
    
> [!NOTE]
> 在 Citrix HDX 实时优化包或 VMWare 地平线虚拟化包中不支持 Skype for Business 基本客户端。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX 实时优化包
<a name="Citrix_RT"> </a>

Citrix 的 VDI 环境插件（XenApp 和 XenDesktop 的一个功能）与 Lync 2013 和 Skype for Business 2015 和2016（使用任意单击运行安装程序的完整客户端，或在安装在虚拟机上的年 1 2017 月的更新之后发布的 MSI 安装程序）兼容。 其总体功能基于 Microsoft Lync VDI 插件，但在更广泛的客户端操作系统（包括 Windows 10、Macintosh 和 Linux）上运行。
  
在将[Microsoft Skype For Business 发送到 XenApp 和 XenDesktop 用户](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)的 Citrix 网站上，可以找到功能和受支持的技术的完整列表。
  
有关详细信息，请参阅以下链接：
  
- Citrix [HDX 实时优化包 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype for Business 功能支持](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 地平线虚拟化包
<a name="Citrix_RT"> </a>

VMWare 的 VDI 环境解决方案与安装在虚拟桌面上的 Skype for Business 2015 和2016完全客户端兼容。 其总体功能基于 Microsoft Lync VDI 插件，但在更广泛的客户端操作系统（包括 Windows 10、Macintosh 和 Linux）上运行。 
  
可在 VMWare 网站上找到有关功能和受支持的技术的完整讨论，这些链接如下所示：
  
- [VMware 地平线 7.4 &amp; 地平线客户端4.7 中的新增功能](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Skype for business 的地平线虚拟化包](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [使用 VMWare 的 Microsoft Skype for Business 范围](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft 的 Lync VDI 插件
<a name="Citrix_RT"> </a>

使用 Microsoft Lync VDI 插件解决方案，用户必须在 Windows 计算机或瘦客户端上，并已安装 Microsoft 的 Lync VDI 插件，以便在虚拟机上处理来自客户端的音频/视频流。 用户将：
  
1. 将音频/视频设备（如耳机或相机）连接到本地计算机。
    
2. 使用 Lync 2013 或 Skype for Business 2015 客户端连接到远程虚拟桌面。
    
3. 在虚拟机上输入 Skype for Business 的凭据。
    
4. 重新输入用户凭据以在本地 Windows 计算机或瘦客户端上建立与 Lync VDI 插件的连接。
    
建立连接后，用户可以发出和接收音频和视频呼叫。 因为本地计算机处理音频/视频处理，所以网络上的流量和虚拟桌面上的负载都将最小化。
  
Microsoft 的 Lync VDI 插件仅在某些 Windows 操作系统上受支持，并且仅支持 Lync 2013 或 Skype for Business 2015 客户端。 有关受支持的技术和限制的更多详细信息，请参阅[支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)。
  
有关详细信息，请参阅以下链接：
  
- [支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 插件先决条件](vdi-environments.md#VDI_prereq)
    
- [使用 Skype for Business Server 部署 Lync VDI 插件](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 知识中心文章[CTX138408](https://support.citrix.com/article/CTX138408)
    
Microsoft VDI 插件在[Microsoft LYNC vdi 2013 插件（32位）](https://www.microsoft.com/download/details.aspx?id=35457)或[microsoft lync vdi 2013 插件（64位）](https://www.microsoft.com/download/details.aspx?id=35454)中可用。 无论名称是什么，Skype for Business 2015 客户端都支持此插件。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>支持的虚拟化技术和已知限制
<a name="Supported_virt"> </a>

Lync VDI 插件允许音频和视频呼叫支持的虚拟化技术。 在遵守标准电话法规的情况下，还包括对 E911 的支持。 以下各节介绍了 Lync VDI 插件支持的虚拟化技术和已知的功能限制。
  
#### <a name="support-for-virtualization-technologies"></a>对虚拟化技术的支持

Lync VDI 插件支持个人虚拟桌面方案中的完整桌面远程会话，但不支持在远程桌面会话方案中。 可以按如下所述描述这些方案：
  
- **支持：个性化虚拟桌面或虚拟桌面基础结构（VDI）。** 在这种情况下，每个用户都登录到可自定义的虚拟桌面，并且能够在桌面上保存跨会话保留的文件。 Microsoft 远程桌面服务和 VMware 地平线视图是已经过测试用于 Skype for Business 2015 的示例实现。 正在进行验证的其他实施包括 Citrix XenDesktop。 有关已由 Microsoft 测试的供应商特定的 VDI 环境和客户端硬件的信息，请参阅[适用于 Microsoft Lync 的基础结构限定](https://go.microsoft.com/fwlink/?LinkID=313435)。
    
- **不支持：远程桌面会话。** 在这种情况下，每个用户登录到无法自定义的通用虚拟桌面会话。 示例包括 Microsoft 远程桌面会话（RDSH）和与 Citrix 接收器组合的 Citrix XenApp。
    
Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，它允许使用应用程序，而无需在本地安装完整应用程序。 示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization （App-v）。 不支持应用程序流式处理、应用程序远程处理和混合虚拟化模式（例如，在完整桌面远程处理中进行应用程序远程处理）。
  
Lync VDI 插件旨在使用称为 "动态虚拟通道" （Dvc）的独立于平台的 Api。 对于未明确支持的方案，请参阅 VDI 解决方案提供商提供的支持声明。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 插件先决条件
<a name="VDI_prereq"> </a>

在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。
  
> [!NOTE]
>  您的虚拟化解决方案提供商可提供有关如何安装和部署其环境的详细信息。 有关基于 Hyper-v 和远程桌面服务部署虚拟化环境的一般信息，请参阅 Microsoft Library 中的以下文章： [hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514)， [Windows Server 2008 R2 中的远程桌面服务](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
虚拟机必须使用 Windows 8、Windows 7 或 Windows Server 2008 R2 以及最新的 service pack 进行配置。
  
用户的本地计算机必须满足以下要求：
  
- 用户必须驻留在 Skype for Business Server 或 Lync Server 2013 上。
    
- 本地计算机必须运行 Windows Embedded Standard 7 with SP1、Windows 7 SP1 （SP1）或 Windows 8。
    
- 如果正在使用远程桌面服务，请选择32位或64位 Lync VDI 插件以匹配本地计算机的操作系统。 本地计算机和虚拟机都不需要具有32位或64位的操作系统。 如果使用的是其他虚拟化解决方案或平台，请参考提供商的要求。
    
- 本地计算机必须运行[最新版本的远程桌面客户端](https://go.microsoft.com/fwlink/p/?LinkId=268032)。 从虚拟化解决方案提供商处安装来自 Microsoft 或最新远程桌面客户端软件的远程桌面服务客户端的最新更新。 
    
- 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频，并禁用远程录制。 若要在 Windows 中为远程桌面连接配置这些设置，请参阅下一节 "配置远程桌面连接设置"。 
    
Microsoft VDI 插件在[Microsoft LYNC vdi 2013 插件（32位）](https://www.microsoft.com/download/details.aspx?id=35457)或[microsoft lync vdi 2013 插件（64位）](https://www.microsoft.com/download/details.aspx?id=35454)中可用。
  
#### <a name="known-feature-limitations"></a>已知功能限制
<a name="VDI_prereq"> </a>

在 VDI 环境中使用 Skype for Business 2015 客户端时，以下是已知限制：
  
对呼叫委派和响应组代理 Anonymization 功能的支持有限。
  
不支持以下功能：
  
- 集成音频设备和视频设备优化页。
    
- 多视图视频。
    
- 录制对话。
    
- 匿名加入会议（即，加入由不与您的组织联合的组织托管的 Skype for Business 会议）。
    
- 将 Lync VDI 插件与 Lync Phone Edition 设备结合使用。
    
- 发生网络中断时的呼叫连续性。
    
- 自定义铃声和保持音乐功能。
    
Microsoft 365 或 Office 365 环境中不支持 Lync VDI 插件。
  
> [!NOTE]
> Citrix 实时优化包支持 Microsoft 365 和 Office 365。 对于基于 Citrix 的虚拟环境，请查看 Citrix 的[技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)文档，了解支持的功能和版本的列表。
  
## <a name="see-also"></a>另请参阅
<a name="Citrix_RT"> </a>

[使用 Skype for Business Server 部署 Lync VDI 插件](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

