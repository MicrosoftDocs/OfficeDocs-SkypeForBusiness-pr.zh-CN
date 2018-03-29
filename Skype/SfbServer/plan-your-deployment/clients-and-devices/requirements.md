---
title: Skype 会议室系统 v2 要求
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: 本文总结了支持 Skype 的空间系统 v2 的要求。
ms.openlocfilehash: ca922efa719b956da5516958ce6f684b013ddc62
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Skype 会议室系统 v2 要求
 
本文总结了支持 Skype 的空间系统 v2 的要求。 
  
所述[部署 Skype 的空间系统 v2](../../deploy/deploy-clients/room-systems-v2.md)创建帐户并设置会议控制台[配置 Skype 的空间系统 v2 控制台](../../deploy/deploy-clients/console.md)中所述，会涉及到您的部署。 您可能需要参考[Skype 业务加载项授权](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。
  
## <a name="hardware-requirements"></a>硬件要求

Skype 的空间系统 v2 可以扩展到另一个房间的大小，通过根据音频和视频的外围设备的附件。 音频和视频的外围设备连接至坞站设备上的 USB 或 HDMI 连接通过 Skype 的空间系统 v2。 你还将需要：
  
- 32 GB 或更大的 U 盘将 Windows 10 企业配置为可引导的 Windows 安装媒体。 
    
- 以下的平板电脑产品之一：
    
**受支持的平板电脑**


|**触**|**处理器**|**RAM**|**磁盘**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 和 sup1;  <br/> |酷睿 i5  <br/> |4 GB  <br/> |128GB  <br/> |
|Surface Pro 4 和 sup1;  <br/> |酷睿 i5  <br/> |8 GB  <br/> |256 GB  <br/> |
|Surface Pro 和 sup1; <br/> |酷睿 i5  <br/> |4 GB  <br/> |128GB  <br/> |
|Surface Pro 和 sup1; <br/> |酷睿 i5  <br/> |8 GB  <br/> |256 GB  <br/> |
|Surface Pro 和 sup1; <br/> |酷睿 i7  <br/> |8 GB  <br/> |128GB  <br/> |
|Surface Pro 和 sup1; <br/> |酷睿 i7  <br/> |16 GB  <br/> |512 GB  <br/> |
|Surface Pro 和 sup1; <br/> |酷睿 i7  <br/> |16 GB  <br/> |1 TB  <br/> |
   
和 sup1;— — 核 M3 处理器不支持此模型。
    
 
    
- 另一种下坞站力保触到会议文件室表。 
    
  - [Logitech SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Polycom MSR 系列](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)

  - [联想中心 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**验证 USB 音频和视频的外围设备的固件版本**
|**Skype 的空间系统 v2 外围设备**|**认证，Skype 的空间系统 v2 固件版本**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |音频-1.0.172  <br/> 视频-1.0.156  <br/> |
|[Logitech ConferenceCam 连接](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech 组](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ 专业](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Polycom RealPresence 三个](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 毫秒](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100 c  <br/> |
   
- **USB 扩展器**：
    
  - 在 tablet 坞站上的 USB 端口都兼容 USB 3.0。 您可以使用 USB 2.x 扩展程序，但这样做以便将局限于 USB 2.x 的速度，对登机口和这样做所以不建议用于 USB 3.0 的外围设备。
    
  - 扩展程序必须符合 USB 2.0 或更高版本的规范。
    
  - Tablet 货台支持外部 USB 集线器扩展的至少两个阶段。 如果需要连接多系列中的两个 USB 集线器，您将需要与坞站制造商联系，以确认支持这样做。
    
- 房间内有线千兆以太网连接。 长度合适的以太网电缆。
    
- 使用 HDMI 连接的 1080p 显示最多两个。 适当长度的 HDMI 电缆。
    
    > [!NOTE]
    > 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。 
  
> [!NOTE]
> Skype 的空间系统 v2 不使用键盘。 如果需要，管理员应使用屏幕键盘。 将图像处理 Skype 的空间系统 v2 设备时要求 USB 键盘或鼠标。 
  
下表提供了有关根据房间大小的外围设备的建议：
  
**Skype 的空间系统 v2 认证音频外围设备**

|**房间类型**|**许多人**|**建议从麦克风向说话的人的最大距离**|**最大的房间大小的设备**|**注释**|
|:-----|:-----|:-----|:-----|:-----|
|**焦点** <br/> 10 个 x 9"  <br/> |2-4  <br/> |1.5 米  <br/> |Logitech Connect  <br/> |Logitech 连接设备包括照相机，因此它必须定位在前面的房间 （没有表的中心） 来捕获本地会议与会者。  <br/> |
|**小** <br/> 16 x 16"  <br/> |4-6  <br/> |2.0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |对于较大的会议室，播放音量可能会受到限制。  <br/> |
|**中等深浅** <br/> 18 x 20"  <br/> |6-12  <br/> |2.4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC 毫秒  <br/> |Logitech MeetUp 包括照相机，因此它必须定位在前面的房间 （没有表来捕获本地会议与会者的中心）。  <br/> 一般情况下，房间的长矩形和 u 形表可能会受益于其他附属麦克风。  <br/> 菊花链配置中必须使用 SP 220 MS。  <br/> |
|**大** <br/> 15 x 20"  <br/> |12-16 日  <br/> |3 米  <br/> 此距离也适用于连接到正在使用的音频设备的每个其他卫星麦克风覆盖的区域。  <br/> |Logitech 组 + 卫星话筒  <br/> Polycom 三 + 卫星话筒  <br/> Polycom CX5100 + 卫星话筒  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC 1000MS + 卫星话筒  <br/> |在这行支持附属麦克风选项中列出的所有音频设备。  <br/> CX5100 包含内置的 360 度照相机，以便该设备可以放置在表的中心。  <br/> 菊花链配置中必须使用 SP 220 MS。  <br/> |
   
**Skype 的空间系统 v2 认证视频外设**

|**房间类型**|**许多人**|**最佳的房间大小的设备**|**注释**|
|:-----|:-----|:-----|:-----|
|**焦点** <br/> 10 个 x 9"  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**小** <br/> 16 x 16"  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ 专业  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ 专业人士经常与 Logitech 组捆绑在一起  <br/> |
|**中等深浅** <br/> 18 x 20"  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ 专业  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**大** <br/> 15 x 20"  <br/> |12-16 日  <br/> |Logitech PTZ 专业  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
   
## <a name="required-software-downloads"></a>需要下载的软件

您将需要以下下载来构建自己的 Skype 的空间系统 v2 图像：
  
- [Skype 的空间系统 v2 安装包](https://go.microsoft.com/fwlink/?linkid=851168)。
    
- 获取 Windows 10 企业创建者更新 （英语语言，生成 1703年） 的 64 位版本的副本。 
    
    > [!NOTE]
    > 从 Skype 的空间系统第 2 版 3.0.12.0 （更新 3） 不再支持 Windows 10 企业周年纪念版 （英语语言，1607年版本） 的 64 位版本。 
  
- 受支持的[Surface Pro 4 驱动程序](https://go.microsoft.com/fwlink/?linkid=856887)或[Surface Pro 的驱动程序](https://go.microsoft.com/fwlink/?linkid=856888)。
    
这些下载需要以特定的方式，合并为可引导的 Windows 安装介质盘在[Skype 的空间系统 v2 控制台配置](../../deploy/deploy-clients/console.md)中进一步描述。 
  
此外，您可能需要用来设置 Skype 的空间系统 v2 帐户[Powershell 脚本](https://go.microsoft.com/fwlink/?linkid=870105)的副本。
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 的空间规划系统 v2](skype-room-systems-v2-0.md)
  
[部署 Skype 的空间系统 v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[配置控制台，Skype 的空间系统 v2](../../deploy/deploy-clients/console.md)
  
[Skype 的机房管理系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Skype for Business 附加许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

