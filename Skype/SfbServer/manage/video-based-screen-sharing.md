---
title: 视频基于屏幕共享的 Skype 业务服务器
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype 的基于视频的屏幕共享 (VbSS) 的业务服务器规划和配置信息
ms.openlocfilehash: a658453af5f71d7bb8103411ed16c534e3004a03
ms.sourcegitcommit: aa3258aeb5aa1296c4bb251a9d258b8896457b7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/11/2018
ms.locfileid: "23935473"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>视频基于屏幕共享的 Skype 业务服务器 
 
基于视频的屏幕中的业务服务器 2015 Skype 中共享 (VbSS) 现可供下载：[业务服务器 2015年累积更新 KB3061064 的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)。 附带的业务服务器 2019 Skype VbSS。
  
基于视频的屏幕共享，或者 VbSS，变得从 Lync 注销屏幕共享。 VbSS 与传统屏幕共享之间的区别与所用的基础协议及其所擅长的技能有关。 屏幕共享使用远程桌面协议 (RDP)，该协议擅长在各用户计算机之间创建数千个一对一会话。 较新的技术 VbSS 将使用用户数据报协议 (UDP)。
  
Skype 业务服务器想要提高人的 1-为-1，以及其 1 对多 （多方） 对话和会议体验。 VbSS 使用媒体平台（该平台将 UDP 作为基础协议），旨在改进视频的开始时间、你所观看内容的观看质量（尤其是当你所观看的内容正在快速移动时）以及整体可靠性。
  
改进屏幕共享的部分目的在于尽可能无缝地在 VbSS 与 RDP 之间进行切换。 由于 VbSS 是屏幕共享 Skype 业务服务器中使用的基础技术的更新，因此它可能很难检测您在利用除非正在看 SIP 详细信息中的网络流量，或您正在共享的技术内容fast 移动或三维。 如果，例如，工作场所中有大量的旧客户端，RDP 将仍可作为安全模式向您的会议和对话。 Skype 业务服务器使用内部逻辑决定哪些 （VbSS 或传统的屏幕共享） 客户端连接时要应用的两种方法。 RDP 在必要时可以并且会替换为 VbSS，确保你的观看体验不会被中断。
  
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

|**服务器角色**|**服务名称**|**端口或端口范围**|**协议**|**说明**|
|:-----|:-----|:-----|:-----|:-----|
|前端服务器  <br/> |Skype 业务服务器应用程序共享服务  <br/> |5065  <br/> |TCP  <br/> |用于应用程序共享的传入 SIP 侦听请求。  <br/> |
|前端服务器  <br/> |Skype 业务服务器应用程序共享服务  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |用于应用程序共享的媒体端口范围。  <br/> |
   
**所需的客户端端口**

|**组件**|**端口范围**|**协议**|**说明**|
|:-----|:-----|:-----|:-----|
|客户端  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |应用程序共享。  <br/> |
   
如果以下的媒体端口已启用 QoS，还启用 VbSS 包括 AS MCU 将使用视频端口设置中所示的桌面共享会议期间加粗下面的屏幕共享流量。 
  
> [!IMPORTANT]
> 这些设置是一个特例，并实现这些功能的时，必须使用这些准确的设置。 这将覆盖[QoS 文档](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)中的其他建议的设置。 此外需要 QoS GPO 除了定义这些端口值中指定 ASMCUSVC.exe Fo 共享您的应用程序。 
  
**应用程序服务器 QoS/VbSS 所需的设置**

|**属性**|**端口值**|**协议**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>容量规划

每个前端服务器运行 Skype 业务服务器 2015年累积更新 2 (CU2) 或更高版本支持的屏幕共享使用 RDP (每个会议的虽然只 250) 达 375 参与者。 引入并使用 VbSS 时，此容量在 CU3 后不会更改。
  
也就是说，我们已在实验室中完成性能和压力测试，并且就你自己的部署还应考虑以下度量（当然具体要取决于使用情况）。
  
假设：
  
- 您正在使用 Skype 业务 Server 2015 CU2 或更高版本中您的部署。
    
- 在您 Skype 业务服务器环境中的所有用户都具有高于 1920 x 1080 的屏幕分辨率。
    
全容量 （即如上所述，每个前端服务器的 375 屏幕共享参与者在每个会议的总，但仅 250），您前端服务器可能正在使用 ~ 89%1 千兆位网卡。 这是因为现有屏幕共享业务服务器 CU2 (RDP) 的技术 Skype 中的传输屏幕上内容的演示者的 PC 本机的分辨率。 因此使用较高的屏幕分辨率分解，您可能已遇到屏幕与 Skype 的业务 Server 2015 CU2 共享的网络瓶颈。
  
要缓解此问题，以下一个或多个选项可能有用：
  
- 从 1 千兆位网卡的您前端服务器升级到 10 的千兆以太网卡片。

- 增加到负载平衡流量的前端服务器数量。

- 通过对任意通道所用的最大带宽设定限制来限制用于 VbSS 和 RDP 的带宽（比特率）。
    
此表中的数字受个别网络和所共享内容的影响。请通过测试建立一个或多个网络的基准。
  
|**1080p 内容 **|**RDP 平均值**|**RDP 峰值**|**VbSS 平均值**|**VbSS 峰值**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 kbps  <br/> |12mbps  <br/> |100 kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|视频  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>媒体流量的网络带宽要求

VbSS 带宽为：
  
|**视频编解码器**|**分辨率和纵横比**|**最大视频负载比特率 (Kbps)**|**最小视频负载比特率 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> （纵横比取决于共享者的显示器分辨率，并且不会始终为 16:9）  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>客户端和服务器支持

基于视频的屏幕共享要求 Skype 的业务服务器 2015 CU3 或更高版本，以及支持客户端[的 Skype for Business 的移动客户端功能比较](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)和[会议支持](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)中列出的当前版本。 
  
有其中屏幕共享将转换到 RDP，类似这样的情况下：
  
- 如果你的帐户托管在 ASMCU 不满足支持 VbSS 的最低内部版本的环境中。
- 如果 for Business 客户端使用的 Skype 较早版本的任何人加入会话，例如任何人都使用低于 16.0.6330.1000，对于业务会议室系统设备，Skype 或业务移动应用程序的 Skype 任何 Windows 客户端版本。 
- 如果用户正在共享 Skype 的企业 Web 应用程序。
- 如果有人在 Mac 上的业务用 Skype 并不驻留在 Skype 业务 online。
- 如果某人开始任何程序/Windows 共享。
- 如果某人开始录制会话。
- 如果某人在会话期间调用远程屏幕控制。

    请注意，会话切换到 RDP 后，将不会切换回 VbSS。另外，从 VbSS 进行切换应为无缝操作，并且希望在大多数情况下不容易被检测到。
  
- 包含 250 个以上的参与者的会议（当前不支持 VbSS）。
    
> [!NOTE]
> 它具有不受支持到块中，或尝试阻止，请从转换 VbSS 到中 Skype RDP 业务屏幕共享。 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>启用、禁用和配置 VbSS

很好的做法是，您已安装 Skype 业务服务器 2015年累积更新 3 (CU3) 或更高版本，您的所有用户将为都启用 1-1 和多方 VbSS 默认情况下之后。 如果你有理由不为所有用户启用此功能，这对你来说可能有问题。 在这种情况下，你可以使用这些步骤禁用用户（然后执行启用用户步骤）：
  
### <a name="how-to-disable-users-from-using-vbss"></a>如何禁止用户使用 VbSS

- 您可以分配给不应通过为业务管理控制台 （替换 [PolicyName] 与您正在执行此操作的策略） Skype 中运行此 cmdlet 使用 VbSS 任何用户不允许 VbSS 的用户策略：
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 你还可以更新全局会议策略，这会影响所有未分配策略的用户：
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    此命令的详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要完全关闭 VbSS，你可以运行以下命令：
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在业务会议多方 Skype，所有客户端终结点将尊重会议组织者的策略设置。 
  
### <a name="how-to-enable-users-to-use-vbss"></a>如何允许用户使用 VbSS

- 您可以分配给需要通过业务管理控制台 （替换 [PolicyName] 与您正在执行此操作的策略） 的 Skype 中运行此 cmdlet 使用 VbSS 任何用户允许 VbSS 的特定用户策略：
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 你还可以更新全局会议策略，这会影响所有未分配策略的用户：
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    此命令的详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
    
- 如果需要在关闭 VbSS 后将其重新打开（默认情况下处于打开状态），你可以运行以下命令：
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    此命令的详细信息，请参阅[设置 CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)。
    
> [!NOTE]
> 在业务会议多方 Skype，所有客户端终结点将尊重会议组织者的策略设置。 
  
## <a name="see-also"></a>另请参阅

[业务服务器 2015年累积更新 KB3061064 的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[基于视频的屏幕共享 (VBSS) 有业务服务器 2015年的 Skype](https://support.microsoft.com/en-us/kb/3170163)
