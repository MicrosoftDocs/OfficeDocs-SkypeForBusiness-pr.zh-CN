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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824933"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="40090-103">安装 Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="40090-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="40090-104">本文介绍如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="40090-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="40090-105">这些说明适用于 Azure 云 Shell、Linux、macOS 和 Windows 平台。 [Azure Cloud Shell](/azure/cloud-shell/overview)</span><span class="sxs-lookup"><span data-stu-id="40090-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="40090-106">要求</span><span class="sxs-lookup"><span data-stu-id="40090-106">Requirements</span></span>

<span data-ttu-id="40090-107">Teams PowerShell 要求所有平台上使用 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="40090-107">Teams PowerShell requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="40090-108">安装[适用于你的操作系统的最新版 PowerShell。](/powershell/scripting/install/installing-powershell)</span><span class="sxs-lookup"><span data-stu-id="40090-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span>

> [!WARNING]
> <span data-ttu-id="40090-109">PowerShell 7 和 Teams PowerShell 存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="40090-109">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="40090-110">为获得最佳体验，我们建议使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="40090-110">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="40090-111">安装 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="40090-111">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="40090-112">为了获得最佳体验，请使用 GA 或公 (共) 体中的) 功能，而不是使用两者都可使用。</span><span class="sxs-lookup"><span data-stu-id="40090-112">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="40090-113">这些按钮不要协同工作。</span><span class="sxs-lookup"><span data-stu-id="40090-113">They're not intended to work together.</span></span>


<span data-ttu-id="40090-114">使用 **PowerShellGet** cmdlet 安装 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="40090-114">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="40090-115">为系统上的所有用户安装模块需要具有提升的权限。</span><span class="sxs-lookup"><span data-stu-id="40090-115">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="40090-116">使用 Windows 中的"以管理员身份 **运行"启动** PowerShell 会话，或在 `sudo` macOS 或 Linux 上使用命令：</span><span class="sxs-lookup"><span data-stu-id="40090-116">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="40090-117">默认情况下，PowerShell (库管理器与 **powerShellGet**的受) 信任存储库而未配置为受信任的存储库。</span><span class="sxs-lookup"><span data-stu-id="40090-117">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="40090-118">首次使用 PSGallery 时，您会看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="40090-118">The first time you use the PSGallery, you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="40090-119">对所有年**的解\*\*\*\*答或是**"是"以继续安装。</span><span class="sxs-lookup"><span data-stu-id="40090-119">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="40090-120">安装 Teams PowerShell 公共预览</span><span class="sxs-lookup"><span data-stu-id="40090-120">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="40090-121">如果你使用的是 Teams PowerShell 的公共预览版，我们强烈建议首先卸载 Skype for Business Online Connector。</span><span class="sxs-lookup"><span data-stu-id="40090-121">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="40090-122">为系统上的所有用户安装 Teams PowerShell 公共预览版模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="40090-122">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="40090-123">使用 Windows 中的"以管理员身份 **运行"启动** PowerShell 会话，或在 `sudo` macOS 或 Linux 上使用命令。</span><span class="sxs-lookup"><span data-stu-id="40090-123">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="40090-124">如果使用 PowerShell 5.1，则必须提前更新 **PowerShellGet** 模块。</span><span class="sxs-lookup"><span data-stu-id="40090-124">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="40090-125">更新**PowerShellGet**后，请关闭并重新打开提级的 PowerShell 会话，以确保加载最新的**PowerShellGet。**</span><span class="sxs-lookup"><span data-stu-id="40090-125">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="40090-126">若要安装 Teams PowerShell 公共预览版，请运行以下 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="40090-126">To install Teams PowerShell public preview, run the PowerShell command below.</span></span>

> [!NOTE]
> <span data-ttu-id="40090-127">可通过运行"查找模块 -AllowPrerelease"，在 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 库或 PowerShell 中找到最新预览版本</span><span class="sxs-lookup"><span data-stu-id="40090-127">You can find the latest preview version at [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) or in PowerShell by running "Find-Module MicrosoftTeams -AllowPrerelease"</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="40090-128">安装 Skype for Business Online Connector</span><span class="sxs-lookup"><span data-stu-id="40090-128">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="40090-129">Skype for Business Online 连接器当前是 Teams PowerShell 公共预览版的一部分。</span><span class="sxs-lookup"><span data-stu-id="40090-129">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="40090-130">在我们将此功能推出到 Teams PowerShell 的 GA 版本中后，Skype for Business Online 连接器将不再可用。</span><span class="sxs-lookup"><span data-stu-id="40090-130">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="40090-131">下载并安装 [Skype for Business PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在 PowerShell 中运行以下内容。</span><span class="sxs-lookup"><span data-stu-id="40090-131">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="40090-132">登录</span><span class="sxs-lookup"><span data-stu-id="40090-132">Sign in</span></span>

<span data-ttu-id="40090-133">要开始使用 Teams PowerShell，请使用 Azure 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="40090-133">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="40090-134">如果你使用的是最新的 Teams [PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype for Business Online Connector。</span><span class="sxs-lookup"><span data-stu-id="40090-134">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="40090-135">更新 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="40090-135">Update Teams PowerShell</span></span>

<span data-ttu-id="40090-136">若要更新 Teams PowerShell，请打开一个新的增强的 PowerShell 命令提示符，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="40090-136">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="40090-137">如果已将 Teams PowerShell 导入 PowerShell 会话中，更新模块将失败。</span><span class="sxs-lookup"><span data-stu-id="40090-137">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="40090-138">关闭 PowerShell 并重新打开一个新的提级 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="40090-138">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="40090-139">卸载 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="40090-139">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="40090-140">若要卸载 Teams PowerShell，请打开一个新的增强的 PowerShell 命令提示符，并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="40090-140">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="40090-141">如果已将 Teams PowerShell 导入 PowerShell 会话中，则卸载模块将失败。</span><span class="sxs-lookup"><span data-stu-id="40090-141">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="40090-142">关闭 PowerShell 并重新打开一个新的提级 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="40090-142">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="40090-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="40090-143">Next Steps</span></span>

<span data-ttu-id="40090-144">现在，你就可以使用 Teams PowerShell 管理 Teams。</span><span class="sxs-lookup"><span data-stu-id="40090-144">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="40090-145">请参阅 [使用 Teams 和 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="40090-145">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="40090-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="40090-146">Related topics</span></span>

[<span data-ttu-id="40090-147">使用 Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="40090-147">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="40090-148">Teams PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="40090-148">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="40090-149">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="40090-149">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="40090-150">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="40090-150">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
