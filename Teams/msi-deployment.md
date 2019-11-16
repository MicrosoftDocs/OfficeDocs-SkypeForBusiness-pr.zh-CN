---
title: 通过 SCCM 使用 MSI 安装 Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "37567957"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="3ffa2-103">使用 MSI 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ffa2-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="3ffa2-104">观看以下会话，了解 Windows 桌面客户端的优点、如何规划它以及如何部署它：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="3ffa2-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="3ffa2-105">若要使用 System Center Configuration Manager 或组策略或任何第三方分发机制进行广泛的部署，Microsoft 提供了 MSI 文件（ [32 位](https://aka.ms/teams32bitmsi)和[64 位](https://aka.ms/teams64bitmsi)），管理员可以使用这些文件批量部署团队以选择用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="3ffa2-106">管理员可以使用这些文件远程部署团队，以便用户不必手动下载团队应用。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="3ffa2-107">部署后，团队将为登录到该计算机的所有用户自动启动。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="3ffa2-108">（您可以在安装应用后禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="3ffa2-109">[请参阅下文](#disable-auto-launch-for-the-msi-installer)。）我们建议你将程序包部署到计算机，以便计算机的所有新用户也将受益于此部署。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="3ffa2-110">团队还可以包含在 Office 365 专业增强版的部署中。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="3ffa2-111">有关详细信息，请参阅[部署 Microsoft 团队和 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="3ffa2-112">若要了解有关 SCCM 的详细信息，请参阅[System Center Configuration Manager 简介](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="3ffa2-113">部署过程（推荐）</span><span class="sxs-lookup"><span data-stu-id="3ffa2-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="3ffa2-114">检索最新的程序包。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="3ffa2-115">使用由 MSI 预填充的默认值。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="3ffa2-116">尽可能部署到计算机。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="3ffa2-117">Microsoft 团队 MSI 程序包的工作原理</span><span class="sxs-lookup"><span data-stu-id="3ffa2-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="3ffa2-118">PC 安装</span><span class="sxs-lookup"><span data-stu-id="3ffa2-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="3ffa2-119">有关如何将团队部署到虚拟 DesktopInfrastructure （VDI）环境的指南，请参阅[VDI 安装](#vdi-installation)。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="3ffa2-120">团队 MSI 将在程序文件中放置一个安装程序。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="3ffa2-121">当用户登录到新的 Windows 用户配置文件时，将启动安装程序，并将在该用户的 appdata 文件夹中安装 "团队" 应用副本。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="3ffa2-122">如果用户已在 appdata 文件夹中安装了 "团队" 应用，则 MSI 安装程序将跳过该用户的进程。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="3ffa2-123">请勿使用 MSI 部署更新，因为客户端将在检测到服务提供新版本时自动更新。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="3ffa2-124">若要重新部署最新的安装程序，请使用下面所述的重新部署 MSI 的过程。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="3ffa2-125">如果你部署较旧版本的 MSI 程序包，客户端将在可能的情况下自动更新（在 VDI 环境中除外）。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="3ffa2-126">如果部署了非常旧的版本，MSI 将在用户可以使用团队之前触发应用更新。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="3ffa2-127">我们不建议你更改默认安装位置，因为这可能会中断更新流。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="3ffa2-128">如果版本过旧，最终会阻止用户访问该服务。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="3ffa2-129">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="3ffa2-129">Target computer requirements</span></span>

- <span data-ttu-id="3ffa2-130">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3ffa2-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="3ffa2-131">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3ffa2-131">Windows 7 or later</span></span>
- <span data-ttu-id="3ffa2-132">每个用户配置文件 3 GB 的磁盘空间（推荐）</span><span class="sxs-lookup"><span data-stu-id="3ffa2-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="3ffa2-133">VDI 安装</span><span class="sxs-lookup"><span data-stu-id="3ffa2-133">VDI installation</span></span>

<span data-ttu-id="3ffa2-134">下面是部署团队桌面应用的过程。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="3ffa2-135">有关完整指南，请参阅[针对虚拟化桌面基础结构的团队](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="3ffa2-136">根据环境，使用下列链接之一下载团队 MSI 程序包。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="3ffa2-137">我们建议使用64位操作系统的 VDI VM 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="3ffa2-138">32位版本</span><span class="sxs-lookup"><span data-stu-id="3ffa2-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="3ffa2-139">64位版本</span><span class="sxs-lookup"><span data-stu-id="3ffa2-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="3ffa2-140">运行以下命令，将 MSI 安装到 VDI VM （或完成更新）。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="3ffa2-141">这将把团队安装到程序文件。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="3ffa2-142">此时，将完成黄金图像设置。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="3ffa2-143">下一个交互式登录会话将启动团队并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="3ffa2-144">请注意，在 VDI 上使用 ALLUSER 属性安装团队时，不可能禁用团队的自动启动。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="3ffa2-145">运行以下命令以从 VDI VM 卸载 MSI （或准备更新它）。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="3ffa2-146">这将从程序文件中卸载团队。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="3ffa2-147">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="3ffa2-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="3ffa2-148">如果用户从其用户配置文件中卸载团队，则 MSI 安装程序将跟踪用户已卸载团队应用，并且不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="3ffa2-149">若要在卸载的特定计算机上为此用户重新部署团队，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3ffa2-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="3ffa2-150">卸载为每个用户配置文件安装的团队应用。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="3ffa2-151">卸载后，在%localappdata%\Microsoft\Teams\. 下递归删除目录</span><span class="sxs-lookup"><span data-stu-id="3ffa2-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="3ffa2-152">将 MSI 程序包重新部署到该特定计算机。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="3ffa2-153">你可以使用[Microsoft 团队部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)脚本，通过 SCCM 完成步骤1和2。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="3ffa2-154">禁用 MSI 安装程序的自动启动</span><span class="sxs-lookup"><span data-stu-id="3ffa2-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="3ffa2-155">MSI 的默认行为是在用户登录后立即安装团队客户端，然后自动启动团队。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="3ffa2-156">你可以按如下方式修改此行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3ffa2-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="3ffa2-157">当用户登录到 Windows 时，将使用 MSI 安装团队</span><span class="sxs-lookup"><span data-stu-id="3ffa2-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="3ffa2-158">但是，团队客户端将不会启动，直到用户手动开始团队</span><span class="sxs-lookup"><span data-stu-id="3ffa2-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="3ffa2-159">将在用户桌面上添加开始团队的快捷方式</span><span class="sxs-lookup"><span data-stu-id="3ffa2-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="3ffa2-160">手动启动后，团队将在用户登录时自动启动</span><span class="sxs-lookup"><span data-stu-id="3ffa2-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="3ffa2-161">对于32位版本</span><span class="sxs-lookup"><span data-stu-id="3ffa2-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="3ffa2-162">对于64位版本</span><span class="sxs-lookup"><span data-stu-id="3ffa2-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="3ffa2-163">如果手动运行 MSI，请确保以提升的权限运行 MSI。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="3ffa2-164">即使以管理员身份运行它，而不以提升的权限运行它，安装程序也无法将该选项配置为禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="3ffa2-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
