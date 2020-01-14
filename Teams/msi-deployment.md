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
ms.openlocfilehash: d4a14876f359b2742a04461671ccaefd523ef3f1
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111536"
---
# <a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="ad179-103">使用 MSI 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad179-103">Install Microsoft Teams using MSI</span></span>

> [!Tip]
> <span data-ttu-id="ad179-104">观看以下会话，了解 Windows 桌面客户端的优点、如何规划它以及如何部署它：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="ad179-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="ad179-105">若要使用 System Center Configuration Manager 或组策略或任何第三方分发机制进行广泛的部署，Microsoft 提供了 MSI 文件（32位和64位），管理员可以使用这些文件批量部署团队以选择用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="ad179-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="ad179-106">管理员可以使用这些文件远程部署团队，以便用户不必手动下载团队应用。</span><span class="sxs-lookup"><span data-stu-id="ad179-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="ad179-107">部署后，团队将为登录到该计算机的所有用户自动启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="ad179-108">（您可以在安装应用后禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="ad179-109">[请参阅下文](#disable-auto-launch-for-the-msi-installer)。）我们建议你将程序包部署到计算机，以便计算机的所有新用户也将受益于此部署。</span><span class="sxs-lookup"><span data-stu-id="ad179-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="ad179-110">以下是指向 MSI 文件的链接：</span><span class="sxs-lookup"><span data-stu-id="ad179-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="ad179-111">元</span><span class="sxs-lookup"><span data-stu-id="ad179-111">Entity</span></span>  |<span data-ttu-id="ad179-112">32位</span><span class="sxs-lookup"><span data-stu-id="ad179-112">32 bit</span></span>      |<span data-ttu-id="ad179-113">64位</span><span class="sxs-lookup"><span data-stu-id="ad179-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="ad179-114">交给</span><span class="sxs-lookup"><span data-stu-id="ad179-114">Commercial</span></span>     | [<span data-ttu-id="ad179-115">32位</span><span class="sxs-lookup"><span data-stu-id="ad179-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="ad179-116">64位</span><span class="sxs-lookup"><span data-stu-id="ad179-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="ad179-117">联邦政府-GCC</span><span class="sxs-lookup"><span data-stu-id="ad179-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="ad179-118">32位</span><span class="sxs-lookup"><span data-stu-id="ad179-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="ad179-119">64位</span><span class="sxs-lookup"><span data-stu-id="ad179-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="ad179-120">联邦政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="ad179-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="ad179-121">32位</span><span class="sxs-lookup"><span data-stu-id="ad179-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="ad179-122">64位</span><span class="sxs-lookup"><span data-stu-id="ad179-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="ad179-123">联邦政府-DoD</span><span class="sxs-lookup"><span data-stu-id="ad179-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="ad179-124">32位</span><span class="sxs-lookup"><span data-stu-id="ad179-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="ad179-125">64位</span><span class="sxs-lookup"><span data-stu-id="ad179-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="ad179-126">团队还可以包含在 Office 365 专业增强版的部署中。</span><span class="sxs-lookup"><span data-stu-id="ad179-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="ad179-127">有关详细信息，请参阅[部署 Microsoft 团队和 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="ad179-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="ad179-128">若要了解有关 SCCM 的详细信息，请参阅[System Center Configuration Manager 简介](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="ad179-128">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="ad179-129">部署过程（推荐）</span><span class="sxs-lookup"><span data-stu-id="ad179-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="ad179-130">检索最新的程序包。</span><span class="sxs-lookup"><span data-stu-id="ad179-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="ad179-131">使用由 MSI 预填充的默认值。</span><span class="sxs-lookup"><span data-stu-id="ad179-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="ad179-132">尽可能部署到计算机。</span><span class="sxs-lookup"><span data-stu-id="ad179-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="ad179-133">Microsoft 团队 MSI 程序包的工作原理</span><span class="sxs-lookup"><span data-stu-id="ad179-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="ad179-134">PC 安装</span><span class="sxs-lookup"><span data-stu-id="ad179-134">PC installation</span></span>

<span data-ttu-id="ad179-135">团队 MSI 将在程序文件中放置一个安装程序。</span><span class="sxs-lookup"><span data-stu-id="ad179-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="ad179-136">当用户登录到新的 Windows 用户配置文件时，将启动安装程序，并将在该用户的 appdata 文件夹中安装 "团队" 应用副本。</span><span class="sxs-lookup"><span data-stu-id="ad179-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="ad179-137">如果用户已在 appdata 文件夹中安装了 "团队" 应用，则 MSI 安装程序将跳过该用户的进程。</span><span class="sxs-lookup"><span data-stu-id="ad179-137">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="ad179-138">请勿使用 MSI 部署更新，因为客户端将在检测到服务提供新版本时自动更新。</span><span class="sxs-lookup"><span data-stu-id="ad179-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="ad179-139">若要重新部署最新的安装程序，请使用下面所述的重新部署 MSI 的过程。</span><span class="sxs-lookup"><span data-stu-id="ad179-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="ad179-140">如果你部署较旧版本的 MSI 程序包，客户端将在可能的情况下自动更新（在 VDI 环境中除外）。</span><span class="sxs-lookup"><span data-stu-id="ad179-140"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="ad179-141">如果部署了非常旧的版本，MSI 将在用户可以使用团队之前触发应用更新。</span><span class="sxs-lookup"><span data-stu-id="ad179-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="ad179-142">我们不建议你更改默认安装位置，因为这可能会中断更新流。</span><span class="sxs-lookup"><span data-stu-id="ad179-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="ad179-143">如果版本过旧，最终会阻止用户访问该服务。</span><span class="sxs-lookup"><span data-stu-id="ad179-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="ad179-144">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="ad179-144">Target computer requirements</span></span>

- <span data-ttu-id="ad179-145">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ad179-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="ad179-146">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ad179-146">Windows 7 or later</span></span>
- <span data-ttu-id="ad179-147">Windows Server 2012 R2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ad179-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="ad179-148">每个用户配置文件 3 GB 的磁盘空间（推荐）</span><span class="sxs-lookup"><span data-stu-id="ad179-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="ad179-149">VDI 安装</span><span class="sxs-lookup"><span data-stu-id="ad179-149">VDI installation</span></span>

<span data-ttu-id="ad179-150">有关如何在 VDI 上部署团队桌面应用的完整指南，请参阅[针对虚拟化桌面基础结构的团队](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="ad179-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="ad179-151">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="ad179-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="ad179-152">如果用户从其用户配置文件中卸载团队，则 MSI 安装程序将跟踪用户已卸载团队应用，并且不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="ad179-152">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="ad179-153">若要在卸载的特定计算机上为此用户重新部署团队，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ad179-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="ad179-154">卸载为每个用户配置文件安装的团队应用。</span><span class="sxs-lookup"><span data-stu-id="ad179-154">Uninstall Teams App installed for every user profile.</span></span>
2. <span data-ttu-id="ad179-155">卸载后，在%localappdata%\Microsoft\Teams\. 下递归删除目录</span><span class="sxs-lookup"><span data-stu-id="ad179-155">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="ad179-156">将 MSI 程序包重新部署到该特定计算机。</span><span class="sxs-lookup"><span data-stu-id="ad179-156">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="ad179-157">你可以使用[Microsoft 团队部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)脚本，通过 SCCM 完成步骤1和2。</span><span class="sxs-lookup"><span data-stu-id="ad179-157">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="ad179-158">阻止团队在安装后自动启动</span><span class="sxs-lookup"><span data-stu-id="ad179-158">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="ad179-159">MSI 的默认行为是在用户登录后立即安装团队应用，然后自动启动团队。</span><span class="sxs-lookup"><span data-stu-id="ad179-159">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="ad179-160">如果您不希望团队在用户安装后自动启动，则可以使用组策略来设置策略设置或禁用 MSI 安装程序的自动启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-160">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

#### <a name="use-group-policy-recommended"></a><span data-ttu-id="ad179-161">使用组策略（推荐）</span><span class="sxs-lookup"><span data-stu-id="ad179-161">Use Group Policy (recommended)</span></span>

<span data-ttu-id="ad179-162">启用 "**阻止 Microsoft 团队在安装组策略设置后自动启动**"。</span><span class="sxs-lookup"><span data-stu-id="ad179-162">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="ad179-163">可以在用户 Configuration\Policies\Administrative Templates\Microsoft 团队中找到此策略设置。</span><span class="sxs-lookup"><span data-stu-id="ad179-163">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="ad179-164">这是推荐的方法，因为你可以根据组织的需要关闭或打开策略设置。</span><span class="sxs-lookup"><span data-stu-id="ad179-164">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="ad179-165">如果在安装团队之前启用此策略设置，则当用户登录到 Windows 时不会自动启动团队。</span><span class="sxs-lookup"><span data-stu-id="ad179-165">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="ad179-166">用户首次登录到团队后，团队将在下次用户登录时自动启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-166">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="ad179-167">若要了解详细信息，请参阅[使用组策略防止团队在安装后自动启动](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。</span><span class="sxs-lookup"><span data-stu-id="ad179-167">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="ad179-168">禁用 MSI 安装程序的自动启动</span><span class="sxs-lookup"><span data-stu-id="ad179-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="ad179-169">你可以通过使用**选项 = "noAutoStart = true"** 参数来禁用 MSI 安装程序的自动启动，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ad179-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="ad179-170">对于32位版本</span><span class="sxs-lookup"><span data-stu-id="ad179-170">For the 32-bit version</span></span>
```PowerShell
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="ad179-171">对于64位版本</span><span class="sxs-lookup"><span data-stu-id="ad179-171">For the 64-bit version</span></span>
```PowerShell
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

<span data-ttu-id="ad179-172">当用户登录到 Windows 时，团队与 MSI 一起安装，并将启动团队的快捷方式添加到用户的桌面。</span><span class="sxs-lookup"><span data-stu-id="ad179-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="ad179-173">在用户手动启动团队之前，团队将不会启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="ad179-174">用户手动启动团队后，团队会在用户登录时自动启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

> [!Note]
> <span data-ttu-id="ad179-175">如果手动运行 MSI，请确保以提升的权限运行 MSI。</span><span class="sxs-lookup"><span data-stu-id="ad179-175">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="ad179-176">即使以管理员身份运行它，并且不使用提升的权限运行它，安装程序也无法将该选项配置为禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="ad179-176">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
