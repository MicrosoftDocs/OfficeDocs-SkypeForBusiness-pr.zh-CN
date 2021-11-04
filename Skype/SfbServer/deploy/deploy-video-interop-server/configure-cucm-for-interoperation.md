---
title: 配置 CUCM 以与 Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要：配置 CUCM 以使用Skype for Business Server。
ms.openlocfilehash: 809ad19e89f398c507673ec677b4ce882d341327
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741318"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a>配置 CUCM 以与 Skype for Business Server
 
**摘要：** 配置 CUCM 以使用Skype for Business Server。
  
> [!CAUTION]
> 此功能使用 Cisco 统一通信管理器 (CallManager 或 CUCM) 版本 10.5（仅通过 TCP 的中继设置）进行测试。 在继续之前，请验证 CUCM 环境是否满足这些条件。 
  
此处所述的设置仅用作如何配置 CUCM 以使用 VIS 的示例。 其他设置和/或备用 CUCM 功能的用法也可以用来获得相同的结果。 对于特定方案的最佳配置，不隐含任何建议。
  
需要确认或更改大量 CUCM 设置，以与 VIS 进行互操作。 请按照下面的过程操作，以避免缺少所需的设置。
  
### <a name="configure-the-cucm"></a>配置 CUCM

1. 登录到 CUCM 并导航到 Cisco Unified CM Administration- \> Call Routing- \> Class of Control- \> Partition。
    
2. 在"分区配置"屏幕中，输入分区名称和说明，然后单击"添加新 **"。**
    
3. 导航到 Cisco 统一 CM 管理 - \> 呼叫路由 - \> 控制类别 - \> 呼叫搜索空间。
    
4. 在"呼叫搜索空间配置"屏幕中，输入呼叫搜索空间的名称，在"选择的分区"中，输入刚创建的分区的名称。 完成后 **，单击** "保存"。
    
5. 导航到"Cisco 统一 CM 管理- \> 系统- \> 安全性- \> SIP 中继安全配置文件"。
    
6. 在"SIP 中继安全配置文件配置"屏幕中，按如下所示设置"SIP 中继安全配置文件信息"选项，然后单击"**添加新"。**
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |名称  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
   |设备安全模式  <br/> |非安全  <br/> |
   |传入传输类型  <br/> |TCP + UDP  <br/> |
   |传出传输类型  <br/> |TCP  <br/> |
   |传入端口  <br/> |5060  <br/> |
   
7. 导航到 Cisco 统一 CM 管理 - \> 设备- \> 设置 - SIP \> 配置文件。
    
8. 在"SIP 配置文件配置"屏幕中，设置"SIP 配置文件信息"选项，如下所示。 
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |名称  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   |说明  <br/> |SfBVideoInterop_SIPProfile  <br/> |
   
9. 在同一屏幕上，向下滚动到"SDP 配置文件信息"部分。 默认情况下 **，"早期优惠和** 重新邀请的 SDP 会话级别带宽修饰符"选项设置为 TIAS 和 AS。 仅将此选项更改为 TIAS。 如果将此选项保留为默认设置，Skype for Business Server将不能理解 SIP 消息中的带宽修饰符信息。 TIAS 表示特定于传输独立应用程序，而 AS 表示特定于应用程序。 这些是 RFC3890 中指定的 SIP 选项。
    
10. 在同一屏幕上，继续向下滚动。 在"SIP 配置文件的中继特定配置"下，选择"语音和视频呼叫的早期提供支持"，并将其设置为" (插入 **MTP"（如果需要)** 选项。 这将允许 CUCM 设置具有 Early Offer 的传出 SIP 呼叫。 CUCM 8.5 及以后的一项新功能是，它支持具有 Early Offer 的传出呼叫设置，而无需媒体 (MTP) 。
    
11. 确认在"SIP 选项 ping"部分，选中了"启用 OPTIONS Ping 以监视服务类型为'无 (默认) '的中继的目标状态"旁边的框。
    
12. 完成后，单击"添加新 **"。**
    
13. 导航到"Cisco 统一 CM 管理 - \> 设备- \> 中继"。 
    
14. 将设备协议设置为 SIP 并按"下一 **步"。**
    
15. 在"设备信息"下，将设备名称和 (可能设置为 SfBVideoInterop_SIPTrunk) ，将媒体资源组列表设置为包含正确媒体资源的 MRGL。 
    
16. 继续向下滚动。 视频呼叫 (MTP) ，如果尚未取消选中，请取消选中它。 选中"在所有活动 **统一 CM 节点上运行"选项**。 请注意，你应该将所有 CUCM 节点添加到Skype for Business Server配置。
    
17. 继续向下滚动。 设置"入站呼叫"和"设置"选项，如下所示。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |调用搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |AAR 呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |连接方转换 CSS  <br/> |CSS_SfBVideoInterop  <br/> |
   
18. 继续向下滚动。 在 SIP 中继配置的"SIP 信息目标"部分下，指定 VIS 池的 FQDN 或池中各个 VIS 服务器的 IP 地址， (添加多个) 。 在"目标端口"中，指定 VIS 侦听 CUCM 连接端口的端口 (默认值为 6001) 。 还要指定您之前创建的 SIP 中继安全配置文件和 SIP 配置文件，如下所示。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |SIP 中继安全配置文件  <br/> |SfBVideoInterop_SecurityProfile  <br/> |
    |重新路由呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |Out-of-Dialog Refer Calling Search Space  <br/> |CSS_SfBVideoInterop  <br/> |
    |订阅呼叫搜索空间  <br/> |CSS_SfBVideoInterop  <br/> |
    |SIP 配置文件  <br/> |SfBVideoInterop_SIPProfile  <br/> |
    |DTMF 信号方法  <br/> |RFC 2833  <br/> |
   
19.  继续向下滚动。 根据您的系统设置"录制信息"。 可以保留为"无 **"。** 
    
20. 完成后，单击"添加新 **"。**
    
21. 导航到 Cisco 统一 CM 管理 - \> 呼叫路由- \> 路由/智能 \> 寻线模式。
    
22. 在"路由模式配置"屏幕中，输入如下所示的模式定义参数。 向下滚动到"被叫方转换"部分，按如下所示设置掩码，然后在完成后单击" **添加新** "。
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |路由模式  <br/> |7779999  <br/> |
    |路由分区  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |说明  <br/> |SfBVideoInterop 的分区  <br/> |
    |网关/路由列表  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |被叫方转换掩码  <br/> |+14257779999  <br/> |
   
23. 导航到 Cisco 统一 CM 管理 - \> 呼叫路由 - \> SIP 路由模式。
    
24. 在"SIP 路由模式配置"屏幕中，按如下所示设置模式定义选项，然后单击"**添加新"。**
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    | 模式用法 <br/> |域路由  <br/> |
    |IPv4 模式  <br/> |contoso.com (IPv6 时保留为空)   <br/> |
    |IPv6 模式  <br/> |contoso.com (IPv4 时保留为空)   <br/> |
    |说明  <br/> |mediarv 的 SIPRoute 模式  <br/> |
    |路由分区  <br/> |SfBVideoInterop_RoutePartition  <br/> |
    |SIP 中继/路由列表  <br/> |SfBVideoInterop_SIPTrunk  <br/> |
    |阻止模式复选框  <br/> |保留未选中状态  <br/> |
   
25. 如果已更改音频或视频比特率的默认设置，则需要将其恢复为默认值。 若要设置音频/视频呼叫的比特率，请导航到"Cisco 统一 CM 管理- \> 系统- 区域 \> 信息- \> 区域"。 下面显示了默认值，仅供参考：
    
    |**参数**|**推荐设置**|
    |:-----|:-----|
    |区域  <br/> |默认值  <br/> |
    |音频编解码器首选项列表  <br/> |系统默认值  <br/> |
    |最大音频比特率  <br/> |64 kbps (G.722、G.711)   <br/> |
    |视频呼叫的最大会话比特率  <br/> |200000 kbps  <br/> |
    |最大会话比特率  <br/> |2000000000 kbps  <br/> |
   
此时，CUCM 视频网关已配置为与 VIS 一起运行。 您需要在要集成的每个 VTC 上完成相应的配置。
> [!NOTE]
> 为了提高恢复能力，您可能需要配置此 CUCM 网关以使用第二个视频互操作服务器或 VIS 池。 有关详细信息 [，请参阅](../../plan-your-deployment/video-interop-server.md#resiliency) 复原机制。
  
## <a name="see-also"></a>另请参阅

[配置 VTC 以与 Skype for Business Server](configure-a-vtc-for-interoperation.md)
