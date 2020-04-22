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
ms.openlocfilehash: 8a3425ca19ded72f814e8f81252b7224c2c08a42
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749490"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="00e13-103">获取 Microsoft Teams 的客户端</span><span class="sxs-lookup"><span data-stu-id="00e13-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="00e13-104">支持 Microsoft Teams 的客户端包括桌面（Windows、Mac 和 Linux）、Web 和移动设备（Android 和 iOS）。</span><span class="sxs-lookup"><span data-stu-id="00e13-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="00e13-105">这些客户端都要求有活动的 Internet 连接，不支持脱机模式。</span><span class="sxs-lookup"><span data-stu-id="00e13-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="00e13-106">自 2018 年 11 月 29 日起，用户将不再能够使用 Microsoft Store 提供的 Microsoft Teams for Windows 10 S（预览版）应用。</span><span class="sxs-lookup"><span data-stu-id="00e13-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="00e13-107">现在，可以在运行 Windows 10 S 模式的设备上下载并安装 Teams 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="00e13-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="00e13-108">若要下载桌面客户端，请转到 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)。</span><span class="sxs-lookup"><span data-stu-id="00e13-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="00e13-109">Teams 桌面客户端的 MSI 内部版本尚不适用于运行 Windows 10 S 模式的设备。</span><span class="sxs-lookup"><span data-stu-id="00e13-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="00e13-110">有关 Windows 10 S 模式的详细信息，请参阅 [Windows 10 S 模式简介](https://www.microsoft.com/windows/s-mode)。</span><span class="sxs-lookup"><span data-stu-id="00e13-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="00e13-111">桌面客户端</span><span class="sxs-lookup"><span data-stu-id="00e13-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="00e13-112">观看以下会话以了解 Windows 桌面客户端的优势，如何规划它，以及如何部署它：[Teams Windows 桌面客户端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="00e13-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="00e13-113">Microsoft Teams 桌面客户端是独立的应用程序，也[可以在 Office 365 专业增强版中使用](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="00e13-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="00e13-114">Teams 可用于 32 位和 64 位版本的 Windows（8.1 或更高版本）和 Windows Server（2012 R2 或更高版本），以及 macOS（10.10 或更高版本）和 Linux（`.deb` 和 `.rpm` 格式）。</span><span class="sxs-lookup"><span data-stu-id="00e13-114">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later) and Windows Server (2012 R2 or later), as well as for macOS (10.10 or later) and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="00e13-115">在 Windows 上，Teams 需要 .NET Framework 4.5 或更高版本；如果没有，Teams 安装程序将为你安装。</span><span class="sxs-lookup"><span data-stu-id="00e13-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="00e13-116">在 Linux 上，程序包管理器（例如 `apt` 和 `yum`）将尝试为你安装任何要求。</span><span class="sxs-lookup"><span data-stu-id="00e13-116">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="00e13-117">但是，如果没有，则在 Linux 上安装 Teams 前，你将需要安装任何报告的要求。</span><span class="sxs-lookup"><span data-stu-id="00e13-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="00e13-118">桌面客户端为团队会议、群组通话和专线一对一呼叫提供实时通信支持（音频、视频和内容共享）。</span><span class="sxs-lookup"><span data-stu-id="00e13-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="00e13-119">如果最终用户有合适的本地权限（在 PC 上安装 Teams 客户端不需要管理权限，但在 Mac 上需要），可以直接从 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 下载并安装桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="00e13-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="00e13-120">有关在 Chromebook 上安装团队的更多详细信息，请参阅[如何在 Chromebook 上安装和运行 Microsoft Office](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)。</span><span class="sxs-lookup"><span data-stu-id="00e13-120">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="00e13-121">IT 管理员可以选择其首选方法将安装文件分发到其组织中的计算机上。</span><span class="sxs-lookup"><span data-stu-id="00e13-121">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="00e13-122">一些示例包括 Microsoft Endpoint Configuration Manager (Windows) 或 Jamf Pro (macOS)。</span><span class="sxs-lookup"><span data-stu-id="00e13-122">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="00e13-123">要获取用于 Windows 分发的 MSI 包，请参阅[使用 MSI 安装 Microsoft Teams](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="00e13-123">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="00e13-124">通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。</span><span class="sxs-lookup"><span data-stu-id="00e13-124">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="00e13-125">Windows</span><span class="sxs-lookup"><span data-stu-id="00e13-125">Windows</span></span>

<span data-ttu-id="00e13-126">适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。</span><span class="sxs-lookup"><span data-stu-id="00e13-126">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="00e13-127">安装的 Windows 和 Office 的体系结构不限制 Microsoft Teams 的体系结构（32 位和 64 位）。</span><span class="sxs-lookup"><span data-stu-id="00e13-127">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="00e13-128">Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="00e13-128">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="00e13-129">部署到用户的本地配置文件后，无需提升的权限即可安装客户端。</span><span class="sxs-lookup"><span data-stu-id="00e13-129">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="00e13-130">Windows 客户端会利用以下位置：</span><span class="sxs-lookup"><span data-stu-id="00e13-130">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="00e13-131">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="00e13-131">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="00e13-132">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="00e13-132">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="00e13-133">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="00e13-133">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="00e13-134">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="00e13-134">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="00e13-135">用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。</span><span class="sxs-lookup"><span data-stu-id="00e13-135">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="00e13-136">可以指示用户忽略此消息，因为即使忽略此警告，也可以进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="00e13-136">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="00e13-138">即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="00e13-138">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="00e13-139">将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。</span><span class="sxs-lookup"><span data-stu-id="00e13-139">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="00e13-140">如果你想要防止团队在用户第一次从团队发出呼叫时提示用户创建防火墙规则，请使用以下[示例 PowerShell 脚本-入站防火墙规则](#sample-powershell-script---inbound-firewall-rule)。</span><span class="sxs-lookup"><span data-stu-id="00e13-140">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span> 

### <a name="mac"></a><span data-ttu-id="00e13-141">Mac</span><span class="sxs-lookup"><span data-stu-id="00e13-141">Mac</span></span>

<span data-ttu-id="00e13-142">Mac 用户可以使用 macOS 计算机的 PKG 安装文件安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="00e13-142">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="00e13-143">安装 Mac 客户端需要管理访问权限。</span><span class="sxs-lookup"><span data-stu-id="00e13-143">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="00e13-144">将 macOS 客户端安装到 /Applications 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="00e13-144">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="00e13-145">使用 PKG 文件安装 Teams</span><span class="sxs-lookup"><span data-stu-id="00e13-145">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="00e13-146">在 **Mac** 下的 [Teams下载页面](https://teams.microsoft.com/downloads)中，单击 **“下载”**。</span><span class="sxs-lookup"><span data-stu-id="00e13-146">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="00e13-147">双击 PKG 文件。</span><span class="sxs-lookup"><span data-stu-id="00e13-147">Double click the PKG file.</span></span>
3. <span data-ttu-id="00e13-148">按照安装向导的说明完成安装。</span><span class="sxs-lookup"><span data-stu-id="00e13-148">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="00e13-149">Teams 将安装到 /Applications 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="00e13-149">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="00e13-150">它是计算机范围内的安装。</span><span class="sxs-lookup"><span data-stu-id="00e13-150">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="00e13-151">安装期间，PKG 将提示输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="00e13-151">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="00e13-152">无论用户是否为管理员，都需要输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="00e13-152">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="00e13-153">如果用户当前有 Teams 的 DMG 安装，并且想要将其替换为 PKG 安装，则用户应：</span><span class="sxs-lookup"><span data-stu-id="00e13-153">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="00e13-154">退出 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="00e13-154">Exit the Teams app.</span></span>
2. <span data-ttu-id="00e13-155">卸载 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="00e13-155">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="00e13-156">安装 PKG 文件。</span><span class="sxs-lookup"><span data-stu-id="00e13-156">Install the PKG file.</span></span>

<span data-ttu-id="00e13-157">IT 管理员可以使用 Teams 的托管部署将安装文件分发到其组织中的所有 Mac，例如 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="00e13-157">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="00e13-158">如果安装 PKG 时遇到问题，请告诉我们。</span><span class="sxs-lookup"><span data-stu-id="00e13-158">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="00e13-159">在本文末尾的 **“反馈”** 部分中，单击 **“产品反馈”**。</span><span class="sxs-lookup"><span data-stu-id="00e13-159">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="00e13-160">Linux</span><span class="sxs-lookup"><span data-stu-id="00e13-160">Linux</span></span>

<span data-ttu-id="00e13-161">用户将能够以 `.deb` 和 `.rpm` 格式安装本机 Linux 程序包。</span><span class="sxs-lookup"><span data-stu-id="00e13-161">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="00e13-162">安装 DEB 包或 RPM 程序包将自动安装程序包存储库。</span><span class="sxs-lookup"><span data-stu-id="00e13-162">Installing the DEB or RPM package will automatically install the package repository.</span></span>
- <span data-ttu-id="00e13-163">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="00e13-163">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="00e13-164">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="00e13-164">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="00e13-165">使用系统的程序包管理器启用自动更新的签名密钥将自动安装。</span><span class="sxs-lookup"><span data-stu-id="00e13-165">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="00e13-166">但是，也可以在以下位置找到它：(https://packages.microsoft.com/keys/microsoft.asc).</span><span class="sxs-lookup"><span data-stu-id="00e13-166">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="00e13-167">Microsoft Teams 每月发布一次，并且如果正确安装了存储库，则系统程序包管理器应按照与系统中其他程序包相同的方式处理自动更新。</span><span class="sxs-lookup"><span data-stu-id="00e13-167">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="00e13-168">如果发现 Bug，请使用客户端中的 `Report a Problem` 进行提交。</span><span class="sxs-lookup"><span data-stu-id="00e13-168">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="00e13-169">有关已知问题，请参阅[已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="00e13-169">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="00e13-170">对于适用于 Linux 的 Teams 支持，可以使用 [Microsoft 问答上的 Linux 论坛支持频道](https://docs.microsoft.com/answers/topics/teams.html)。</span><span class="sxs-lookup"><span data-stu-id="00e13-170">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="00e13-171">发布问题时，请务必使用 `teams-linux` 标记。</span><span class="sxs-lookup"><span data-stu-id="00e13-171">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="00e13-172">使用 DEB 程序包安装团队</span><span class="sxs-lookup"><span data-stu-id="00e13-172">Install Teams using DEB package</span></span>

1. <span data-ttu-id="00e13-173">从 https://aka.ms/getteams 下载该程序包。</span><span class="sxs-lookup"><span data-stu-id="00e13-173">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="00e13-174">使用以下方式之一进行安装：</span><span class="sxs-lookup"><span data-stu-id="00e13-174">Install using one of the following:</span></span>  
    - <span data-ttu-id="00e13-175">打开相关的程序包管理工具，完成自助式 Linux 应用安装过程。</span><span class="sxs-lookup"><span data-stu-id="00e13-175">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="00e13-176">或者，如果你喜欢“终端”，请键入：`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="00e13-176">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="00e13-177">可以通过“活动”启动团队，也可以通过键入 `Teams` 通过“终端”启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="00e13-177">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="00e13-178">使用 RPM 程序包安装团队</span><span class="sxs-lookup"><span data-stu-id="00e13-178">Install Teams using RPM package</span></span>

1. <span data-ttu-id="00e13-179">从 https://aka.ms/getteams 下载该程序包。</span><span class="sxs-lookup"><span data-stu-id="00e13-179">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="00e13-180">使用以下方式之一进行安装：</span><span class="sxs-lookup"><span data-stu-id="00e13-180">Install using one of the following:</span></span>
    - <span data-ttu-id="00e13-181">打开相关的程序包管理工具，完成自助式 Linux 应用安装过程。</span><span class="sxs-lookup"><span data-stu-id="00e13-181">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="00e13-182">或者，如果你喜欢“终端”，请键入：`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="00e13-182">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="00e13-183">可以通过“活动”启动团队，也可以通过键入 `Teams` 通过“终端”启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="00e13-183">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="00e13-184">从命令行手动安装</span><span class="sxs-lookup"><span data-stu-id="00e13-184">Install manually from the command line</span></span>

<span data-ttu-id="00e13-185">在 Debian 和 Ubuntu 分发上手动安装：</span><span class="sxs-lookup"><span data-stu-id="00e13-185">Install manually on Debian and Ubuntu distributions:</span></span>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="00e13-186">在基于 RHEL、Fedora 和 CentOS 的分发上手动安装：</span><span class="sxs-lookup"><span data-stu-id="00e13-186">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="00e13-187">或者，使用 yum 代替 dnf：</span><span class="sxs-lookup"><span data-stu-id="00e13-187">Alternatively, to use yum instead of dnf:</span></span>
```
yum check-update
sudo yum install teams
```

<span data-ttu-id="00e13-188">在基于 openSUSE 的分发上手动安装：</span><span class="sxs-lookup"><span data-stu-id="00e13-188">Install manually on openSUSE based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="00e13-189">Web 客户端</span><span class="sxs-lookup"><span data-stu-id="00e13-189">Web client</span></span> 

<span data-ttu-id="00e13-190">Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是具有完整功能的客户端，可以从各种浏览器使用该客户端。</span><span class="sxs-lookup"><span data-stu-id="00e13-190">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="00e13-191">Web 客户端使用 webRTC 支持通话和会议，因此在 Web 浏览器中运行 Teams 不需要插件或进行下载。</span><span class="sxs-lookup"><span data-stu-id="00e13-191">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="00e13-192">必须配置浏览器以允许第三方 Cookie。</span><span class="sxs-lookup"><span data-stu-id="00e13-192">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="00e13-193">Web 客户端在连接到 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) 时执行浏览器版本检测。</span><span class="sxs-lookup"><span data-stu-id="00e13-193">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="00e13-194">如果检测到不支持的浏览器版本，它将阻止对 Web 界面的访问，并建议用户下载桌面客户端或移动应用。</span><span class="sxs-lookup"><span data-stu-id="00e13-194">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="00e13-195">移动客户端</span><span class="sxs-lookup"><span data-stu-id="00e13-195">Mobile clients</span></span>

<span data-ttu-id="00e13-196">Microsoft Teams 移动应用适用于 Android 和 iOS，适合参与基于聊天的对话的忙碌用户，允许进行点对点音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="00e13-196">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="00e13-197">对于移动应用，请访问 Google Play 和 Apple App Store 的相关移动应用商店。</span><span class="sxs-lookup"><span data-stu-id="00e13-197">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="00e13-198">Windows Phone 应用已于 2018 年 7 月 20 日停用，可能无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="00e13-198">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="00e13-199">以下是在中国[获取 Android 版 Teams](get-teams-android-in-china.md) 的方法。</span><span class="sxs-lookup"><span data-stu-id="00e13-199">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span> 

<span data-ttu-id="00e13-200">Microsoft Teams 移动应用的支持移动平台如下：</span><span class="sxs-lookup"><span data-stu-id="00e13-200">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="00e13-201">**Android**：支持仅限于 Android 的最后四个主要版本。</span><span class="sxs-lookup"><span data-stu-id="00e13-201">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="00e13-202">新的 Android 主要版本发布后，将正式支持新版本和前三个版本。</span><span class="sxs-lookup"><span data-stu-id="00e13-202">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="00e13-203">**iOS**：支持仅限于 iOS 的两个最新主要版本。</span><span class="sxs-lookup"><span data-stu-id="00e13-203">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="00e13-204">新的 iOS 主要版本发布后，将正式支持 iOS 新版本和前一版本。</span><span class="sxs-lookup"><span data-stu-id="00e13-204">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="00e13-205">必须向公众提供移动版本，Teams 才能按预期工作。</span><span class="sxs-lookup"><span data-stu-id="00e13-205">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="00e13-206">移动应用仅通过各自移动平台的应用商店进行分发和更新。</span><span class="sxs-lookup"><span data-stu-id="00e13-206">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="00e13-207">Microsoft 不支持通过 MDM 或侧加载来分发移动应用。</span><span class="sxs-lookup"><span data-stu-id="00e13-207">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="00e13-208">在支持的移动平台上安装移动应用后，将支持 Teams 移动应用本身，前提是该版本是 3 个月内的最新版本。</span><span class="sxs-lookup"><span data-stu-id="00e13-208">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![描述决策点的图标](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="00e13-210">决策点</span><span class="sxs-lookup"><span data-stu-id="00e13-210">Decision Point</span></span>         |<span data-ttu-id="00e13-211">是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？</span><span class="sxs-lookup"><span data-stu-id="00e13-211">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![描述后续步骤的图标](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="00e13-213">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00e13-213">Next Steps</span></span>         |<span data-ttu-id="00e13-214">如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。</span><span class="sxs-lookup"><span data-stu-id="00e13-214">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="00e13-215">注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。</span><span class="sxs-lookup"><span data-stu-id="00e13-215">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="00e13-216">客户端更新管理</span><span class="sxs-lookup"><span data-stu-id="00e13-216">Client update management</span></span>

<span data-ttu-id="00e13-217">当前，Microsoft Teams 服务会自动更新客户端，无需 IT 管理员干预。</span><span class="sxs-lookup"><span data-stu-id="00e13-217">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="00e13-218">如果有更新，客户端将自动下载更新，当应用空闲一段时间后，将开始执行更新过程。</span><span class="sxs-lookup"><span data-stu-id="00e13-218">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="00e13-219">客户端配置</span><span class="sxs-lookup"><span data-stu-id="00e13-219">Client-side configurations</span></span>

<span data-ttu-id="00e13-220">当前，未提供支持的选项来通过租户管理、PowerShell、组策略对象或注册表配置客户端。</span><span class="sxs-lookup"><span data-stu-id="00e13-220">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="00e13-221">通知设置</span><span class="sxs-lookup"><span data-stu-id="00e13-221">Notification settings</span></span>

<span data-ttu-id="00e13-222">当前，未提供选项允许 IT 管理员配置客户端通知设置。</span><span class="sxs-lookup"><span data-stu-id="00e13-222">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="00e13-223">所有通知选项均由用户设置。</span><span class="sxs-lookup"><span data-stu-id="00e13-223">All notification options are set by the user.</span></span> <span data-ttu-id="00e13-224">下图概括显示了默认客户端设置。</span><span class="sxs-lookup"><span data-stu-id="00e13-224">The figure below outlines the default client settings.</span></span>

![“通知设置”屏幕截图。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="00e13-226">PowerShell 脚本示例-入站防火墙规则</span><span class="sxs-lookup"><span data-stu-id="00e13-226">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="00e13-227">需要在提升的管理员帐户上下文中的客户端计算机上运行的此示例脚本将为 c:\users 中找到的每个用户文件夹创建新的入站防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="00e13-227">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="00e13-228">Teams 找到此规则后，当用户通过 Teams 进行首次呼叫时，将阻止 Teams 应用程序提示用户创建防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="00e13-228">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
