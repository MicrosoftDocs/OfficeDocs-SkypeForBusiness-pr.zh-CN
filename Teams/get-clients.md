---
title: 获取 Microsoft Teams 的客户端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/27/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara; vichau
localization_priority: Normal
description: 了解如何使用支持 Microsoft Teams 的各种客户端，包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 579bc0290c8375adf23a17aa8121fb7a8d363718
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
<a name="get-clients-for-microsoft-teams"></a>获取 Microsoft Teams 的客户端 
===========================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

支持 Microsoft Teams 的客户端包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。 这些客户端都要求有活动的 Internet 连接，不支持脱机模式。

<a name="web-client"></a>Web 客户端 
----------

Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是完整、 功能的客户端可以从多个浏览器使用。 Web 客户端通过使用 webRTC，因此没有任何插件或下载 web 浏览器中运行团队所必需的支持电话和会议。 浏览器必须配置为允许使用第三方 cookie。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web 客户端执行时连接到的浏览器版本检测[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)如果检测到不受支持的浏览器版本，则它将阻止对 web 接口的访问，并建议用户下载桌面客户端或移动应用程序。

<a name="desktop-client"></a>桌面客户端
--------------

Microsoft 小组台式客户机是一个独立的应用程序和当前不属于办公室专业人员加上。 团队是可用于 Windows （7 +）、 32 位和 64 位版本和 MacOS （10.10 +）。 在 Windows 上，团队需要.NET framework 4.5 或更高版本;提供团队安装程序将为您安装它，如果您没有使用它。 

桌面客户端提供团队会议，组呼叫，和私人一对一调用 （音频、 视频和内容共享） 的实时通信支持。

可以下载并安装的最终用户直接从桌面客户机[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)他们如果有合适的本地权限 （管理员权限在一台 PC 上安装团队客户端不需要，但需要在 Mac 上）。

IT 管理员可以选择其首选方法将安装文件分发到其组织中的计算机上，例如 System Center Configuration Manager (Windows) 或 Casper Suite (MacOS)。 若要获取 Windows 的 MSI 程序包分发，请参阅[安装 Microsoft 小组使用 MSI](msi-deployment.md)。

> [!NOTE]
> 通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。


#### <a name="windows"></a>Windows

适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。 该体系结构应匹配操作系统的体系结构（联机下载默认的体系结构）。



> [!NOTE]
> 安装的 Office 的体系结构不限制 Microsoft Teams 的体系结构（32 位和 64 位）。

Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。 部署到用户的本地配置文件后，无需提升的权限即可安装客户端。 Windows 客户端安装在以下位置：

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。 可以指示用户忽略此消息，因为即使忽略此警告，也可以进行呼叫。

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> 即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。 将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。

#### <a name="mac"></a>Mac

Microsoft 还提供适用于 Mac OSX 计算机的 DMG 安装文件。 要安装 Mac 客户端，需要管理权限。 Mac OSX 客户端安装到 /Applications 文件夹中。


<a name="mobile-clients"></a>移动客户端
--------------

Microsoft Teams 移动应用适用于 Android、iOS 和 Windows Phones，适合参与基于聊天的对话的忙碌用户，允许进行点对点音频呼叫。 对于移动应用，请访问 Google Play、Apple App Store 和 Microsoft 商店的相关移动应用商店。

Microsoft Teams 移动应用的支持移动平台如下：

-   **Android**：4.4 或更高版本

-   **iOS**：10.0 或更高版本

-   **Windows Phone**：Windows 10 移动版

移动应用仅通过各个移动平台的应用商店分发和更新，不可通过 MDM（移动设备管理）解决方案或侧向加载分发。


| | | |
|---------|---------|---------|
|![决策点图标。](media/Get_clients_for_Microsoft_Teams_image4.png)      |决策点         |是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？         |
|![后续步骤图标。](media/Get_clients_for_Microsoft_Teams_image5.png)     |后续步骤         |如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。 注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。         |


  <span id="_Hlk477176062" class="anchor"></span>  决策点   是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？

<a name="client-update-management"></a>客户端更新管理
------------------------

当前，Microsoft Teams 服务会自动更新客户端，无需 IT 管理员干预。 如果有更新，客户端将自动下载更新，当应用空闲一段时间后，将开始执行更新过程。

<a name="client-side-configurations"></a>客户端配置
---------------------------

当前，未提供支持的选项来通过租户管理、PowerShell、组策略对象或注册表配置客户端。

<a name="notification-settings"></a>通知设置
----------------------------

当前，未提供选项允许 IT 管理员配置客户端通知设置。 所有通知选项均由用户设置。 下图概括显示了默认客户端设置。

![“通知设置”屏幕截图。](media/Get_clients_for_Microsoft_Teams_image6.png)
