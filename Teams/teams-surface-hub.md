---
title: 为 Surface Hub 部署 Microsoft Teams
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 了解如何为 Surface Hub 应用安装和配置团队，以便团队是默认的呼叫和会议应用程序。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 589bbfe75f0beea88066b5a6188b1d29c98ddd5f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905644"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>为 Surface Hub 部署 Microsoft Teams
======================================

在安装 Surface Hub 团队之前，请确保执行以下操作：

 □确保满足硬件、操作系统和其他要求。 有关详细信息，请参阅[Microsoft Surface Hub 管理员指南](https://docs.microsoft.com/surface-hub/)。<br>
 □确保已安装团队所需的最低操作系统更新- [KB4343889](https://support.microsoft.com/help/4343889)。<br>
 □将团队许可证分配给中心设备帐户。<br>
 □如果你是从 Skype for Business Online 转换的，请确认已向用户分配了团队许可证。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>从 Microsoft Store 安装 Surface Hub 团队 

这些说明用于从 Microsoft Store 安装 Surface Hub 团队。 
 
1. 启动 Microsoft Store：<br>
   a. 点击 "**开始** > **所有应用** > "**设置**。<br> b. 轻触**Surface Hub 设备帐户，管理**。<br>
   c. 在左侧，点击 "**应用 & 功能**" 选项卡。<br> d. 在右侧，点击 "**打开应用商店**" 按钮。 
2. 在 Microsoft Store 中，搜索*Microsoft 团队*。 将显示**Microsoft "Surface Hub 团队**"。 点击 "**获取应用"** 按钮进行安装。  
3. 安装完成后，重新启动 Surface Hub。 

> [!NOTE]
> 请勿点击 "应用商店" 页面上的 "**启动**"。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>使团队成为默认呼叫和会议应用程序
 
配置默认呼叫和会议应用程序策略有两个选项： 

- **选项 1**：通过 USB 密钥进行配置。 
- **选项 2**：通过 MDM （如 Intune）进行配置。
 
### <a name="option-1-configure-via-usb-key"></a>选项1：通过 USB 密钥配置 
 
可以在此[下载页面](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上找到程序包。 为你计划要安装的程序包选择合适的版本，并将其复制到 USB 密钥。 要使用的正确的 ppkg 文件取决于你希望应用的默认应用程序策略，如下所示： 

|数字  |说明  |
|---------|---------|
|0     | "开始" 屏幕上的 Skype 首选应用，团队会议可用        |
|1     | 团队首选应用在 "开始" 屏幕上，Skype 会议可用        |
|2     | "开始" 屏幕上的 "团队专用应用" （Skype 应用程序不可用）        |
 
1. 将 USB 密钥附加到 Surface Hub 设备。 
2. 在 Surface Hub 设备上打开 "**设置**" 应用。 
3. 开放式**Surface Hub 设备帐户管理**。
4. 打开 "**设备管理**"。 
5. 单击 "**添加或删除预配包**"。 
6. 单击 "**添加程序包**"。
7. 从下拉菜单中选择 "**可移动媒体**" 选项。 
8. 添加以前复制到 USB 密钥的相应<strong>TeamsRTMMode * ppkg</strong>程序包。 
9. 重新启动 Surface Hub 设备。 
10. 重新启动设备后，你应该能够从 "开始" 屏幕启动 "团队" 应用，并从日历中加入会议。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>选项2：通过 MDM （如 Intune）进行配置 

使用以下各项通过 Intune 配置默认呼叫和会议应用程序策略。 另请参阅[使用 Intune 部署 Microsoft 团队 For Surface Hub 应用](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)。

|设置   |值    |说明    |
|----------|---------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|数据类型 | 整数（0-2）   |0-"开始" 屏幕上的 Skype 首选应用，团队会议可用<br>1-团队首选应用在 "开始" 屏幕上，Skype 会议可用<br>2-"开始" 屏幕上的 "团队专用应用" （Skype 应用程序不可用） |
|运营| 获取、设置        |

|设置   |值    |
|----------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|数据类型 | 字符串-将团队应用程序包 ID 的字符串设置为**Microsoft MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe！团队** |
|运营| 获取、设置        |

重新启动 Surface Hub 设备。 重新启动设备后，你应该能够从 "开始" 屏幕启动 "团队" 应用，并从日历中加入会议。

