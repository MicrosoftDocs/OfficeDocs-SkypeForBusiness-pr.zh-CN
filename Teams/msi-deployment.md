---
title: 通过 Microsoft Endpoint Configuration Manager 使用 MSI 安装 Microsoft Teams
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a17b9ed78f484f593715a551fd11fa158bd6262a
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892202"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2b78c-103">使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b78c-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="2b78c-104">观看以下会话以了解 Windows 桌面客户端的优势，如何规划它，以及如何部署它：[Teams Windows 桌面客户端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="2b78c-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="2b78c-105">为了使用 Microsoft Endpoint Configuration Manager 或组策略或任何第三方分发机制以进行广泛部署，Microsoft 提供了 MSI 文件（32 位和 64 位），供管理员用于将 Teams 批量部署至选定的用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="2b78c-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2b78c-106">管理员可以使用这些文件远程部署 Teams，使用户无需手动下载 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="2b78c-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2b78c-107">部署后，对于登录至计算机上的所有用户，Teams 将会自动启用。</span><span class="sxs-lookup"><span data-stu-id="2b78c-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2b78c-108">（你可以在安装此应用之后禁用自动启用。</span><span class="sxs-lookup"><span data-stu-id="2b78c-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2b78c-109">[请参阅下面的](#disable-auto-launch-for-the-msi-installer)。）建议你将程序包部署至计算机，以便该计算机上的所有新用户均可从此部署中受益。</span><span class="sxs-lookup"><span data-stu-id="2b78c-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="2b78c-110">以下是 MSI 文件的链接：</span><span class="sxs-lookup"><span data-stu-id="2b78c-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="2b78c-111">实体</span><span class="sxs-lookup"><span data-stu-id="2b78c-111">Entity</span></span>  |<span data-ttu-id="2b78c-112">32 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-112">32 bit</span></span>      |<span data-ttu-id="2b78c-113">64 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-113">64 bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="2b78c-114">商用</span><span class="sxs-lookup"><span data-stu-id="2b78c-114">Commercial</span></span>     | [<span data-ttu-id="2b78c-115">32 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-115">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="2b78c-116">64 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-116">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="2b78c-117">联邦政府 - GCC</span><span class="sxs-lookup"><span data-stu-id="2b78c-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="2b78c-118">32 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-118">32 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="2b78c-119">64 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-119">64 bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="2b78c-120">联邦政府 - GCC High</span><span class="sxs-lookup"><span data-stu-id="2b78c-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="2b78c-121">32 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-121">32 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="2b78c-122">64 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-122">64 bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="2b78c-123">联邦政府 - DoD</span><span class="sxs-lookup"><span data-stu-id="2b78c-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="2b78c-124">32 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-124">32 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="2b78c-125">64 位</span><span class="sxs-lookup"><span data-stu-id="2b78c-125">64 bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

<span data-ttu-id="2b78c-126">Office 365 专业增强版部署中页包括 Teams。</span><span class="sxs-lookup"><span data-stu-id="2b78c-126">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="2b78c-127">有关详细信息，请参阅[使用 Office 365 专业增强版部署 Microsoft Teams](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="2b78c-127">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="2b78c-128">如需了解与 Microsoft Endpoint Configuration Manager 相关的详细信息，请参阅[什么是 Configuration Manager？](https://docs.microsoft.com/configmgr/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="2b78c-128">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2b78c-129">部署过程（推荐）</span><span class="sxs-lookup"><span data-stu-id="2b78c-129">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="2b78c-130">检索最新程序包。</span><span class="sxs-lookup"><span data-stu-id="2b78c-130">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2b78c-131">使用由 MSI 预填充的默认值。</span><span class="sxs-lookup"><span data-stu-id="2b78c-131">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2b78c-132">部署到计算机（如可能）。</span><span class="sxs-lookup"><span data-stu-id="2b78c-132">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2b78c-133">Microsoft Teams MSI 程序包的工作原理</span><span class="sxs-lookup"><span data-stu-id="2b78c-133">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="2b78c-134">电脑安装</span><span class="sxs-lookup"><span data-stu-id="2b78c-134">PC installation</span></span>

<span data-ttu-id="2b78c-135">Teams MSI 会将安装程序放置在“Program Files”中。</span><span class="sxs-lookup"><span data-stu-id="2b78c-135">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2b78c-136">无论用户何时登录新的 Windows 用户配置文件，该安装程序均会启用并且 Teams 应用副本将安装在该用户的 `AppData` 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2b78c-136">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="2b78c-137">如果用户已在 `AppData` 文件夹中安装了 Teams 应用，则MSI 安装程序将为该用户跳过此过程。</span><span class="sxs-lookup"><span data-stu-id="2b78c-137">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2b78c-138">请勿使用 MSI 部署更新，因为当客户端从服务中检测到可用的新版本时将会自动更新。</span><span class="sxs-lookup"><span data-stu-id="2b78c-138">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2b78c-139">要冲虚部署最新的安装程序，请使用下述重新部署 MSI 流程。</span><span class="sxs-lookup"><span data-stu-id="2b78c-139">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="2b78c-140">如果部署的是旧版的 MSI 程序包，则除了在 VDI 环境中以外，客户端将为用户自动更新（如可能）。</span><span class="sxs-lookup"><span data-stu-id="2b78c-140">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="2b78c-141">如果部署的是非常旧的版本，则在用户能够使用 Teams 之前，MSI 将会触发应用更新。</span><span class="sxs-lookup"><span data-stu-id="2b78c-141">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="2b78c-142">不建议更改默认安装位置，因为这可能会中断更新流。</span><span class="sxs-lookup"><span data-stu-id="2b78c-142">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2b78c-143">版本太旧最终会阻止用户访问服务。</span><span class="sxs-lookup"><span data-stu-id="2b78c-143">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="2b78c-144">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="2b78c-144">Target computer requirements</span></span>

- <span data-ttu-id="2b78c-145">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2b78c-145">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2b78c-146">Windows 8.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2b78c-146">Windows 8.1 or later</span></span>
- <span data-ttu-id="2b78c-147">Windows Server 2012 R2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2b78c-147">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="2b78c-148">每个用户配置文件 3 GB 磁盘空间（推荐）</span><span class="sxs-lookup"><span data-stu-id="2b78c-148">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="2b78c-149">VDI 安装</span><span class="sxs-lookup"><span data-stu-id="2b78c-149">VDI installation</span></span>

<span data-ttu-id="2b78c-150">如需如何在 VDI 上部署 Teams 桌面应用的完整指南，请参阅[适用于虚拟化桌面基础结构的 Teams](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="2b78c-150">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2b78c-151">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="2b78c-151">Clean up and redeployment procedure</span></span>

<span data-ttu-id="2b78c-152">如果用户从其用户配置文件中卸载团队，则 MSI 安装程序将跟踪用户已卸载团队应用，并且不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="2b78c-152">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="2b78c-153">要为此用户在已从其中卸载 Teams 的特定计算机上重新部署 Teams，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2b78c-153">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2b78c-154">卸载为每个用户配置文件安装的团队应用。</span><span class="sxs-lookup"><span data-stu-id="2b78c-154">Uninstall the Teams app installed for every user profile.</span></span>
2. <span data-ttu-id="2b78c-155">卸载后，在下`%localappdata%\Microsoft\Teams\`递归删除目录。</span><span class="sxs-lookup"><span data-stu-id="2b78c-155">After uninstall, delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="2b78c-156">将 MSI 程序包重新部署到该特定计算机。</span><span class="sxs-lookup"><span data-stu-id="2b78c-156">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="2b78c-157">阻止 Teams 在安装后自动启动</span><span class="sxs-lookup"><span data-stu-id="2b78c-157">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="2b78c-158">MSI 的默认行为是在用户登录时立即安装 Teams 应用，然后自动启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="2b78c-158">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2b78c-159">如果不希望 Teams 在安装之后对用户自动启动，则可以使用组策略设置策略设置，或者禁用 MSI 安装程序自动启用。</span><span class="sxs-lookup"><span data-stu-id="2b78c-159">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="2b78c-160">使用组策略（推荐）</span><span class="sxs-lookup"><span data-stu-id="2b78c-160">Use Group Policy (recommended)</span></span>

<span data-ttu-id="2b78c-161">启用**阻止 Microsoft Teams 在安装后自动启动**组策略设置。</span><span class="sxs-lookup"><span data-stu-id="2b78c-161">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="2b78c-162">可在 User Configuration\Policies\Administrative Templates\Microsoft Teams 中找到此策略设置。</span><span class="sxs-lookup"><span data-stu-id="2b78c-162">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="2b78c-163">推荐使用此方法，因为你可以根据组织需要关闭或启用策略设置。</span><span class="sxs-lookup"><span data-stu-id="2b78c-163">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="2b78c-164">如果在安装 Teams 前启用此策略设置，则Teams 将不会在用户登录 Windows 时自动启动。</span><span class="sxs-lookup"><span data-stu-id="2b78c-164">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="2b78c-165">用户首次登录 Teams 之后，Teams 将在用户下次登录时自动启动。</span><span class="sxs-lookup"><span data-stu-id="2b78c-165">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="2b78c-166">如需了解更多信息，请参阅[使用组策略阻止 Teams 在安装后自动启动](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。</span><span class="sxs-lookup"><span data-stu-id="2b78c-166">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="2b78c-167">如果已部署 Teams 并且想要设置此策略以禁用 Teams 自动启动，请先将组策略设置设为想要的值，然后对每个用户运行 [Teams 自动启动重置脚本](scripts/powershell-script-teams-reset-autostart.md)。</span><span class="sxs-lookup"><span data-stu-id="2b78c-167">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2b78c-168">禁用 MSI 安装程序自动启动</span><span class="sxs-lookup"><span data-stu-id="2b78c-168">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2b78c-169">可以使用如下所示的 **OPTIONS="noAutoStart=true"** 参数禁用 MSI 安装程序自动启动。</span><span class="sxs-lookup"><span data-stu-id="2b78c-169">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="2b78c-170">对于 32 位版本</span><span class="sxs-lookup"><span data-stu-id="2b78c-170">For the 32-bit version</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="2b78c-171">对于 64 位版本</span><span class="sxs-lookup"><span data-stu-id="2b78c-171">For the 64-bit version</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="2b78c-172">当用户登录 Windows 时，Teams 已通过 MSI 安装并且启动 Teams 的快捷方式已添加至用户桌面。</span><span class="sxs-lookup"><span data-stu-id="2b78c-172">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="2b78c-173">在用户手动启动 Teams 之前，它不会启动。</span><span class="sxs-lookup"><span data-stu-id="2b78c-173">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="2b78c-174">用户手动启动 Teams 之后，无论用户何时登录，Teams 均会自动启动。</span><span class="sxs-lookup"><span data-stu-id="2b78c-174">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="2b78c-175">请注意，这些示例还使用**ALLUSERS = 1**参数。</span><span class="sxs-lookup"><span data-stu-id="2b78c-175">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="2b78c-176">设置此参数时，团队计算机范围的安装程序将显示在 "控制面板" 的 "程序和功能" 和 "应用程序" 中的 "Windows 设置" 中的 "应用 & 功能" 中。</span><span class="sxs-lookup"><span data-stu-id="2b78c-176">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="2b78c-177">如果团队拥有计算机上的管理员凭据，则所有用户都可以卸载团队。</span><span class="sxs-lookup"><span data-stu-id="2b78c-177">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="2b78c-178">如果手动运行 MSI，请确保使用已提升的权限运行它。</span><span class="sxs-lookup"><span data-stu-id="2b78c-178">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2b78c-179">即便以管理员身份而不是使用已提升的权限运行 MSI，安装程序也无法将选项配置为禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="2b78c-179">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
