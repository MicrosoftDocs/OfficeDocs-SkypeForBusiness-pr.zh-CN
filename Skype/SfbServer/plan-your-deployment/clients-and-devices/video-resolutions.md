---
title: Skype for Business 客户端视频解决方案
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 摘要：在规划 Skype for business Server 时检查客户端视频要求。
ms.openlocfilehash: 126c19d817a2cd656b7d581e0d467db80e4969e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027973"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business 客户端视频解决方案
 
**摘要：** 在规划 Skype for business Server 时查看客户端视频要求。
  
本文介绍了 Skype for business 视频通话的视频硬件支持，并介绍了如何确定各种计算机、平板电脑和移动设备配置的预期视频质量。 
  
IT 专业人员将在评估组织中已使用的便携式计算机的适用性或在考虑使用时对此信息有用。 他们还可以在[解决方案目录](https://partnersolutions.skypeforbusiness.com/solutionscatalog)中搜索有关特定设备的信息。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows desktop、Mac 和平板电脑视频要求和功能

Skype for Business 使用硬件加速进行视频编码，并基于 H-p/MPEG-2 第10部分高级视频编码标准进行视频编码和解码。 这样一来，CPU 时钟速度较低的计算机就可以对更高分辨率的视频进行编码和解码。 视频硬件要求随计算机配置和所需的视频分辨率的不同而不同。
  
另请参阅[Windows 和 Mac 硬件要求](https://products.office.com/office-system-requirements)。
  
### <a name="video-hardware-requirements"></a>视频硬件要求

|**功能**|**要求**|
|:-----|:-----|
|使用 DirectX 视频加速 (DXVA) 的硬件加速 H.264 解码  <br/> |•图形卡必须支持 DirectX 9.0，并且必须公开 DXVA2_ModeH264_VLD_NoFGT 解码模式和 DirectX 9 API。  <br/> •必须安装最新的图形卡驱动程序。  <br/> |
|硬件加速 H.264 编码：芯片集要求  <br/> |支持以下 Intel 硬件加速视频编码解决方案：  <br/> •第二和第三代 Intel HD Graphics 2000、2500、3000和4000芯片组（或更高版本），带有集成的硬件视频编码器。 需要安装 Intel HD 图形驱动程序15.28.9.2884 或包含以下内容的最新驱动程序：  <br/> •显示驱动程序9.17.10.2884 或最新驱动程序  <br/> •硬件媒体基础转换（HMFT）版本3.12.10.31 或最新 HMFT  <br/> 支持以下 AMD 硬件加速视频编码解决方案：  <br/> • AMD Video 编解码器引擎，可在多个独立的图形卡和 AMD A 系列的加速处理器的集成加速处理单元中提供。 必须安装 AMD 视频编解码器引擎驱动程序9.12.0.0 或更高版本。  <br/> |
|硬件加速 H.264 编码：摄像机要求  <br/> |具有符合 USB Video Class (UVC) 规格版本 1.5 的集成 H.264 硬件编码器的 USB 视频摄像机。  <br/> **注意：** Skype for Business 支持 Windows 8 或 Windows 8.1 的 UVC 1.5 摄像头，其中包括对 UVC 1.5 的支持。 由于 Windows 7 不包括对 UVC 1.5 的支持，Skype for Business 将 UVC 1.5 相机视为常规相机，不支持硬件编码。 <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>确定 H-p 视频编码和解码功能

通常，存在确定特定计算机配置的最大编码和解码功能的四大因素：
  
- 使用 DXVA 支持硬件加速解码
    
- 支持硬件加速编码
    
- 物理核心数
    
- Windows 体验指数 (WEI)
    
Windows 系统评估工具 (WinSAT) 确定 WEI。在运行 WinSAT 工具时，它会在计算机上的 %windir%\Performance\WinSAT\DataStore 目录中生成一个 Formal.Assessment XML 文档。此 XML 文件包含对于确定编码功能和解码功能非常重要的以下两项分数：
  
- VideoEncodeScore 指示计算机的基于软件的视频编码功能。
    
- GraphicsScore 值指示计算机的硬件加速编码功能。
    
以下三个表说明了不同的 PC 类型依据其支持的硬件加速所具有的最大编码功能和解码功能。对于 640x360 和更高分辨率，最大支持帧速率为 30 帧/秒 (fps)。对于低于 640x360 的分辨率，最大支持帧速率为 15 fps。
  
**不带 DXVA 且不带硬件加速编码器的计算机**

|**支持的编码器分辨率**|**支持的解码器分辨率**|**要求**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240（对于仅接收方案，分辨率为 640x360，帧速率为15fps）  <br/> |单核且 VideoEncodeScore ≥ 4.0  <br/> |
|640x360  <br/> |640x360  <br/> |双核且 VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1280x720  <br/> |双核且 VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1920x1080  <br/> |四核且 VideoEncodeScore ≥ 4.5  <br/> |
|1280x720  <br/> |1280x720  <br/> |四核且 VideoEncodeScore ≥ 7.3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |四核且 VideoEncodeScore ≥ 7.3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |不适用  <br/> |
   
**带 DXVA 但不带硬件加速编码器的计算机**

|**支持的编码器分辨率**|**支持的解码器分辨率**|**要求**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |单核且 VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |双核且 VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |双核且 VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |四核且 VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |四核且 VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7 上的 WinSAT 分数最高为 7.9。 因此，只有在 Windows 8 或 Windows 8.1 上才能实现不带硬件加速编码器的计算机的编码功能，其中最大 WinSAT 分数为9.9。 
  
**带 DXVA 且带 Intel 高清显卡硬件加速编码器的计算机**

|**支持的编码器分辨率**|**支持的解码器分辨率**|**要求**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |所有第 2 代和第 3 代 Intel 高清显卡  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |第 2 代和第 3 代 Intel 高清显卡且 GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>移动设备视频功能

下表介绍了在受支持的移动设备上可用的最大视频分辨率。 有关移动设备支持的详细信息，请参阅[Skype for business 的移动客户端功能比较](mobile-feature-comparison.md)。
  
|**功能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|最大分辨率-264 编码  <br/> |VGA  <br/> |QVGA： iPhone 4S  <br/> VGA： iPhone 5  <br/> 720p： iPhone 5S 及更高版本  <br/> |VGA： iPad 2 及更高版本/iPad 迷你1及更高版本  <br/> 720p： iPad Air/iPad 迷你 2/iPad Pro 及更高版本  <br/> |最高为 VGA，具体取决于设备型号  <br/> |
|H-p 解码最大分辨率  <br/> |VGA  <br/> |QVGA： iPhone 4S  <br/> VGA： iPhone 5  <br/> 720p： iPhone 5S 及更高版本  <br/> |VGA： iPad 2 及更高版本/iPad 迷你1及更高版本  <br/> 720p： iPad Air/iPad 迷你 2/iPad Pro 及更高版本  <br/> |最高为 VGA，具体取决于设备型号  <br/> |
   

