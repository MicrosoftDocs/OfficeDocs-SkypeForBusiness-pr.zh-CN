---
title: Microsoft 团队会议室需求
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: 本文概述了支持 Microsoft 团队聊天室的要求。
ms.openlocfilehash: 7e78c2f33a52d5848b8b996c65fefbeabdab4c3e
ms.sourcegitcommit: dcc5c09e6b891fe44c9d2cf384fe7ef678e7768c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "35911957"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft 团队会议室需求

本文概述了支持 Microsoft 团队聊天室的要求。 

你的部署将涉及[部署 Microsoft 团队聊天室](room-systems-v2.md)和设置会议控制台中所述的帐户创建, 如[配置 microsoft 团队聊天室控制台](console.md)中所述。 

您可能还需要参阅:

- [Skype for Business 加载项授权](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [基于你的计划的许可证选项: Microsoft 团队聊天室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft 球队会议室旨在与 Microsoft 团队、Skype for business Server 2019、Skype for business Server 2015 或 Skype for business Online 配合使用。 <br><br>早期平台 (如 Lync Server 2013) 不希望与 Microsoft 团队聊天室一起使用。

> [!NOTE]
> 如果使用的是本地 Exchange server, 则 Microsoft 团队聊天室需要使用 Exchange Server 2013 SP1 或更高版本。

## <a name="hardware-requirements"></a>硬件要求

Microsoft 团队聊天室可以通过附件根据音频和视频外围设备缩放到不同的空间大小。 本文中列出的硬件同时支持 Skype 和团队会议模式。  音频和视频外设通过插接设备上的 USB 或 HDMI 连接连接到 Microsoft 团队聊天室。 你还将需要：

- 将配置为 Windows 10 企业版可启动 Windows 安装媒体的32GB 或更大的 USB 磁盘。 

- 下列平板电脑或控制台之一:

**支持的平板电脑**

|电脑|Processor|RAM|磁盘|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |核心 i5  |不限或8GB |128GB 或更多  |
|Surface Pro (第五代)  |核心 i5  |8GB 或4GB  |128GB 或更多  |
|Surface Pro 4          |核心 i5  |8GB 或4GB  |128GB 或更多  |

- 以下扩展坞选项之一, 用于将平板电脑固定到会议室表。 

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR 系列](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


**其他支持的 Microsoft 团队聊天室控制台**

|控制台|Processor|RAM|磁盘|
|:-----|:-----|:-----|:-----|
|[Crestron Flex UC-M150](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|双核 i7|s |128GB |
[Crestron Flex UC-B160](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|双核 i7|s |128GB|
|[Crestron Flex UC-C160](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|双核 i7|s|128GB|
|[会议室 G2 的 HP 精英扇面](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |核心 i5  |s  |128GB  | 
|[HP 精英扇区将 G2 与 Microsoft 团队会议室一起准备的音频](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |核心 i5 |s |128GB | 
|[联想 ThinkSmart 中心500](https://www3.lenovo.com/us/en/hub500) |核心 i5  |s  |128GB  |  
|[Logitech 点击](https://www.logitech.com/en-us/product/microsoft-rooms)|核心 i5|s |128GB |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|核心 i5|s|128GB|
|[Yealink MVC500](https://www.yealink.com/products_126.html)|核心 i5|s |128GB |
|||||

> [!NOTE]
> 不支持核心 M3 处理器。

**适用于 USB 音频和视频外设的认证固件版本**

|Microsoft 团队会议室外围设备|针对 Microsoft 团队聊天室认证的固件版本|
|:-----|:-----|
|[Logitech Rally](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam) <br/> |1.2.4 |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech 聚会](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |音频-1.0.172  <br/> 视频-1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech 组](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100 ](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Polycom Eagle 眼主任 II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html) <br/> |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30) <br/> |2.1.52 <br/>|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra evolve 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **USB 延长**器:

  - 平板电脑上的 USB 端口兼容 USB 3.0。 你可以使用 USB 2 a.x 扩展器, 但这样做会将您的 USB 2 的速度限制在最远的 USB 2。对于 USB 3.0 外设, 不推荐使用 x 的速度。

  - 扩展器必须符合 USB 2.0 或更高版本的规范。

  - 平板电脑停靠支持外部 USB 集线器扩展的至少两个阶段。 如果需要在系列中连接两个以上的 USB 集线器, 您需要与 dock 制造商联系以确认此操作是否受支持。

- 聊天室中的有线 GbE 连接。 长度合适的以太网电缆。

- 通过 HDMI 连接最多可显示两个1080p。 合适长度的 HDMI 电缆。

> [!NOTE]
> 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。 

> [!NOTE]
> Microsoft 团队聊天室不使用键盘。 如果需要，管理员应使用屏幕键盘。 当图像处理 Microsoft 团队聊天室设备时, 将需要使用 USB 键盘或鼠标。 

下表提供了基于房间大小的外围设备的建议:

**Microsoft 团队聊天室认证的音频外围设备**

|会议室类型|人数|麦克风与发言人员之间的建议最大距离|设备（按最大会议室大小）|备注|
|:-----|:-----|:-----|:-----|:-----|
|**焦距** <br/> 10 "x 9"  <br/> |2-4  <br/> |1.5m   <br/> |Logitech Connect  <br/> |Logitech 连接设备包括一个相机, 因此它必须位于房间 (而不是表格中间) 的前面, 以捕获本地会议与会者。  <br/> |
|**小** <br/> 16 "x 16"  <br/> |4-6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |对于较大的会议室，播放音量可能会受到限制。  <br/> |
|**中** <br/> 18 "x 20"  <br/> |6-12  <br/> |2.4m  <br/> |Jabra evolve 710  <br/> Jabra 810  <br/> Logitech 聚会  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Logitech 聚会包括一个相机, 因此它必须位于会议室的前方 (而不是表中央才能捕获本地会议与会者)。  <br/> 通常, 具有长矩形或 u 形表格的房间可从其他卫星麦克风获益。  <br/> 菊花链配置中必须使用 SP 220 MS。  <br/> |
|**大** <br/> 15 "x 32"  <br/> |12-16  <br/> |3m  <br/> 此距离也适用于连接到正在使用的音频设备的每个其他卫星麦克风覆盖的区域。  <br/> |Logitech Group + 卫星麦克风  <br/> Polycom Trio + 卫星麦克风  <br/> Polycom CX5100 + 卫星麦克风  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + 卫星麦克风  <br/> |此行列出的所有音频设备都支持卫星麦克风选项。  <br/> CX5100 包括内置的 360 度摄像头，因此该设备可以放置在桌子中心。  <br/> 菊花链配置中必须使用 SP 220 MS。  <br/> |

**Microsoft 团队聊天室经认证的视频外设**

|会议室类型|人数|按最佳房间大小的设备|备注|
|:-----|:-----|:-----|:-----|
|**焦距** <br/> 10 "x 9"  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech 聚会  <br/> Polycom CX5100   <br/> ||
|**小** <br/> 16 "x 16"  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech 聚会  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro 通常捆绑在 Logitech 组中  <br/> |
|**中** <br/> 18 "x 20"  <br/> |6-12  <br/> |Logitech 聚会  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**大** <br/> 15 "x 32"  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||

 > [!NOTE]
 > 房间的正面显示分辨率应设置为不大于1920x1080p。

## <a name="required-software-downloads"></a>所需软件下载

若要生成自己的 Microsoft 团队聊天室图像, 请按照[配置 Microsoft 团队聊天室控制台](console.md)中的说明进行操作。 这些说明将指导你下载安装过程所需的所有软件。 

> [!NOTE]
> IT 专业人员将需要通过其批量许可协议访问 Windows 10 企业版 ISO 文件。

此外, 你可能需要[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)的副本, 你可以使用该副本预配 Microsoft 团队聊天室帐户。

## <a name="see-also"></a>另请参阅
[浏览所有捆绑包](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)

[部署 Microsoft 团队聊天室](room-systems-v2.md)

[配置 Microsoft 团队聊天室控制台](console.md)

[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)

[Skype for Business 附加许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
