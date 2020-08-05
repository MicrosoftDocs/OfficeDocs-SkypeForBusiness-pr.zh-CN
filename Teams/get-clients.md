---
title: 获取 Microsoft Teams 的客户端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用支持 Microsoft Teams 的各种客户端，包括 Web、桌面（Windows 和 Mac）和移动（Android 和 iOS）。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d19e7b997a5972d3b3eb9b28d89b3e1b06359889
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552340"
---
# <a name="get-clients-for-microsoft-teams"></a>获取 Microsoft Teams 的客户端 


支持 Microsoft Teams 的客户端包括桌面（Windows、Mac 和 Linux）、Web 和移动设备（Android 和 iOS）。 这些客户端都要求有活动的 Internet 连接，不支持脱机模式。

> [!NOTE]
> 自 2018 年 11 月 29 日起，用户将不再能够使用 Microsoft Store 提供的 Microsoft Teams for Windows 10 S（预览版）应用。 现在，可以在运行 Windows 10 S 模式的设备上下载并安装 Teams 桌面客户端。 若要下载桌面客户端，请转到 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)。 Teams 桌面客户端的 MSI 内部版本尚不适用于运行 Windows 10 S 模式的设备。
>
> 有关 Windows 10 S 模式的详细信息，请参阅 [Windows 10 S 模式简介](https://www.microsoft.com/windows/s-mode)。 

## <a name="desktop-client"></a>桌面客户端

> [!TIP]
> 观看以下会话以了解 Windows 桌面客户端的优势，如何规划它，以及如何部署它：[Teams Windows 桌面客户端](https://aka.ms/teams-clients)

Microsoft 团队桌面客户端是独立的应用程序，也[可在适用于企业的 Microsoft 365 应用中使用](https://docs.microsoft.com/deployoffice/teams-install)。 团队可用于32位和64位版本的 Windows (8.1 或更高版本) 和 Windows Server (2012 R2 或更高版本) ，以及格式 (的 macOS 和 Linux) `.deb` `.rpm` 。 在 Windows 上，Teams 需要 .NET Framework 4.5 或更高版本；如果没有，Teams 安装程序将为你安装。 在 Linux 上，程序包管理器（例如 `apt` 和 `yum`）将尝试为你安装任何要求。 但是，如果没有，则在 Linux 上安装 Teams 前，你将需要安装任何报告的要求。

桌面客户端为团队会议、群组通话和专线一对一呼叫提供实时通信支持（音频、视频和内容共享）。

如果最终用户有合适的本地权限（在 PC 上安装 Teams 客户端不需要管理权限，但在 Mac 上需要），可以直接从 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 下载并安装桌面客户端。

> [!NOTE]
> 有关在 Chromebook 上安装团队的更多详细信息，请参阅[如何在 Chromebook 上安装和运行 Microsoft Office](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)。

IT 管理员可以选择其首选方法将安装文件分发到其组织中的计算机上。 一些示例包括 Microsoft Endpoint Configuration Manager (Windows) 或 Jamf Pro (macOS)。 要获取用于 Windows 分发的 MSI 包，请参阅[使用 MSI 安装 Microsoft Teams](msi-deployment.md)。  

> [!NOTE]
> 通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。

### <a name="windows"></a>Windows

适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。

> [!NOTE]
> 安装的 Windows 和 Office 的体系结构不限制 Microsoft Teams 的体系结构（32 位和 64 位）。

Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。 部署到用户的本地配置文件后，无需提升的权限即可安装客户端。 Windows 客户端会利用以下位置：

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。 可以指示用户忽略此消息，因为即使忽略此警告，也可以进行呼叫。

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> 即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。 将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。

如果你想要防止团队在用户第一次从团队发出呼叫时提示用户创建防火墙规则，请使用以下[示例 PowerShell 脚本-入站防火墙规则](#sample-powershell-script---inbound-firewall-rule)。 

### <a name="mac"></a>Mac

Mac 用户可以使用 macOS 计算机的 PKG 安装文件安装 Teams。 安装 Mac 客户端需要管理访问权限。 将 macOS 客户端安装到 /Applications 文件夹中。

#### <a name="install-teams-by-using-the-pkg-file"></a>使用 PKG 文件安装 Teams

1. 在 **Mac** 下的 [Teams下载页面](https://teams.microsoft.com/downloads)中，单击 **“下载”**。
2. 双击 PKG 文件。
3. 按照安装向导的说明完成安装。
4. Teams 将安装到 /Applications 文件夹中。 它是计算机范围内的安装。

> [!NOTE]
> 安装期间，PKG 将提示输入管理员凭据。 无论用户是否为管理员，都需要输入管理员凭据。

如果用户当前有 Teams 的 DMG 安装，并且想要将其替换为 PKG 安装，则用户应：

1. 退出 Teams 应用。
2. 卸载 Teams 应用。
3. 安装 PKG 文件。

IT 管理员可以使用 Teams 的托管部署将安装文件分发到其组织中的所有 Mac，例如 Jamf Pro。

> [!NOTE]
> 如果安装 PKG 时遇到问题，请告诉我们。 在本文末尾的 **“反馈”** 部分中，单击 **“产品反馈”**。

### <a name="linux"></a>Linux

用户将能够以 `.deb` 和 `.rpm` 格式安装本机 Linux 程序包。
安装 DEB 包或 RPM 程序包将自动安装程序包存储库。
- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams` 

使用系统的程序包管理器启用自动更新的签名密钥将自动安装。 但是，也可以在以下位置找到它：(https://packages.microsoft.com/keys/microsoft.asc). Microsoft Teams 每月发布一次，并且如果正确安装了存储库，则系统程序包管理器应按照与系统中其他程序包相同的方式处理自动更新。

> [!NOTE] 
> 如果发现 Bug，请使用客户端中的 `Report a Problem` 进行提交。 对于已知问题，请参阅[组织中的支持团队](Known-issues.md)。
> 对于适用于 Linux 的 Teams 支持，可以使用 [Microsoft 问答上的 Linux 论坛支持频道](https://docs.microsoft.com/answers/topics/teams.html)。 发布问题时，请务必使用 `teams-linux` 标记。 

#### <a name="install-teams-using-deb-package"></a>使用 DEB 程序包安装团队

1. 从 https://aka.ms/getteams 下载该程序包。
2. 使用以下方式之一进行安装：  
    - 打开相关的程序包管理工具，完成自助式 Linux 应用安装过程。
    - 或者，如果你喜欢“终端”，请键入：`sudo apt install **teams download file**`

可以通过“活动”启动团队，也可以通过键入 `teams` 通过“终端”启动 Teams。 

#### <a name="install-teams-using-rpm-package"></a>使用 RPM 程序包安装团队

1. 从 https://aka.ms/getteams 下载该程序包。
2. 使用以下方式之一进行安装：
    - 打开相关的程序包管理工具，完成自助式 Linux 应用安装过程。
    - 或者，如果你喜欢“终端”，请键入：`sudo yum install **teams download file**`

可以通过“活动”启动团队，也可以通过键入 `teams` 通过“终端”启动 Teams。

#### <a name="install-manually-from-the-command-line"></a>从命令行手动安装

在 Debian 和 Ubuntu 分发上手动安装：

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

在基于 RHEL、Fedora 和 CentOS 的分发上手动安装：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

或者，使用 yum 代替 dnf：

```bash
yum check-update
sudo yum install teams
```

在基于 openSUSE 的分发上手动安装：

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>Web 客户端 

Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是具有完整功能的客户端，可以从各种浏览器使用该客户端。 Web 客户端使用 webRTC 支持通话和会议，因此在 Web 浏览器中运行 Teams 不需要插件或进行下载。 必须配置浏览器以允许第三方 Cookie。 

[!INCLUDE [browser-support](includes/browser-support.md)]

Web 客户端在连接到 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) 时执行浏览器版本检测。 如果检测到不支持的浏览器版本，它将阻止对 Web 界面的访问，并建议用户下载桌面客户端或移动应用。

## <a name="mobile-clients"></a>移动客户端

Microsoft Teams 移动应用适用于 Android 和 iOS，适合参与基于聊天的对话的忙碌用户，允许进行点对点音频呼叫。 对于移动应用，请访问 Google Play 和 Apple App Store 的相关移动应用商店。 Windows Phone 应用已于 2018 年 7 月 20 日停用，可能无法正常运行。 

以下是在中国[获取 Android 版 Teams](get-teams-android-in-china.md) 的方法。 

Microsoft Teams 移动应用的支持移动平台如下：

-   **Android**：支持仅限于 Android 的最后四个主要版本。 新的 Android 主要版本发布后，将正式支持新版本和前三个版本。

-   **iOS**：支持仅限于 iOS 的两个最新主要版本。 新的 iOS 主要版本发布后，将正式支持 iOS 新版本和前一版本。

> [!NOTE]
> 必须向公众提供移动版本，Teams 才能按预期工作。

移动应用仅通过各自移动平台的应用商店进行分发和更新。 Microsoft 不支持通过 MDM 或侧加载来分发移动应用。 在支持的移动平台上安装移动应用后，将支持 Teams 移动应用本身，前提是该版本是 3 个月内的最新版本。


| | | |
|---------|---------|---------|
|![描述决策点的图标](media/Get_clients_for_Microsoft_Teams_image4.png)      |决策点         |是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？         |
|![描述后续步骤的图标](media/Get_clients_for_Microsoft_Teams_image5.png)     |后续步骤         |如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。 注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。         |

## <a name="client-update-management"></a>客户端更新管理

当前，Microsoft Teams 服务会自动更新客户端，无需 IT 管理员干预。 如果有更新，客户端将自动下载更新，当应用空闲一段时间后，将开始执行更新过程。

## <a name="client-side-configurations"></a>客户端配置

当前，未提供支持的选项来通过租户管理、PowerShell、组策略对象或注册表配置客户端。

## <a name="notification-settings"></a>通知设置

当前，未提供选项允许 IT 管理员配置客户端通知设置。 所有通知选项均由用户设置。 下图概括显示了默认客户端设置。

![“通知设置”屏幕截图。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a>PowerShell 脚本示例-入站防火墙规则

需要在提升的管理员帐户上下文中的客户端计算机上运行的此示例脚本将为 c:\users 中找到的每个用户文件夹创建新的入站防火墙规则。 Teams 找到此规则后，当用户通过 Teams 进行首次呼叫时，将阻止 Teams 应用程序提示用户创建防火墙规则。 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
