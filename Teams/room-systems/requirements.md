---
title: Microsoft 团队聊天室要求
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: 本文汇总了支持 Microsoft 团队聊天室的要求。
ms.openlocfilehash: c7923948dcfc989375c7fb5de30ff6c52b54d487
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362613"
---
# <a name="microsoft-teams-rooms-requirements"></a>Microsoft 团队聊天室要求

本文汇总了支持 Microsoft 团队聊天室的要求。 

[部署 Microsoft 团队聊天室](room-systems-v2.md)中所述的帐户创建和设置[配置的 Microsoft 团队聊天室控制台](console.md)中所述的会议控制台，将涉及您的部署。 

您可能还需要引用：

- [Skype for Business 加载项授权](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [许可基于您的计划选项： Microsoft 团队聊天室](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft 团队聊天室旨在与 Microsoft 团队、 业务服务器 2019年的 Skype、 业务服务器 2015年的 Skype 或 Skype 业务 online 一起使用。 <br><br>早期平台，如 Lync Server 2013 不应与 Microsoft 团队聊天室工作。

> [!NOTE]
> 如果使用 prem 上 Exchange 服务器，Microsoft 团队聊天室将需要使用 Exchange Server 2013 SP1 或更高版本。

## <a name="hardware-requirements"></a>硬件要求

Microsoft 团队聊天室可以扩展到不同的会议室大小通过根据音频和视频的外围设备的附件。 本文中列出的硬件支持 Skype 和团队会议模式。  通过停靠的设备上的 USB 或 HDMI 连接情况下，音频和视频的外围设备连接到 Microsoft 团队聊天室。 你还将需要：

- 32 GB 或更大的 USB 磁盘将 Windows 10 enterprise 配置为可引导的 Windows 安装介质。 

- 下面的平板电脑或控制台之一：

**支持的平板电脑**

|平板电脑|处理器|RAM|磁盘|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |核心 i5  |16 GB 或 8 GB |128 GB 或更多  |
|Surface Pro (第五个 Gen)  |核心 i5  |8 GB 或 4 GB  |128 GB 或更多  |
|Surface Pro 4          |核心 i5  |8 GB 或 4 GB  |128 GB 或更多  |

> [!NOTE]
> 核心 M3 处理器不受支持。

**支持的控制台**

|控制台|处理器|RAM|磁盘|
|:-----|:-----|:-----|:-----|
|[联想 ThinkSmart 集线器 500](https://www3.lenovo.com/us/en/hub500) |核心 i5  |8 GB  |128 GB  |  
|[HP 精英切片的会议聊天室 G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |核心 i5  |8 GB  |128 GB  |  

- 以下的停靠站选项，以确保以安全会议平板电脑之一会议室表。 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR 系列](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**认证的 USB 音频和视频外围设备的固件版本**

|Microsoft 团队聊天室外围设备|为 Microsoft 团队房间认证的固件版本|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |音频-1.0.172  <br/> 视频-1.0.156  <br/> |
|[Logitech ConferenceCam 连接](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Logitech 组](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ 专业人员](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ 专业人员 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom RealPresence 三个](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100 ](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100 c  <br/> |

- **USB 扩展程序**：

  - 在平板电脑停靠上的 USB 端口是 USB 3.0 兼容。 您可以使用 USB 2.x 扩展，但这样做，以便将限制您最端上的 USB 2.x 速度，这样做，以便不建议 USB 3.0 外围设备。

  - 扩展程序必须符合 USB 2.0 或更高版本的规范。

  - 平板电脑停靠支持外部 USB 集线器扩展至少两个的阶段。 如果需要连接以上系列中的两个 USB 集线器，您将需要检查停靠制造商，以确认因此支持这样做。

- 中聊天室的有线的 GbE 连接。 长度合适的以太网电缆。

- 为两个 1080p 显示 HDMI 连接。 HDMI 适当长度的线。

    > [!NOTE]
    > 用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。 并非所有电视都支持此功能。 

> [!NOTE]
> Microsoft 团队聊天室不使用键盘。 如果需要，管理员应使用屏幕键盘。 USB 键盘或鼠标将在需要时图像处理 Microsoft 团队聊天室设备。 

下表提供有关外围设备基于会议室大小的建议：

**认证音频外围设备的 Microsoft 团队聊天室**

|会议室类型|人数|麦克风与发言人员之间的建议最大距离|设备（按最大会议室大小）|备注|
|:-----|:-----|:-----|:-----|:-----|
|**焦距** <br/> 10 个 x 9"  <br/> |2-4  <br/> |1.5m   <br/> |Logitech Connect  <br/> |Logitech 连接设备包括了摄像机，因此它必须定位在前面的聊天室 （不表的中心） 捕获本地与会者。  <br/> |
|**小** <br/> 16 x 16"  <br/> |4-6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |对于较大的会议室，播放音量可能会受到限制。  <br/> |
|**中** <br/> 18 x 20"  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC 毫秒  <br/> |Logitech MeetUp 包含了摄像机，因此它必须定位在前面的聊天室 （不中心要捕获本地与会者表）。  <br/> 一般来说，与长矩形或 u 形表聊天室可以受益于其他附属麦克风。  <br/> 菊花链配置中必须使用 SP 220 MS。  <br/> |
|**大** <br/> 15' x 32"  <br/> |12 16  <br/> |3m  <br/> 此距离也适用于连接到正在使用的音频设备的每个其他卫星麦克风覆盖的区域。  <br/> |Logitech 组 + 附属话筒  <br/> Polycom 三个 + 附属话筒  <br/> Polycom CX5100 + 附属话筒  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC 1000MS + 附属话筒  <br/> |此行列出的所有音频设备都支持卫星麦克风选项。  <br/> CX5100 包括内置的 360 度摄像头，因此该设备可以放置在桌子中心。  <br/> 菊花链配置中必须使用 SP 220 MS。  <br/> |

**认证视频外围设备的 Microsoft 团队聊天室**

|会议室类型|人数|按最佳会议室大小的设备|备注|
|:-----|:-----|:-----|:-----|
|**焦距** <br/> 10 个 x 9"  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**小** <br/> 16 x 16"  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ 专业人员  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ 专业人员通常与 Logitech 组捆绑在一起  <br/> |
|**中** <br/> 18 x 20"  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ 专业人员  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**大** <br/> 15' x 32"  <br/> |12 16  <br/> |Logitech PTZ 专业人员  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||

 > [!NOTE]
 > 前面的聊天室显示解决方案应设置为不超过 1920x1080p。

## <a name="required-software-downloads"></a>所需的软件下载

若要构建您自己的 Microsoft 团队聊天室图像，按照中[配置的 Microsoft 团队聊天室控制台](console.md)的说明。 这些说明将指导您完成下载所有必需的软件安装过程。 

> [!NOTE]
> IT 专业人员需要对其的批量许可协议通过 Windows 10 企业 ISO 文件的访问。

此外，您可能需要一份[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，其中您可用于设置 Microsoft 团队会议室帐户。

## <a name="see-also"></a>另请参阅

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)

[部署 Microsoft 团队聊天室](room-systems-v2.md)

[配置 Microsoft 团队聊天室控制台](console.md)

[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)

[Skype for Business 附加许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
