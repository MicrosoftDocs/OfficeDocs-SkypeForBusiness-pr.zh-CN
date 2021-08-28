---
title: 配置 VTC 以与 Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要：将 VTC 设备配置为与 Skype for Business Server。
ms.openlocfilehash: 1165b4bf569701d71a435a4162ef9feb9ef3018f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594676"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a>配置 VTC 以与 Skype for Business Server
 
**摘要：** 将 VTC 设备配置为与 Skype for Business Server。
  
您需要为通过 SIP 中继和 Cisco 统一通信管理器 (CallManager 或 CUCM) 视频网关连接到 Skype for Business VIS 服务器的每个 VTC 执行以下配置自定义过程。
  
此处所述的设置仅用作如何配置 CUCM 以使用 VIS 的示例。 其他设置和/或备用 CUCM 功能的用法也可以用来获得相同的结果。 对于特定方案的最佳配置，不隐含任何建议。
  
### <a name="configure-a-vtc-registered-with-cucm"></a>配置在 CUCM 中注册的 VTC

1. 登录到 Cisco VTC 设备并导航到配置- \> 系统配置 - \> 预配。
    
2. 验证以下设置，根据需要更正： 
    
   |**Parameter**|**推荐设置**|
   |:-----|:-----|
   |预配模式  <br/> | CUCM <br/> |
   |ExternalManager 地址  <br/> | CUCM 的 FQDN <br/> |
   | ExternalManager 域 <br/> |CUCM 的域  <br/> |
   
3. 导航到配置 - \> 系统配置 - \> 网络。
    
4. 验证以下设置，根据需要更正： 
    
   |**Parameter**|**推荐设置**|
   |:-----|:-----|
   |DNS 域名  <br/> | CUCM 的域名 <br/> |
   |DNS 服务器 1 地址  <br/> | 所需的 DNS 服务器地址 <br/> |
   
5. 导航到配置 - \> 系统配置 - \> 网络服务。 确保 H.323 模式已关闭，SIP 模式已打开。 
    
6. 当终结点注册 CUCM 时，会自动设置这些选项。 验证以下设置，根据需要更正： 
    
   |**Parameter**|**推荐设置**|
   |:-----|:-----|
   |H.323 模式  <br/> | 关闭 <br/> |
   |HTTP 模式  <br/> | 打开 <br/> |
   | SIP 模式 <br/> | 打开 <br/> |
   |Telnet 模式  <br/> | 打开 <br/> |
   |WelcomeText  <br/> | 打开 <br/> |
   |XMLAPI 模式  <br/> | 打开 <br/> |
   
7. 导航到配置 - \> 系统配置 - \> SIP。
    
8. 验证以下设置，根据需要更正： 
    
   |**Parameter**|**推荐设置**|
   |:-----|:-----|
   |配置文件 1 - DefaultTransport  <br/> | TCP <br/> |
   |配置文件 1 - 出站  <br/> | 关闭 <br/> |
   |配置文件 1 - TlsVerify  <br/> | 打开 <br/> |
   |配置文件 1 - 类型  <br/> | Cisco <br/> |
   |配置文件 1 - URI  <br/> | 在 CUCM 注册时自动分配 <br/> |
   |代理 1 - 地址  <br/> |CUCM 的主机名  <br/> |
   
VTC 现已配置为进行互操作。 在服务开始之前，需要完成 CUCM 端上的最后步骤。
### <a name="configure-vtc-devices-on-cucm"></a>在 CUCM 上配置 VTC 设备

1. 登录到 CUCM 并导航到 Cisco 统一 CM 管理 - \> device- \> 电话 - \> 查找。 
    
2. 选择要配置的 VTC 设备。 在"配置电话验证以下设置，并根据需要进行更正。 更改或验证这些设置后，单击"保存 **"。**
    
   |**Parameter**|**推荐设置**|
   |:-----|:-----|
   |设备信息 - 电话按钮模板  <br/> | 标准 Cisco 网真编解码器 C40 <br/> |
   |设备信息 - 常见电话配置文件  <br/> | 标准公用电话配置文件 <br/> |
   |设备信息 - 调用搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |设备信息 - AAR 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |设备信息 - 媒体资源组列表  <br/> | MRGL_SfBVideoInterop <br/> |
   |协议特定信息 - 设备安全配置文件  <br/> | Cisco Telepresence Codec C40 <br/> |
   |协议特定信息 - 重新路由呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |协议特定信息 - 订阅呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |协议特定信息 -SIP 配置文件  <br/> | 网真终结点的标准 SIP 配置文件 <br/> |
   
3. 保存 VTC 配置后，重新导航到电话配置屏幕。 在"关联"组的屏幕顶部，单击"视频互操作"的关联。 此时将显示"目录号码配置"屏幕。 
    
4. 验证以下设置，根据需要更正： 
    
    对目录号码信息和目录号码信息进行相应的设置。
    
   |**Parameter**|**推荐设置**|
   |:-----|:-----|
   | 目录号码信息 - 路由分区 <br/> | SfBVideoInterop_RoutePartition <br/> |
   |目录号码设置 - 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |MLPP 备用方和机密访问设置 - MLPP 呼叫搜索空间  <br/> | CSS_SfBVideoInterop <br/> |
   |设备上第 1 行 - 显示 (来电显示)   <br/> | 所需 <br/> |
   |设备上第 1 行 - ASCII 显示 (来电显示)   <br/> | 所需 <br/> |
   
5. 完成后，滚动到屏幕顶部，然后按"保存 **"。** 
    
此 VTC 设备的配置现已完成。 你需要为企业中其他 VTC 设备重复此过程。

