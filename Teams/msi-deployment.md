---
title: 使用 Microsoft 终结点配置管理器安装团队
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: 使用 Microsoft 终结点配置管理器批量部署 Microsoft 团队以选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f3eb845321a13e7701f7a8d49b975fe077fa2e14
ms.sourcegitcommit: a1524afb546fde9844f53390fab85e7073da8cb2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2020
ms.locfileid: "48778785"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="cd85f-103">使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd85f-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="cd85f-104">观看以下会话，了解 Windows 桌面客户端的优点、如何规划它以及如何部署它： [团队 Windows 桌面客户端](https://aka.ms/teams-clients)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="cd85f-105">为了使用 Microsoft Endpoint Configuration Manager 或组策略或任何第三方分发机制以进行广泛部署，Microsoft 提供了 MSI 文件（32 位和 64 位），供管理员用于将 Teams 批量部署至选定的用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="cd85f-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="cd85f-106">管理员可以使用这些文件远程部署 Teams，使用户无需手动下载 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="cd85f-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="cd85f-107">部署后，对于登录至计算机上的所有用户，Teams 将会自动启用。</span><span class="sxs-lookup"><span data-stu-id="cd85f-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="cd85f-108">（你可以在安装此应用之后禁用自动启用。</span><span class="sxs-lookup"><span data-stu-id="cd85f-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="cd85f-109">[请参阅下面的](#disable-auto-launch-for-the-msi-installer)。）建议你将程序包部署至计算机，以便该计算机上的所有新用户均可从此部署中受益。</span><span class="sxs-lookup"><span data-stu-id="cd85f-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="cd85f-110">以下是 MSI 文件的链接：</span><span class="sxs-lookup"><span data-stu-id="cd85f-110">These are the links to the MSI files:</span></span>

|<span data-ttu-id="cd85f-111">实体</span><span class="sxs-lookup"><span data-stu-id="cd85f-111">Entity</span></span>  |<span data-ttu-id="cd85f-112">32位</span><span class="sxs-lookup"><span data-stu-id="cd85f-112">32-bit</span></span>      |<span data-ttu-id="cd85f-113">64位</span><span class="sxs-lookup"><span data-stu-id="cd85f-113">64-bit</span></span>      | <span data-ttu-id="cd85f-114">ARM64</span><span class="sxs-lookup"><span data-stu-id="cd85f-114">ARM64</span></span> |
|---------|---------|---------|-----------|
|<span data-ttu-id="cd85f-115">商用</span><span class="sxs-lookup"><span data-stu-id="cd85f-115">Commercial</span></span>     | [<span data-ttu-id="cd85f-116">32位</span><span class="sxs-lookup"><span data-stu-id="cd85f-116">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="cd85f-117">64位</span><span class="sxs-lookup"><span data-stu-id="cd85f-117">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [<span data-ttu-id="cd85f-118">ARM64</span><span class="sxs-lookup"><span data-stu-id="cd85f-118">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|<span data-ttu-id="cd85f-119">联邦政府 - GCC</span><span class="sxs-lookup"><span data-stu-id="cd85f-119">Federal Government - GCC</span></span>     | [<span data-ttu-id="cd85f-120">32位</span><span class="sxs-lookup"><span data-stu-id="cd85f-120">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="cd85f-121">64位</span><span class="sxs-lookup"><span data-stu-id="cd85f-121">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[<span data-ttu-id="cd85f-122">ARM64</span><span class="sxs-lookup"><span data-stu-id="cd85f-122">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="cd85f-123">联邦政府 - GCC High</span><span class="sxs-lookup"><span data-stu-id="cd85f-123">Federal Government - GCC High</span></span>    | [<span data-ttu-id="cd85f-124">32位</span><span class="sxs-lookup"><span data-stu-id="cd85f-124">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="cd85f-125">64位</span><span class="sxs-lookup"><span data-stu-id="cd85f-125">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[<span data-ttu-id="cd85f-126">ARM64</span><span class="sxs-lookup"><span data-stu-id="cd85f-126">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="cd85f-127">联邦政府 - DoD</span><span class="sxs-lookup"><span data-stu-id="cd85f-127">Federal Government - DoD</span></span>     | [<span data-ttu-id="cd85f-128">32位</span><span class="sxs-lookup"><span data-stu-id="cd85f-128">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="cd85f-129">64位</span><span class="sxs-lookup"><span data-stu-id="cd85f-129">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [<span data-ttu-id="cd85f-130">ARM64</span><span class="sxs-lookup"><span data-stu-id="cd85f-130">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

<span data-ttu-id="cd85f-131">**若要确保部署成功，请注意以下事项：**</span><span class="sxs-lookup"><span data-stu-id="cd85f-131">**To ensure a successful deployment, be aware of the following:**</span></span>

- <span data-ttu-id="cd85f-132">在64位操作系统上安装64位版本的团队。</span><span class="sxs-lookup"><span data-stu-id="cd85f-132">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="cd85f-133">如果你尝试在32位操作系统上安装64位版本的团队，则安装将不会成功，并且当前不会收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="cd85f-133">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and currently you won't receive an error message.</span></span>

- <span data-ttu-id="cd85f-134">如果客户租户位于 GCCH 或 DoD 云上，客户应通过将 **CloudType** 值添加到注册表中的 **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** 键来设置注册表中的初始终结点。</span><span class="sxs-lookup"><span data-stu-id="cd85f-134">If the customer tenant is on the GCCH or DoD clouds, the customer should set the initial endpoint in the registry by adding the **CloudType** value to the **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** key in the registry.</span></span> <span data-ttu-id="cd85f-135">**CloudType** 的类型为 **DWORD** 值，值为 (0 = Unset，1 = 商业，2 = GCC，3 = GCCH，4 = DOD) 。</span><span class="sxs-lookup"><span data-stu-id="cd85f-135">The type for **CloudType** is **DWORD** and values are (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD).</span></span> <span data-ttu-id="cd85f-136">将终结点设置为注册表项会限制团队连接到正确的云终结点，以便与团队进行预登录连接。</span><span class="sxs-lookup"><span data-stu-id="cd85f-136">Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams.</span></span>

- <span data-ttu-id="cd85f-137">团队也可以包含在适用于企业的 Microsoft 365 应用的部署中。</span><span class="sxs-lookup"><span data-stu-id="cd85f-137">Teams can also be included with a deployment of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="cd85f-138">有关详细信息，请参阅 [通过适用于企业的 microsoft 365 应用部署 Microsoft 团队](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-138">For more information, see [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

- <span data-ttu-id="cd85f-139">若要了解有关 Microsoft 终结点配置管理器的详细信息，请参阅 [什么是配置管理器？](https://docs.microsoft.com/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="cd85f-139">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="cd85f-140">部署过程（推荐）</span><span class="sxs-lookup"><span data-stu-id="cd85f-140">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="cd85f-141">检索最新程序包。</span><span class="sxs-lookup"><span data-stu-id="cd85f-141">Retrieve the latest package.</span></span>
2. <span data-ttu-id="cd85f-142">使用由 MSI 预填充的默认值。</span><span class="sxs-lookup"><span data-stu-id="cd85f-142">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="cd85f-143">部署到计算机（如可能）。</span><span class="sxs-lookup"><span data-stu-id="cd85f-143">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="cd85f-144">Microsoft Teams MSI 程序包的工作原理</span><span class="sxs-lookup"><span data-stu-id="cd85f-144">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="cd85f-145">电脑安装</span><span class="sxs-lookup"><span data-stu-id="cd85f-145">PC installation</span></span>

<span data-ttu-id="cd85f-146">Teams MSI 会将安装程序放置在“Program Files”中。</span><span class="sxs-lookup"><span data-stu-id="cd85f-146">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="cd85f-147">无论用户何时登录新的 Windows 用户配置文件，该安装程序均会启用并且 Teams 应用副本将安装在该用户的 `AppData` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cd85f-147">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="cd85f-148">如果用户已在 `AppData` 文件夹中安装了 Teams 应用，则MSI 安装程序将为该用户跳过此过程。</span><span class="sxs-lookup"><span data-stu-id="cd85f-148">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="cd85f-149">请勿使用 MSI 部署更新，因为当客户端从服务中检测到可用的新版本时将会自动更新。</span><span class="sxs-lookup"><span data-stu-id="cd85f-149">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="cd85f-150">要冲虚部署最新的安装程序，请使用下述重新部署 MSI 流程。</span><span class="sxs-lookup"><span data-stu-id="cd85f-150">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="cd85f-151">如果部署的是旧版的 MSI 程序包，则除了在 VDI 环境中以外，客户端将为用户自动更新（如可能）。</span><span class="sxs-lookup"><span data-stu-id="cd85f-151">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="cd85f-152">如果部署的是非常旧的版本，则在用户能够使用 Teams 之前，MSI 将会触发应用更新。</span><span class="sxs-lookup"><span data-stu-id="cd85f-152">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd85f-153">默认位置是64位操作系统上的 (x86) \Teams 安装程序和32位操作系统上 C:\Program Files\Teams 安装程序的 C:\Program 文件。</span><span class="sxs-lookup"><span data-stu-id="cd85f-153">The default location is C:\Program Files (x86)\Teams Installer on 64-bit operating systems and C:\Program Files\Teams Installer on 32-bit operating systems.</span></span>
> <span data-ttu-id="cd85f-154">不建议更改默认安装位置，因为这可能会中断更新流。</span><span class="sxs-lookup"><span data-stu-id="cd85f-154">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="cd85f-155">版本太旧最终会阻止用户访问服务。</span><span class="sxs-lookup"><span data-stu-id="cd85f-155">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="cd85f-156">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="cd85f-156">Target computer requirements</span></span>

- <span data-ttu-id="cd85f-157">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cd85f-157">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="cd85f-158">Windows 8.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cd85f-158">Windows 8.1 or later</span></span>
- <span data-ttu-id="cd85f-159">Windows Server 2012 R2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cd85f-159">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="cd85f-160">每个用户配置文件 3 GB 磁盘空间（推荐）</span><span class="sxs-lookup"><span data-stu-id="cd85f-160">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="cd85f-161">VDI 安装</span><span class="sxs-lookup"><span data-stu-id="cd85f-161">VDI installation</span></span>

<span data-ttu-id="cd85f-162">如需如何在 VDI 上部署 Teams 桌面应用的完整指南，请参阅[适用于虚拟化桌面基础结构的 Teams](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-162">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="cd85f-163">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="cd85f-163">Clean up and redeployment procedure</span></span>

<span data-ttu-id="cd85f-164">如果用户从其用户配置文件中卸载团队，则 MSI 安装程序将跟踪用户已卸载团队应用，并且不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="cd85f-164">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="cd85f-165">要为此用户在已从其中卸载 Teams 的特定计算机上重新部署 Teams，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cd85f-165">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd85f-166">接下来的步骤包含有关如何修改注册表的信息。</span><span class="sxs-lookup"><span data-stu-id="cd85f-166">The next steps contain information about how to modify the registry.</span></span> <span data-ttu-id="cd85f-167">请确保在修改注册表之前对其进行备份，如果出现问题，您知道如何还原注册表。</span><span class="sxs-lookup"><span data-stu-id="cd85f-167">Make sure that you back up the registry before you modify it and that you know how to restore the registry if a problem occurs.</span></span> <span data-ttu-id="cd85f-168">有关如何备份、还原和修改注册表的详细信息，请参阅 [高级用户的 Windows 注册表信息](https://support.microsoft.com/help/256986)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-168">For more information about how to back up, restore, and modify the registry, see [Windows registry information for advanced users](https://support.microsoft.com/help/256986).</span></span>

1. <span data-ttu-id="cd85f-169">卸载为每个用户配置文件安装的团队应用。</span><span class="sxs-lookup"><span data-stu-id="cd85f-169">Uninstall the Teams app installed for every user profile.</span></span> <span data-ttu-id="cd85f-170">有关详细信息，请参阅 [卸载 Microsoft 团队](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-170">For more information, see [Uninstall Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).</span></span>
2. <span data-ttu-id="cd85f-171">在下递归删除目录 `%localappdata%\Microsoft\Teams\` 。</span><span class="sxs-lookup"><span data-stu-id="cd85f-171">Delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="cd85f-172">删除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 注册表值。</span><span class="sxs-lookup"><span data-stu-id="cd85f-172">Delete the `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` registry value.</span></span>
4. <span data-ttu-id="cd85f-173">将 MSI 程序包重新部署到该特定计算机。</span><span class="sxs-lookup"><span data-stu-id="cd85f-173">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="cd85f-174">您也可以使用我们的 [团队部署清理脚本](scripts/powershell-script-deployment-cleanup.md) 来完成步骤1和2。</span><span class="sxs-lookup"><span data-stu-id="cd85f-174">You can also use our [Teams deployment clean up script](scripts/powershell-script-deployment-cleanup.md) to complete steps 1 and 2.</span></span>  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="cd85f-175">阻止 Teams 在安装后自动启动</span><span class="sxs-lookup"><span data-stu-id="cd85f-175">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="cd85f-176">MSI 的默认行为是在用户登录时立即安装 Teams 应用，然后自动启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="cd85f-176">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="cd85f-177">如果不希望 Teams 在安装之后对用户自动启动，则可以使用组策略设置策略设置，或者禁用 MSI 安装程序自动启用。</span><span class="sxs-lookup"><span data-stu-id="cd85f-177">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="cd85f-178">使用组策略（推荐）</span><span class="sxs-lookup"><span data-stu-id="cd85f-178">Use Group Policy (recommended)</span></span>

<span data-ttu-id="cd85f-179">启用 **阻止 Microsoft Teams 在安装后自动启动** 组策略设置。</span><span class="sxs-lookup"><span data-stu-id="cd85f-179">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="cd85f-180">可在 User Configuration\Policies\Administrative Templates\Microsoft Teams 中找到此策略设置。</span><span class="sxs-lookup"><span data-stu-id="cd85f-180">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="cd85f-181">推荐使用此方法，因为你可以根据组织需要关闭或启用策略设置。</span><span class="sxs-lookup"><span data-stu-id="cd85f-181">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="cd85f-182">如果在安装 Teams 前启用此策略设置，则Teams 将不会在用户登录 Windows 时自动启动。</span><span class="sxs-lookup"><span data-stu-id="cd85f-182">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="cd85f-183">用户首次登录 Teams 之后，Teams 将在用户下次登录时自动启动。</span><span class="sxs-lookup"><span data-stu-id="cd85f-183">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="cd85f-184">如需了解更多信息，请参阅[使用组策略阻止 Teams 在安装后自动启动](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-184">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="cd85f-185">如果已部署 Teams 并且想要设置此策略以禁用 Teams 自动启动，请先将组策略设置设为想要的值，然后对每个用户运行 [Teams 自动启动重置脚本](scripts/powershell-script-teams-reset-autostart.md)。</span><span class="sxs-lookup"><span data-stu-id="cd85f-185">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="cd85f-186">禁用 MSI 安装程序自动启动</span><span class="sxs-lookup"><span data-stu-id="cd85f-186">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="cd85f-187">可以使用如下所示的 **OPTIONS="noAutoStart=true"** 参数禁用 MSI 安装程序自动启动。</span><span class="sxs-lookup"><span data-stu-id="cd85f-187">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="cd85f-188">对于32位版本：</span><span class="sxs-lookup"><span data-stu-id="cd85f-188">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="cd85f-189">对于64位版本：</span><span class="sxs-lookup"><span data-stu-id="cd85f-189">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="cd85f-190">当用户登录 Windows 时，Teams 已通过 MSI 安装并且启动 Teams 的快捷方式已添加至用户桌面。</span><span class="sxs-lookup"><span data-stu-id="cd85f-190">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="cd85f-191">在用户手动启动 Teams 之前，它不会启动。</span><span class="sxs-lookup"><span data-stu-id="cd85f-191">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="cd85f-192">用户手动启动 Teams 之后，无论用户何时登录，Teams 均会自动启动。</span><span class="sxs-lookup"><span data-stu-id="cd85f-192">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="cd85f-193">请注意，这些示例还使用 **ALLUSERS = 1** 参数。</span><span class="sxs-lookup"><span data-stu-id="cd85f-193">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="cd85f-194">设置此参数时，团队 Machine-Wide 安装程序的 "程序和功能" 将显示在 "控制面板" 的 "程序和功能" 和 "适用于计算机的所有用户的 Windows 设置" & 功能中。</span><span class="sxs-lookup"><span data-stu-id="cd85f-194">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="cd85f-195">如果团队拥有计算机上的管理员凭据，则所有用户都可以卸载团队。</span><span class="sxs-lookup"><span data-stu-id="cd85f-195">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="cd85f-196">如果手动运行 MSI，请确保使用已提升的权限运行它。</span><span class="sxs-lookup"><span data-stu-id="cd85f-196">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="cd85f-197">即便以管理员身份而不是使用已提升的权限运行 MSI，安装程序也无法将选项配置为禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="cd85f-197">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
