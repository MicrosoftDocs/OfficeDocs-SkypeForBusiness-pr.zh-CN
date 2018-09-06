---
title: 获取 Microsoft Teams 的客户端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/05/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: vichau, majafry
localization_priority: Priority
description: 了解如何使用支持 Microsoft Teams 的各种客户端，包括 Web、桌面（Windows 和 Mac）和移动（Android、iOS 和 Windows Phone）。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: d662775f700586c3811aabce329f065652630c01
ms.sourcegitcommit: 309941f79f0f8dbcbce620fe90e9f73dd0bcfcbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23289904"
---
<a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="8255e-103">获取 Microsoft Teams 的客户端</span><span class="sxs-lookup"><span data-stu-id="8255e-103">Get clients for Microsoft Teams</span></span> 
===========================

<span data-ttu-id="8255e-104">Microsoft 团队具有客户端适用于桌面 （Windows 和 Mac） web 和移动 （Android、 iOS 和 Windows Phone）。</span><span class="sxs-lookup"><span data-stu-id="8255e-104">Microsoft Teams has clients available for desktop (Windows and Mac), web, and mobile (Android,  iOS, and Windows Phone).</span></span> <span data-ttu-id="8255e-105">这些客户端都要求有活动的 Internet 连接，不支持脱机模式。</span><span class="sxs-lookup"><span data-stu-id="8255e-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

<a name="desktop-client"></a><span data-ttu-id="8255e-106">桌面客户端</span><span class="sxs-lookup"><span data-stu-id="8255e-106">Desktop client</span></span>
--------------

<span data-ttu-id="8255e-107">Microsoft 团队桌面客户端是一个独立的应用程序和当前不是 Office 365 ProPlus 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8255e-107">The Microsoft Teams desktop client is a standalone application and currently not part of Office 365 ProPlus.</span></span> <span data-ttu-id="8255e-108">团队是可用于 Windows （7 +）、 32 位和 64 位版本和 macOS （10.10 +）。</span><span class="sxs-lookup"><span data-stu-id="8255e-108">Teams is available for both Windows (7+), both 32-bit and 64-bit versions, and macOS (10.10+).</span></span> <span data-ttu-id="8255e-109">在 Windows 上，团队需要.NET framework 4.5 或更高版本;团队安装程序将自动为您进行安装，如果您没有使用它。</span><span class="sxs-lookup"><span data-stu-id="8255e-109">On Windows, Teams requires .NET framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> 

<span data-ttu-id="8255e-110">桌面客户端提供实时通信 （音频、 视频以及内容共享） 的支持团队会议，组呼叫，和专用一对一呼叫。</span><span class="sxs-lookup"><span data-stu-id="8255e-110">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="8255e-111">桌面客户端可以下载并安装由最终用户直接从[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)如果拥有适当的本地权限 （管理员权限不需要在 PC 上安装团队客户端，但需要在 Mac 上）。</span><span class="sxs-lookup"><span data-stu-id="8255e-111">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="8255e-112">IT 管理员可以选择其分发到其组织，如 System Center Configuration Manager (Windows) 或 Jamf Pro (macOS) 中的计算机上安装文件的首选的方法。</span><span class="sxs-lookup"><span data-stu-id="8255e-112">IT admins can choose their preferred method to distribute the installation files to computers in their organization, such as System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="8255e-113">若要获取 Windows 通讯组的 MSI 程序包，请参阅[安装的 Microsoft 团队使用 MSI](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="8255e-113">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8255e-114">通过这些机制分发客户端仅适用于初次安装 Microsoft Team 客户端，不适用于将来更新。</span><span class="sxs-lookup"><span data-stu-id="8255e-114">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="8255e-115">Windows</span><span class="sxs-lookup"><span data-stu-id="8255e-115">Windows</span></span>

<span data-ttu-id="8255e-116">适用于 Windows 的 Microsoft Teams 安装提供 32 位和 64 位体系结构的可下载安装程序。</span><span class="sxs-lookup"><span data-stu-id="8255e-116">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="8255e-117">Windows 和 Office 安装的体系结构不可知的 Microsoft 团队的体系结构 （32 位与 64 位）。</span><span class="sxs-lookup"><span data-stu-id="8255e-117">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="8255e-118">Windows 客户端部署到位于用户配置文件中的 AppData 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8255e-118">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="8255e-119">部署到用户的本地配置文件后，无需提升的权限即可安装客户端。</span><span class="sxs-lookup"><span data-stu-id="8255e-119">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="8255e-120">Windows 客户端安装在以下位置：</span><span class="sxs-lookup"><span data-stu-id="8255e-120">The Windows client is installed in the following locations:</span></span>

- <span data-ttu-id="8255e-121">%appdata%\\local\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="8255e-121">%appdata%\\local\\Microsoft\\Teams</span></span>

- <span data-ttu-id="8255e-122">%appdata%\\roaming\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="8255e-122">%appdata%\\roaming\\Microsoft\\Teams</span></span>

<span data-ttu-id="8255e-123">用户首次使用 Microsoft Teams 客户端启动呼叫时，他们可能会注意到有关 Windows 防火墙设置的警告，要求用户允许通信。</span><span class="sxs-lookup"><span data-stu-id="8255e-123">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="8255e-124">指示用户可能由于呼叫将工作原理，即使在消除警告时忽略此消息。</span><span class="sxs-lookup"><span data-stu-id="8255e-124">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Windows 安全警报对话框屏幕截图。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="8255e-126">即使选择“取消”忽略该提示，也将会更改 Windows 防火墙配置。</span><span class="sxs-lookup"><span data-stu-id="8255e-126">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="8255e-127">将会创建两条针对 teams.exe 的入站规则，操作是阻止 TCP 和 UDP 协议。</span><span class="sxs-lookup"><span data-stu-id="8255e-127">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="8255e-128">Mac</span><span class="sxs-lookup"><span data-stu-id="8255e-128">Mac</span></span>

<span data-ttu-id="8255e-129">Mac 用户可以使用 macOS 计算机软件包安装文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="8255e-129">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="8255e-130">要安装 Mac 客户端，需要管理权限。</span><span class="sxs-lookup"><span data-stu-id="8255e-130">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="8255e-131">MacOS 客户端安装到/应用程序 — 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8255e-131">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="8255e-132">使用软件包文件安装团队</span><span class="sxs-lookup"><span data-stu-id="8255e-132">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="8255e-133">从[工作组下载页面](https://teams.microsoft.com/downloads)，在**Mac**，下单击**下载**。</span><span class="sxs-lookup"><span data-stu-id="8255e-133">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="8255e-134">双击软件包文件。</span><span class="sxs-lookup"><span data-stu-id="8255e-134">Double click the PKG file.</span></span>
3. <span data-ttu-id="8255e-135">按照安装向导以完成安装。</span><span class="sxs-lookup"><span data-stu-id="8255e-135">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="8255e-136">团队将安装到/应用程序 — 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8255e-136">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="8255e-137">计算机范围安装它。</span><span class="sxs-lookup"><span data-stu-id="8255e-137">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="8255e-138">安装期间，PKG 将提示管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="8255e-138">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="8255e-139">用户需要输入管理员凭据，而不管用户管理员。</span><span class="sxs-lookup"><span data-stu-id="8255e-139">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="8255e-140">如果用户当前已团队的 DMG 安装，并希望将其替换为 PKG 安装，用户应：</span><span class="sxs-lookup"><span data-stu-id="8255e-140">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="8255e-141">退出团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="8255e-141">Exit the Teams app.</span></span>
2. <span data-ttu-id="8255e-142">卸载团队应用程序。</span><span class="sxs-lookup"><span data-stu-id="8255e-142">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="8255e-143">安装软件包文件。</span><span class="sxs-lookup"><span data-stu-id="8255e-143">Install the PKG file.</span></span>

<span data-ttu-id="8255e-144">IT 管理员可以使用托管的部署团队的安装文件分发给其组织，如 Jamf Pro 中的所有 Mac。</span><span class="sxs-lookup"><span data-stu-id="8255e-144">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="8255e-145">如果您遇到问题安装 PKG，让我们知道。</span><span class="sxs-lookup"><span data-stu-id="8255e-145">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="8255e-146">在本文末尾的**反馈**部分中，单击**产品反馈**。</span><span class="sxs-lookup"><span data-stu-id="8255e-146">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

<a name="web-client"></a><span data-ttu-id="8255e-147">Web 客户端</span><span class="sxs-lookup"><span data-stu-id="8255e-147">Web client</span></span> 
----------

<span data-ttu-id="8255e-148">Web 客户端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是可从多个浏览器的完整、 职能客户端。</span><span class="sxs-lookup"><span data-stu-id="8255e-148">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="8255e-149">Web 客户端支持使用 webRTC，因此不插件或下载需要在 web 浏览器中运行团队呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="8255e-149">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="8255e-150">在浏览器必须配置为允许使用第三方 cookie。</span><span class="sxs-lookup"><span data-stu-id="8255e-150">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="8255e-151">Web 客户端执行时连接到的浏览器版本检测[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)。</span><span class="sxs-lookup"><span data-stu-id="8255e-151">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="8255e-152">如果检测到不受支持的浏览器版本时，它将阻止对 web 界面访问并建议用户下载桌面客户端或移动应用程序。</span><span class="sxs-lookup"><span data-stu-id="8255e-152">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

<a name="mobile-clients"></a><span data-ttu-id="8255e-153">移动客户端</span><span class="sxs-lookup"><span data-stu-id="8255e-153">Mobile clients</span></span>
--------------

<span data-ttu-id="8255e-154">Microsoft Teams 移动应用适用于 Android、iOS 和 Windows Phones，适合参与基于聊天的对话的忙碌用户，允许进行点对点音频呼叫。</span><span class="sxs-lookup"><span data-stu-id="8255e-154">The Microsoft Teams mobile apps are available for Android, iOS, and Windows Phones, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="8255e-155">对于移动应用，请访问 Google Play、Apple App Store 和 Microsoft 商店的相关移动应用商店。</span><span class="sxs-lookup"><span data-stu-id="8255e-155">For mobile apps, go to the relevant mobile store for Google Play, Apple App Store, and Microsoft Store.</span></span>

<span data-ttu-id="8255e-156">Microsoft Teams 移动应用的支持移动平台如下：</span><span class="sxs-lookup"><span data-stu-id="8255e-156">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="8255e-157">**Android**：4.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8255e-157">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="8255e-158">**iOS**：10.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8255e-158">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="8255e-159">移动的版本必须为按预期方式工作的团队顺序公众。</span><span class="sxs-lookup"><span data-stu-id="8255e-159">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="8255e-160">移动应用仅通过各个移动平台的应用商店分发和更新，不可通过 MDM（移动设备管理）解决方案或侧向加载分发。</span><span class="sxs-lookup"><span data-stu-id="8255e-160">Mobile apps are distributed and updated through the respective mobile platform’s app store only, and are not available to be distributed through MDM (mobile device management) solutions or side-loaded.</span></span>


| | | |
|---------|---------|---------|
|![决策点图标。](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="8255e-162">决策点</span><span class="sxs-lookup"><span data-stu-id="8255e-162">Decision Point</span></span>         |<span data-ttu-id="8255e-163">是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？</span><span class="sxs-lookup"><span data-stu-id="8255e-163">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![后续步骤图标。](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="8255e-165">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8255e-165">Next Steps</span></span>         |<span data-ttu-id="8255e-166">如果贵组织限制软件安装，请确保 Microsoft Teams 不会受到阻止。</span><span class="sxs-lookup"><span data-stu-id="8255e-166">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="8255e-167">注意：PC 客户端安装不需要管理权限，但在 Mac 上安装需要。</span><span class="sxs-lookup"><span data-stu-id="8255e-167">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |


  <span data-ttu-id="8255e-168"><span id="_Hlk477176062" class="anchor"></span>  决策点   是否存在阻止用户在其设备上安装合适 Microsoft Teams 客户端的任何限制？</span><span class="sxs-lookup"><span data-stu-id="8255e-168"><span id="_Hlk477176062" class="anchor"></span>  Decision Point   Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>

<a name="client-update-management"></a><span data-ttu-id="8255e-169">客户端更新管理</span><span class="sxs-lookup"><span data-stu-id="8255e-169">Client update management</span></span>
------------------------

<span data-ttu-id="8255e-170">当前，Microsoft Teams 服务会自动更新客户端，无需 IT 管理员干预。</span><span class="sxs-lookup"><span data-stu-id="8255e-170">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="8255e-171">如果有更新，客户端将自动下载更新，当应用空闲一段时间后，将开始执行更新过程。</span><span class="sxs-lookup"><span data-stu-id="8255e-171">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will kick off.</span></span>

<a name="client-side-configurations"></a><span data-ttu-id="8255e-172">客户端配置</span><span class="sxs-lookup"><span data-stu-id="8255e-172">Client-side configurations</span></span>
---------------------------

<span data-ttu-id="8255e-173">当前，未提供支持的选项来通过租户管理、PowerShell、组策略对象或注册表配置客户端。</span><span class="sxs-lookup"><span data-stu-id="8255e-173">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

<a name="notification-settings"></a><span data-ttu-id="8255e-174">通知设置</span><span class="sxs-lookup"><span data-stu-id="8255e-174">Notification settings</span></span>
----------------------------

<span data-ttu-id="8255e-175">当前，未提供选项允许 IT 管理员配置客户端通知设置。</span><span class="sxs-lookup"><span data-stu-id="8255e-175">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="8255e-176">所有通知选项均由用户设置。</span><span class="sxs-lookup"><span data-stu-id="8255e-176">All notification options are set by the user.</span></span> <span data-ttu-id="8255e-177">下图概括显示了默认客户端设置。</span><span class="sxs-lookup"><span data-stu-id="8255e-177">The figure below outlines the default client settings.</span></span>

![“通知设置”屏幕截图。](media/Get_clients_for_Microsoft_Teams_image6.png)
