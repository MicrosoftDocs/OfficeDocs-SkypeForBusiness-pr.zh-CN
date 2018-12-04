---
title: 曲面集线器部署的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 配置 Microsoft 团队面中心的管理设置。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132000"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>曲面集线器部署的 Microsoft 团队
======================================

为 Microsoft Surface 集线器部署的 Microsoft 团队之前，请确保您已满足硬件、 操作系统和其他要求。 有关详细信息，请参阅[Microsoft Surface 中心管理指南](https://docs.microsoft.com/surface-hub/)。

> [!NOTE]
> 如果您从 Skype 中的业务联机转换，您需要确认的 Microsoft 团队许可证分配给用户。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>从 Microsoft 存储的表面集线器安装团队 

安装 Microsoft 存储中的图面集线器团队供以下说明。 
 
1. 启动 Microsoft 存储：<br>
   a. 点击**开始** > **所有应用程序** > **设置**。<br> b. 点击**面集线器设备帐户、 管理**。<br>
   c. 在左侧，点击**应用程序和功能**选项卡。<br> d. 在右侧，点击**打开存储**按钮。 
2. 从 Microsoft 存储，搜索*的 Microsoft 团队*。 将显示**图面中心的 Microsoft 团队**。 点击**获取应用程序**按钮以安装。  
3. 安装完成后，重新启动面集线器。 

> [!NOTE]
> 不点击从商店列表页的**启动**。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>使团队默认呼叫和会议应用程序
 
有两种配置的默认呼叫和会议应用程序策略： 

- **选项 1**： 配置通过 USB 键。 
- **选项 2**： 通过如 Intune MDM 配置。
 
### <a name="option-1-configure-via-usb-key"></a>选项 1： 配置通过 USB 键 
 
此[下载页](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上，可以找到包。 选择相应的包的安装，并将其复制到 usb 闪存盘您计划。 要使用的正确.ppkg 文件取决于您想要应用，如下所示的默认应用程序策略： 

|数字  |说明  |
|---------|---------|
|0     | Skype 团队会议可用的启动屏幕上的首选应用程序        |
|1     | 团队 Skype 会议可用的启动屏幕上的首选应用程序        |
|2     | 在开始屏幕 (Skype app 不可用) 团队专用应用程序        |
 
1. 将 usb 闪存盘附加到面集线器设备。 
2. 打开面集线器设备上的**设置**应用程序。 
3. **曲面集线器设备帐户管理**打开。
4. 打开**设备管理**。 
5. 单击**添加或删除设置包**。 
6. 单击**添加包**。
7. 从下拉列表菜单中选择**可移动媒体**选项。 
8. 添加适当的<strong>TeamsRTMMode*.ppkg</strong>包以前复制到 usb 闪存盘。 
9. 重新启动面集线器设备。 
10. 设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>选项 2： 配置通过如 Intune MDM 

使用以下配置通过 Intune 的默认呼叫和会议应用程序策略。 另请参阅[Deploy 使用 Intune 的图面集线器应用程序的 Microsoft 团队](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/)的博客。

|设置   |值    |说明    |
|----------|---------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|数据类型 | 整数 (0-2)   |0-团队会议可用的启动屏幕上的 Skype 首选应用程序<br>1-团队 Skype 会议可用的启动屏幕上的首选应用程序<br>2-团队 （不可用 Skype 应用程序） 在开始屏幕上的专用应用程序 |
|运营| 获取、 设置        |

|设置   |值    |
|----------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|数据类型 | 字符串-团队应用程序包 ID 为**Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe 设置字符串 ！团队** |
|运营| 获取、 设置        |

重新启动面集线器设备。 设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。

