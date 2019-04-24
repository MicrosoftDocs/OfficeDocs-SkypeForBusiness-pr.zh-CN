---
title: 在 VDI 环境中规划 Skype for Business
author: jambirk
ms.author: jambirk
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: 本主题讨论使用 Skype for Business 连接到远程虚拟桌面时的规划注意事项。
ms.openlocfilehash: 0d24426ea661e5a2d445e4fd7ef90d6a41518692
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207249"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>在 VDI 环境中规划 Skype for Business
 
本主题讨论使用 Skype for Business 连接到远程虚拟桌面时的规划注意事项。 
  
某些对安全问题及合规性问题特别敏感的组织使用虚拟桌面基础结构 (Virtual Desktop Infrastructure, VDI) 环境。 这些组织的用户在虚拟桌面上进行工作，在该虚拟桌面上，用户的所有桌面应用程序和文件均使用远程桌面服务或类似的远程连接。 For Business 与使用 Skype 完整的音频和视频连接这样需要过重的音频和视频处理客户端上驻留在虚拟机上。 其他 VDI 插件软件是可用的减轻到最终用户的本地计算机的处理和减少了虚拟桌面上的负载。
  
为 VDI 插件的组件，提供 Microsoft、 Citrix 或 VMWare 提供了三个解决方案。 对于新的部署，Microsoft 建议使用 Citrix HDX 实时 Optimization Pack 解决方案或 VMWare 范围虚拟化包。 原始 Lync VDI 插件仍然支持生命周期的其余部分。
  
- **Lync VDI 插件**为 Lync 2013 开发的在虚拟机上运行的业务 2015年客户端的 Lync 2013 或 Skype 兼容。 它是一个独立的应用程序的本地计算机上安装并允许有虚拟桌面上的客户端使用本地音频和视频设备。 插件不需要 Skype 业务客户端安装本地计算机或瘦客户端，它必须运行 Windows 7、 Windows 8 或 Windows Server 2008 操作系统上。 (使用这些操作系统和支持 Microsoft 瘦客户端设备包括： Dell Wyse Z90D7、 Dell Wyse R90L7、 Dell Wyse X90m7、 HP t610 和 HP t5740e。)仍然支持此插件，但没有将来的更新计划。 对于基于 Citrix 虚拟环境中，建议 Citrix 实时 Optimization Pack。
    
- **Citrix 实时 Optimization Pack**上 Lync VDI 插件生成并与 Lync 2013 或 Skype 适用于业务 2016年客户端，虚拟机上。 该解决方案由 Citrix 和 Microsoft 共同开发并在原始 VDI 插件的基础上进行了改进。 该解决方案可以在安装在使用 Windows 和非 Windows 操作系统（包括 Windows 10、Mac 和 Linux）的客户端上。 两个组件组成： 实时连接器 （其中已安装在虚拟桌面上） 和实时媒体引擎 （这最终用户的本地计算机上安装）。 这两个组件允许用户的本地计算机 Skype 用于业务客户端运行虚拟桌面上与 A / V 处理移动到本地计算机。 对于基于 Citrix 的虚拟桌面环境，建议使用 Citrix RealTime Optimization Pack，Microsoft 计划为该解决方案提供进一步支持。
    
- 业务，开发 VMWare，与协作的 Skype **VMWare 范围虚拟化包**允许您在虚拟桌面提供 for Business 的 Skype，同时提供了出色的用户体验。 利用在客户端优化的解决方案，创建与客户端终结点提供媒体的媒体引擎的解决方案的工作原理卸载音频和视频呼叫的功能。 此解决方案可提供音频和视频，或者直接之间的一对一协作终结点或卸载它到中央多点控制单元 (MCU) 的多方会议呼叫或会议。
    
> [!NOTE]
> 业务基本客户端的 Skype 不支持与 Citrix HDX 实时 Optimization Pack 或 VMWare 范围虚拟化包。 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

是与 Lync 2013 和 Skype 业务 2015年和上一个虚拟安装的 2016年 （使用任何单击运行安装程序或 MSI 安装程序后年 1 月版公共更新 2017 年完整客户端） 客户端兼容 Citrix 的 VDI 环境插件 （XenApp 和 XenDesktop 功能）桌面。 其全部功能取决于 Microsoft Lync VDI 插件，但更广泛的客户端操作系统，包括 Windows 10、 Macintosh 和 Linux 上的工作原理。
  
可以在[for Business XenApp 和 XenDesktop 用户提供 Microsoft Skype](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf)Citrix 网站上找到的功能和支持的技术的完整列表。
  
有关详细信息，请访问以下链接：
  
- Citrix [HDX 实时 Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [CTX200279 Skype 业务功能支持](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare 范围虚拟化包
<a name="Citrix_RT"> </a>

与业务 2015年和 2016年完整的客户端安装在虚拟机上的 Skype 兼容 VMWare 的 VDI 环境解决方案。 其全部功能取决于 Microsoft Lync VDI 插件，但更广泛的客户端操作系统，包括 Windows 10、 Macintosh 和 Linux 上的工作原理。 
  
可通过以下链接 VMWare 网站上找到的功能和支持的技术的完整讨论：
  
- [What's New in VMware 范围 7.4&amp;范围客户端 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [范围虚拟化包 Skype 业务](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business With VMWare 范围](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Microsoft Lync VDI 插件
<a name="Citrix_RT"> </a>

Microsoft Lync VDI 插件解决方案后，用户必须是 Windows 计算机或瘦客户端上，并且具有 Microsoft Lync VDI 插件才能处理从虚拟桌面客户端的音频/视频流。 用户需要执行以下操作：
  
1. 将音频/视频设备（例如耳机或摄像头）连接到本地计算机。
    
2. 连接到业务 2015年客户端与 Lync 2013 或 Skype 远程虚拟桌面。
    
3. 在虚拟桌面上 for Business 的 Skype 输入凭据。
    
4. 重新输入用于建立与 Lync VDI 插件的本地 Windows 计算机或瘦客户端上的连接的用户凭据。
    
建立连接之后，用户已准备好发出和接收音频调用及视频调用。网络流量和虚拟桌面负载将会最大程度减少，因为音频/视频处理在本地计算机上进行。
  
Microsoft Lync VDI 插件仅支持某些 Windows 操作系统和业务 2015年客户端仅支持 Lync 2013 或 Skype。 有关支持的技术和限制的更多详细信息，请参阅[支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)。
  
有关详细信息，请访问以下链接：
  
- [支持的虚拟化技术和已知限制](vdi-environments.md#Supported_virt)
    
- [Lync VDI 插件先决条件](vdi-environments.md#VDI_prereq)
    
- [部署 Lync VDI 插件与 Skype 业务服务器](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Citrix 知识中心文章[CTX138408](https://support.citrix.com/article/CTX138408)
    
可在[Microsoft Lync VDI 2013 插件 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[Microsoft Lync VDI 2013 插件 （64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)Microsoft VDI 插件。 与业务 2015年客户端，尽管名称为 Skype 支持此插件。
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>支持的虚拟化技术和已知限制
<a name="Supported_virt"> </a>

允许 Lync VDI 插件的音频和视频呼叫支持虚拟化技术。 符合标准电话法规获得 E911 还包括支持。 以下各节介绍虚拟化技术支持的 Lync VDI 插件和功能的已知的限制。
  
#### <a name="support-for-virtualization-technologies"></a>虚拟化技术支持

Lync VDI 插件支持完整桌面远程会话在个人虚拟桌面方案中，但不能在远程桌面会话方案。 这些方案如下所述：
  
- **支持：个性化虚拟桌面或虚拟桌面基础结构 (VDI)。** 在此方案中，每个用户都登录到可自定义的虚拟桌面，并且能够将文件保存到桌面上，这些文件跨会话持续存在。 Microsoft 远程桌面服务和 VMware 范围视图是用于测试与业务 2015年的 Skype 的示例实现的。 其他正在进行验证的实施包括 Citrix XenDesktop。 供应商特定 VDI 环境和由 Microsoft 已经过测试的客户端硬件有关的信息，请参阅[基础结构符合 Microsoft Lync 要求](https://go.microsoft.com/fwlink/?LinkID=313435)。
    
- **不支持：远程桌面会话。** 在此方案中，每个用户都登录到无法自定义的常规虚拟桌面会话。 示例包括 Microsoft 远程桌面会话 (RDSH) 和 Citrix XenApp 结合使用 Citrix 接收器。
    
Lync VDI 插件不支持其他虚拟化技术，如应用程序虚拟化，而不需要本地完整的应用程序安装允许应用程序的使用。 示例实现包括 Citrix XenApp 和 Microsoft Application Virtualization (APP-V)。 不支持应用程序流式传输、 应用程序远程处理和混合虚拟化模式 （例如，应用程序中的远程处理完整桌面远程处理）。
  
Lync VDI 插件旨在使用独立于平台的 Api 调用动态虚拟通道 (DVCs)。 不明确支持的方案，请参阅支持从 VDI 解决方案提供商的语句。
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Lync VDI 插件先决条件
<a name="VDI_prereq"> </a>

在 VDI 环境中，虚拟机和用户的本地计算机必须满足本节中所述的要求。
  
> [!NOTE]
>  虚拟化解决方案提供商会提供有关如何安装和部署其环境的详细信息。 有关部署基于 HYPER-V 和远程桌面服务的虚拟化的环境的常规信息，请参阅 Microsoft 库中的以下文章： [HYPER-V](https://go.microsoft.com/fwlink/p/?linkid=247514)、 [Windows Server 2008 R2 中的远程桌面服务](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
带有最新的 service pack，虚拟机必须配置与 Windows 8、 Windows 7 或 Windows Server 2008 R2。
  
用户的本地计算机必须满足以下要求：
  
- 用户必须驻留在 Skype，业务服务器或 Lync Server 2013。
    
- 本地计算机必须运行 Windows Embedded Standard 7 SP1、 Windows 7 SP1 或 Windows 8。
    
- 如果您正在使用远程桌面服务，则选择 32 位或 64 位 Lync VDI 插件匹配本地计算机的操作系统。 本地计算机和虚拟机不必都使用 32 位或 64 位操作系统。 如果使用其他虚拟化解决方案或平台，请参阅提供商的要求。
    
- 本地计算机必须运行[的远程桌面客户端的最新版本](https://go.microsoft.com/fwlink/p/?LinkId=268032)。 可以安装由 Microsoft 提供的最新远程桌面服务客户端更新，也可以安装由虚拟化解决方案提供商提供的最新远程桌面客户端软件。 
    
- 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频并禁用远程录制。 若要在 Windows 中配置这些设置用于远程桌面连接，请参阅下一节"以"配置远程桌面连接设置。 
    
可在[Microsoft Lync VDI 2013 插件 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35457)或[Microsoft Lync VDI 2013 插件 （64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=35454)Microsoft VDI 插件。
  
#### <a name="known-feature-limitations"></a>已知功能限制
<a name="VDI_prereq"> </a>

Skype 用于在 VDI 环境中的业务 2015年客户端时，以下是已知限制：
  
支持是有限的呼叫委派和响应组代理匿名处理功能。
  
不支持以下功能：
  
- 集成音频设备和视频设备优化页。
    
- 多视图视频。
    
- 录制对话。
    
- 加入会议以匿名方式 （即，承载与您的组织不未联盟的组织的业务会议加入 Skype）。
    
- 使用 Lync VDI 插件与 Lync Phone Edition 设备。
    
- 发生网络中断时的呼叫连续性。
    
- 自定义铃声和保持音乐功能。
    
Office 365 环境中不支持 Lync VDI 插件。
  
> [!NOTE]
> Citrix RealTime Optimization Pack 明确支持 Office 365。 为基于 Citrix 虚拟环境中，查看受支持的功能和版本的列表的 Citrix 的[技术概述](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl)文档。
  
## <a name="see-also"></a>另请参阅
<a name="Citrix_RT"> </a>

[部署 Lync VDI 插件与 Skype 业务服务器](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

