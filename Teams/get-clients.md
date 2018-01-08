---
title: "获取 Microsoft Teams 的客户端"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何使用支持 Microsoft Teams 的各种客户端，包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。"
ms.openlocfilehash: 8037d765e304aa6e950fdd0b9b5ad55079ec1700
ms.sourcegitcommit: 19d7af5d60276c0a1ca3e01588b91c34a3fd0f92
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
<a name="get-clients-for-microsoft-teams"></a>获取 Microsoft Teams 的客户端 
===========================

支持 Microsoft Teams 的客户端包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。 这些客户端都要求有活动的 Internet 连接，不支持脱机模式。

<a name="web-client"></a>Web 客户端 
----------------

Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是具有完整功能的客户端，可以从各种浏览器使用该客户端。 目前，Web 客户端不支持实时通信（即，加入会议和进行一对一通话）。 此外，还必须配置浏览器以允许第三方 Cookie。 

在 Web 浏览器中运行 Teams 无需插件和下载。

Web 客户端在连接到 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) 时执行浏览器版本检测，如果检测到不支持的浏览器版本，它将阻止对 Web 界面的访问，并建议用户下载桌面客户端或移动应用。

Microsoft Teams 支持以下浏览器和版本：

-   **Edge**：12+

-   **Internet Explorer：**11+

-   **Chrome**: 51.0+

-   **Firefox**：47.0+



> [!NOTE]
> 尚不支持 Safari，但不久以后将会支持。

<a name="desktop-clients"></a>桌面客户端
------------------------

Microsoft Teams 桌面客户端是独立应用，当前不属于 Office 专业增强版。 Microsoft Teams 适用于 Windows (7+)（32 位和 64 版本）和 MacOS (10.10+)。

桌面客户端为团队会议、群组通话和专线一对一呼叫提供实时通信支持（音频、视频和内容共享）。

如果最终用户有合适的本地权限（在 PC 上安装 Teams 客户端不需要管理权限，但在 Mac 上需要），可以直接从 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 下载并安装桌面客户端。

IT 管理员可以选择其首选方法将安装文件分发到其组织中的计算机上，例如 System Center Configuration Manager (Windows) 或 Casper Suite (MacOS)。



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
