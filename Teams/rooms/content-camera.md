---
title: 了解如何设置内容相机 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom:
- seo-marvel-mar2020
description: 使用Microsoft Teams 会议室中的内容相机与图像处理软件交互，使演示者能够在模拟白板上绘制。
ms.openlocfilehash: 6f8116e8c54c24d31a122d54ec505b72f4ef8fdc
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606371"
---
# <a name="content-cameras"></a>内容照相机

现在可以将内容相机与Microsoft Teams 会议室系统配合使用。 内容相机与特殊的图像处理软件和白板交互，使演示者能够在模拟白板上绘制内容并与远程参与者共享内容。

[!INCLUDE [teams-pro-license-requirement](../includes/teams-pro-license-requirement.md)]

有关内容相机功能的示例，请参阅以下视频。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>设置内容相机

> [!NOTE]
> 始终遵守国家或地区的建筑代码，该代码可能定义与地板的最小距离，或者要求将装载天花板的设备保护到木筏或其他结构。 按照所选相机提供的硬件的装载指令操作。 OEM 相机装载工具包包括相机、USB 2.0 扩展器和所需的布线。

用于共享的白板的大小会影响相机的位置。 开发板大小建议包括：

- 3-6 英尺 (0.9-1.8 米) 宽 - 受支持
- 6-9 英尺 (1.8-2.7 米) 宽 - 建议
- 9-12 英尺 (2.7-3.6 米) 宽 - 受支持
- 超过12英尺 (3.6米) 宽 - 相机覆盖9-12英尺 (2.7-3.6米) 和作物其余。

## <a name="camera-location"></a>相机位置

内容相机的理想位置在白板上垂直和水平居中。 本地建筑代码可能有高度限制，要求相机高于白板顶部。

最多可以安装 6 个内的摄像头。  (比白板顶部高 152 毫米) ，居中位于白板上，如下所示。 确保相机图像至少包含 6 个内。 两侧水平 (152 毫米) 边框。 可以在Microsoft Teams 会议室应用中使用相机预览来确定相机的最终位置。

![内容相机放置图。](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>相机距离

使用典型的白板标记，最佳远程用户体验是共享内容相机图像中每像素 1-2 毫米范围内的墨迹笔划，最佳结果为每像素 1.5 毫米。 所有支持的相机都提供 1920 x 1080 分辨率，有些可以超过该分辨率。

相机与白板的距离与相机分辨率和水平视场 (HFoV) 相结合，以确定与白板的距离。 下表显示了不同白板大小的距离示例。 可以使用这些值作为起点来确定内容相机的最终位置。

**相机与白板的距离**

| 相机 HFoV |3 英尺 (0.91 米)      | 6 英尺 (1.8 米)     | 9 英尺 (2.74 米)         |12 英尺 (3.65 米)          | 与白板的最大距离  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1.79 英尺 (0.54 米)  | 3.58 英尺 (1.09 米)   | 5.36 英尺 (1.6 米)     |7.15 英尺 (2.17 米)  |7.51 英尺 (2.28 米)  |
| 90°         | 1.5 英尺 (0.45 米)  | 3.00 英尺 (0.91 米)    | 4.5 英尺 (1.37 米)     |6.0 英尺 (1.82 米)     |6.3 英尺 (1.92 米)  |
| 100°        | 1.26 英尺 (0.38 米) | 2.52 英尺 (0.77 米)    | 3.78 英尺 (1.15 米)    |5.03 英尺 (1.53 米)    |5.29 英尺 (1.61 米)  |
| 110°        | 1.05 英尺 (0.32 米) | 2.10 英尺 (0.64 米)    | 3.15 英尺 (0.96 米)    |4.2 英尺 (1.28 米)     |4.41 英尺 (1.31 米)  |
| 120°        | 0.87 英尺 (0.26 米) | 1.73 英尺 (0.52 米)    | 2.60 英尺 (0.79 米)    |3.46 英尺 (1.05 米)    |3.64 英尺 (1.10 米)  |
             

安装白板的内容相机和墙壁之间的距离取决于该相机模型的 HFoV，该模型各不相同。 安装具有较大 HFoV (120 度的摄像头，例如，) 靠近墙壁，以及距离墙较窄的 HFoV 的摄像头。 在开始安装所选相机之前，请检查 HFoV。

如果你的白板大于 12 英尺 (3.65 米) 或没有角落 (像全壁白板) ，你可以把相机放在中间的任何位置。 如果无法找到白板角，增强软件将选择中间的区域。

> [!NOTE]
> 可以使用深色磁带或其他项目在全壁白板上创建定义的内容相机区域。 这有助于会议室内与会者了解他们何时在内容相机捕获的区域中绘制。
>
> 可以选择将相机装载在可移动的三脚架上，而不是永久装载上。 将三脚架放在白板上。 此设置可能是临时的，或者在几乎不可能敲开设备的情况下使用。 如果使用临时装载，请记住，如果在初始共享后移动相机，并且需要重新共享以更正移动，则内容增强将受到影响。
>
> 不支持非白色的写入板。

## <a name="supported-cameras"></a>支持的相机

若要确定是否可以使用相机作为内容相机，请参阅 [USB 音频和视频外围设备的认证固件版本](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)。

或者，请参阅 Microsoft Teams 设备市场，了解 [aka.ms/teamsdevices](https://aka.ms/teamsdevices) 支持的内容相机工具包。

## <a name="camera-settings"></a>相机设置

在会议室中安装摄像头后，将其设置在该会议室的Microsoft Teams 会议室控制台上：

1. 选择 **“设置**![”图标，](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)以管理员身份登录，然后选择 **“外围设备**”。
2. 在 **“内容相机** ”部分，选择内容相机，并确保选择 **“内容增强** 功能”选项。
3.  (可选) 如果由于相机从天花板上装载而倒置了相机，请检查 **“旋转内容相机 180°** ”选项。
4. 选择 **“保存”并退出**。

![内容相机设置。](../media/content-camera1.png)

还可以使用 [XML 配置文件](xml-config-file.md)远程调整这些设置。

## <a name="see-also"></a>另请参阅

[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md)

[Microsoft Teams 会议室要求](requirements.md)


