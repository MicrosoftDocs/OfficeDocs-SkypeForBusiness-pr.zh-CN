---
title: 适用于 Skype for Business Server 的基于视频的屏幕共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 基于视频的屏幕共享的 Skype for business 服务器规划和配置信息 (VbSS)
ms.openlocfilehash: ae2cc683148fdb2a2cb80e3fe3cf25a698a56c00
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548993"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>适用于 Skype for Business Server 的基于视频的屏幕共享 
 
Skype for business Server 2015 中的基于视频的屏幕共享 (VbSS) 现在可供下载: [skype for Business server 2015 累积更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。 VbSS 包含在 Skype for Business Server 2019 中。
  
基于视频的屏幕共享或 VbSS 从 Lync 屏幕共享中增长。 VbSS 与传统屏幕共享之间的区别与所用的基础协议及其所擅长的技能有关。 屏幕共享使用远程桌面协议 (RDP)，该协议擅长在各用户计算机之间创建数千个一对一会话。 较新的技术 VbSS 将使用用户数据报协议 (UDP)。
  
Skype for Business 服务器希望提高人员的1对 1, 以及其一对多 (多方) 对话和会议体验。 VbSS 使用媒体平台（该平台将 UDP 作为基础协议），旨在改进视频的开始时间、你所观看内容的观看质量（尤其是当你所观看的内容正在快速移动时）以及整体可靠性。
  
改进屏幕共享的部分目的在于尽可能无缝地在 VbSS 与 RDP 之间进行切换。 由于 VbSS 是对 Skype for business Server 的屏幕共享中使用的基础技术的更新, 因此可能很难检测你正在使用的技术, 除非你在网络流量中查看 SIP 详细信息, 或者你正在共享的内容快速移动或三维。 例如, 如果您的工作场所有大量旧版客户端, 则 RDP 仍可用作您的会议和对话的安全保护。 Skype for Business 服务器使用内部逻辑确定在客户端连接时要应用的两种方法 (VbSS 或传统的屏幕共享)。 RDP 在必要时可以并且会替换为 VbSS，确保你的观看体验不会被中断。
  
## <a name="planning"></a>规划

### <a name="vbss-pros-and-cons"></a>VbSS 的利与弊

切换到 VbSS 旨在做出三项关键改进：
  
1. 与单独的 RDP 相比，提高屏幕共享的可靠性（高达 5%）。

2. 与单独的 RDP 相比，使会话设置和视频体验更快（设置时间减半，每秒帧数提高为 6:1）。

3. 在低带宽情况下优于 RDP，即使在共享高运动内容（如三维图形）时也是如此。
    
请记住，这些数字依赖于你网络的运行状况和适当性能调整，并且可能涉及你自身外部的网络（如果你的客户端位于移动设备上）。
  
你还应注意，我们牺牲了共享内容的部分保真度/脆度来确保可靠性、速度和效率。在大多数情况下，这对用户并不明显。
  
### <a name="ports-and-protocols"></a>端口和协议

**所需的服务器端口**

|**服务器角色**|**服务名称**|**端口或端口范围**|**协议**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|前端服务器  <br/> |Skype for Business 服务器应用程序共享服务  <br/> |5065  <br/> |TCP  <br/> |用于应用程序共享的传入 SIP 侦听请求。  <br/> |
|前端服务器  <br/> |Skype for Business 服务器应用程序共享服务  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用于应用程序共享的媒体端口范围。  <br/> |
   
**所需的客户端端口**

|**组件**|**端口范围**|**协议**|**注释**|
|:-----|:-----|:-----|:-----|
|客户端  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |应用程序共享。  <br/> |
   
如果为以下媒体端口启用了 QoS, 并且在包括桌面共享的会议期间启用了 VbSS, 则在屏幕共享流量中, 将使用以粗体显示的视频端口设置。 
  
> [!IMPORTANT]
> 这些设置是一种特殊情况, 在实现这些功能时, 必须使用这些确切设置。 这将覆盖[文档中针对 QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)的其他推荐设置。 对于应用程序共享, 除了定义这些端口值之外, 还需要在 QoS GPO 中指定 ASMCUSVC。 
  
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

运行 Skype for Business Server 2015 累积更新 2 (CU2) 或更高版本的每台前端服务器都支持使用 RDP 的屏幕共享的最多375个参与者 (尽管每个会议仅有 250)。 引入并使用 VbSS 时，此容量在 CU3 后不会更改。
  
也就是说，我们已在实验室中完成性能和压力测试，并且就你自己的部署还应考虑以下度量（当然具体要取决于使用情况）。
  
假设：
  
- 您在部署中使用的是 Skype for Business Server 2015 CU2 或更高版本。
    
- Skype for Business 服务器环境中的所有用户都具有比1920x1080 更高的屏幕分辨率。
    
在完全容量 (如上所述) 是每台前端服务器的375屏幕共享参与者总数, 虽然只有250每个会议, 但你的前端服务器可能正在使用约1千兆个网卡的 89%。 这是因为 Skype for Business Server CU2 (RDP) 中的现有屏幕共享技术以演示者电脑的本机分辨率传输屏幕内容。 因此, 在中考虑更高的屏幕分辨率, 你可能已遇到与 Skype for Business Server 2015 CU2 的屏幕共享的网络瓶颈。
  
要缓解此问题，以下一个或多个选项可能有用：
  
- 将前端服务器从1千兆位网卡升级到10千兆位以太网卡。

- 增加前端服务器的数量以达到负载平衡流量。

- 通过对任意通道所用的最大带宽设定限制来限制用于 VbSS 和 RDP 的带宽（比特率）。
    
此表中的数字受个别网络和所共享内容的影响。请通过测试建立一个或多个网络的基准。
  
|**1080p 内容 **|**RDP 平均**|**RDP 峰值**|**VbSS 平均值**|**VbSS 峰值**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|视频  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求

VbSS 带宽为：
  
|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率 (Kbps)**|**最小视频负载比特率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> （纵横比取决于共享者的显示器分辨率，并且不会始终为 16:9）  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>客户端和服务器支持

基于视频的屏幕共享需要 Skype for business Server 2015 CU3 或更高版本, 以及适用于 Skype for business 和[会议支持](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)的[移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)中列出的支持客户端的当前版本。 
  
在某些情况下, 屏幕共享将转换为 RDP, 如下所示:
  
- 如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。
- 如果使用较早版本的 Skype for Business 客户端的人员加入你的会话, 例如任何使用低于16.0.6330.1000、Skype for Business 会议室系统设备或 Skype for Business 移动应用的任何 Windows 客户端版本的用户。 
- 如果用户从 Skype for Business Web 应用共享。
- 如果有人使用的是 Mac 版 Skype for business, 而不是托管在 Skype for business Online 或 Skype for business Server 2015 上 (使用7月、2018累积更新 (或更高版本)。
- 如果某人启动了任何程序/Windows 共享。
- 如果有人开始录制会话。
- 如果某人在会话期间调用远程屏幕控制。 
- 包含 250 个以上的参与者的会议（当前不支持 VbSS）。

请注意，会话切换到 RDP 后，将不会切换回 VbSS。另外，从 VbSS 进行切换应为无缝操作，并且希望在大多数情况下不容易被检测到。
    
> [!NOTE]
> 在 Skype for Business 屏幕共享中, 不支持阻止或尝试阻止、从 VbSS 切换到 RDP。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>启用、禁用和配置 VbSS

好的是, 一旦您安装了 Skype for Business Server 2015 累积更新 3 (CU3) 或更高版本后, 默认情况下, 所有用户都将启用1到1和多方 VbSS。 如果你有理由不为所有用户启用此功能，这对你来说可能有问题。 在这种情况下，你可以使用这些步骤禁用用户（然后执行启用用户步骤）：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何禁止用户使用 VbSS

- 你可以通过在 Skype for Business 管理控制台中运行此 cmdlet 来分配不允许 VbSS 使用 VbSS 的用户策略 (使用你为其执行此操作的策略替换 [PolicyName]):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 你还可以更新全局会议策略，这会影响所有未分配策略的用户：
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    有关此命令的详细信息, 请参阅[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要完全关闭 VbSS，你可以运行以下命令：
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    有关此命令的详细信息, 请参阅[Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方 Skype for business 会议中, 所有客户终结点都将遵守会议组织者的策略设置。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何允许用户使用 VbSS

- 你可以通过在 Skype for Business 管理控制台中运行此 cmdlet 来分配特定的用户策略, 从而允许 VbSS 使用 VbSS 的任何用户 (使用你执行此操作的策略替换 [PolicyName]):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 你还可以更新全局会议策略，这会影响所有未分配策略的用户：
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    有关此命令的详细信息, 请参阅[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要在关闭 VbSS 后将其重新打开（默认情况下处于打开状态），你可以运行以下命令：
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    有关此命令的详细信息, 请参阅[Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在多方 Skype for business 会议中, 所有客户端终结点将遵循会议组织者的策略设置。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 2015 累积更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[基于视频的屏幕共享 (VBSS) 在 Skype for Business Server 2015 中可用](https://support.microsoft.com/en-us/kb/3170163)
