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
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 了解支持Microsoft Teams 会议室的要求，包括选择合适的设备、麦克风、扬声器、相机和显示器。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 361a81e4945e191bbb0443d0a73555b14a8770fb
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584373"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft Teams 会议室要求

Microsoft Teams 会议室缩放到不同的房间大小。 Teams 会议室根据房间的大小和使用情况使用各种经过认证的音频和视频外围设备。 通过选择合适的核心设备和控制台，结合麦克风、扬声器、相机和适合空间的显示器，可以将Microsoft Teams 会议室部署到任何大小的空间中，从小型拥挤的空间向上穿过大型会议空间和会议室。  [设备展示](https://products.office.com/microsoft-teams/across-devices)中提供了所有可用于配置会议室的经过认证的全套音频和视频外围设备。

本文概述了为 Microsoft Teams 会议室提供支持的设备部署和配置要求。

部署涉及资源帐户创建和设置Teams 会议室，如[部署Microsoft Teams 会议室](rooms-deploy.md)中所述。

请参阅：

- [基于计划的许可证选项：Microsoft Teams 会议室](rooms-licensing.md)

> [!NOTE]
> Microsoft Teams 会议室登录到 Microsoft Teams、Skype for Business Server 2019 或 2015 Skype for Business Server，并可以加入其中任何服务托管的会议。
>
> Microsoft Teams 会议室不支持 Lync Server 2013 等早期平台。 Microsoft 365 或由 21Vianet 或 DoD 环境运营的Office 365不支持Microsoft Teams 会议室。
>
> 如果你有本地 Exchange Server，则 Microsoft Teams 会议室需要使用 Exchange Server 2013 SP1 或更高版本。

## <a name="hardware-requirements"></a>硬件要求
硬件部署包括一系列Microsoft Teams 会议室系统，以及经过认证的音频和视频外围设备，以及用于将这些设备集成在一起的布线解决方案。  此处将介绍这些选项。

**支持的Microsoft Teams 会议室系统**

Teams 会议室[产品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=)中提供了所有当前Microsoft Teams 会议室设备和捆绑包。

  |控制台|处理器|RAM|磁盘|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [使用 Intel NUC 的 Crestron Flex UC-C140-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |使用 Intel NUC  +  [的 Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)[CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T with Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[使用 Intel NUC 的 Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[使用 UC 演示文稿传输器的 Crestron Flex UC-MMX30-T (UC-PR) 和 ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|核心 i5/i7|8 GB |128 GB |
  |[使用 UC 演示文稿传输器的 Crestron Flex UC-BX30-T (UC-PR) 和 ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|核心 i5/i7|8 GB |128 GB |
  |[使用 UC 演示文稿传输器的 Crestron Flex UC-CX100-T (UC-PR) 和 ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|核心 i5/i7|8 GB |128 GB |
  |[使用 ASUS PC 的 Crestron Flex UC-B30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|核心 i5/i7|8 GB |128 GB |
   |[使用 ASUS PC 的 Crestron Flex UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|核心 i5/i7|8 GB |128 GB |
   |[使用 ASUS PC 的 Crestron Flex UC-M50-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|核心 i5/i7|8 GB |128 GB |
   |[使用 ASUS PC 的 Crestron Flex UC-M70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|核心 i5/i7|8 GB |128 GB |
   |[使用 ASUS PC 的 Crestron Flex UC-MX50-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|核心 i5/i7|8 GB |128 GB |
   |[使用 ASUS PC 的 Crestron Flex UC-MX70-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|核心 i5/i7|8 GB |128 GB |
   |使用 Dell OPTIPLEX 的 Crestron FLEX UC-B30-T|Core i5|8 GB|128 GB|
   |采用 Dell OPTIPLEX 的 Crestron FLEX UC-Bx30-T|Core i5|8 GB|128 GB|
   |使用 Dell OPTIPLEX 的 Crestron FLEX UC-MM30-T|Core i5|8 GB|128 GB|
   |采用 Dell OPTIPLEX 的 Crestron FLEX UC-MMX30-T|Core i5|8 GB|128 GB|
   |使用 Dell OPTIPLEX 的 Crestron FLEX UC-M50-T|Core i5|8 GB|128 GB|
   |采用 Dell OPTIPLEX 的 Crestron FLEX UC-MX50-T|Core i5|8 GB|128 GB|
   |使用 Dell OPTIPLEX 的 Crestron FLEX UC-M70-T|Core i5|8 GB|128 GB|
   |采用 Dell OPTIPLEX 的 Crestron FLEX UC-MX70-T|Core i5|8 GB|128 GB|
   |采用 Dell OPTIPLEX 的 Crestron FLEX UC-C100-T|Core i5|8 GB|128 GB|
   |采用 Dell OPTIPLEX 的 Crestron FLEX UC-CX100-T|Core i5|8 GB|128 GB|
  |[克里斯特龙水星微型UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 with Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 GB |128 GB|
  |[HP Elite Slice for Meeting Rooms G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[带 Microsoft Teams 会议室的 HP Elite Slice G2 Audio Ready](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP 切片合作伙伴已准备好使用 Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  |[具有Microsoft Teams 会议室的 HP 状态小型空间解决方案](https://www.hp.com/us-en/solutions/presence.html)|核心 i5/i7|8 GB/16 GB|256 GB|
  |[具有 Microsoft Teams 会议室 的 HP 状态小型空间解决方案加上 AI 相机](https://www.hp.com/us-en/solutions/presence.html)|核心 i5/i7|8 GB/16 GB|256 GB|
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 GB |128 GB |
  |[联想思想智能中心](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |联想 ThinkSmart Core 工具包 |Core i5|8 GB|128 GB|
  |[使用 Intel NUC 点击 Logitech](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Logitech Tap 和 Intel Tiger 峡谷 NUC PC |Core i5|8 GB|128 GB|
  |使用联想核心计算的 Logitech TAP 控制台 |Core i5|8 GB|128 GB|
  |[Logitech Tap 和 Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T 与联想 ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Poly G40-T Kit with Poly Studio USB， with Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g40) |Core i5| 8 GB | 128 GB|
  |[Poly G85-T 套件与 Poly Eagle Eye Director II，与联想](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g85) |Core i5| 8 GB | 128 GB|
  |Poly GC8 控制台与联想思想智能核心|Core i5|8 GB|128 GB|
  |使用 Dell Optiplex 7080 的 Poly GC8 控制台|Core i5|8 GB|128 GB|
  |[使用 Intel NUC 的 Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[使用 Intel NUC 的 Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[使用 Intel NUC 的 Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[使用 Intel NUC 的 Yealink MVC900](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  |Yealink MVC340|Core i5|8 GB | 128 GB|
  
  
> [!NOTE]
> - Core M3 处理器不受支持。
> - 需要将 32 GB 或更大的 USB 驱动器配置为 Windows 10 企业版的可启动 Windows 安装介质。

**支持的适用于坞站式系统的 Surface Pro 平板电脑**

  |平板电脑|处理器|RAM|磁盘|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB 或 8 GB |128 GB 或更多 |
  |Surface Pro </br>（第五代） |Core i5 |8 GB 或 4 GB |128 GB 或更多 |
  |Surface Pro 4 |Core i5 |8 GB 或 4 GB |128 GB 或更多 |

- Surface Pro设备需要以下停靠站选项之一：

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR 系列](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>适用于 USB 音频和视频外围设备的认证固件版本

可在[会议室系统配件产品展示](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)和 [https://office.com/teamsdevices](https://office.com/teamsdevices) 中找到这些设备。

|Microsoft Teams 会议室外围设备|认证的固件版本 | 支持内容相机|智能相机|
|:--- |:--- | :--- |:--- |
|[Aver VC520 专业相机 + 免提电话](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VC520 PRO2 会议系统](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Aver VB342+ 相机声栏](https://www.averusa.com/products/conference-camera/vb342plus) | 声栏：0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 550](https://www.averusa.com/products/conference-camera/cam550) |0.0.8000.51 |
|[Aver CAM 520 专业版](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Aver Fone540](https://www.averusa.com/products/vc-accessories/fone540) |0.0.7002.17|
|[Aver VB130 相机声栏](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[音频代码 RXVCAM50L](https://www.audiocodes.com/solutions-products/products/room-experience-rx-suite/rxvcam50lm-video-camera) |1.0.5 |
|[Bose 视频栏 VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[带天花板麦克风的 Biamp Devio SCR-20CX Web-Based会议中心](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[使用桌面麦克风将 Biamp Devio SCR-20TX Web-Based会议中心](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|HP 状态查看相机| 1.0.23.0 |
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Huddly IQ 相机](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Huddly L1](https://www.huddly.com/conference-cameras/l1/) | 1.2.9 |
|带 [Crestron UC-C100-T MTR](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T) 工具包的 Huddly L1 相机 | Huddly L1 相机：1.2.1 </br> Crestron UC-C100-T 与 ASUS Tek Computer INC 9934 计算 1.0.20.246 或更高版本 |
|带 [Crestron UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W Kit 的 Huddly L1 相机 | Huddly L1 相机：1.2.9 </br> 使用 ASUS Tek Computer INC 9934 1.00.20.246 或更高版本的 Crestron UC-CX100-T |
|带 Crestron UC-M70-T MTR 工具包的 Huddly L1 相机 | Huddly L1 相机：1.2.1 </br> 使用 ASUS Tek Computer INC 9934 计算 1.0.20.246 或更高版本的 Crestron UC-M70-T |
|带 Crestron UC-MX70-T MTR 工具包的 Huddly L1 相机 | Huddly L1 相机：1.2.1 </br> Crestron UC-MX70-T 与 ASUS Tek Computer INC 9934 计算 1.0.20.246 或更高版本 |
|[Jabra Panacast3 相机](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Jabra Panacast 50 视频栏](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|4.0.15| &#x2714; | &#x2714;|
|[联想 ThinkSmart Cam 相机](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[联想 ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|联想 ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |音频 — 1.0.172 <br/> 视频 — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube 摄像头](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.md)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://support.polycom.com/content/dam/polycom-support/products/peripherals/eagle-eye-director-ii/user/en/eagleeye-director-ii-admin-guide-2-0.pdf#:~:text=The%20Polycom%C2%AE%20EagleEye%E2%84%A2%20Director%20II%20camera%20is%20a,while%20the%20other%20camera%20tracks%20the%20second%20speaker.)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Poly Studio P15 视频栏](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Poly Studio E70 相机](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[Poly Studio R30](https://www.poly.com/us/en/products/video-conferencing/studio/studio-r30)|2.0.0.001096|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS 展开 80T + 2 扩展麦克风](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |扬声器 - 4.6.55 <br/> 扩展麦克风 - 0.2.314|
|[EPOS 展开捕获 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Extron DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT， DMP 128 Plus C AT， DMP 128 Plus C V， DMP 128 Plus C， DMP 128 Plus AT， DMP 128 Plus， DMP 128 FlexPlus C AT， DMP 128 FlexPlus C V AT) ](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Extron DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT， DMP 64 Plus C AT， DMP 64 Plus C V， DMP 64 plus C) ](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Yamaha ADECIA Ceiling 解决方案](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Yamaha ADECIA Tabletop 解决方案](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|E1.2.0 for table mic， D1.2.0 for processor (与 V1.5.1 相同的内容) |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC34 一次性视频栏](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Yealink UVC40 一次性视频栏](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 桌面矩阵麦克风](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/products/mixers/p300) +</br>[带 Intellimix 天花板矩阵麦克风的 Shure MXA 910](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 表数组麦克风 ](https://www.shure.com/products/microphones/mxa310) +</br>[MXN5W-C Ceiling 扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP：4.1.11 </br> MXA310 表数组麦克风：4.1.41 </br> MXN5W-C 扬声器：1.0.4 |
|[Shure Intellimix P300 音频会议处理器](https://www.shure.com/products/mixers/p300) + </br>[使用 Intellimix Ceiling Array Mic 的 Shure MXA 920](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[MXN5W-C Ceiling 扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP：4.7.7 </br> MXA920 天花板数组麦克风：1.1.56 </br> MXN5W-C 扬声器：1.5.6 |
|ANIUSB + </br> [使用 Intellimix Ceiling Array Mic 的 Shure MXA 920](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[MXN5 天花板扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| ANIUSB： 4.4.7 </br> MXA920：1.1.56 </br> MXN5：1.5.6|
|[Shure MXA 710 2 英尺表线性阵列麦克风](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 音频会议处理器](https://www.shure.com/products/mixers/p300) +</br>[MXN5-C 天花板扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2 英尺表线性数组麦克风：1.2.0 </br> P300 DSP：4.4.8 </br> MXN5-C 扬声器：1.1.1 |
|[Shure MXA 710 4 英尺墙体线性阵列麦克风](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 音频会议处理器](https://www.shure.com/products/mixers/p300) +</br>[MXN5-C 天花板扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4 英尺墙体线性数组麦克风：1.2.0 </br> P300 DSP：4.4.8 </br> MXN5-C 扬声器：1.1.1 |
|[使用 Intellimix Ceiling Array 麦克风的 Shure MXA 910](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software： 3.0.4.14 </br> 使用 Intellimix Ceiling Array 麦克风的 Shure MXA 910：4.4.11 </br> Shure MXN5-C 扬声器：1.2.1 </br> 使用 ASUS Tek Computer INC 9934 计算的 Crestron UC-C100-T | 
|[使用 Intellimix Ceiling Array 麦克风的 Shure MXA 910](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>联想 ThinkSmart Core | Shure Intellimix Room Software： 3.2.0.52 </br> 使用 Intellimix Ceiling Array 麦克风的 Shure MXA 910：4.4.11 </br> Shure MXN5-C 扬声器：1.2.1 |
|[Shure MXA920XX-R 圆形天花板数组麦克风](https://www.shure.com/en-US/products/microphones/mxa920?variant=MXA920AL-R) + </br> [P300 处理器](https://www.shure.com/en-US/products/mixers/p300?variant=P300-IMX) + </br> [MXN5 扬声器](https://www.shure.com/en-US/products/loudspeakers/mxn5) | MXA920XX-R：1.1.56 </br> P300 处理器：4.7.7 </br> MXN5 扬声器：1.5.6 |
|[使用 Intellimix Ceiling Array 麦克风的 Shure MXA 910](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Dell Optiplex 7080 | Shure Intellimix Room Software： 3.2.0.52 </br> 使用 Intellimix Ceiling Array 麦克风的 Shure MXA 910：4.4.11 </br> Shure MXN5-C 扬声器：1.2.1 |
|[Sennheiser TeamConnect 智能扬声器/TC ISP (T-Rock) ](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 固定音频 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br>[Sennheiser TeamConnect Ceiling 2 麦克风](https://sennheiser.com/tcc2)+ &Dagger;</br>[Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP：3.12.0.15 </br> TCC2：1.3.3 </br>EX-UBT：3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+</br>[Biamp Parlé TCM-XA 天花板麦克风](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Biamp Desono C-IC6 天花板装载扬声器](https://www.biamp.com/products/tesira-speakers)| 音频 FW 版本：3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[分析 TTM-X (表麦克风) ](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Ex-UBT]() |音频 FW 版本：3.15|
|[Biamp Devio SCX Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Biamp Parlé TCM-XA 天花板麦克风](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Biamp Desono C-IC6 天花板装载扬声器](https://www.biamp.com/products/tesira-speakers) | Devio SCX 系列：4.2.5 |
|[Biamp Tesira Forte X 系列音频 DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Biamp Parlé TCM-XA 天花板麦克风](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Biamp Desono C-IC6 天花板装载扬声器](https://www.biamp.com/products/tesira-speakers) | Tesira FORTE X 系列：4.2.5 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink 扬声器 +</br> Sennheiser TCC2 天花板麦克风 + </br> Bose EdgeMax EM180 天花板扬声器](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier +</br> [Sennheiser TCC2 天花板麦克风](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP 天花板扬声器](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [Sennheiser TCC2 天花板麦克风](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [EdgeMax EM180 天花板扬声器](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP：2.290  </br> P2600A：1.160  </br> TCC2：1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/)、 [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/)、 [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) 或 [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Sennheiser TCC2 天花板麦克风](https://en-us.sennheiser.com/tcc2) + </br> QSC 放大器 ([SPA 系列](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) 或 [CX-Q 系列](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [QSC AcousticDesign 系列扬声器](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> QSC IP 相机 ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)、 [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) 可选 + </br> [QSC Q-SYS I/O USB 桥](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) 可选 | QSC Q-SYS Core、PTZ-IP 相机和 I/O USB Bridge：QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 天花板麦克风： TCC2 - 1.5.1，但丁 1.2.0 </br> QSC 放大器：N/A </br> QSC AcousticDesign 系列扬声器：N/A | 
|[Vaddio IntelliSHOT-M](https://www.legrandav.com/products/cameras/hd_fixed_camera/intellishot-eptz-camera) | 1.0.0 |


&Dagger; 客户可以选择 Biamp/Sennheiser 为此捆绑包推荐的 Dante 界面或网络交换机。

#### <a name="usb-extenders"></a>USB 扩展器

- 平板电脑坞站上的 USB 端口兼容 USB 3.0。 可以使用 USB 2.x 扩展器，但最远端限制为 USB 2.x 速度。 建议不要将扩展器用于 USB 3.0 外围设备。
- 扩展器必须符合 USB 2.0 或更高版本的规范。
  - 平板电脑扩展坞至少支持两个阶段的外部 USB 集线器扩展。 如果你串联连接了两个以上的 USB 集线器，请与扩展坞制造商联系以确认其是否支持串联连接。
  - 会议室中的有线 GbE 连接。 长度合适的以太网电缆。
  - 包含 HDMI 连接的最多两个 1080p 显示器。 长度合适的 HDMI 电缆。

> [!NOTE]
> A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode. This feature is not supported on all TVs.
>
> Microsoft Teams 会议室不使用键盘。 如果需要，管理员应使用屏幕键盘。 在映像 Microsoft Teams 会议室设备时需要 USB 键盘或鼠标。

下表根据会议室大小提供了针对外围设备的建议：

**Microsoft Teams 会议室认证的音频外围设备**

|会议室类型|人数|麦克风与发言人之间的建议最大距离|
|:-----|:-----|:-----|
|**焦点** <br/> 10' x 9'   |2–4  |1.5 米  |
|**小型** <br/> 16' x 16'  |4–6  |2.0 米  |
|**中型** <br/> 18' x 20'  |6–12  |2.4 米  |
|**大型** <br/> 15' x 32'  |12–16  |3 米 <br/> 此距离也适用于每个连接的卫星麦克风所覆盖的区域。  |

**Microsoft Teams 会议室认证的视频外围设备**

|会议室类型|人数|
|:-----|:-----|
|**焦点** <br/> 10' x 9'  |2–4  |
|**小型** <br/> 16' x 16'  |4–6  |
|**中型** <br/> 18' x 20'  |6–12  |
|**大型** <br/> 15' x 32'  |12–16  |

 > [!NOTE]
 > 会议室正面的显示分辨率应设置为不超过 1920x1080p。


## <a name="see-also"></a>另请参阅

[浏览所有捆绑包](https://products.office.com/microsoft-teams/across-devices/devices)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[配置 Microsoft Teams 会议室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)
