---
title: Microsoft Teams 会议室要求
ms.author: dstrome
author: dstrome
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
description: 了解支持 Microsoft Teams 会议室的要求，包括选择合适的设备、麦克风、扬声器、摄像头和显示器。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fa2436d84ab3ddacc4b7c137aecafce000d26045
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397517"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams 会议室要求

根据会议室的大小和用途，Microsoft Teams 会议室可使用各种经过认证的音频和视频外围设备来扩展到不同的会议室大小。 通过选择合适的核心设备和控制台，结合麦克风、扬声器、摄像头和适合该空间的显示器，你可以将 Microsoft Teams 会议室部署到任何大小的空间 — 从非常小的拥挤空间到非常大的会议室和董事会会议室。  [设备展示](https://products.office.com/microsoft-teams/across-devices)中提供了所有可用于配置会议室的经过认证的全套音频和视频外围设备。

本文概述了为 Microsoft Teams 会议室提供支持的设备部署和配置要求。

你的部署涉及创建帐户（如[部署 Microsoft Teams 会议室](rooms-deploy.md)中所述）和设置会议控制台（如[配置 Microsoft Teams 会议室控制台](console.md)中所述）。

另请参阅：

- [Skype for Business 加载项授权](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [基于计划的许可证选项：Microsoft Teams 会议室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams 会议室可登录到 Microsoft Teams、Skype for Business Server 2019、Skype for Business Server 2015 或 Skype for Business Online，并且可参加由任何这些服务主持的会议。
>
> Microsoft Teams 会议室不支持 Lync Server 2013 等早期平台。 Microsoft 365 或由世纪新闻网运营的 Office 365、GCC-High 或 DoD 环境不支持 Microsoft Teams 会议室。
>
> 如果你有本地 Exchange Server，则 Microsoft Teams 会议室需要使用 Exchange Server 2013 SP1 或更高版本。

## <a name="hardware-requirements"></a>硬件要求
硬件部署包括一系列 Microsoft Teams 会议室系统（结合经过认证的音频和视频外围设备）以及将这些设备集成在一起的电缆解决方案。  此处将介绍这些选项。

**支持的 Microsoft Teams 会议室系统**

[会议室系统产品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)中提供了所有当前的 Microsoft Teams 会议室设备和捆绑包。

  |控制台|处理器|RAM|磁盘|
  |:-----|:-----|:-----|:-----|
  |[将 Crestron Flex UC-M130-T 与 Intel NUC 一起](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[将 Crestron Flex UC- B130-T 与 Intel NUC 一起](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[将 Crestron Flex UC-B140-T 与 Intel NUC 一起](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [将 Crestron Flex UC-C140-T 与 Intel NUC 一起](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[将 Crestron Flex UC-M150-T 与 Intel NUC 一起](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  + [CCS-进行 MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[将 Crestron Flex UC-MX150-T 与 Intel NUC 一起](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [将 Crestron Flex UC-B160-T 与 Intel NUC 一起](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[将 Crestron Flex UC-C160-T 与 Intel NUC 一起](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[CrestronTron Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 with Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | 核心 i5 & i7 |8 GB |128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[带 Microsoft Teams 会议室的 HP Elite Slice G2 Audio Ready](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP 切片合作伙伴 Ready with Logitech TAP]( https://www.logitech.com/en-us/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB|
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Le地g ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |[Logitech Tap with Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Logitech Tap 和 Le位 ThinkSmart Tiny](https://www.logitech.com/en-us/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[将 Poly G10-T 与 Lenovo ThinkSmart Tiny 一起](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Yealink MVC300 与 Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 与 Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 与 Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 与 Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  

> [!NOTE]
> - Core M3 处理器不受支持。
> - 需要将 32 GB 或更大的 USB 驱动器配置为 Windows 10 企业版的可启动 Windows 安装介质。

**支持的适用于坞站式系统的 Surface Pro 平板电脑**

  |平板电脑|处理器|RAM|磁盘|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB 或 8 GB |128 GB 或更多 |
  |Surface Pro </br>（第五代） |Core i5 |8 GB 或 4 GB |128 GB 或更多 |
  |Surface Pro 4 |Core i5 |8 GB 或 4 GB |128 GB 或更多 |

- Surface Pro 设备需要以下扩展坞选项之一：

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR 系列](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>适用于 USB 音频和视频外围设备的认证固件版本

可在[会议室系统配件产品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)和 [https://office.com/teamsdevices](https://office.com/teamsdevices) 中找到这些设备。

|Microsoft Teams 会议室外围设备|认证的固件版本 | 相机支持内容相机使用|
|:--- |:--- | :--- |
|[Aver VC520 专业摄像机 + 免提电话](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VB342+ 相机声音栏](https://www.averusa.com/products/conference-camera/vb342plus) | 音栏：0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Bose 视频栏 VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ 相机](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Jabra Panacast3 相机](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|Le并 ThinkSmart Cam Camera|1.0.111.4|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |音频 — 1.0.172 <br/> 视频 — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Eva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube 摄像头](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS 展开 80T + 2 个扩展麦克风](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |免提电话 - 4.6.55 <br/> 扩展麦克风 - 0.2.314|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC40 一体式视频栏](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 桌面矩阵麦克风](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [带 Intellimix 天花板矩阵麦克风的 Shure MXA 910](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 表数组麦克风 ](https://www.shure.com/en-US/products/microphones/mxa310) +</br></br> [MXN5W-C Ceiling 扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP：4.1.11 </br> MXA310 表数组麦克风：4.1.41 </br> MXN5W-C 扬声器：1.0.4 |
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 与 Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) +</br></br> [MXN5W-C Ceiling 扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP：4.1.11 </br> MXA910 Ceiling Array 麦克风：4.1.41 </br> MXN5W-C 扬声器：1.0.4 |
|[Biamp Tesira Fore AVB VT4 固定音频 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 麦克风](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP：3.12.0.15  </br></br> TCC2：1.3.3 </br></br> EX-UBT：3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 音频 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp Parlé TCM-XA Ceiling Microphone](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6 顶置扬声器](https://www.biamp.com/products/tesira-speakers)| 音频 FW 版本：3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X (表麦克风) ](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |音频 FW 版本：3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink 扬声器 +</br> Sennheiser TCC2 天花板麦克风 + </br> Bose EdgeMax EM180 天花板扬声器](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink 用户 + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink 功能 +</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink 云+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [EdgeMax EM180 Ceiling 扬声器](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Sennheiser TCC2 Ceiling Microphone]() +</br> [QSC EnergyStar PowerSpa SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS 系列网络交换机 NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [QSC 柱形图面安装扬声器 AD-S402T](https://www.qsc.com/systems/products/loudspeakers/column-surface-mount-loudspeakers/acousticdesigntm-series-column-surface-mount/ad-s402t/) +</br> [QSC PTZ 20x60 相机](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |Q-sys Designer：8.4.0.1 </br> <br> TCC2 ：1.5.1 Dante 1.2.0 </br>  <br> 不适用 </br>  <br>N1100v6.4.2.8 </br> 不适用 </br> <br> 6.3.2.2|
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Sennheiser TCC2 Ceiling Microphone]() +</br> [QSC EnergyStar PowerSpa SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS 系列网络交换机 NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [QSC 柱形图面安装扬声器 AD-C6T-LP](https://www.qsc.com/systems/products/loudspeakers/ceiling-mount-loudspeakers/acousticdesigntm-series-ceiling-mount/ad-c6t-lp/?L=) +</br> [QSC PTZ 20x60 相机](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |Q-sys Designer：8.4.0.1 </br> <br> TCC2 ：1.5.1 Dante 1.2.0 </br>  <br> 不适用 </br>  <br>N1100v6.4.2.8 </br> 不适用 </br> <br> 6.3.2.2|


&Dagger; 客户可以选择 Biamp/Sennheiser 为此捆绑包推荐的 Dante 界面或网络交换机。

#### <a name="usb-extenders"></a>USB 扩展器

- 平板电脑坞站上的 USB 端口兼容 USB 3.0。 可以使用 USB 2.x 扩展器，但这样做会限制远端的 USB 2.x 速度。 建议不要将扩展器用于 USB 3.0 外围设备。
- 扩展器必须符合 USB 2.0 或更高版本的规范。
  - 平板电脑扩展坞至少支持两个阶段的外部 USB 集线器扩展。 如果你串联连接了两个以上的 USB 集线器，请与扩展坞制造商联系以确认其是否支持串联连接。
  - 会议室中的有线 GbE 连接。 长度合适的以太网电缆。
  - 最多两个 1080-p 显示器，带有 HDMI 连接。 长度合适的 HDMI 电缆。

> [!NOTE]
> 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。
>
> Microsoft Teams 会议室不使用键盘。 如果需要，管理员应使用屏幕键盘。 在映像 Microsoft Teams 会议室设备时需要 USB 键盘或鼠标。

下表根据会议室大小提供了针对外围设备的建议：

**Microsoft Teams 会议室认证的音频外围设备**

|会议室类型|人数|麦克风与发言人之间的建议最大距离|设备（按最大会议室大小）|备注|
|:-----|:-----|:-----|:-----|:-----|
|**焦点** <br/> 10' x 9'   |2–4  |1.5 米  |Logitech Connect  |Logitech Connect 设备包括摄像头，它必须放置在会议室前方（不是桌子中心）以拍摄本地会议与会者。 |
|**小型** <br/> 16' x 16'  |4–6  |2.0 米  |Jabra 510 <br/> Sennheiser SP20  |对于较大的会议室，播放音量可能会受到限制。  |
|**中型** <br/> 18' x 20'  |6–12  |2.4 米  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Logitech MeetUp 设备包括摄像头，因此它必须放置在会议室前方（不是桌子中心）以拍摄本地会议与会者。 <br/> 通常，配备长矩形或 U 形桌子的会议室可以使用卫星麦克风。 <br/> SP 220 MS 必须采用菊花链配置。  |
|**大型** <br/> 15' x 32'  |12–16  |3 米 <br/> 此距离也适用于每个连接的卫星麦克风所覆盖的区域。  |Logitech Group + 卫星麦克风 <br/> Polycom Trio+ 卫星麦克风 <br/> Polycom CX5100 + 卫星麦克风 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + 卫星麦克风  |此行中列出的所有音频设备均支持卫星麦克风选项。 <br/> CX5100 包括内置的 360 度摄像头，因此该设备可以放置在桌子中心。 <br/> SP 220 MS 必须采用菊花链配置。  |

**Microsoft Teams 会议室认证的视频外围设备**

|会议室类型|人数|按最佳会议室大小列出的设备|备注|
|:-----|:-----|:-----|:-----|
|**焦点** <br/> 10' x 9'  |2–4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**小型** <br/> 16' x 16'  |4–6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro 通常与 Logitech Group 捆绑在一起  |
|**中型** <br/> 18' x 20'  |6–12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**大型** <br/> 15' x 32'  |12–16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > 会议室正面的显示分辨率应设置为不超过 1920x1080p。

## <a name="required-software-downloads"></a>需要下载的软件

若要构建自己的 Microsoft Teams 会议室图像，请按照[配置 Microsoft Teams 会议室控制台](console.md)中的说明进行操作。 这些说明将指导你下载安装所需的所有软件。

> [!NOTE]
> IT 专业人员将需要通过批量许可协议访问 Windows 10 企业版 ISO 文件。

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) 是可选下载，可用于预配 Microsoft Teams 会议室帐户。

## <a name="see-also"></a>另请参阅

[浏览所有捆绑包](https://products.office.com/microsoft-teams/across-devices/devices)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[配置 Microsoft Teams 会议室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Skype for Business 加载项授权](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
