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
description: 了解如何安装和配置 Teams for Surface Hub 应用，使 Teams 成为默认的通话和会议应用程序。
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
ms.openlocfilehash: 38202fcbb4c2147baae3f745bc2455da6fdff3e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093932"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>为 Surface Hub 部署 Microsoft Teams
======================================

安装 Teams for Surface Hub 之前，请务必执行以下操作：

 □确保满足硬件、操作系统和其他要求。 有关详细信息，请参阅 Microsoft [Surface Hub 管理员指南](/surface-hub/)。<br>
 □确保已安装 Teams 所需的最低操作系统更新 - [KB4343889。](https://support.microsoft.com/help/4343889)<br>
 □向中心设备帐户分配 Teams 许可证。<br>
 □如果你正在从 Skype for Business Online 进行转换，请确认为用户分配了 Teams 许可证。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>从 Microsoft Store 安装 Teams for Surface Hub 

这些说明用于从 Microsoft Store 安装 Teams for Surface Hub。 
 
1. 启动 Microsoft Store：<br>
   a. 点击 **"启动**  >  **所有应用设置**  >  **"。**<br> b. 点击 **"Surface Hub 设备帐户，管理"。**<br>
   c. 在左侧，点击" **应用和功能&选项卡** 。<br> d. 在右侧，点击" **打开应用商店"** 按钮。 
2. 在 Microsoft Store 中，搜索 *"Microsoft Teams"。* 将显示 **Microsoft Teams for Surface Hub。** 点击" **获取应用"** 按钮进行安装。  
3. 安装完成后，重启 Surface Hub。 

> [!NOTE]
> 不要从应用商店 **一览** 页点击"启动"。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>将 Teams 设置为默认通话和会议应用程序
 
有两个选项用于配置默认呼叫和会议应用程序策略： 

- **选项 1：** 通过 USB 密钥进行配置。 
- **选项 2：** 通过 MDM（如 Intune）进行配置。
 
### <a name="option-1-configure-via-usb-key"></a>选项 1：通过 USB 密钥配置 
 
可以在此下载页上找到 [程序包](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)。 为计划安装的包选择适当的一个，并复制到 USB 密钥。 使用的正确 .ppkg 文件取决于要应用的默认应用程序策略，如下所示： 

|数字  |说明  |
|---------|---------|
|0     | "开始"屏幕上的 Skype 首选应用，Teams 会议可用        |
|1     | "开始"屏幕上的 Teams 首选应用，Skype 会议可用        |
|2     | "开始"屏幕上的 Teams 专属应用 (Skype 应用不可用)         |
 
1. 将 USB 密钥连接到 Surface Hub 设备。 
2. 在 Surface Hub **设备上打开** "设置"应用。 
3. 打开 **Surface Hub 设备帐户管理**。
4. 打开 **"设备管理"。** 
5. 单击 **"添加或删除预配包"。** 
6. 单击"**添加包"。**
7. 从 **下拉菜单中选择** "可移动媒体"选项。 
8. 添加之前复制到 USB 密钥的适当 <strong>TeamsRTMMode*.ppkg</strong> 包。 
9. 重新启动 Surface Hub 设备。 
10. 设备重启后，应该能够从"开始"屏幕启动 Teams 应用，然后从日历加入会议。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>选项 2：通过 MDM（如 Intune）进行配置 

使用以下代码通过 Intune 配置默认呼叫和会议应用程序策略。 另请参阅博客使用 [Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)部署 Microsoft Teams for Surface Hub 应用。

|设置   |值    |说明    |
|----------|---------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/properties/SurfaceHubMeetingMode        |
|数据类型 | 整数 (0-2)    |0 - "开始"屏幕上的 Skype 首选应用，Teams 会议可用<br>1 - "开始"屏幕上的 Teams 首选应用，Skype 会议可用<br>2 - Skype 应用不可用时，"开始"屏幕上 (Teams 专属)  |
|运营| 获取、设置        |

|设置   |值    |
|----------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|数据类型 | string - 将字符串设置为 Teams 应用程序包 ID **作为Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe！Teams** |
|运营| 获取、设置        |

重新启动 Surface Hub 设备。 设备重启后，应该能够从"开始"屏幕启动 Teams 应用，然后从日历加入会议。