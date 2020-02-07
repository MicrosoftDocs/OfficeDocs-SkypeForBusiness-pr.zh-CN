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
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用适用于 Microsoft 团队的各种客户端，其中包括 web、桌面（Windows 和 Mac）和移动设备（Android 和 iOS）。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4abae267bf1a8c0c770eebf1c1b12018a6c7deb
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833762"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="1f2e3-103">获取 Microsoft Teams 的客户端</span><span class="sxs-lookup"><span data-stu-id="1f2e3-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="1f2e3-104">Microsoft 团队拥有适用于桌面（Windows、Mac 和 Linux）、web 和移动设备（Android 和 iOS）的客户端。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="1f2e3-105">这些客户端都要求有活动的 Internet 连接，不支持脱机模式。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2e3-106">2018年11月29日，您将不再能够使用 microsoft Store 提供的 Microsoft Windows 10 S （预览版）应用程序。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="1f2e3-107">现在，你可以在运行 Windows 10 S 模式的设备上下载和安装团队桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="1f2e3-108">若要下载桌面客户端，请[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)转到。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="1f2e3-109">适用于运行 Windows 10 S 模式的设备尚不支持团队桌面客户端的 MSI 内部版本。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="1f2e3-110">有关 Windows 10 S 模式的详细信息，请参阅[windows 10 的 s 模式简介](https://www.microsoft.com/windows/s-mode)。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="1f2e3-111">桌面客户端</span><span class="sxs-lookup"><span data-stu-id="1f2e3-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="1f2e3-112">观看以下会话，了解 Windows 桌面客户端的优点、如何规划它以及如何部署它：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="1f2e3-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="1f2e3-113">Microsoft 团队桌面客户端是独立的应用程序，也[可以在 Office 365 专业增强版中使用](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="1f2e3-114">团队可用于 Windows （7 +）、Windows Server （2012 R2 +）、32位和64位版本、macOS （10.10 +）和 Linux （"格式" 和`.deb` `.rpm` "格式"）。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-114">Teams is available for Windows (7+), Windows Server (2012 R2+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="1f2e3-115">在 Windows 上，团队需要 .NET Framework 4.5 或更高版本;如果您没有，团队安装程序将为您提供安装它的功能。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="1f2e3-116">在 Linux 上，程序包管理器（如 apt 和 yum）将尝试为你安装任何要求。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="1f2e3-117">但是，如果不是这样，则需要安装任何报告的要求，然后才能在 Linux 上安装团队。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="1f2e3-118">桌面客户端为团队会议、群组通话和私人一对一通话提供实时通信支持（音频、视频和内容共享）。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="1f2e3-119">[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)如果最终用户拥有相应的本地权限（在电脑上安装团队客户端，但在 Mac 上需要管理员权限），则最终用户可以直接下载和安装桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="1f2e3-120">IT 管理员可以选择其首选方法将安装文件分发给组织中的计算机。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="1f2e3-121">一些示例包括 Microsoft 终结点配置管理器（Windows）或 Jamf Pro （macOS）。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-121">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="1f2e3-122">若要获取适用于 Windows 分发的 MSI 程序包，请参阅[使用 Msi 安装 Microsoft 团队](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="1f2e3-123">通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="1f2e3-124">Windows</span><span class="sxs-lookup"><span data-stu-id="1f2e3-124">Windows</span></span>

<span data-ttu-id="1f2e3-125">适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2e3-126">Microsoft 团队的体系结构（32位和64位）对安装的 Windows 和 Office 体系结构而言不可知。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="1f2e3-127">Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="1f2e3-128">部署到用户的本地配置文件后，无需提升的权限即可安装客户端。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="1f2e3-129">Windows 客户端利用以下位置：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="1f2e3-130">% LocalAppData%\\Microsoft\\团队</span><span class="sxs-lookup"><span data-stu-id="1f2e3-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="1f2e3-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="1f2e3-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="1f2e3-132">% AppData%\\Microsoft\\团队</span><span class="sxs-lookup"><span data-stu-id="1f2e3-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="1f2e3-133">% LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="1f2e3-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="1f2e3-134">用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="1f2e3-135">系统可能会指示用户忽略此消息，因为呼叫将正常工作，即使消除警告时也是如此。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="1f2e3-137">即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="1f2e3-138">将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="1f2e3-139">Mac</span><span class="sxs-lookup"><span data-stu-id="1f2e3-139">Mac</span></span>

<span data-ttu-id="1f2e3-140">通过使用 macOS 计算机的 INSTALLER.PKG 安装文件，Mac 用户可以安装团队。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="1f2e3-141">要安装 Mac 客户端，需要管理权限。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="1f2e3-142">MacOS 客户端安装到/Applications 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="1f2e3-143">使用 INSTALLER.PKG 文件安装团队</span><span class="sxs-lookup"><span data-stu-id="1f2e3-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="1f2e3-144">从 "[团队下载" 页面](https://teams.microsoft.com/downloads)上的 " **Mac**" 下，单击 "**下载**"。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="1f2e3-145">双击 "INSTALLER.PKG" 文件。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="1f2e3-146">按照安装向导完成安装。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="1f2e3-147">团队将安装到/Applications 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="1f2e3-148">这是一种计算机范围的安装。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2e3-149">在安装期间，INSTALLER.PKG 将提示输入管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="1f2e3-150">用户需要输入管理员凭据，无论用户是否为管理员。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="1f2e3-151">如果用户当前具有团队的 .DMG 安装，并且想要将其替换为 INSTALLER.PKG 安装，用户应：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="1f2e3-152">退出 "团队" 应用。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="1f2e3-153">卸载 "团队" 应用。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="1f2e3-154">安装 INSTALLER.PKG 文件。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-154">Install the PKG file.</span></span>

<span data-ttu-id="1f2e3-155">IT 管理员可以使用团队的托管部署将安装文件分发到其组织中的所有 Mac，例如 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2e3-156">如果您安装 INSTALLER.PKG 时遇到问题，请告知我们。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="1f2e3-157">在本文末尾的 "**反馈**" 部分中，单击 "**产品反馈**"。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="1f2e3-158">Linux</span><span class="sxs-lookup"><span data-stu-id="1f2e3-158">Linux</span></span>

<span data-ttu-id="1f2e3-159">用户将能够安装本机 Linux 程序包`.deb`并`.rpm`设置其格式。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="1f2e3-160">安装 DEB 包或 RPM 程序包将自动安装程序包存储库</span><span class="sxs-lookup"><span data-stu-id="1f2e3-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="1f2e3-161">DEB 包`https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="1f2e3-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="1f2e3-162">转`https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="1f2e3-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="1f2e3-163">使用系统的程序包管理器启用自动更新的签名密钥将自动安装。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="1f2e3-164">但是，还可以在以下位置找到：（https://packages.microsoft.com/keys/microsoft.asc)。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="1f2e3-165">Microsoft 团队按月付费，如果存储库已正确安装，则系统程序包管理器应以与系统上其他程序包相同的方式处理自动更新。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="1f2e3-166">如果发现 bug，请使用`Report a Problem`客户端中的进行提交。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="1f2e3-167">对于已知问题，请参阅[已知问题](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="1f2e3-168">对于支持 Linux 的团队，您可以使用[Microsoft 问答中的 Linux 论坛支持频道&](https://docs.microsoft.com/answers/topics/teams.html)。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-168">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](https://docs.microsoft.com/answers/topics/teams.html).</span></span> <span data-ttu-id="1f2e3-169">请确保在发布问题`teams-linux`时使用该标记。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="1f2e3-170">使用 DEB 包程序包安装团队</span><span class="sxs-lookup"><span data-stu-id="1f2e3-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="1f2e3-171">从https://aka.ms/getteams下载程序包。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-171">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="1f2e3-172">使用下列操作之一进行安装：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-172">Install using one of the following:</span></span>  
    - <span data-ttu-id="1f2e3-173">打开相关的程序包管理工具，并浏览自行引导的 Linux 应用安装过程。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-173">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="1f2e3-174">或者，如果您喜欢终端，请键入：`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="1f2e3-174">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="1f2e3-175">你可以通过活动或通过输入`Teams`通过 "终端" 启动团队。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-175">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="1f2e3-176">使用 RPM 程序包安装团队</span><span class="sxs-lookup"><span data-stu-id="1f2e3-176">Install Teams using RPM package</span></span>

1. <span data-ttu-id="1f2e3-177">从https://aka.ms/getteams下载程序包。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-177">Download the package from https://aka.ms/getteams.</span></span>
2. <span data-ttu-id="1f2e3-178">使用下列操作之一进行安装：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-178">Install using one of the following:</span></span>
    - <span data-ttu-id="1f2e3-179">打开相关的程序包管理工具，并浏览自行引导的 Linux 应用安装过程。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-179">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="1f2e3-180">或者，如果您喜欢终端，请键入：`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="1f2e3-180">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="1f2e3-181">你可以通过活动或通过输入`Teams`通过 "终端" 启动团队。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-181">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="1f2e3-182">从命令行手动安装</span><span class="sxs-lookup"><span data-stu-id="1f2e3-182">Install manually from the command line</span></span>

<span data-ttu-id="1f2e3-183">在 Debian 和 Ubuntu 分发设备上手动安装：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-183">Install manually on Debian and Ubuntu distributions:</span></span>
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

<span data-ttu-id="1f2e3-184">在 RHEL、Fedora 和基于 CentOS 的分配上手动安装：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-184">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="1f2e3-185">或者，若要使用 yum 而不是 dnf：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-185">Alternatively, to use yum instead of dnf:</span></span>
```
yum check-update
sudo yum install teams
```

<span data-ttu-id="1f2e3-186">在基于 openSUSE 的发行版上手动安装：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-186">Install manually on openSUSE based distributions:</span></span>
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="1f2e3-187">Web 客户端</span><span class="sxs-lookup"><span data-stu-id="1f2e3-187">Web client</span></span> 

<span data-ttu-id="1f2e3-188">Web 客户端（[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)）是一种完整的功能客户端，可从各种浏览器使用。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-188">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="1f2e3-189">Web 客户端通过使用 webRTC 支持呼叫和会议，因此在 web 浏览器中不需要使用插件或下载来运行团队。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-189">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="1f2e3-190">浏览器必须配置为允许第三方 cookie。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-190">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="1f2e3-191">Web 客户端在连接到[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)时执行浏览器版本检测。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-191">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="1f2e3-192">如果检测到不受支持的浏览器版本，它将阻止对 web 界面的访问，并建议用户下载桌面客户端或移动应用。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-192">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="1f2e3-193">移动客户端</span><span class="sxs-lookup"><span data-stu-id="1f2e3-193">Mobile clients</span></span>

<span data-ttu-id="1f2e3-194">Microsoft 团队移动应用适用于 Android 和 iOS，并且适用于参与基于聊天的对话的用户和允许对等音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-194">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="1f2e3-195">对于移动应用，请转到相关的移动应用商店 Google Play 和 Apple App Store。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-195">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="1f2e3-196">Windows Phone 应用已于2018年7月20日停用，可能不再有效。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-196">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="1f2e3-197">Microsoft Teams 移动应用的支持移动平台如下：</span><span class="sxs-lookup"><span data-stu-id="1f2e3-197">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="1f2e3-198">**Android**：支持仅限于 Android 的最后四个主要版本。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-198">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="1f2e3-199">发布新的 Android 主要版本时，正式支持新版本和前三个版本。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-199">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

-   <span data-ttu-id="1f2e3-200">**iOS**：支持仅限于最新版本 iOS 的两个主要版本。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-200">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="1f2e3-201">当发布新的主要版本 iOS 时，正式支持新版本的 iOS 和早期版本。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-201">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2e3-202">移动版必须可供公众使用，以便团队能够按预期工作。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-202">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="1f2e3-203">移动应用仅通过相应的移动平台的应用商店进行分发和更新。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-203">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="1f2e3-204">Microsoft 不支持通过 MDM 或加载方传播移动应用。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-204">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="1f2e3-205">在受支持的移动平台上安装了移动应用后，只要版本在当前版本的三个月内，就会支持团队移动应用本身。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-205">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![描述决策点的图标](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="1f2e3-207">决策点</span><span class="sxs-lookup"><span data-stu-id="1f2e3-207">Decision Point</span></span>         |<span data-ttu-id="1f2e3-208">是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？</span><span class="sxs-lookup"><span data-stu-id="1f2e3-208">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![描述后续步骤的图标](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="1f2e3-210">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1f2e3-210">Next Steps</span></span>         |<span data-ttu-id="1f2e3-211">如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-211">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="1f2e3-212">注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-212">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="1f2e3-213">客户端更新管理</span><span class="sxs-lookup"><span data-stu-id="1f2e3-213">Client update management</span></span>

<span data-ttu-id="1f2e3-214">当前，Microsoft Teams 服务会自动更新客户端，无需 IT 管理员干预。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-214">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="1f2e3-215">如果有可用更新，客户端将自动下载更新，并且当应用在一段时间内有 idled 时，将开始更新过程。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-215">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="1f2e3-216">客户端配置</span><span class="sxs-lookup"><span data-stu-id="1f2e3-216">Client-side configurations</span></span>

<span data-ttu-id="1f2e3-217">当前，未提供支持的选项来通过租户管理、PowerShell、组策略对象或注册表配置客户端。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-217">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="1f2e3-218">通知设置</span><span class="sxs-lookup"><span data-stu-id="1f2e3-218">Notification settings</span></span>

<span data-ttu-id="1f2e3-219">当前，未提供选项允许 IT 管理员配置客户端通知设置。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-219">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="1f2e3-220">所有通知选项均由用户设置。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-220">All notification options are set by the user.</span></span> <span data-ttu-id="1f2e3-221">下图概括显示了默认客户端设置。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-221">The figure below outlines the default client settings.</span></span>

![“通知设置”屏幕截图。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="1f2e3-223">PowerShell 脚本示例</span><span class="sxs-lookup"><span data-stu-id="1f2e3-223">Sample PowerShell Script</span></span>

<span data-ttu-id="1f2e3-224">此示例脚本（需要在已提升的管理员帐户上下文中的客户端计算机上运行）将为在 c:\users. 中找到的每个用户文件夹创建新的入站防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-224">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="1f2e3-225">当团队发现此规则时，它将阻止团队应用程序在用户第一次从团队发出呼叫时提示用户创建防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="1f2e3-225">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

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
