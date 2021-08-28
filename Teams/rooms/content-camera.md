---
title: 了解如何设置内容摄像头 - Microsoft Teams
ms.author: serdars
author: serdarsoysal
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
ms.custom:
- seo-marvel-mar2020
description: 使用会议室中的内容Microsoft Teams相机，该相机与图像处理软件交互，允许演示者在模拟白板上绘图。
ms.openlocfilehash: e24a90e65a5d844a5431951283153a5de2406498
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613001"
---
# <a name="content-cameras"></a>内容照相机

现在，您可以将内容相机与 Microsoft Teams 会议室系统一起使用。 内容相机与特殊的图像处理软件和白板交互，允许演示者在模拟白板上绘图并与远程参与者共享内容。

有关内容相机功能的示例，请参阅以下视频。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>设置内容相机

> [!NOTE]
> 始终遵守你国家/地区或地区的建筑代码，该代码可能定义与楼层的最小距离，或者要求将安装在天花板上的设备固定到排水机或其他结构。 按照随所选相机一起提供的硬件的安装说明操作。 OEM 相机安装工具包包括相机、USB 2.0 扩展器以及所需的布线。

用于共享的白板大小会影响相机的位置。 板大小建议包括：

- 3-6 ft. (0.9–1.8 m) - 支持
- 6-9 ft. (1.8–2.7 m) 宽 — 推荐
- 9-12 ft. (2.7–3.6 m) - 支持
- 在 12 ft. (3.6 m) 宽 - 相机覆盖 9-12 ft. (2.7–3.6 m) 并覆盖其余部分。

## <a name="camera-location"></a>相机位置

内容相机的理想位置在白板上垂直和水平居中。 本地建筑物代码可能有高度限制，要求相机提升高于白板的顶部。

可以安装最多 6 个摄像头。  (152 mm) 高于白板顶部，居中显示在白板上，如下所示。 请确保相机图像至少包含 6 个 in。  (两侧) 152 毫米的边框。 可以在应用内使用相机预览Microsoft Teams 会议室确定相机的最终位置。

![内容相机放置图](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>相机距离

使用典型的白板标记，最佳远程用户体验是共享内容相机图像中每像素 1-2 毫米的墨迹笔划，最佳结果使用 1.5 mm/像素。 所有受支持的相机都提供 1920 x 1080 分辨率，有些相机可以超过该分辨率。

相机与白板的距离与相机分辨率和 HFoV 相结合，以确定与白板的距离。 下表显示了各种白板大小的距离示例。 可以使用这些值作为起点来确定内容相机的最终位置。

**从白板到相机的距离**

| 相机 HFoV |3 ft. (0.91 m)      | 6 ft. (1.8 m)     | 9 ft. (2.74 m)         |12 ft. (365 万)          | 与 Whiteboard 的最大距离  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1.79 ft. (0.54 m)  | 3.58 ft. (1.09 m)   | 5.36 ft. (1.6 m)     |7.15 ft. (2.17 m)  |7.51 ft. (2.28 m)  |
| 90°         | 1.5 ft. (0.45 m)  | 3.00 ft. (0.91 m)    | 4.5 ft. (1.37 m)     |6.0 ft. (1.82 m)     |6.3 ft. (1.92 m)  |
| 100°        | 1.26 ft. (0.38 m) | 2.52 ft. (0.77 m)    | 3.78 ft. (1.15 m)    |5.03 ft. (1.53 m)    |5.29 ft. (1.61 m)  |
| 110°        | 1.05 ft. (0.32 m) | 2.10 ft. (0.64 m)    | 3.15 ft. (0.96 m)    |4.2 ft. (1.28 m)     |4.41 ft. (1.31 m)  |
| 120°        | 0.87 ft. (0.26 m) | 1.73 ft. (0.52 m)    | 2.60 ft. (0.79 m)    |3.46 ft. (1.05 m)    |3.64 ft. (1.10 m)  |
|             |               |                  |                  |        |                    |                  |

内容相机与白板装载的墙壁之间的距离取决于该型号相机的 HFoV，该型号因不同而异。 安装 HFoV 大于 120 度 (例如，) 靠近墙壁的相机，以及距离墙壁较窄的 HFoV 的相机。 在开始安装所选相机之前，请检查 HFoV。

如果你的白板大于 12 ft. ( (3.65 m) 或者没有角落 (如满墙白板) ，你可以将相机放在中间的任意位置。 如果找不到白板角落，增强软件会选择中间的某个区域。

> [!NOTE]
> 可以使用深色磁带或其他项目在全屏白板上创建定义的内容相机区域。
>
> 你可以选择将相机安装在可移动的三脚架上，而不是永久装载上。 将三脚架居中放在白板上。 此设置可能是临时的，或在很少有机会损坏设备的地方使用。 如果使用临时装入点，请记住，如果在初始共享后移动相机，内容增强将受到影响，并且需要重新共享以更正移动。
>
> 不支持非白色书写板。

## <a name="supported-cameras"></a>支持的摄像头

若要确定是否可以将相机用作内容相机，请参阅 USB 音频和视频外围设备的认证 [固件版本](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)。

或者，有关受支持的Microsoft Teams工具包，请参阅[aka.ms/teamsdevices。](https://aka.ms/teamsdevices)

## <a name="camera-settings"></a>相机设置

在房间中安装摄像机后，在房间的主机上Microsoft Teams 会议室摄像机：

1. 选择 ![ ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) 设置设置"图标，以"管理员"登录，然后选择"**设备设置"。**
2. 在" **相机默认值"** 部分中，选择内容相机并确保选中"内容 **增强"** 选项。
3.  (可选) 如果由于相机从天花板安装而倒置安装了相机，请选中"旋转内容相机 **180°"** 选项。
4. 选择 **"保存并退出"。**

![内容相机设置](../media/content-camera.png)

也可使用 XML 配置文件远程调整 [这些设置](xml-config-file.md)。

## <a name="see-also"></a>另请参阅

[使用 XML Microsoft Teams 会议室远程管理主机设置](xml-config-file.md)

[Microsoft Teams 会议室要求](requirements.md)


