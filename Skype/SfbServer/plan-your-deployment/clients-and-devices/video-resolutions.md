---
title: Skype 业务客户端的视频分辨率
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 摘要： 规划为 Skype 业务服务器 2015年同时查看客户端视频要求。
ms.openlocfilehash: fea2ae1aaa0e75248f9b1102bdfd9ebd5d03afb5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype 业务客户端的视频分辨率
 
**摘要：**同时规划为 Skype 业务服务器 2015年查看客户端视频需求。
  
本文介绍业务可视电话的 Skype 的视频硬件支持，并介绍了如何确定预期的视频质量的各种计算机、 平板电脑和移动设备的配置。 
  
IT 专业人员会发现此信息可用于评估已在使用中其组织，或正在考虑使用便携式计算机的适用性。 他们还可以搜索在特定设备上的信息[解决方案目录](https://partnersolutions.skypeforbusiness.com/solutionscatalog)。
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows 桌面、 Mac 和手写板视频要求和功能

Skype 业务使用硬件加速的视频编码和解码基于 H.264/mpeg-4 部分 10 高级视频编码标准。 这使计算机使用较低的 CPU 时钟速度进行编码和解码更高分辨率的视频。 视频硬件要求随计算机配置和所需的视频分辨率的不同而不同。
  
请参阅[Windows 和 Mac 的硬件要求](https://products.office.com/en-us/office-system-requirements)。
  
### <a name="video-hardware-requirements"></a>视频硬件要求

|**功能**|**要求**|
|:-----|:-----|
|使用 DirectX 视频加速 (DXVA) 的硬件加速 H.264 解码  <br/> |• 图形卡必须支持 DirectX 9.0 和 DXVA2_ModeH264_VLD_NoFGT 解码模式和 DirectX 9 API 必须公开。  <br/> • 必须安装最新的图形卡驱动程序。  <br/> |
|硬件加速 H.264 编码：芯片集要求  <br/> |支持以下 Intel 硬件加速视频编码解决方案：  <br/> • 第二和第三代英特尔 HD 2000、 2500年、 3000 和 4000 的图形芯片组 （或更高版本） 与集成的硬件视频编码器。 需要安装 Intel 高清显卡驱动程序 15.28.9.2884 或包含以下内容的最新驱动程序：  <br/> • 显示驱动程序 9.17.10.2884 或最新驱动程序  <br/> • 硬件媒体基础转换 (HMFT) 版本 3.12.10.31 或最新 HMFT  <br/> 支持以下 AMD 硬件加速视频编码解决方案：  <br/> • AMD 视频编解码器引擎，可以在多个独立显卡和集成加速 AMD A 系列加快处理器的处理的单元。 必须安装 AMD 视频编解码引擎驱动程序 9.12.0.0 或更高版本。  <br/> |
|硬件加速 H.264 编码：摄像机要求  <br/> |具有符合 USB Video Class (UVC) 规格版本 1.5 的集成 H.264 硬件编码器的 USB 视频摄像机。  <br/> **注意：**Skype 的业务支持 UVC 1.5 照相机与 Windows 8 或 Windows 8.1，包括对 UVC 1.5 的支持。 因为 Windows 7 不包括对 UVC 1.5 的支持，Skype 业务视为 UVC 1.5 照相机常规相机不硬件编码支持。 <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>确定 H.264 视频编码和解码功能

通常，存在确定特定计算机配置的最大编码和解码功能的四大因素：
  
- 使用 DXVA 支持硬件加速解码
    
- 支持硬件加速编码
    
- 物理核心数
    
- Windows 体验指数 (WEI)
    
Windows 系统评估工具 (WinSAT) 确定 WEI。在运行 WinSAT 工具时，它会在计算机上的 %windir%\Performance\WinSAT\DataStore 目录中生成一个 Formal.Assessment XML 文档。此 XML 文件包含对于确定编码功能和解码功能非常重要的以下两项分数：
  
- VideoEncodeScore 指示计算机的基于软件的视频编码功能。
    
- GraphicsScore 值指示计算机的硬件加速编码功能。
    
以下三个表说明了不同的 PC 类型依据其支持的硬件加速所具有的最大编码功能和解码功能。对于 640x360 和更高分辨率，最大支持帧速率为 30 帧/秒 (fps)。对于低于 640x360 的分辨率，最大支持帧速率为 15 fps。
  
**计算机无需 DXVA 和硬件加速的编码器**

|**能够编码器分辨率**|**解码器能够解析**|**要求**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424x240（对于仅接收方案，分辨率为 640x360，帧速率为15fps）  <br/> |单核且 VideoEncodeScore ≥ 4.0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |双核且 VideoEncodeScore ≥ 4.5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |双核且 VideoEncodeScore ≥ 4.5  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |四核且 VideoEncodeScore ≥ 4.5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |四核且 VideoEncodeScore ≥ 7.3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |四核且 VideoEncodeScore ≥ 7.3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |不适用  <br/> |
   
**计算机具有 DXVA 但没有硬件加速编码器**

|**能够编码器分辨率**|**解码器能够解析**|**要求**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080  <br/> |单核且 VideoEncodeScore ≥ 3.0  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |双核且 VideoEncodeScore ≥ 4.5  <br/> |
|960 x 540  <br/> |1920 x 1080  <br/> |双核且 VideoEncodeScore ≥ 6.0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |四核且 VideoEncodeScore ≥ 6.7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |四核且 VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> Windows 7 上的 WinSAT 分数最高为 7.9。因此，不带硬件加速编码器的计算机的编码功能仅可在 Windows 8 或 Windows 8.1 上实现，其中最高 WinSAT 分数为 9.9。 
  
**计算机与 DXVA 和英特尔 HD 图形硬件加速编码器**

|**能够编码器分辨率**|**解码器能够解析**|**要求**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |所有第 2 代和第 3 代 Intel 高清显卡  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |第 2 代和第 3 代 Intel 高清显卡且 GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>移动设备视频功能

下表描述受支持的移动设备上可用的最大的视频分辨率。 移动设备支持、[业务的 Skype 的移动客户端功能比较](mobile-feature-comparison.md)有关的详细信息。
  
|**功能**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|H.264 编码最大分辨率  <br/> |VGA  <br/> |QVGA：iPhone 4S  <br/> VGA：iPhone 5  <br/> 720p：iPhone 5S 和更高版本  <br/> |VGA：iPad 2 和更高版本/iPad mini 1 和更高版本  <br/> 720p：iPad Air/iPad mini 2/iPad Pro 和更高版本  <br/> |这取决于设备模型的 VGA 到  <br/> |
|H.264 解码最大分辨率  <br/> |VGA  <br/> |QVGA：iPhone 4S  <br/> VGA：iPhone 5  <br/> 720p：iPhone 5S 和更高版本  <br/> |VGA：iPad 2 和更高版本/iPad mini 1 和更高版本  <br/> 720p：iPad Air/iPad mini 2/iPad Pro 和更高版本  <br/> |这取决于设备模型的 VGA 到  <br/> |
   

