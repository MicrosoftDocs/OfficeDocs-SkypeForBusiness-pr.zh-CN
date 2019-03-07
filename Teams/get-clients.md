---
title: 获取 Microsoft Teams 的客户端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用包含 web、 桌面 （Windows 和 Mac） 和 mobile 的 Microsoft 团队提供的各种客户端 （Android 和 iOS）。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32fba747deb73b7f4e2c19b96cb4c0c62b741722
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458905"
---
<a name="get-clients-for-microsoft-teams"></a>获取 Microsoft Teams 的客户端 
===========================

Microsoft 团队具有客户端适用于桌面 （Windows 和 Mac） web 和移动 （Android 和 iOS）。 这些客户端都要求有活动的 Internet 连接，不支持脱机模式。

> [!NOTE]
> 有效年 11 月 29，2018，您将不再能够使用 Microsoft 团队 Windows 10 S （预览） 应用程序，可从 Microsoft 存储。 我们建议您使用后 11 月 29 日下述本文中的团队应用程序之一。

<a name="desktop-client"></a>桌面客户端
--------------

> [!Tip]
> 观看下面的会话，若要了解有关 Windows 桌面的优势，客户端、 如何规划，以及如何将其部署：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)

Microsoft 团队桌面客户端是一个独立的应用程序和当前不是 Office 365 ProPlus 的一部分。 团队是可用于 Windows （7 +）、 32 位和 64 位版本和 macOS （10.10 +）。 在 Windows 上，团队需要.NET Framework 4.5 或更高版本;团队安装程序将自动为您进行安装，如果您没有使用它。 

桌面客户端提供实时通信 （音频、 视频以及内容共享） 的支持团队会议，组呼叫，和专用一对一呼叫。

桌面客户端可以下载并安装由最终用户直接从[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)如果拥有适当的本地权限 （管理员权限不需要在 PC 上安装团队客户端，但需要在 Mac 上）。

IT 管理员可以选择其分发到其组织，如 System Center Configuration Manager (Windows) 或 Jamf Pro (macOS) 中的计算机上安装文件的首选的方法。 若要获取 Windows 通讯组的 MSI 程序包，请参阅[安装的 Microsoft 团队使用 MSI](msi-deployment.md)。

> [!NOTE]
> 通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。

### <a name="windows"></a>Windows

适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。

> [!NOTE]
> Windows 和 Office 安装的体系结构不可知的 Microsoft 团队的体系结构 （32 位与 64 位）。

Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。 部署到用户的本地配置文件后，无需提升的权限即可安装客户端。 Windows 客户端利用在以下位置：

- %Localappdata%\\Microsoft\\团队

- %Localappdata%\\Microsoft\\TeamsMeetingsAddin

- %应用程序数据 %\\Microsoft\\团队

- %Localappdata%\\SquirrelTemp

用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。 指示用户可能由于呼叫将工作原理，即使在消除警告时忽略此消息。

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> 即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。 将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。

### <a name="mac"></a>Mac

Mac 用户可以使用 macOS 计算机软件包安装文件安装团队。 要安装 Mac 客户端，需要管理权限。 MacOS 客户端安装到/应用程序 — 文件夹中。

#### <a name="install-teams-by-using-the-pkg-file"></a>使用软件包文件安装团队

1. 从[工作组下载页面](https://teams.microsoft.com/downloads)，在**Mac**，下单击**下载**。
2. 双击软件包文件。
3. 按照安装向导以完成安装。
4. 团队将安装到/应用程序 — 文件夹中。 计算机范围安装它。

> [!NOTE]
> 安装期间，PKG 将提示管理员凭据。 用户需要输入管理员凭据，而不管用户管理员。

如果用户当前已团队的 DMG 安装，并希望将其替换为 PKG 安装，用户应：

1. 退出团队应用程序。
2. 卸载团队应用程序。
3. 安装软件包文件。

IT 管理员可以使用托管的部署团队的安装文件分发给其组织，如 Jamf Pro 中的所有 Mac。

> [!NOTE]
> 如果您遇到问题安装 PKG，让我们知道。 在本文末尾的**反馈**部分中，单击**产品反馈**。

<a name="web-client"></a>Web 客户端 
----------

Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是可从多个浏览器的完整、 职能客户端。 Web 客户端支持使用 webRTC，因此不插件或下载需要在 web 浏览器中运行团队呼叫和会议。 在浏览器必须配置为允许使用第三方 cookie。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web 客户端执行时连接到的浏览器版本检测[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)。 如果检测到不受支持的浏览器版本时，它将阻止对 web 界面访问并建议用户下载桌面客户端或移动应用程序。

<a name="mobile-clients"></a>移动客户端
--------------

Microsoft 团队移动应用程序适用于 Android 和 iOS，和适用于转上用户参与基于聊对话，允许对等音频呼叫。 对于移动应用程序，请转到相关 mobile 存储 Google 播放和 Apple App Store。 Windows Phone 应用程序已停用 2018 年 7 月 20，并可能不再有效。 

Microsoft Teams 移动应用的支持移动平台如下：

-   **Android**：4.4 或更高版本

-   **iOS**：10.0 或更高版本

> [!NOTE]
> 移动的版本必须为按预期方式工作的团队顺序公众。

移动应用仅通过各个移动平台的应用商店分发和更新，不可通过 MDM（移动设备管理）解决方案或侧向加载分发。


| | | |
|---------|---------|---------|
|![决策点图标。](media/Get_clients_for_Microsoft_Teams_image4.png)      |决策点         |是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？         |
|![后续步骤图标。](media/Get_clients_for_Microsoft_Teams_image5.png)     |后续步骤         |如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。 注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。         |

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

<a name="sample-powershell-script"></a>示例 PowerShell 脚本
----------------------------

此示例脚本，这需要提升的管理员帐户的上下文中的客户端计算机上运行，将创建新的入站的防火墙规则 c:\users 中找到的每个用户文件夹。 当团队找到此规则时，它将阻止团队中的应用程序提示用户创建防火墙规则，当用户进行来自团队其第一个呼叫。 

```
$users = Get-Childitem c:\users
foreach ($user in $users) 
{
    $Path = "c:\users\" + $user.Name + "\appdata\local\Microsoft\Teams\Current\Teams.exe"
    if (Test-Path $Path) 
    {
            $name = "teams.exe " + $user.Name
            if (!(Get-NetFirewallRule -DisplayName $name))
        {
                New-NetFirewallRule -DisplayName “teams.exe” -Direction Inbound -Profile Domain -Program $Path -Action Allow
        }
    }
}
<#
        .ABOUT THIS SCRIPT
        (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.

        Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 

        The script will create a new inbound firewall rule for each user folder found in c:\users. 

        Requires PowerShell 3.0
        
#>

```
