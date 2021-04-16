---
title: 安装 Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何使用 PowerShell 控件管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768333"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="10f48-103">安装 Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="10f48-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="10f48-104">本文介绍如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="10f48-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="10f48-105">这些说明在 [Azure Cloud](/azure/cloud-shell/overview)Shell、Linux、macOS 和 Windows 平台上工作。</span><span class="sxs-lookup"><span data-stu-id="10f48-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="10f48-106">要求</span><span class="sxs-lookup"><span data-stu-id="10f48-106">Requirements</span></span>

<span data-ttu-id="10f48-107">Teams PowerShell 要求在所有平台上使用 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="10f48-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="10f48-108">安装[适用于操作系统的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)</span><span class="sxs-lookup"><span data-stu-id="10f48-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!NOTE]
> <span data-ttu-id="10f48-109">为获得最佳体验，建议使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="10f48-109">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="10f48-110">安装 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="10f48-110">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="10f48-111">为获得最佳体验，请使用公开发布版 (GA) 公共预览版模块 - 而不是同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="10f48-111">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="10f48-112">它们并非旨在协同工作。</span><span class="sxs-lookup"><span data-stu-id="10f48-112">They're not intended to work together.</span></span>


<span data-ttu-id="10f48-113">使用 **PowerShellGet** cmdlet 安装 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="10f48-113">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="10f48-114">为系统上的所有用户安装模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="10f48-114">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="10f48-115">使用在 Windows 中 **以管理员** 角色运行或在 macOS 或 Linux 上使用 命令启动 PowerShell `sudo` 会话：</span><span class="sxs-lookup"><span data-stu-id="10f48-115">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="10f48-116">默认情况下，PSGallery (PowerShell 库) 未配置为 **PowerShellGet** 的受信任存储库。</span><span class="sxs-lookup"><span data-stu-id="10f48-116">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="10f48-117">首次使用 PSGallery 时，会看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="10f48-117">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="10f48-118">对 **"** 全部 **"回答"** 是"或"是"以继续安装。</span><span class="sxs-lookup"><span data-stu-id="10f48-118">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="sign-in"></a><span data-ttu-id="10f48-119">登录</span><span class="sxs-lookup"><span data-stu-id="10f48-119">Sign in</span></span>

<span data-ttu-id="10f48-120">若要开始使用 Teams PowerShell，请通过 Azure 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="10f48-120">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="10f48-121">如果你使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公共预览版 ，则不需要安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="10f48-121">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a><span data-ttu-id="10f48-122">使用 MFA 和新式身份验证登录</span><span class="sxs-lookup"><span data-stu-id="10f48-122">Sign in using MFA and modern authentication</span></span>

 <span data-ttu-id="10f48-123">如果帐户使用多重身份验证，请使用本部分中的步骤。</span><span class="sxs-lookup"><span data-stu-id="10f48-123">If your account uses multi-factor authentication, use the steps in this section.</span></span>

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a><span data-ttu-id="10f48-124">更新 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="10f48-124">Update Teams PowerShell</span></span>

<span data-ttu-id="10f48-125">若要更新 Teams PowerShell，请打开新的提升权限的 PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="10f48-125">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="10f48-126">如果 Teams PowerShell 已导入 PowerShell 会话，则更新模块将失败。</span><span class="sxs-lookup"><span data-stu-id="10f48-126">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="10f48-127">关闭 PowerShell，然后重新打开新的提升权限的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="10f48-127">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="10f48-128">卸载 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="10f48-128">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="10f48-129">若要卸载 Teams PowerShell，请打开新的提升权限的 PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="10f48-129">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="10f48-130">如果 Teams PowerShell 已导入 PowerShell 会话，卸载模块将失败。</span><span class="sxs-lookup"><span data-stu-id="10f48-130">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="10f48-131">关闭 PowerShell，然后重新打开新的提升权限的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="10f48-131">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="10f48-132">安装 Teams PowerShell 公共预览版</span><span class="sxs-lookup"><span data-stu-id="10f48-132">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="10f48-133">如果你使用的是 Teams PowerShell 的公共预览版，我们强烈建议你首先卸载 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="10f48-133">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="10f48-134">为系统上的所有用户安装 Teams PowerShell 公共预览版模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="10f48-134">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="10f48-135">使用在 Windows 中 **以管理员** 角色运行或在 macOS 或 Linux 上使用 命令启动 PowerShell `sudo` 会话。</span><span class="sxs-lookup"><span data-stu-id="10f48-135">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="10f48-136">如果使用 PowerShell 5.1，必须事先更新 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="10f48-136">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="10f48-137">更新 **PowerShellGet** 后，关闭并重新打开提升权限的 PowerShell 会话，以确保加载最新的 **PowerShellGet。**</span><span class="sxs-lookup"><span data-stu-id="10f48-137">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="10f48-138">若要安装 Teams PowerShell 公共预览版，请运行下面的 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="10f48-138">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="10f48-139">可以通过运行"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"在 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 库或 PowerShell 中查找最新的预览版本</span><span class="sxs-lookup"><span data-stu-id="10f48-139">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a><span data-ttu-id="10f48-140">后续步骤</span><span class="sxs-lookup"><span data-stu-id="10f48-140">Next Steps</span></span>

<span data-ttu-id="10f48-141">现在，可以使用 Teams PowerShell 管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="10f48-141">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="10f48-142">请参阅 [使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以开始。</span><span class="sxs-lookup"><span data-stu-id="10f48-142">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10f48-143">相关主题</span><span class="sxs-lookup"><span data-stu-id="10f48-143">Related topics</span></span>

[<span data-ttu-id="10f48-144">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="10f48-144">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="10f48-145">Teams PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="10f48-145">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="10f48-146">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="10f48-146">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="10f48-147">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="10f48-147">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
