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
description: 了解如何安装和配置 Teams 应用程序Surface Hub，Teams呼叫和会议应用程序。
ms.localizationpriority: medium
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
ms.openlocfilehash: 7b3856dd7cd88626236e370b633663c1e3182bba
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586474"
---
# <a name="deploy-microsoft-teams-for-surface-hub"></a>为 Surface Hub 部署 Microsoft Teams

在安装Teams Surface Hub，请确保执行以下操作：

 □确保满足硬件、操作系统和其他要求。 有关详细信息，请参阅管理员[Microsoft Surface Hub指南](/surface-hub/)。<br>
 □确保已安装安装 Teams所需的最低操作系统更新 - [KB4343889。](https://support.microsoft.com/help/4343889)<br>
 □将Teams许可证分配给中心设备帐户。<br>
 □如果要从 Skype for Business Online 转换，请确认Teams用户分配了一个许可证。

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>从Teams Surface Hub安装Microsoft Store 

这些说明用于从Teams Surface Hub安装Microsoft Store。 
 
1. 启动Microsoft Store：<br>
   a. 点击 **"启动**  >  **所有应用**  >  **设置"。**<br> b. 点击 **"Surface Hub设备帐户，管理"。**<br>
   c. 在左侧，点击" **应用和功能&选项卡** 。<br> d. 在右侧，点击" **打开应用商店"** 按钮。 
2. 从Microsoft Store，搜索 *"Microsoft Teams"。* 将显示 **Microsoft Teams的Surface Hub。** 点击" **获取应用"** 按钮进行安装。  
3. 安装完成后，重启Surface Hub。 

> [!NOTE]
> 不要从应用商店 **一览** 页点击"启动"。

## <a name="make-teams-the-default-calling-and-meetings-application"></a>使用Teams呼叫和会议应用程序
 
有两个选项用于配置默认呼叫和会议应用程序策略： 

- **选项 1：** 通过 USB 密钥进行配置。 
- **选项 2：** 通过 MDM（如 Intune）进行配置。
 
### <a name="option-1-configure-via-usb-key"></a>选项 1：通过 USB 密钥配置 
 
可以在此下载页上找到 [程序包](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)。 为计划安装的包选择适当的一个，并复制到 USB 密钥。 使用的正确 .ppkg 文件取决于要应用的默认应用程序策略，如下所示： 

|数字  |说明  |
|---------|---------|
|0     | Skype屏幕上显示首选应用，Teams会议可用        |
|1     | Teams屏幕上显示首选应用，Skype会议可用        |
|2     | Teams"开始"屏幕上显示独占应用 (Skype应用不可用)         |
 
1. 将 USB 密钥连接到Surface Hub设备。 
2. 在 **设置** 设备上打开 Surface Hub 应用。 
3. 打开 **Surface Hub帐户管理"。**
4. 打开 **"设备管理"。** 
5. 单击 **"添加或删除预配包"。** 
6. 单击"**添加包"。**
7. 从 **下拉菜单中选择** "可移动媒体"选项。 
8. 添加之前复制到 USB 密钥的适当 <strong>TeamsRTMMode*.ppkg</strong> 包。 
9. 重启Surface Hub设备。 
10. 设备重启后，应该能够从"开始Teams启动应用，然后从日历加入会议。 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>选项 2：通过 MDM（如 Intune）进行配置 

使用以下代码通过 Intune 配置默认呼叫和会议应用程序策略。 另请参阅博客使用[Intune 部署Microsoft Teams应用Surface Hub应用。](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|设置   |值    |说明    |
|----------|---------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/properties/SurfaceHubMeetingMode        |
|数据类型 | 整数 (0-2)    |0 - Skype屏幕上的首选应用，Teams会议可用<br>1 - Teams屏幕上的首选应用，Skype会议可用<br>2 - Teams"开始"屏幕上显示 (Skype应用不可用)  |
|运营| 获取、设置        |

|设置   |值    |
|----------|---------|
|路径      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|数据类型 | string - 将 string 设置为Teams ID 作为 **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe！Teams** |
|运营| 获取、设置        |

重启Surface Hub设备。 设备重启后，应该能够从"开始Teams启动应用，然后从日历加入会议。