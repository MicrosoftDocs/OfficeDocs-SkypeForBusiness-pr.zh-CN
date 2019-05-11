---
title: 通过 SCCM 使用 MSI 安装 Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea2f6b85dc4802f2caac4df5b69754d27e8fb9a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33899014"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="2f200-103">使用 MSI 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2f200-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="2f200-104">观看下面的会话，若要了解有关 Windows 桌面客户端、 如何规划其以及如何将其部署的优势：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="2f200-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="2f200-105">若要使用广泛部署 System Center Configuration Manager，组策略或任何第三方分发机制，Microsoft 提供了管理员可以使用批量部署团队选择的 MSI 文件 （ [32 位](https://aka.ms/teams32bitmsi)和[64 位](https://aka.ms/teams64bitmsi)）用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="2f200-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="2f200-106">管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="2f200-107">在部署时，团队将自动启动的所有用户登录的计算机。</span><span class="sxs-lookup"><span data-stu-id="2f200-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="2f200-108">（您可以禁用自动启动后安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f200-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="2f200-109">[请参见下文](#disable-auto-launch-for-the-msi-installer)。）我们建议您部署包到计算机，这样的计算机的所有新用户也将从此部署中获益。</span><span class="sxs-lookup"><span data-stu-id="2f200-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="2f200-110">若要了解有关 SCCM 的详细信息，请参阅[Introduction 到 System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="2f200-110">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="2f200-111">部署过程 （推荐）</span><span class="sxs-lookup"><span data-stu-id="2f200-111">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="2f200-112">检索的最新程序包。</span><span class="sxs-lookup"><span data-stu-id="2f200-112">Retrieve the latest package.</span></span>
2. <span data-ttu-id="2f200-113">使用默认值由 MSI 预填充。</span><span class="sxs-lookup"><span data-stu-id="2f200-113">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="2f200-114">部署到计算机时可能。</span><span class="sxs-lookup"><span data-stu-id="2f200-114">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="2f200-115">Microsoft 团队 MSI 数据包的工作原理</span><span class="sxs-lookup"><span data-stu-id="2f200-115">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="2f200-116">PC 安装</span><span class="sxs-lookup"><span data-stu-id="2f200-116">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="2f200-117">有关如何将团队部署到虚拟 DesktopInfrastructure (VDI) 环境的指南，请参阅[VDI 安装](#vdi-installation)。</span><span class="sxs-lookup"><span data-stu-id="2f200-117">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="2f200-118">团队 MSI 将安装程序置于 Program Files。</span><span class="sxs-lookup"><span data-stu-id="2f200-118">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="2f200-119">只要用户迹象到新的 Windows 用户配置文件，将启动安装程序和一份团队应用程序将安装该用户的应用程序数据文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2f200-119">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="2f200-120">如果用户已安装应用程序数据文件夹中的团队应用程序，MSI 安装程序将跳过该用户的过程。</span><span class="sxs-lookup"><span data-stu-id="2f200-120">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="2f200-121">不要使用 MSI 部署更新，因为客户端检测到新版本可从服务时将自动更新。</span><span class="sxs-lookup"><span data-stu-id="2f200-121">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="2f200-122">若要重新部署最新的安装程序，请使用如下所述的 MSI 中重新部署的过程。</span><span class="sxs-lookup"><span data-stu-id="2f200-122">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="2f200-123">如果您部署的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。</span><span class="sxs-lookup"><span data-stu-id="2f200-123"> If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="2f200-124">如果部署获取非常旧版本，MSI 将触发应用程序更新之前用户能够使用团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-124">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="2f200-125">我们不建议您更改默认安装位置，因为这可能会中断的更新流程。</span><span class="sxs-lookup"><span data-stu-id="2f200-125">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="2f200-126">具有太旧版本最终将阻止用户访问服务。</span><span class="sxs-lookup"><span data-stu-id="2f200-126">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="2f200-127">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="2f200-127">Target computer requirements</span></span>

- <span data-ttu-id="2f200-128">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2f200-128">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="2f200-129">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="2f200-129">Windows 7 or later</span></span>
- <span data-ttu-id="2f200-130">3 GB 的磁盘空间，每个用户配置文件 （推荐）</span><span class="sxs-lookup"><span data-stu-id="2f200-130">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="2f200-131">VDI 安装</span><span class="sxs-lookup"><span data-stu-id="2f200-131">VDI installation</span></span>

<span data-ttu-id="2f200-132">下面是部署团队桌面应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="2f200-132">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="2f200-133">完整的指南，请参阅[虚拟化桌面基础结构团队](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="2f200-133">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="2f200-134">下载团队 MSI 程序包使用具体取决于环境的以下链接之一。</span><span class="sxs-lookup"><span data-stu-id="2f200-134">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="2f200-135">建议 VDI vm 与 64 位操作系统的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="2f200-135">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="2f200-136">32 位版本</span><span class="sxs-lookup"><span data-stu-id="2f200-136">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="2f200-137">64 位版本</span><span class="sxs-lookup"><span data-stu-id="2f200-137">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="2f200-138">运行以下命令以安装 VDI VM MSI （或完成更新它）。</span><span class="sxs-lookup"><span data-stu-id="2f200-138">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="2f200-139">此安装程序文件的团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-139">This installs Teams to Program Files.</span></span> <span data-ttu-id="2f200-140">此时，金色映像安装已完成。</span><span class="sxs-lookup"><span data-stu-id="2f200-140">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="2f200-141">下一个交互式登录会话启动团队，并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="2f200-141">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="2f200-142">请注意，不能使用 ALLUSER 属性 VDI 上安装团队时禁用自动启动的团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-142">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="2f200-143">运行以下命令以卸载从 VDI 虚拟机的 MSI （或准备更新它）。</span><span class="sxs-lookup"><span data-stu-id="2f200-143">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="2f200-144">这将从 Program Files 卸载团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-144">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="2f200-145">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="2f200-145">Clean up and redeployment procedure</span></span>

<span data-ttu-id="2f200-146">如果用户从其用户配置文件中卸载团队，MSI 安装程序将跟踪用户已卸载团队应用程序和不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-146">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="2f200-147">若要重新团队部署为此用户其中它已卸载特定计算机上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2f200-147">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="2f200-148">卸载团队应用程序安装每个用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="2f200-148">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="2f200-149">卸载后，删除目录以递归方式 %localappdata%\microsoft\teams\ 下。</span><span class="sxs-lookup"><span data-stu-id="2f200-149">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="2f200-150">重新部署特定计算机的 MSI 数据包。</span><span class="sxs-lookup"><span data-stu-id="2f200-150">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="2f200-151">您可以使用我们[的 Microsoft 团队部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)的脚本完成通过 SCCM 的步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="2f200-151">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="2f200-152">禁用自动启动的 MSI 安装程序</span><span class="sxs-lookup"><span data-stu-id="2f200-152">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="2f200-153">MSI 默认行为是安装团队客户端，只要用户使用登录，然后自动启动团队。</span><span class="sxs-lookup"><span data-stu-id="2f200-153">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="2f200-154">您可以如下所示修改此行为与以下参数：</span><span class="sxs-lookup"><span data-stu-id="2f200-154">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="2f200-155">当用户登录到 Windows 时，将使用 MSI 安装团队</span><span class="sxs-lookup"><span data-stu-id="2f200-155">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="2f200-156">但是，团队客户端之前不会启动用户已手动启动团队</span><span class="sxs-lookup"><span data-stu-id="2f200-156">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="2f200-157">将用户的桌面上添加一个快捷方式，以启动团队</span><span class="sxs-lookup"><span data-stu-id="2f200-157">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="2f200-158">手动启动后，团队将自动启动时用户登录</span><span class="sxs-lookup"><span data-stu-id="2f200-158">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="2f200-159">32 位版本</span><span class="sxs-lookup"><span data-stu-id="2f200-159">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="2f200-160">64 位版本</span><span class="sxs-lookup"><span data-stu-id="2f200-160">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="2f200-161">如果手动运行 MSI，请务必运行以提升的权限。</span><span class="sxs-lookup"><span data-stu-id="2f200-161">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="2f200-162">即使您运行它作为管理员，但不运行以提升的权限，安装程序不能配置选项后，可以禁用自动启动。</span><span class="sxs-lookup"><span data-stu-id="2f200-162">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
