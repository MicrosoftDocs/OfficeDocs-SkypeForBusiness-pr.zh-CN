---
title: 配置 CUCM 以与 Skype for Business Server 2015 进行互操作
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要： 配置 CUCM 以使用 Skype 的业务服务器 2015年。
ms.openlocfilehash: 04913508ba0200da4b34e8b1e18c3e57a5fc7141
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501967"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server-2015"></a>配置 CUCM 以与 Skype for Business Server 2015 进行互操作
 
**摘要：** 配置 CUCM 以使用 Skype 的业务服务器 2015年。
  
> [!CAUTION]
> 使用仅通过 TCP 的中继设置在 CUCM 10.5 版上测试了此功能。请验证 CUCM 环境是否满足这些条件，然后方可继续下一步。 
  
此处所述的设置，旨在仅作为 CUCM 可以配置方式的示例使用 VIS. 也可使用其他设置和/或备选 CUCM 功能来实现同样的结果。 示例中不对适用于特定场景的最佳配置作任何推荐暗示。
  
需要确认或更改大量 CUCM 设置才能与 VIS 进行互操作。请按照以下过程操作以避免错过必要的设置。
  
### <a name="configure-the-cucm"></a>配置 CUCM

1. 登录到 CUCM 并导航到 Cisco 统一厘米管理-\>呼叫路由-\>类的控件-\>分区。
    
2. 在“分区配置”屏幕中，输入分区名称和说明，然后单击“**新增**”。
    
3. 导航到 Cisco 统一厘米管理-\>呼叫路由-\>控件-类\>调用搜索空间。
    
4. 在“呼叫搜索空间配置”屏幕中，输入呼叫搜索空间的名称，然后在“所选分区”中输入刚才创建的分区名称。完成时，单击“**保存**”。
    
5. 导航到 Cisco 统一厘米管理-\>系统-\>安全-\>SIP 中继的安全配置文件。
    
6. 在“SIP 中继安全配置文件配置”屏幕中，如图所示设置“SIP 中继安全配置文件信息”选项，然后单击“**新增**”。
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |名称  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |设备安全模式  <br/> |非安全  <br/> |
   |传入传输类型  <br/> |TCP + UDP  <br/> |
   |传出传输类型  <br/> |TCP  <br/> |
   |传入端口  <br/> |5060  <br/> |
   
7. 导航到 Cisco 统一厘米管理-\>设备-\>设备设置-\>SIP 配置文件。
    
8. 在“SIP 配置文件配置”屏幕中，如图所示设置“SIP 配置文件信息”选项。 
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |名称  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |说明  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 在同一个屏幕上，向下滚动 SDP 配置文件信息部分。 “**Early Offer 和重新邀请的 SDP 会话级别带宽修饰符**”选项默认设为 TIAS 和 AS。 将此选项更改为仅 TIAS。 如果您将此选项保留为其默认设置，Skype 业务服务器不能理解的 SIP 消息对话中的带宽修饰符信息。 TIAS 表示 Transport Independent Application Specific（特定于传输独立的应用程序），AS 表示 Application Specific（特定于应用程序）。 这些是在 RFC3890 中指定的 SIP 选项。
    
10. 在同一屏幕上，继续向下滚动。 在 SIP 配置文件的中继特定配置下选择 * * 早期的语音和视频呼叫 * * 提供支持，并将其设置为**强制 （插入 MTP 如果需要）** 选项。 这使得 CUCM 能够设置具有 Early Offer 的传出 SIP 呼叫。 CUCM 8.5 中有一些新增功能，其中一个在于，它无需媒体端点 (MTP) 便可支持具有 Early Offer 的传出呼叫设置。
    
11. 在“SIP 选项 ping”部分，验证是否选中“启用选项 Ping 以监控具有服务类型‘无（默认）’的中继的目标状态”旁边的复选框。
    
12. 完成后，单击“**新增**”。
    
13. 导航到 Cisco 统一厘米管理-\>设备-\>中继。 
    
14. 将设备协议设为 SIP，然后单击“**下一步**”。
    
15. 在“设备信息”下，设置“设备名称”和“说明”（比如 SfBVideoInterop_SIPTrunk），然后将“媒体资源组列表”设为包含正确的媒体资源的 MRGL。 
    
16. 继续向下滚动。 视频呼叫无需媒体端点 (MTP)，如果尚未取消选中它，请取消选中。 选中“**在所有活动统一 CM 节点上运行**”的选项。 请注意，您应将所有 CUCM 节点都添加到业务服务器配置的 Skype。
    
17. 继续向下滚动。如图所示设置“入站呼叫”和“连接方设置”选项。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR 呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |连接方转换 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. 继续向下滚动。 在 SIP 中继配置的 SIP 信息目标部分中，在池 （添加多个条目） 指定 VIS 池的 FQDN 或 IP 地址的单个 VIS 服务器。 在目标端口指定 VIS 正在监听来自 CUCM 的连接的端口 （默认为 6001）。 此外指定的 SIP 中继安全配置文件和更早版本，创建的 SIP 配置文件，如下所示。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |SIP 中继安全配置文件  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |重新路由呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog 引用呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |订阅呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP 配置文件  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF 信号方法  <br/> |RFC 2833  <br/> |
   
19.  继续向下滚动。 为您的系统设置相应的“记录信息”。 若要将其设置为**None**没关系。 
    
20. 完成后，单击“**新增**”。
    
21. 导航到 Cisco 统一厘米管理-\>呼叫路由-\>路由/智能寻线-\>路由模式。
    
22. 在“路由模式配置”屏幕中，如下所示输入模式定义参数。向下滚动至“被叫方转换”部分并按图中所示设置掩码，然后在完成时单击“**新增**”。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |路由模式  <br/> |7779999  <br/> |
    |路由分区  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |说明  <br/> |SfBVideoInterop 的分区  <br/> |
    |网关/路由列表  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |被叫方转换掩码  <br/> |+14257779999  <br/> |
   
23. 导航到 Cisco 统一厘米管理-\>呼叫路由-\>SIP 路由模式。
    
24. 在“SIP 路由模式配置”屏幕中，如图所示设置“模式定义”选项，然后单击“**新增**”。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    | 模式使用 <br/> |域路由  <br/> |
    |IPv4 模式  <br/> |contoso.com（ 使用 IPv6 时则留空）  <br/> |
    |IPv6 模式  <br/> |contoso.com（ 使用 IPv4 时则留空）  <br/> |
    |说明  <br/> |到 mediarv 的 SIP 路由模式  <br/> |
    |路由分区  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP 中继/路由列表  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |“阻止模式”复选框  <br/> |保留未选中状态  <br/> |
   
25. 如果您更改了音频或视频比特率的默认设置，您需要将其重设为默认设置。 若要设置的音频/视频呼叫的比特率，导航到 Cisco 统一厘米管理-\>系统-\>地区信息-\>区域。 默认设置如下所示（供参考）：
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |区域  <br/> |默认值  <br/> |
    |音频编解码器首选项列表  <br/> |系统默认值  <br/> |
    |最大音频比特率  <br/> |64 kbps（G.722、G.711）  <br/> |
    |视频呼叫的最大会话比特率  <br/> |200000 kbps  <br/> |
    |最大会话比特率  <br/> |2000000000 kbps  <br/> |
   
此时，CUCM 视频网关被配置为与 VIS 进行协作。 必须在要集成的每个 VTC 上完成相应的配置。
> [!NOTE]
> 若要提高恢复能力，您可能要配置此 CUCM 网关以与第二个视频互操作服务器或 VIS 池一起使用。 有关更多信息，请参阅[Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency)。
  
## <a name="see-also"></a>另请参阅

[为业务服务器 2015年与 Skype 的互操作配置 VTC](configure-a-vtc-for-interoperation.md)