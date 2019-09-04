---
title: 获取 Microsoft Teams 的客户端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用适用于 Microsoft 团队的各种客户端, 其中包括 web、桌面 (Windows 和 Mac) 和移动设备 (Android 和 iOS)。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 646305383c8f38671c07f598bc9ff1671890d22f
ms.sourcegitcommit: 3c40bdd228ef88967cdf689100f2030f6997d9d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2019
ms.locfileid: "36715796"
---
<a name="get-clients-for-microsoft-teams"></a>获取 Microsoft Teams 的客户端 
===========================

Microsoft 团队拥有适用于桌面 (Windows 和 Mac)、web 和移动设备 (Android 和 iOS) 的客户端。 这些客户端都要求有活动的 Internet 连接，不支持脱机模式。

> [!NOTE]
> 2018年11月29日, 您将不再能够使用 microsoft Store 提供的 Microsoft Windows 10 S (预览版) 应用程序。 现在, 你可以在运行 Windows 10 S 模式的设备上下载和安装团队桌面客户端。 若要下载桌面客户端, 请[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)转到。 适用于运行 Windows 10 S 模式的设备尚不支持团队桌面客户端的 MSI 内部版本。
>
> 有关 Windows 10 S 模式的详细信息, 请参阅[windows 10 的 s 模式简介](https://www.microsoft.com/windows/s-mode)。 

<a name="desktop-client"></a>桌面客户端
--------------

> [!Tip]
> 观看以下会话, 了解 Windows 桌面客户端的优点、如何规划它以及如何部署它:[团队 Windows 桌面客户端](https://aka.ms/teams-clients)

Microsoft 团队桌面客户端是独立的应用程序, 也[可以在 Office 365 专业增强版中使用](https://docs.microsoft.com/en-us/deployoffice/teams-install)。 团队可用于两个窗口 (7 +)、32位和64位版本以及 macOS (10.10 +)。 在 Windows 上, 团队需要 .NET Framework 4.5 或更高版本;如果您没有, 团队安装程序将为您提供安装它的功能。 

桌面客户端为团队会议、群组通话和私人一对一通话提供实时通信支持 (音频、视频和内容共享)。

[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)如果最终用户拥有相应的本地权限 (在电脑上安装团队客户端, 但在 Mac 上需要管理员权限), 则最终用户可以直接下载和安装桌面客户端。

IT 管理员可以选择其首选方法将安装文件分发到其组织中的计算机, 如 System Center Configuration Manager (Windows) 或 Jamf Pro (macOS)。 若要获取适用于 Windows 分发的 MSI 程序包, 请参阅[使用 Msi 安装 Microsoft 团队](msi-deployment.md)。  

> [!NOTE]
> 通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。

### <a name="windows"></a>Windows

适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。

> [!NOTE]
> Microsoft 团队的体系结构 (32 位和64位) 对安装的 Windows 和 Office 体系结构而言不可知。

Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。 部署到用户的本地配置文件后，无需提升的权限即可安装客户端。 Windows 客户端利用以下位置:

- % LocalAppData%\\Microsoft\\团队

- % LocalAppData%\\Microsoft\\TeamsMeetingsAddin

- % AppData%\\Microsoft\\团队

- % LocalAppData%\\SquirrelTemp

用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。 系统可能会指示用户忽略此消息, 因为呼叫将正常工作, 即使消除警告时也是如此。

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> 即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。 将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。

### <a name="mac"></a>Mac

通过使用 macOS 计算机的 INSTALLER.PKG 安装文件, Mac 用户可以安装团队。 要安装 Mac 客户端，需要管理权限。 MacOS 客户端安装到/Applications 文件夹。

#### <a name="install-teams-by-using-the-pkg-file"></a>使用 INSTALLER.PKG 文件安装团队

1. 从 "[团队下载" 页面](https://teams.microsoft.com/downloads)上的 " **Mac**" 下, 单击 "**下载**"。
2. 双击 "INSTALLER.PKG" 文件。
3. 按照安装向导完成安装。
4. 团队将安装到/Applications 文件夹。 这是一种计算机范围的安装。

> [!NOTE]
> 在安装期间, INSTALLER.PKG 将提示输入管理员凭据。 用户需要输入管理员凭据, 无论用户是否为管理员。

如果用户当前具有团队的 .DMG 安装, 并且想要将其替换为 INSTALLER.PKG 安装, 用户应:

1. 退出 "团队" 应用。
2. 卸载 "团队" 应用。
3. 安装 INSTALLER.PKG 文件。

IT 管理员可以使用团队的托管部署将安装文件分发到其组织中的所有 Mac, 例如 Jamf Pro。

> [!NOTE]
> 如果您安装 INSTALLER.PKG 时遇到问题, 请告知我们。 在本文末尾的 "**反馈**" 部分中, 单击 "**产品反馈**"。

<a name="web-client"></a>Web 客户端 
----------

Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是一种完整的功能客户端, 可从各种浏览器使用。 Web 客户端通过使用 webRTC 支持呼叫和会议, 因此在 web 浏览器中不需要使用插件或下载来运行团队。 浏览器必须配置为允许第三方 cookie。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web 客户端在连接到[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)时执行浏览器版本检测。 如果检测到不受支持的浏览器版本, 它将阻止对 web 界面的访问, 并建议用户下载桌面客户端或移动应用。

<a name="mobile-clients"></a>移动客户端
--------------

Microsoft 团队移动应用适用于 Android 和 iOS, 并且适用于参与基于聊天的对话的用户和允许对等音频呼叫。 对于移动应用, 请转到相关的移动应用商店 Google Play 和 Apple App Store。 Windows Phone 应用已于2018年7月20日停用, 可能不再有效。 

Microsoft Teams 移动应用的支持移动平台如下：

-   **Android**：4.4 或更高版本

-   **iOS**：10.0 或更高版本

> [!NOTE]
> 移动版必须可供公众使用, 以便团队能够按预期工作。

移动应用仅通过相应的移动平台的应用商店进行分发和更新。 Microsoft 不支持通过 MDM 或加载方传播移动应用。 在受支持的移动平台上安装了移动应用后, 只要版本在当前版本的三个月内, 就会支持团队移动应用本身。


| | | |
|---------|---------|---------|
|![描述决策点的图标](media/Get_clients_for_Microsoft_Teams_image4.png)      |决策点         |是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？         |
|![描述后续步骤的图标](media/Get_clients_for_Microsoft_Teams_image5.png)     |后续步骤         |如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。 注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。         |

<a name="client-update-management"></a>客户端更新管理
------------------------

当前，Microsoft Teams 服务会自动更新客户端，无需 IT 管理员干预。 如果有可用更新, 客户端将自动下载更新, 并且当应用在一段时间内有 idled 时, 将开始更新过程。

<a name="client-side-configurations"></a>客户端配置
---------------------------

当前，未提供支持的选项来通过租户管理、PowerShell、组策略对象或注册表配置客户端。

<a name="notification-settings"></a>通知设置
----------------------------

当前，未提供选项允许 IT 管理员配置客户端通知设置。 所有通知选项均由用户设置。 下图概括显示了默认客户端设置。

![“通知设置”屏幕截图。](media/Get_clients_for_Microsoft_Teams_image6.png)

<a name="sample-powershell-script"></a>PowerShell 脚本示例
----------------------------

此示例脚本 (需要在已提升的管理员帐户上下文中的客户端计算机上运行) 将为在 c:\users. 中找到的每个用户文件夹创建新的入站防火墙规则。 当团队发现此规则时, 它将阻止团队应用程序在用户第一次从团队发出呼叫时提示用户创建防火墙规则。 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
