---
title: 获取 Microsoft Teams 的客户端
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: 了解如何在电脑、Mac 和移动设备上安装 Microsoft Teams 的各种客户端。
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e02013ddc158e1e64386bc22652404ec387aee1
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893551"
---
# <a name="get-clients-for-microsoft-teams"></a>获取 Microsoft Teams 的客户端

> [!TIP]
> **想要在电脑、Mac 或移动设备上安装 Teams？** 请查看[安装 Teams 客户端](https://go.microsoft.com/fwlink/?linkid=855754)。

Microsoft Teams 可以安装在电脑、Mac 和移动设备上，也可以通过 Web 浏览器访问。 大多数最终用户只需自行[安装客户端](https://go.microsoft.com/fwlink/?linkid=855754)即可开始使用 Teams。 安装 Teams 客户端后，他们只需使用用户名和密码登录即可。

如果你是 IT 专业人员，并且想要了解有关 Teams 安装体验及其要求的详细信息，请在本文中选择客户端操作系统以获取更多信息。

关于每个客户端在不同平台上的功能的详细情况，请参阅 [按平台划分的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="desktop-clients"></a>桌面客户端

Teams 桌面客户端作为独立应用程序提供，并作为以下操作系统的 [Microsoft 365 企业应用版](/deployoffice/teams-install)的一部分提供：

- 32 位和 64 位版本的 Windows（8.1 或更高版本）
- 适用于 ARM 上的 Windows 10 的 ARM64
- Windows Server（2012 R2 或更高版本）
- macOS
- Linux（采用 `.deb` 和 `.rpm` 格式）
- Chrome OS（有关详细信息，请参阅[如何在 Chromebook 上使用 Microsoft Office](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)）

如果最终用户具有适当的本地权限，则可以直接从 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 下载和安装桌面客户端。 在 Windows 电脑上安装 Teams 客户端不需要管理员权限，但在 Mac 上需要。

IT 专业人员可以选择将安装文件分发到其组织中计算机上的首选方法。 一些示例包括 Microsoft Endpoint Configuration Manager (Windows) 或 Jamf Pro (macOS)。 有关分发 Teams 的详细信息，请参阅以下内容。

- **Windows** [使用 Endpoint Configuration Manager 安装 Teams](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> 通过这些机制分发客户端仅适用于初次安装 Teams 客户端，不适用于将来的更新。 有关 Teams 更新过程的信息，请参阅 [Teams 更新过程](teams-client-update.md)。

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> 观看以下会话以了解 Windows 桌面客户端的优势，如何规划它，以及如何部署它：[Teams Windows 桌面客户端](https://aka.ms/teams-clients)

Windows 版 Teams 在 [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)、[64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)和 [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) 体系结构中提供可下载的 MSI 安装程序。 Teams 的 x86 体系结构（32 位与 64 位）与已安装的 Windows 和 Office 的体系结构无关。 建议在 64 位系统上使用 64 位版本的 Teams。

Teams 需要 .NET Framework 4.5 或更高版本。 如果未安装 .NET Framework 或更高版本，Teams 安装程序将提供供你安装。

Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。 部署到用户的本地配置文件后，无需提升的权限即可安装客户端。 Windows 客户端会利用以下位置：

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

当用户首次使用 Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。 可以指示用户忽略此消息，因为即使忽略此警告，也可以进行呼叫。

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> 即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。 将为 teams.exe 创建两个入站规则，并对 TCP 和 UDP 协议进行“允许”操作。

如果想要阻止 Teams 在用户首次从 Teams 进行呼叫时提示用户创建防火墙规则，请使用[示例脚本 - Microsoft Teams 防火墙 PowerShell 脚本](client-firewall-script.md)中的 PowerShell 脚本。

### <a name="mac"></a>[Mac](#tab/Mac)

Mac 用户可以使用 macOS 计算机的 PKG 安装文件安装 Teams。 安装 Mac 客户端需要管理访问权限。 将 macOS 客户端安装到 /Applications 文件夹中。

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

IT 专业人员可以使用托管部署解决方案（如 Jamf Pro）将 Teams 安装文件分发到其组织中的所有 Mac。

### <a name="linux"></a>[Linux](#tab/Linux)

在 Linux 上，程序包管理器（例如 `apt` 和 `yum`）将尝试为你安装任何要求。 但是，如果没有，则在 Linux 上安装 Teams 前，你将需要安装任何报告的要求。

用户将能够以 `.deb` 和 `.rpm` 格式安装本机 Linux 程序包。 安装 DEB 或 RPM 程序包将自动安装程序包存储库。

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

使用系统的程序包管理器启用自动更新的签名密钥将自动安装。 但是，也可以在以下位置找到它: <https://packages.microsoft.com/keys/microsoft.asc>。 Teams 每月发布一次，并且如果正确安装了存储库，则系统包管理器应按照与系统中其他程序包相同的方式处理自动更新。

#### <a name="install-teams-using-deb-package"></a>使用 DEB 程序包安装团队

1. 从 <https://aka.ms/getteams> 下载该程序包。
2. 使用以下方式之一进行安装：
    - 打开相关的程序包管理工具，完成自助式 Linux 应用安装过程。
    - 或者，如果你喜欢“终端”，请键入：`sudo dpkg -i **teams download file**`

可以通过“活动”启动团队，也可以通过键入 `teams` 通过“终端”启动 Teams。

#### <a name="install-teams-using-rpm-package"></a>使用 RPM 程序包安装团队

1. 从 <https://aka.ms/getteams> 下载该程序包。
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

---

## <a name="mobile-clients"></a>移动客户端

Teams 移动应用适用于 Android 和 iOS，适合参与基于聊天的对话的忙碌用户，允许进行点对点音频呼叫。 对于移动应用，请访问 Google Play 和 Apple App Store 的相关移动应用商店。

Teams 移动应用支持的移动平台如下：

- **Android**：支持仅限于 Android 的最后四个主要版本。 新的 Android 主要版本发布后，将正式支持新版本和前三个版本。

- **iOS**：支持仅限于 iOS 的两个最新主要版本。 新的 iOS 主要版本发布后，将正式支持 iOS 新版本和前一版本。

> [!NOTE]
> 必须向公众提供移动版本，Teams 才能按预期工作。

移动应用仅通过各自移动平台的应用商店进行分发和更新。 Microsoft 不支持通过 MDM 或侧加载来分发移动应用。 在支持的移动平台上安装移动应用后，将支持 Teams 移动应用本身，前提是该版本是 3 个月内的最新版本。

如果你在中国，则可以从以下应用商店安装 Teams：

- **小米** <https://aka.ms/TeamsXiaomi>
- **华为** <https://aka.ms/TeamsHuawei>
- **Oppo** 在 Oppo 应用商店中搜索“Teams”
- **百度** <https://aka.ms/teams_baidu_direct_dl>

## <a name="browser-client"></a>浏览器客户端

浏览器客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是具有完整功能的客户端，可以从各种浏览器使用该客户端。 浏览器客户端支持使用 webRTC 进行呼叫和会议，因此无需插件或下载即可在浏览器中运行 Teams。 必须配置浏览器以允许第三方 Cookie。

[!INCLUDE [browser-support](includes/browser-support.md)]

浏览器客户端在连接到 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) 时执行浏览器版本检测。 如果检测到不支持的浏览器版本，它将阻止对浏览器界面的访问，并建议用户下载桌面客户端或移动应用。