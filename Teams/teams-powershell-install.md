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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944082"
---
# <a name="install-microsoft-teams-powershell"></a><span data-ttu-id="3cfe2-103">安装 Microsoft 团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cfe2-103">Install Microsoft Teams PowerShell</span></span>

<span data-ttu-id="3cfe2-104">本文介绍如何使用[PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft 团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-104">This article explains how to install the Microsoft Teams PowerShell module using [PowerShellGet](/powershell/scripting/gallery/installing-psget).</span></span> <span data-ttu-id="3cfe2-105">这些说明适用于[Azure 云 Shell](/azure/cloud-shell/overview)、Linux、MacOS 和 Windows 平台。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-105">These instructions work on [Azure Cloud Shell](/azure/cloud-shell/overview), Linux, macOS, and Windows platforms.</span></span>

## <a name="requirements"></a><span data-ttu-id="3cfe2-106">要求</span><span class="sxs-lookup"><span data-stu-id="3cfe2-106">Requirements</span></span>

<span data-ttu-id="3cfe2-107">团队 PowerShell 在所有平台上使用 PowerShell 6.2.4 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-107">Teams PowerShell works with PowerShell 6.2.4 and later on all platforms.</span></span> <span data-ttu-id="3cfe2-108">Windows 上的 PowerShell 5.1 也支持它。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-108">It is also supported with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="3cfe2-109">安装适用于你的操作系统的[最新版本的 PowerShell](/powershell/scripting/install/installing-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-109">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> <span data-ttu-id="3cfe2-110">在 PowerShell 6.2.4 和更高版本上运行时，团队 PowerShell 没有其他要求。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-110">Teams PowerShell has no additional requirements when run on PowerShell 6.2.4 and later.</span></span>

> [!WARNING]
> <span data-ttu-id="3cfe2-111">PowerShell 7 和团队 PowerShell 存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-111">There are known issues with PowerShell 7 and Teams PowerShell.</span></span> <span data-ttu-id="3cfe2-112">为了获得最佳体验，我们建议使用 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-112">For the best experience, we recommend that you use PowerShell 5.1.</span></span>

## <a name="install-the-teams-powershell-module"></a><span data-ttu-id="3cfe2-113">安装团队 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="3cfe2-113">Install the Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="3cfe2-114">为获得最佳体验，请使用常规可用性（GA）或公共预览版模块（不是两者）。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-114">For the best experience, use either General Availability (GA) or Public Preview modules - not both.</span></span> <span data-ttu-id="3cfe2-115">它们不打算协同工作。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-115">They're not intended to work together.</span></span>


<span data-ttu-id="3cfe2-116">使用**PowerShellGet** Cmdlet 安装团队 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-116">Use the **PowerShellGet** cmdlets to install the Teams PowerShell module.</span></span> <span data-ttu-id="3cfe2-117">为系统上的所有用户安装模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-117">Installing the module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="3cfe2-118">使用 Windows 中的 "以**管理员身份运行**" 或使用 `sudo` macOS 或 Linux 上的命令启动 PowerShell 会话：</span><span class="sxs-lookup"><span data-stu-id="3cfe2-118">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux:</span></span>

```powershell
Install-Module MicrosoftTeams
```

<span data-ttu-id="3cfe2-119">默认情况下，PowerShell 库（PSGallery）未配置为**PowerShellGet**的受信任存储库。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-119">By default, the PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**.</span></span> <span data-ttu-id="3cfe2-120">首次使用 PSGallery 时，您将看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="3cfe2-120">The first time you use the PSGallery, you'll see the following message:</span></span>

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="3cfe2-121">回答 `Yes` 或 `Yes to All` 继续安装。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-121">Answer `Yes` or `Yes to All` to continue with the installation.</span></span>


## <a name="install-teams-powershell-public-preview"></a><span data-ttu-id="3cfe2-122">安装团队 PowerShell 公共预览版</span><span class="sxs-lookup"><span data-stu-id="3cfe2-122">Install Teams PowerShell public preview</span></span>

> [!NOTE]
> <span data-ttu-id="3cfe2-123">如果你使用的是团队 PowerShell 的公共预览版，我们强烈建议你首先卸载 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-123">If you're using the Public Preview version of Teams PowerShell, we strongly recommend that you first uninstall Skype for Business Online Connector.</span></span>

<span data-ttu-id="3cfe2-124">为系统上的所有用户安装团队 PowerShell 公共预览版模块需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-124">Installing the Teams PowerShell public preview module for all users on a system requires elevated privileges.</span></span> <span data-ttu-id="3cfe2-125">使用 Windows 中的 "以**管理员身份运行**" 或使用 `sudo` macOS 或 Linux 上的命令启动 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-125">Start the PowerShell session using **Run as administrator** in Windows or use the `sudo` command on macOS or Linux.</span></span>

<span data-ttu-id="3cfe2-126">如果您使用的是 PowerShell 5.1，则必须事先更新**PowerShellGet**模块。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-126">If you're using PowerShell 5.1, you must update the **PowerShellGet** module beforehand.</span></span> <span data-ttu-id="3cfe2-127">更新**PowerShellGet**后，关闭并重新打开提升的 PowerShell 会话，以确保加载最新的**PowerShellGet** 。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-127">After you update **PowerShellGet**, close and reopen an elevated PowerShell session to ensure that the latest **PowerShellGet** is loaded.</span></span>

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

<span data-ttu-id="3cfe2-128">若要安装团队 Powershell 公共预览版，请运行以下 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-128">To install Teams Powershell public preview, run the PowerShell command below.</span></span>

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a><span data-ttu-id="3cfe2-129">安装 Skype for Business Online 连接器</span><span class="sxs-lookup"><span data-stu-id="3cfe2-129">Install the Skype for Business Online Connector</span></span>

> [!WARNING]
> <span data-ttu-id="3cfe2-130">Skype for Business Online 连接器目前是团队 PowerShell 公共预览版的一部分。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-130">Skype for Business Online Connector is currently part of Teams PowerShell public preview.</span></span> <span data-ttu-id="3cfe2-131">将此功能汇总到团队 PowerShell 的 GA 版本后，Skype for Business Online 连接器将不再可用。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-131">Once we've rolled this feature into the GA release of Teams PowerShell, Skype for Business Online Connector will no longer be available.</span></span>

<span data-ttu-id="3cfe2-132">下载并安装[Skype for Business PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在 PowerShell 中运行以下内容。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-132">Download and install the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), then run the following in PowerShell.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a><span data-ttu-id="3cfe2-133">登录</span><span class="sxs-lookup"><span data-stu-id="3cfe2-133">Sign in</span></span>

<span data-ttu-id="3cfe2-134">若要开始使用团队 PowerShell，请使用你的 Azure 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-134">To start working with Teams PowerShell, sign in with your Azure credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="3cfe2-135">如果您使用的是最新的[团队 PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-135">If you're using the latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a><span data-ttu-id="3cfe2-136">更新团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cfe2-136">Update Teams PowerShell</span></span>

<span data-ttu-id="3cfe2-137">若要更新团队 PowerShell，请打开新的提升的 PowerShell 命令提示符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3cfe2-137">To update Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="3cfe2-138">如果团队 PowerShell 已导入到你的 PowerShell 会话中，更新模块将失败。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-138">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="3cfe2-139">关闭 PowerShell 并重新打开一个新的已提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-139">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="3cfe2-140">卸载团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3cfe2-140">Uninstall Teams PowerShell</span></span>



<span data-ttu-id="3cfe2-141">若要卸载团队 PowerShell，请打开新的提升的 PowerShell 命令提示符，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3cfe2-141">To uninstall Teams PowerShell, open a new elevated PowerShell command prompt and run the following:</span></span>

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> <span data-ttu-id="3cfe2-142">如果团队 PowerShell 已导入你的 PowerShell 会话，则卸载该模块将失败。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-142">If Teams PowerShell has already been imported into your PowerShell session, uninstalling the module will fail.</span></span> <span data-ttu-id="3cfe2-143">关闭 PowerShell 并重新打开一个新的已提升的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-143">Close PowerShell and re-open a new elevated PowerShell session.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3cfe2-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3cfe2-144">Next Steps</span></span>

<span data-ttu-id="3cfe2-145">现在，你已准备好使用团队 PowerShell 管理团队。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-145">Now you're ready to manage Teams using Teams PowerShell.</span></span> <span data-ttu-id="3cfe2-146">请参阅[使用团队 PowerShell 管理团队](teams-powershell-managing-teams.md)以开始使用。</span><span class="sxs-lookup"><span data-stu-id="3cfe2-146">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3cfe2-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="3cfe2-147">Related topics</span></span>

[<span data-ttu-id="3cfe2-148">通过团队 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="3cfe2-148">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="3cfe2-149">团队 PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="3cfe2-149">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="3cfe2-150">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="3cfe2-150">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="3cfe2-151">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="3cfe2-151">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
