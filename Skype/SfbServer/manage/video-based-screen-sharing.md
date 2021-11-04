---
title: 适用于 Skype for Business Server 的基于视频的屏幕共享
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 'Skype for Business Server基于视频的屏幕共享和 VbSS (规划和配置) '
ms.openlocfilehash: 2921330887b4e52aee5069d2bd1f97992a015ba9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762330"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>适用于 Skype for Business Server 的基于视频的屏幕共享 
 
Skype For Business Server 2015 中基于视频的屏幕共享 (VbSS) 现已可供下载[：Skype for Business Server 2015 累积更新 KB3061064。](https://www.microsoft.com/download/details.aspx?id=47690) VbSS 包含在 2019 Skype for Business Server中。
  
基于视频的屏幕共享（即 VbSS）退出 Lync 屏幕共享。 VbSS 与传统屏幕共享的区别与所使用的基础协议及其擅长内容有关。 屏幕共享使用远程桌面协议 (RDP) ，这非常能够创建数千个在用户计算机之间的一对一会话。 较新的技术 VbSS 将使用用户数据报协议 (UDP) 。
  
Skype for Business Server改进人们一对一及其一对多的多方 (对话和) 体验。 VbSS 利用媒体平台 (它依赖于 UDP 作为基础协议) ，目的是改善视频开始时间、观看 (尤其是当你正在观看的内容快速移动) 以及整体可靠性时。
  
改进屏幕共享的一部分是，在 VbSS 和 RDP 之间实现尽可能无缝的转换。 由于 VbSS 是针对 Skype for Business Server 的屏幕共享中使用的基础技术的更新，因此很难检测您利用的技术，除非您正在查看网络流量中的 SIP 详细信息，或者您共享的是快速移动的内容或三维内容。 例如，如果工作区中有许多旧版客户端，RDP 仍将作为会议和对话的故障安全。 Skype for Business Server使用内部逻辑来决定在客户端连接时 (VbSS 或传统屏幕) 应用哪一种方法。 RDP 可以且将替换为 VbSS（当情况需要它时）以便你的查看体验不会中断。
  
## <a name="planning"></a>规划

### <a name="vbss-pros-and-cons"></a>VbSS 的优缺点

切换到 VbSS 旨在进行三项关键改进：
  
1. 使屏幕共享功能 (RDP 相比) 5% 的可靠性。

2. 使会话设置和视频体验比仅 RDP 快一 (一半时间进行设置，每秒帧数提高 6：1) 。

3. 在低带宽条件下，即使共享高运动内容（如 3D 图形）也比 RDP 更有效。
    
请记住，这些数字依赖于网络的运行状况和正确性能调整，如果客户端位于移动设备上，则这些网络可能涉及您自己的外部网络。
  
还应注意，共享内容的一些保真度/清晰度已用于可靠性、速度和效率。 在大多数情况下，用户不会立即看到它。
  
### <a name="ports-and-protocols"></a>端口和协议

**所需的服务器端口**

|**服务器角色**|**服务名称**|**端口或端口范围**|**协议**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|前端服务器  <br/> |Skype for Business Server应用程序共享服务  <br/> |5065  <br/> |TCP  <br/> |用于应用程序共享的传入 SIP 侦听请求。  <br/> |
|前端服务器  <br/> |Skype for Business Server应用程序共享服务  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用于应用程序共享的媒体端口范围。  <br/> |
   
**所需的客户端端口**

|**组件**|**端口范围**|**协议**|**备注**|
|:-----|:-----|:-----|:-----|
|客户端  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |应用程序共享。  <br/> |
   
如果为以下媒体端口启用了 QoS，并且也启用了 VbSS，那么在包含桌面共享的会议期间，AS MCU 将使用下方加粗显示的视频端口设置用于屏幕共享流量。 
  
> [!IMPORTANT]
> 这些设置是一个特例，必须在实现这两个功能时使用这些确切设置。 这将覆盖 [QoS 文档中建议的其他设置](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)。 对于应用程序共享，除了定义这些端口值ASMCUSVC.exe还需要在 QoS GPO 中指定端口。 
  
**应用程序服务器 QoS/VbSS 所需设置**

|**属性**|**端口值**|**协议**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>容量规划

运行 Skype for Business Server 2015 累积更新 2 (CU2) 或更高版本的每个前端服务器最多支持 375 个参与者使用 RDP (但每个会议仅支持 250 个) 。 引入和使用 VbSS 时，此容量在 CU3 后不会更改。
  
也就是说，我们已在实验室中完成性能和压力测试，也应当根据你的部署环境考虑以下 (测量，当然) 。
  
假定：
  
- 在部署中使用的是 Skype for Business Server 2015 CU2 或更高版本。
    
- 用户环境中所有用户的Skype for Business Server分辨率高于 1920x1080。
    
达到完整容量 (如上所述，每个前端服务器总共有 375 个屏幕共享参与者，尽管每个会议) 只有 250 个参与者，但前端服务器可能使用大约 1 GB 网卡的 89%。 这是因为 Skype for Business Server CU2 (RDP) 中的现有屏幕共享技术以演示者电脑的本机分辨率传输屏幕内容。 因此，如果考虑更高的屏幕分辨率，你可能已经遇到使用 Skype for Business Server 2015 CU2 进行屏幕共享的网络瓶颈。
  
若要缓解这种情况，以下一个或多个选项可能会有所帮助：
  
- 将前端服务器从 1 GB 网卡升级到 10 GB 以太网卡。

- 增加前端服务器的数量以对流量进行负载平衡。

- 限制用于 VbSS () RDP (的带宽比特率，方法为任一通道使用的最大带宽设置上限。
    
此表中的数字受各个网络和共享内容的影响。 请进行测试，为网络建立基线。
  
|**1080p 内容**|**RDP 平均值**|**RDP 峰值**|**VbSS 平均值**|**VbSS 峰值**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|视频  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求

VbSS 带宽为：
  
|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率 (Kbps)**|**最小视频负载比特率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16：9)   <br/>  (纵横比取决于共享者监视器的分辨率，并且不会始终为 16：9)   <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>客户端和服务器支持

基于视频的屏幕共享需要 Skype for Business Server 2015 CU3 或更高版本，以及 Skype for Business 和会议支持的移动客户端功能[](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)比较中列出的支持客户端[的当前版本](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)。 
  
在某些情况下，屏幕共享将转换为 RDP，如下所示：
  
- 如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。
- 如果使用早期版本的 Skype for Business 客户端的人加入会话，例如使用低于 16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用的任何 Windows 客户端版本的任何人。 
- 如果用户正在从网站Skype for Business Web应用。
- 如果某人使用的是 Mac Skype for Business，但并非在 Skype for Business Online 或 Skype for Business Server 2015 上（包含 2018 年 7 月或更高版本的 2018 年 7 月累积更新 (或更高版本) ）。
- 如果有人启动任何计划/Windows共享。
- 如果有人开始录制会话。
- 如果有人在会话期间调用远程屏幕控制。 
- 参与者超过 250 人的会议 (目前不支持 VbSS) 。

请注意，会话转换到 RDP 后，将不会转换回 VbSS。 同样，从 VbSS 进行转换是无缝的，并且希望在大多数情况下都很难检测到。
    
> [!NOTE]
> 不支持在屏幕共享中阻止或尝试阻止从 VbSS Skype for Business RDP。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>启用、禁用和配置 VbSS

最重要的是，安装 Skype for Business Server 2015 累积更新 3 (CU3) 或更高版本后，默认情况下所有用户都将启用一对一和多方 VbSS。 如果你没有理由不为所有用户启用此功能，这可能会导致你出现问题。 在这种情况下，可以使用以下步骤禁用用户， (启用用户步骤将) ：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何禁止用户使用 VbSS

- 可以通过在 Skype for Business 管理控制台 (中运行此 cmdlet，为不应使用 VbSS 的任何用户分配不允许 VbSS 的用户策略 (将 [PolicyName] 替换为针对) 执行此操作的策略：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 还可以更新全局会议策略，这将影响没有分配策略的所有用户：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    有关此命令详细信息，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要完全关闭 VbSS，可以运行以下命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    有关此命令详细信息，请参阅 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方Skype for Business中，所有客户端终结点都将遵守会议组织者的策略设置。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何允许用户使用 VbSS

- 您可以通过在 Skype for Business 管理控制台 (中运行此 cmdlet，为需要使用 VbSS 的任何用户分配允许 VbSS 的特定用户策略，将 [PolicyName] 替换为针对) 执行此操作的策略：
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 还可以更新全局会议策略，这将影响没有分配策略的所有用户：
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    有关此命令详细信息，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要在关闭 VbSS (它默认打开，) 运行以下命令：
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    有关此命令详细信息，请参阅 [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方会议Skype for Business，所有客户端终结点都将遵守会议组织者的策略设置。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 累积更新 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[2015 年 6 月 (VBSS) 基于视频Skype for Business Server共享功能](https://support.microsoft.com/kb/3170163)