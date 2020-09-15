---
title: 安装 Microsoft 团队 PowerShell
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
description: 了解如何使用 PowerShell 控件管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: f008d154099c57376fca914d576d7c9df4487780
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814461"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="3ef29-103">安装 Microsoft 团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef29-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="3ef29-104">本文介绍如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft 团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="3ef29-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="3ef29-105">这些说明适用于 [Azure 云 Shell](/azure/cloud-shell/overview)、Linux、MacOS 和 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="3ef29-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ef29-106">要求</span><span class="sxs-lookup"><span data-stu-id="3ef29-106">Requirements</span></span>

<span data-ttu-id="3ef29-107">团队 PowerShell 需要在所有平台上安装 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3ef29-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="3ef29-108">安装适用于你的操作系统的 [最新版本的 PowerShell](/powershell/scripting/install/installing-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="3ef29-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="3ef29-109">PowerShell 7 和团队 PowerShell 存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="3ef29-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="3ef29-110">为了获得最佳体验，我们建议使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="3ef29-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="3ef29-111">安装团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="3ef29-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="3ef29-112">为获得最佳体验，请使用常规可用性 (GA) 或公共预览版模块。</span><span class="sxs-lookup"><span data-stu-id="3ef29-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="3ef29-113">它们不打算协同工作。</span><span class="sxs-lookup"><span data-stu-id="3ef29-113">They're not intended to work together.</span></span>


<span data-ttu-id="3ef29-114">使用 **PowerShellGet** Cmdlet 安装团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="3ef29-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="3ef29-115">为系统上的所有用户安装模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="3ef29-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="3ef29-116">使用 Windows 中的 "以 **管理员身份运行** " 或使用 `sudo` macOS 或 Linux 上的命令启动 PowerShell 会话：</span><span class="sxs-lookup"><span data-stu-id="3ef29-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="3ef29-117">默认情况下，PowerShell 库 (PSGallery) 未配置为 **PowerShellGet**的受信任存储库。</span><span class="sxs-lookup"><span data-stu-id="3ef29-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="3ef29-118">首次使用 PSGallery 时，您将看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="3ef29-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="3ef29-119">回答 **"是"** 或 **"是"** ，以继续安装。</span><span class="sxs-lookup"><span data-stu-id="3ef29-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="3ef29-120">安装团队 PowerShell 公共预览版</span><span class="sxs-lookup"><span data-stu-id="3ef29-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="3ef29-121">如果你使用的是团队 PowerShell 的公共预览版，我们强烈建议你首先卸载 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="3ef29-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="3ef29-122">为系统上的所有用户安装团队 PowerShell 公共预览版模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="3ef29-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="3ef29-123">使用 Windows 中的 "以 **管理员身份运行** " 或使用 `sudo` macOS 或 Linux 上的命令启动 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3ef29-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="3ef29-124">如果您使用的是 PowerShell 5.1，则必须事先更新 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="3ef29-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="3ef29-125">更新 **PowerShellGet**后，关闭并重新打开提升的 PowerShell 会话，以确保加载最新的 **PowerShellGet** 。</span><span class="sxs-lookup"><span data-stu-id="3ef29-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="3ef29-126">若要安装团队 PowerShell 公共预览版，请运行以下 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3ef29-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="3ef29-127">你可以通过运行 "Find-Module MicrosoftTeams-AllowPrerelease"，在 [Powershell 库](https://www.powershellgallery.com/packages/MicrosoftTeams) 或 powershell 中找到最新的预览版版本</span><span class="sxs-lookup"><span data-stu-id="3ef29-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="3ef29-128">安装 Skype for Business Online 连接器</span><span class="sxs-lookup"><span data-stu-id="3ef29-128">Install the Skype for Business Online Connector</span></span>

> [!NOTE]
>
> <span data-ttu-id="3ef29-129">Skype for Business Online 连接器目前是最新团队 PowerShell 模块的一部分。</span><span class="sxs-lookup"><span data-stu-id="3ef29-129">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
> <span data-ttu-id="3ef29-130">如果您使用的是最新的 [团队 PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="3ef29-130">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="3ef29-131">登录</span><span class="sxs-lookup"><span data-stu-id="3ef29-131">Sign in</span></span>

<span data-ttu-id="3ef29-132">若要开始使用团队 PowerShell，请使用你的 Azure 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3ef29-132">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="3ef29-133">如果您使用的是最新的 [团队 PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="3ef29-133">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="3ef29-134">更新团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef29-134">Update Teams PowerShell</span></span>

<span data-ttu-id="3ef29-135">若要更新团队 PowerShell，请打开新的提升的 PowerShell 命令提示符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3ef29-135">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="3ef29-136">如果团队 PowerShell 已导入到你的 PowerShell 会话中，更新模块将失败。</span><span class="sxs-lookup"><span data-stu-id="3ef29-136">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="3ef29-137">关闭 PowerShell 并重新打开一个新的已提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3ef29-137">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="3ef29-138">卸载团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ef29-138">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="3ef29-139">若要卸载团队 PowerShell，请打开新的提升的 PowerShell 命令提示符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3ef29-139">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="3ef29-140">如果团队 PowerShell 已导入你的 PowerShell 会话，则卸载该模块将失败。</span><span class="sxs-lookup"><span data-stu-id="3ef29-140">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="3ef29-141">关闭 PowerShell 并重新打开一个新的已提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3ef29-141">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ef29-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3ef29-142">Next Steps</span></span>

<span data-ttu-id="3ef29-143">现在，你已准备好使用团队 PowerShell 管理团队。</span><span class="sxs-lookup"><span data-stu-id="3ef29-143">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="3ef29-144">请参阅 [使用团队 PowerShell 管理团队](teams-powershell-managing-teams.md) 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="3ef29-144">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ef29-145">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ef29-145">Related topics</span></span>

[<span data-ttu-id="3ef29-146">通过团队 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="3ef29-146">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="3ef29-147">团队 PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="3ef29-147">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="3ef29-148">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="3ef29-148">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="3ef29-149">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="3ef29-149">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
