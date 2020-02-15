---
title: Skype for business Server 的基于视频的屏幕共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype for Business Server 规划和配置信息，用于基于视频的屏幕共享（VbSS）
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009565"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Skype for business Server 的基于视频的屏幕共享 
 
Skype For business Server 2015 中基于视频的屏幕共享（VbSS）现在可供下载： [skype For Business server 2015 累积更新 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)。 VbSS 包含在 Skype for Business Server 2019 中。
  
基于视频的屏幕共享（或 VbSS）在 Lync 屏幕共享中增长。 VbSS 与传统屏幕共享的区别与所使用的基本协议以及它们的 excel 的区别相同。 屏幕共享使用远程桌面协议（RDP），这在用户计算机之间创建数千个1到1会话时非常有用。 较新的技术 VbSS 将使用用户数据报协议（UDP）。
  
Skype for Business Server 希望改进人员的1到1，以及其一对多（多方）对话和会议体验。 VbSS 使用媒体平台（依赖 UDP 作为基础协议），目的是改进视频启动时间、观看内容的质量（尤其是您正在观看的内容是快速移动的）以及整体的可靠性。
  
改进屏幕共享的目标的一部分是在 VbSS 和 RDP 发生时尽可能无缝地进行转换。 由于 VbSS 是对适用于 Skype for business Server 的屏幕共享中使用的基础技术的更新，因此如果您在网络流量中查看 SIP 详细信息，或者您正在共享的内容，则可能很难检测到您要利用的技术。为快速移动或三维。 例如，如果您的工作场所有大量旧版客户端，则 RDP 仍可用作您的会议和对话的故障安全。 Skype for Business Server 使用内部逻辑决定在客户端连接时要应用的两种方法（VbSS 或传统屏幕共享）中的哪一种。 在对 VbSS 的情况下，RDP 可以和将替换为，以便您的观看体验不会中断。
  
## <a name="planning"></a>计划

### <a name="vbss-pros-and-cons"></a>VbSS 的优点和缺点

切换到 VbSS 旨在实现三项关键改进：
  
1. 进行屏幕共享（最长为5%）与 RDP 相比，单独进行更可靠的比较。

2. 使会话设置和视频体验与 RDP 的比较速度更快（安装时间减半，每秒帧数提高6:1）。

3. 在低带宽条件下，即使在共享高运动内容（如三维图形）时，工作原理也会更好。
    
请记住，这些数字依赖于运行状况和正确的网络性能调整，如果客户端在移动设备上，则可能会涉及自己外部的网络。
  
此外，您还应注意，共享内容的一些保真度/脆已得到可靠性、速度和效率的提高。 在大多数情况下，不会对用户很容易看到这一点。
  
### <a name="ports-and-protocols"></a>端口和协议

**所需的服务器端口**

|**服务器角色**|**服务名称**|**端口或端口范围**|**协议**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|前端服务器  <br/> |Skype for Business Server 应用程序共享服务  <br/> |5065  <br/> |TCP  <br/> |用于应用程序共享的传入 SIP 侦听请求。  <br/> |
|前端服务器  <br/> |Skype for Business Server 应用程序共享服务  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用于应用程序共享的媒体端口范围。  <br/> |
   
**必需的客户端端口**

|**组件**|**端口范围**|**协议**|**注释**|
|:-----|:-----|:-----|:-----|
|客户端  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |应用程序共享。  <br/> |
   
如果为以下媒体端口启用了 QoS，同时还启用了 VbSS，则在包含桌面共享的会议过程中，在屏幕共享流量的下面以粗体显示的视频端口设置将使用。 
  
> [!IMPORTANT]
> 这些设置是一种特殊情况，在实现这两种功能时，必须使用这些确切的设置。 这将覆盖[针对 QoS 的文档](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)中的其他建议设置。 对于应用程序共享，除了定义这些端口值之外，还需要在 QoS GPO 中指定 ASMCUSVC。 
  
**应用程序服务器 QoS/VbSS 必需设置**

|**Property**|**端口值**|**协议**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>容量规划

每个运行 Skype for Business Server 2015 累积更新2（CU2）或更高版本的前端服务器都支持最高为375个参与者使用 RDP 进行屏幕共享（尽管每个会议仅有250）。 当引入并使用 VbSS 时，此容量不会更改 CU3。
  
在这种情况下，我们已在实验室中完成了性能和压力测试，还应考虑使用您自己的部署（当然，这取决于使用情况）的以下度量。
  
假如
  
- 您在部署中使用的是 Skype for Business Server 2015 CU2 或更高版本。
    
- Skype for Business Server 环境中的所有用户都具有高于1920x1080 的屏幕分辨率。
    
在全容量（如上所述）中，每个前端服务器总共为375个屏幕共享参与者，尽管每个会议仅有250，但前端服务器可能会使用约1千兆个网卡的 ~ 89%。 这是因为 Skype for Business Server CU2 （RDP）中的现有屏幕共享技术以演示者电脑的本机分辨率传输屏幕内容。 因此，在中分解更高的屏幕分辨率时，您可能已遇到与 Skype for business Server 2015 CU2 的屏幕共享的网络瓶颈。
  
若要缓解这一情况，可以通过以下一种或多种方法来获得帮助：
  
- 将前端服务器从1千兆网卡升级到10千兆以太网卡。

- 增加前端服务器的数量以实现负载平衡流量。

- 通过将 cap 放在两个通道使用的最大带宽上，限制用于 VbSS 和 RDP 的带宽（比特率）。
    
此表中的数字受单个网络和共享内容的影响。 请进行测试以建立网络或网络的基准。
  
|**1080p 内容**|**RDP 平均**|**RDP 峰值**|**VbSS 平均值**|**VbSS 峰值**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|视频  <br/> |5mbps  <br/> |7mbps  <br/> |1.3 mbps  <br/> |2.2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求

VbSS 带宽为：
  
|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率（Kbps）**|**最小视频负载比特率（Kbps）**|
|:-----|:-----|:-----|:-----|
|H-p  <br/> |1920x1080 （16:9）  <br/> （纵横比取决于共享者的监视器分辨率，而不是始终为16:9）  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>客户端和服务器支持

基于视频的屏幕共享需要 Skype for Business Server 2015 CU3 或更高版本，以及在[适用于 Skype For business 和会议支持的移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中[](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)列出的支持客户端的当前版本。 
  
在某些情况下，屏幕共享将转换为 RDP，如下所示：
  
- 如果您的帐户托管在 ASMCU 不符合支持 VbSS 的最低版本的环境中。
- 如果使用较旧版本 Skype for business 客户端的用户加入了您的会话，例如，任何人使用的 Windows 客户端版本低于16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用。 
- 如果用户是从 Skype for Business Web 应用程序共享的。
- 如果有人在 Mac 上使用 Skype for business，而不是托管在 Skype for Business Online 或 Skype for business Server 2015 （使用7月、2018累积更新（或更高版本）。
- 如果某人启动了任何程序/Windows 共享。
- 如果有人开始记录会话。
- 如果有人在会话期间调用远程屏幕控制。 
- 参与者超过250个（当前不支持 VbSS）的会议。

请注意，一旦会话转换为 RDP，它就不会转换回 VbSS。 同样，从 VbSS 进行的转换也是无缝的，因此，在大多数情况下，不能很容易地检测到，并且希望这样做。
    
> [!NOTE]
> 不支持在 Skype for Business 屏幕共享中阻止或尝试阻止、从 VbSS 转换为 RDP。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>启用、禁用和配置 VbSS

很棒的是，一旦您安装了 Skype for Business Server 2015 累积更新3（CU3）或更高版本，默认情况下将为所有用户启用1到1和多方 VbSS。 如果你有理由对你的所有用户启用此功能，则这可能会遇到问题。 在这种情况下，您可以使用以下步骤禁用用户（"启用用户" 步骤将遵循）：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何禁止用户使用 VbSS

- 通过在 Skype for Business 管理控制台中运行此 cmdlet （将 [PolicyName] 替换为您要执行此操作的策略），您可以将不允许 VbSS 的用户策略分配给任何不应使用 VbSS 的用户：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 您还可以更新全局会议策略，这将影响未分配策略的所有用户：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    有关此命令的详细信息，请参阅[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要完全关闭 VbSS，可以运行以下命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    有关此命令的详细信息，请参阅[set-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方 Skype for Business 会议中，所有客户端终结点都将遵循会议组织者的策略设置。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何使用户能够使用 VbSS

- 您可以通过在 Skype for Business 管理控制台中运行此 cmdlet （将 [PolicyName] 替换为您要执行此操作的策略），为需要使用 VbSS 的任何用户分配特定的用户策略（将 [] 替换为）：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 您还可以更新全局会议策略，这将影响未分配策略的所有用户：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    有关此命令的详细信息，请参阅[set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果您需要在 VbSS 关闭后重新打开它（默认情况下处于启用状态），则可以运行以下命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    有关此命令的详细信息，请参阅[set-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方 Skype for Business 会议中，所有客户端终结点都将遵循会议组织者的策略设置。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 累积更新 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[基于视频的屏幕共享（VBSS）在 Skype for Business Server 2015 中可用](https://support.microsoft.com/kb/3170163)
