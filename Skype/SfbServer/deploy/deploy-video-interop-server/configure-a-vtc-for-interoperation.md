---
title: 为业务服务器与 Skype 的互操作配置 VTC
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要： 配置对业务服务器使用 Skype VTC 设备。
ms.openlocfilehash: 1a8422ddfa33652fa13d5aeb42b86a72b809126b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219672"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>为业务服务器与 Skype 的互操作配置 VTC
 
**摘要：** 配置对业务服务器使用 Skype VTC 设备。
  
需要执行以下配置自定义过程将连接到业务 VIS 服务器通过 SIP 中继的 Skype 和 Cisco 统一通信管理器 （CallManager 或 CUCM） 每个 VTC 视频的网关。
  
此处所述的设置，旨在仅作为 CUCM 可以配置方式的示例使用 VIS. 也可使用其他设置和/或备选 CUCM 功能来实现同样的结果。 示例中不对适用于特定场景的最佳配置作任何推荐暗示。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>配置在 CUCM 注册的 VTC

1. 登录到 Cisco VTC 设备并导航到配置-\>系统配置-\>设置。
    
2. 验证以下设置并根据需要进行更正： 
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |设置模式  <br/> | CUCM <br/> |
   |外部管理器地址  <br/> | CUCM 的 FQDN <br/> |
   | ExternalManager 域 <br/> |CUCM 的域  <br/> |
   
3. 导航到配置-\>系统配置-\>网络。
    
4. 验证以下设置并根据需要进行更正： 
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |DNS 域名  <br/> | CUCM 的域名 <br/> |
   |DNS 服务器 1 地址  <br/> | 您所需的 DNS 服务器地址 <br/> |
   
5. 导航到配置-\>系统配置-\>网络服务。 确保关闭 H.323 模式并打开 SIP 模式。 
    
6. 终结点在 CUCM 注册时，将自动设置这些选项。验证以下设置并根据需要进行更正： 
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |H.323 模式  <br/> | 关 <br/> |
   |HTTP 模式  <br/> | 开 <br/> |
   | SIP 模式 <br/> | 开 <br/> |
   |Telnet 模式  <br/> | 开 <br/> |
   |欢迎文本  <br/> | 开 <br/> |
   |XMLAPI 模式  <br/> | 开 <br/> |
   
7. 导航到配置-\>系统配置-\>SIP。
    
8. 验证以下设置并根据需要进行更正： 
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |配置文件 1 - 默认传输  <br/> | TCP <br/> |
   |配置文件 1 - 出站  <br/> | 关 <br/> |
   |配置文件 1-TlsVerify  <br/> | 开 <br/> |
   |配置文件 1 - 类型  <br/> | Cisco <br/> |
   |配置文件 1 - URI  <br/> | 在注册 CUCM 时自动分配 <br/> |
   |代理 1 - 地址  <br/> |CUCM 的主机名称  <br/> |
   
VTC 现已配置为可进行互操作。在开始服务前，还需在 CUCM 端执行最后几步。
### <a name="configure-vtc-devices-on-cucm"></a>在 CUCM 上配置 VTC 设备

1. 登录到 CUCM 并导航到 Cisco 统一厘米管理-\>设备-\>电话-\>查找。 
    
2. 选择要配置的 VTC 设备。在“电话配置”屏幕上验证以下设置并根据需要进行更正。更改或验证这些设置后，请单击“**保存**”。
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   |设备信息 - 电话按钮模板  <br/> | 标准 Cisco 适量编解码器 C40 <br/> |
   |设备信息 - 通用电话配置文件  <br/> | 标准通用电话配置文件 <br/> |
   |设备信息 - 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |设备信息 - AAR 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |设备信息 - 媒体资源组列表  <br/> | MRGL_SfBVideoInterop <br/> |
   |特定于协议的信息 - 设备安全配置文件  <br/> | Cisco 适量编解码器 C40 <br/> |
   |特定于协议的信息 - 重新路由呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |协议的特定信息-订阅调用搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |特定于协议的信息 - SIP 配置文件  <br/> | 网真终结点的标准 SIP 配置文件 <br/> |
   
3. 保存 VTC 配置后，重新导航至设备的“电话配置”屏幕。 在“关联”组的屏幕顶部，单击“视频互操作”的关联。 然后将显示“目录号码配置”屏幕。 
    
4. 验证以下设置并根据需要进行更正： 
    
    如图所示对“目录号码信息”和“目录号码设置”进行相应的更改。
    
   |**参数**|**推荐设置**|
   |:-----|:-----|
   | 目录号码信息 - 重新路由分区 <br/> | SfBVideoInterop_RoutePartition <br/> |
   |目录号码设置 - 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 备选方和机密访问级别设置 - MLPP 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |行 1 上的设备-显示 (呼叫者 ID)  <br/> | 根据需要 <br/> |
   |行 1 上的设备-ASCII 显示 (呼叫者 ID)  <br/> | 根据需要 <br/> |
   
5. 完成时，滚动至屏幕顶部并单击“**保存**”。 
    
现已为此 VTC 设备完成配置。您将需要为企业中的其他 VTC 设备重复此流程。

