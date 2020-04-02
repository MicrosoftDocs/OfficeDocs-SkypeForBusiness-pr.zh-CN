---
title: Microsoft 团队会议室需求
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: 本文概述了支持 Microsoft 团队聊天室的要求。
ms.openlocfilehash: 9e07ac6f5f7ca477006dac703f7b3b8b2604c60b
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102333"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft 团队会议室需求

通过使用各种经认证的音频和视频外围设备（基于房间的大小和使用），Microsoft 团队会议室可缩放到不同的会议室大小。 通过选择合适的核心设备和控制台（与麦克风、扬声器、相机和显示器配合使用），你可以通过非常小的 huddle 空间和 boardrooms 将 Microsoft 团队会议室部署到非常小的空间。  [设备展示](https://products.office.com/microsoft-teams/across-devices)中提供了可用于配置房间的所有可用的已认证音频和视频外设的完整集。

本文概述了支持 Microsoft 团队聊天室的设备部署和配置要求。

你的部署包括[部署 Microsoft 团队聊天室](rooms-deploy.md)和设置会议控制台中所述的帐户创建，如[配置 microsoft 团队聊天室控制台](console.md)中所述。

另请参阅：

- [Skype for Business 加载项授权](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [基于你的计划的许可证选项： Microsoft 团队聊天室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft 团队聊天室登录到 Microsoft 团队、Skype for Business Server 2019、Skype for business Server 2015 或 Skype for business Online，并可能加入由这些服务托管的会议。
>
> Microsoft 团队聊天室不支持早期平台（如 Lync Server 2013）。 在由世纪互联运营的 Office 365 或在 GCC-高或 DoD 环境下，Microsoft 球队会议室不受支持。
>
> 如果您有一个本地 Exchange 服务器，则 Microsoft 团队聊天室需要使用 Exchange Server 2013 SP1 或更高版本。

## <a name="hardware-requirements"></a>硬件要求
硬件部署包括一个 Microsoft 团队房间系统的选择、与认证的音频和视频外设结合以及用于将这些设备集成到一起的缆线解决方案。  下面介绍这些选项。

**支持的 Microsoft 团队房间系统**

[会议室系统产品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)中提供了所有当前的 Microsoft 团队聊天室设备和捆绑包。

  |控制台|处理器|RAM|磁盘|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|核心 i5|8 GB |128 GB |
  |[Crestron Flex UC-B130](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|核心 i5|8 GB |128 GB |
  |[Crestron Flex UC-B140](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|核心 i5|8 GB |128 GB |
  |[Crestron Flex UC-M150](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|双核 i7|8 GB |128 GB |
  [Crestron Flex UC-B160](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|双核 i7|8 GB |128 GB|
  |[Crestron Flex UC-C160](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|双核 i7|8 GB|128 GB|
  |[会议室 G2 的 HP 精英扇面](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |核心 i5 |8 GB |128 GB |
  |[HP 精英扇区将 G2 与 Microsoft 团队会议室一起准备的音频](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |核心 i5 |8 GB |128 GB |
  |[联想 ThinkSmart 中心500](https://www3.lenovo.com/us/en/hub500) |核心 i5 |8 GB |128 GB |
  |[Logitech 点击](https://www.logitech.com/product/microsoft-rooms)|核心 i5|8 GB |128 GB |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|核心 i5|8 GB|128 GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|核心 i5|8 GB |128 GB |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|核心 i5|8 GB |128 GB |
  |[Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|核心 i5|8 GB|128 GB|
  ||||||

> [!NOTE]
> - 不支持核心 M3 处理器。
> - 您需要将 32 GB 或更大的 USB 驱动器配置为可启动 windows 10 企业版的 Windows 安装媒体。

**支持用于停靠样式的系统的 Surface Pro 平板电脑**

  |电脑|处理器|RAM|磁盘|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| 核心 i5 |16 GB 或 8 GB |128 GB 或更高 |
  |Surface Pro </br>（第五代） |核心 i5 |8 GB 或 4 GB |128 GB 或更高 |
  |Surface Pro 4 |核心 i5 |8 GB 或 4 GB |128 GB 或更高 |

- 以下扩展坞选项之一，用于将平板电脑固定到会议室表。

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR 系列](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>适用于 USB 音频和视频外设的认证固件版本

这些设备在[房间系统附件产品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)和[https://office.com/teamsdevices](https://office.com/teamsdevices)中可用。

|Microsoft 团队聊天室外围设备|认证的固件版本 | 相机支持内容相机使用|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  |  |
|[Logitech Brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech 聚会](https://www.logitech.com/product/meetup-conferencecam)   |音频-1.0.172 <br/> 视频——1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech 组](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Poly Eagle 眼立方体相机](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100 ](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle 眼主任 II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra evolve 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 表数组 Mic](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 音频 Conferening 处理器](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 with Intellimix 顶棚 Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Biamp Tesira AVB VT4 固定音频 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect 顶棚2麦克风](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [TESIRA EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  Biamp DSP：3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT：3.12.0.15 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink +</br> Sennheiser TCC2 + Bose EDGEMAX + </br> EM180 顶棚扬声器](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4。2  |  |
||||||

&Dagger;客户可以选择 Biamp/Sennheiser 推荐的 Dante 接口或网络交换机。

#### <a name="usb-extenders"></a>USB 扩展器

- 平板电脑上的 USB 端口兼容 USB 3.0。 你可以使用 USB 2. x 扩展器，但这样做会将你限制到最远的 USB 2 x-blade 速度。 对于 USB 3.0 外围设备，不推荐使用扩展程序。
- 扩展器必须符合 USB 2.0 或更高版本的规范。
  - 平板电脑停靠支持外部 USB 集线器扩展的至少两个阶段。 如果您在系列中连接了两个以上的 USB 集线器，请与 dock 制造商确认他们是否支持系列连接。
  - 聊天室中的有线 GbE 连接。 长度合适的以太网电缆。
  - 最多 2 1080-p 显示器，附带 HDMI 连接。 合适长度的 HDMI 电缆。

> [!NOTE]
> 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。
>
> Microsoft 团队聊天室不使用键盘。 如果需要，管理员应使用屏幕键盘。 当图像处理 Microsoft 团队聊天室设备时，将需要使用 USB 键盘或鼠标。

下表提供了基于房间大小的外围设备的建议：

**Microsoft 团队聊天室认证的音频外围设备**

|会议室类型|人数|建议的最大麦克风距离为扬声器|设备（按最大会议室大小）|备注|
|:-----|:-----|:-----|:-----|:-----|
|**焦距** <br/> 10 "x 9"   |2–4  |1.5 m  |Logitech Connect  |Logitech Connect 设备包括必须放置在聊天室（而不是表格中间）前面的相机，以捕获本地会议参与者。 |
|**小** <br/> 16 "x 16"  |4–6  |2.0 m  |Jabra 510 <br/> Sennheiser SP20  |播放音量受限制，可用于更大的会议室。  |
|**中** <br/> 18 "x 20"  |6–12  |2.4 m  |Jabra evolve 710 <br/> Jabra 810 <br/> Logitech 聚会 <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Logitech 聚会包括一个相机，因此它必须位于会议室的前方（而不是表中央才能捕获本地会议与会者）。 <br/> 通常，具有长矩形或 u 形表格的房间可从卫星麦克风获益。 <br/> 菊花链配置中必须使用 SP 220 MS。  |
|**大** <br/> 15 "x 32"  |12–16  |3 m <br/> 这一距离还适用于每个连接的卫星麦克风所覆盖的区域。  |Logitech Group + 卫星麦克风 <br/> Polycom Trio + 卫星麦克风 <br/> Polycom CX5100 + 卫星麦克风 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + 卫星麦克风  |此行列出的所有音频设备都支持卫星麦克风选项。 <br/> CX5100 包括内置的360度相机，以便可以将设备放置在表的中心。 <br/> 菊花链配置中必须使用 SP 220 MS。  |

**Microsoft 团队聊天室经认证的视频外设**

|会议室类型|人数|按最佳房间大小的设备|备注|
|:-----|:-----|:-----|:-----|
|**焦距** <br/> 10 "x 9"  |2–4  |Logitech Connect <br/> Logitech 聚会 <br/> Polycom CX5100   ||
|**小** <br/> 16 "x 16"  |4–6  |Logitech C930e <br/> Logitech 聚会 <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100   |Logitech PTZ Pro 通常捆绑在 Logitech 组中  |
|**中** <br/> 18 "x 20"  |6–12  |Logitech 聚会 <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100   ||
|**大** <br/> 15 "x 32"  |12–16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100   ||

 > [!NOTE]
 > 房间的正面显示分辨率应设置为不大于1920x1080p。

## <a name="required-software-downloads"></a>所需软件下载

若要生成自己的 Microsoft 团队聊天室图像，请按照[配置 Microsoft 团队聊天室控制台](console.md)中的说明进行操作。 这些说明将指导你下载安装所需的所有软件。

> [!NOTE]
> IT 专业人员将需要通过其批量许可协议访问 Windows 10 企业版 ISO 文件。

[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)是可用于预配 Microsoft 团队聊天室帐户的可选下载内容。

## <a name="see-also"></a>另请参阅

[浏览所有捆绑包](https://products.office.com/microsoft-teams/across-devices/devices)

[规划 Microsoft 团队聊天室](rooms-plan.md)

[部署 Microsoft 团队聊天室](rooms-deploy.md)

[配置 Microsoft 团队聊天室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Skype for Business 附加许可](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
