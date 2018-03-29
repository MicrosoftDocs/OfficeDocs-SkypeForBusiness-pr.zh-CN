---
title: 适用于 Skype for Business Server 2015 的基于视频的屏幕共享
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype 业务服务器 2015年规划和配置信息，针对基于视频的屏幕共享 (VbSS)，即现在可供下载： Skype 的业务服务器 2015年累积更新 KB3061064。
ms.openlocfilehash: 21b7868efb9b1a6621aa85cae277114629d67551
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="video-based-screen-sharing-for-skype-for-business-server-2015"></a>适用于 Skype for Business Server 2015 的基于视频的屏幕共享
 
Skype 业务服务器 2015年规划和配置信息，针对基于视频的屏幕共享 (VbSS)，即现在可供下载： [Skype 的业务服务器 2015年累积更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。
  
基于视频的屏幕共享，或 VbSS，起源于 Lync 屏幕共享。 VbSS 与传统屏幕共享之间的区别与所用的基础协议及其所擅长的技能有关。 屏幕共享使用远程桌面协议 (RDP)，该协议擅长在各用户计算机之间创建数千个一对一会话。 较新的技术 VbSS 将使用用户数据报协议 (UDP)。
  
Skype 业务服务器希望提高人民 1-到-1 和他们 1 到许多 （多方） 对话和会议体验。 VbSS 使用媒体平台（该平台将 UDP 作为基础协议），旨在改进视频的开始时间、你所观看内容的观看质量（尤其是当你所观看的内容正在快速移动时）以及整体可靠性。
  
改进屏幕共享的部分目的在于尽可能无缝地在 VbSS 与 RDP 之间进行切换。 VbSS 是为业务服务器共享的 Skype 的屏幕中使用的基础技术的更新，因为它可能很难检测哪种技术利用除非 SIP 的详细信息，在网络通信中，您正在查看或共享内容的是快速移动或三维效果样式。 如果，例如，您的工作区有大量的旧客户端，RDP 将仍可作为您的会议和对话安全模式。 Skype 业务服务器使用内部的逻辑来决定 （VbSS 或传统屏幕共享） 的客户端连接时要应用的两种方法。 RDP 在必要时可以并且会替换为 VbSS，确保你的观看体验不会被中断。
  
## <a name="planning"></a>规划

### <a name="vbss-pros-and-cons"></a>VbSS 的利与弊

切换到 VbSS 旨在做出三项关键改进：
  
1. 与单独的 RDP 相比，提高屏幕共享的可靠性（高达 5%）。

2. 与单独的 RDP 相比，使会话设置和视频体验更快（设置时间减半，每秒帧数提高为 6:1）。

3. 在低带宽情况下优于 RDP，即使在共享高运动内容（如三维图形）时也是如此。
    
请记住，这些数字依赖于你网络的运行状况和适当性能调整，并且可能涉及你自身外部的网络（如果你的客户端位于移动设备上）。
  
你还应注意，我们牺牲了共享内容的部分保真度/脆度来确保可靠性、速度和效率。在大多数情况下，这对用户并不明显。
  
### <a name="ports-and-protocols"></a>端口和协议

**必需的服务器端口**

|**服务器角色**|**服务名称**|**端口或端口范围**|**协议**|**说明**|
|:-----|:-----|:-----|:-----|:-----|
|前端服务器  <br/> |Skype 业务服务器应用程序共享服务  <br/> |5065  <br/> |TCP  <br/> |用于应用程序共享的传入 SIP 侦听请求。  <br/> |
|前端服务器  <br/> |Skype 业务服务器应用程序共享服务  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用于应用程序共享的媒体端口范围。  <br/> |
   
**必需的客户端端口**

|**组件**|**端口范围**|**协议**|**说明**|
|:-----|:-----|:-----|:-----|
|客户端  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |应用程序共享。  <br/> |
   
如果下面的媒体端口已启用 QoS 和 VbSS 也被启用，包括作为 MCU 将使用中所示的视频端口设置桌面共享会议期间粗下面屏幕共享通信。 
  
> [!IMPORTANT]
> 这些设置是一种特殊情况，以及实施这两项功能时，必须使用这些精确的设置。 这将覆盖其他[QoS 的文档](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)中的推荐的设置。 Fo 应用程序共享，您还需要定义这些端口值除了 QoS GPO 中指定 ASMCUSVC.exe。 
  
**应用程序服务器 QoS/VbSS 所需设置**

|**属性**|**端口值**|**协议**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>容量规划

每个前端服务器运行 Skype 业务服务器 2015年累积更新 2 (CU2) 支持的屏幕共享使用 RDP (每个会议虽然只 250) 达 375 参与者。 引入并使用 VbSS 时，此容量在 CU3 后不会更改。
  
也就是说，我们已在实验室中完成性能和压力测试，并且就你自己的部署还应考虑以下度量（当然具体要取决于使用情况）。
  
假设：
  
- 您使用 Skype 业务服务器 2015 CU2 为您的部署中。
    
- 您 Skype 业务服务器环境中的所有用户都具有高于 1920 x 1080 的分辨率。
    
在大容量 （这如上所述，在每个会议的总额，但只有 250 是 375 屏幕共享参与者每个前端服务器） 时，您前端服务器可能正在使用的 1 千兆位网卡的 ~ 89%。 这是因为现有的屏幕共享技术的 Skype 业务服务器 CU2 (RDP) 传输演示者计算机的本机分辨率屏幕内容。 因此具有较高的屏幕分辨率分解，您可能已经遇到与 Skype 业务服务器 2015 CU2 共享屏幕的网络瓶颈。
  
要缓解此问题，以下一个或多个选项可能有用：
  
- 从 1 千兆位网卡的您前端服务器升级到 10 千兆以太网卡。

- 增加流量的负载平衡的前端服务器数。

- 通过对任意通道所用的最大带宽设定限制来限制用于 VbSS 和 RDP 的带宽（比特率）。
    
此表中的数字受个别网络和所共享内容的影响。请通过测试建立一个或多个网络的基准。
  
|**1080p 内容**|**RPD 平均值**|**RDP 高峰**|**VbSS 平均值**|**VbSS 峰值**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 kbps 速率进行传输  <br/> |12mbps  <br/> |100 kbps 速率进行传输  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|视频  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求

VbSS 带宽为：
  
|**视频编解码器**|**分辨率和长宽比**|**视频的最大有效载荷比特率 (Kbps)**|**视频的最小有效载荷比特率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> （纵横比取决于共享者的显示器分辨率，并且不会始终为 16:9）  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>客户端和服务器支持

基于视频的屏幕共享要求 Skype 业务服务器 2015 CU3 或更高版本，以及支持[业务的 Skype 的移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)和[会议支持](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)中列出的客户机的当前版本。 
  
还有一些情况下，屏幕共享将过渡到 RDP，像这样：
  
- 如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。
- 如果对业务客户端使用较旧版本的 Skype 的人加入您的会话，例如任何人使用低于 16.0.6330.1000，对于业务室系统设备，Skype 或 Skype 业务移动应用程序的任何 Windows 客户端版本。 
- 如果用户正在共享 Skype 为企业 Web 应用程序。
- 如果有人正在使用 Skype 的 Businesson Mac 并不驻留在 Skype 上的在线业务。
- 如果某人在会话期间启动任何程序/Windows 共享和/或录制。
- 如果某人在会话期间调用远程屏幕控制。

    请注意，会话切换到 RDP 后，将不会切换回 VbSS。另外，从 VbSS 进行切换应为无缝操作，并且希望在大多数情况下不容易被检测到。
  
- 包含 250 个以上的参与者的会议（当前不支持 VbSS）。
    
> [!NOTE]
> 它不支持到块中，或试图阻止，过渡从 VbSS 到在 Skype 的 RDP 业务屏幕共享。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>启用、禁用和配置 VbSS

很好的做法是，一旦您已经为业务服务器 2015年累积更新 3 (CU3)，所有用户将默认为 1--1 和多方 VbSS 启用安装 Skype。 如果你有理由不为所有用户启用此功能，这对你来说可能有问题。 在这种情况下，你可以使用这些步骤禁用用户（然后执行启用用户步骤）：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何禁止用户使用 VbSS

- 您可以分配给任何用户不应使用 VbSS 通过 Skype 在运行该 cmdlet 业务管理控制台 （这样的策略替换 [PolicyName]） 不允许 VbSS 的用户策略：
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 你还可以更新全局会议策略，这会影响所有未分配策略的用户：
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    有关此命令的详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要完全关闭 VbSS，你可以运行以下命令：
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    有关此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 商务会议多方 Skype，在所有客户端终结点将尊重会议组织者的策略设置。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何允许用户使用 VbSS

- 您可以分配一个特定的用户策略，允许任何用户需要通过 Skype 在运行该 cmdlet 业务管理控制台 （这样的策略替换 [PolicyName]） 使用 VbSS VbSS:
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 你还可以更新全局会议策略，这会影响所有未分配策略的用户：
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    有关此命令的详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要在关闭 VbSS 后将其重新打开（默认情况下处于打开状态），你可以运行以下命令：
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    有关此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 商务会议多方 Skype，在所有客户端终结点将尊重会议组织者的策略设置。 
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 的业务服务器 2015年累积更新 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[基于视频的屏幕共享 (VBSS) 可用于 Skype 的业务服务器 2015](https://support.microsoft.com/en-us/kb/3170163)

