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
description: 了解如何使用 PowerShell 控件管理Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947563"
---
# <a name="install-microsoft-teams-powershell-module"></a><span data-ttu-id="cd8b6-103">安装 Microsoft Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="cd8b6-103">Install Microsoft Teams PowerShell Module</span></span>

<span data-ttu-id="cd8b6-104">本文介绍如何使用 PowerShell 库Microsoft Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-104">This article explains how to install the Microsoft Teams PowerShell module using PowerShell Gallery.</span></span> <span data-ttu-id="cd8b6-105">所有 Microsoft Teams 平台都支持 Windows PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-105">The Microsoft Teams PowerShell module is supported on all Windows platforms.</span></span> 

## <a name="requirements"></a><span data-ttu-id="cd8b6-106">要求</span><span class="sxs-lookup"><span data-stu-id="cd8b6-106">Requirements</span></span>

<span data-ttu-id="cd8b6-107">Microsoft TeamsPowerShell 模块要求在所有平台上使用 PowerShell 5.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-107">Microsoft Teams PowerShell module requires PowerShell 5.1 or higher on all platforms.</span></span> <span data-ttu-id="cd8b6-108">安装 [适用于操作系统的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)  </span><span class="sxs-lookup"><span data-stu-id="cd8b6-108">Install the [latest version of PowerShell](/powershell/scripting/install/installing-powershell) available for your operating system.</span></span> 

<span data-ttu-id="cd8b6-109">若要检查 PowerShell 版本，请在 PowerShell 会话中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-109">To check your PowerShell version, run the following command from within a PowerShell session:</span></span> 

```powershell
$PSVersionTable.PSVersion 
```
<span data-ttu-id="cd8b6-110">我们建议使用 Install-Module cmdlet 安装 Microsoft Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-110">We recommend that you use the  Install-Module cmdlet to install the Microsoft Teams PowerShell module.</span></span> 
 
<span data-ttu-id="cd8b6-111">如果 POWERShell 库 (PSGallery) 未配置为 **PowerShellGet** 的受信任存储库，则首次使用 PSGallery 时会看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-111">If PowerShell Gallery (PSGallery) isn't configured as a trusted repository for **PowerShellGet**, the first time you use the PSGallery you'll see the following message:</span></span>

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="cd8b6-112">对 **"** 全部 **"回答"** 是"或"是"以继续安装。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-112">Answer **Yes** or **Yes to All** to continue with the installation.</span></span>

## <a name="installing-using-the-powershellgallery"></a><span data-ttu-id="cd8b6-113">使用 PowerShellGallery 进行安装</span><span class="sxs-lookup"><span data-stu-id="cd8b6-113">Installing using the PowerShellGallery</span></span>

<span data-ttu-id="cd8b6-114">Microsoft TeamsPowerShell 模块目前支持与 PowerShell 5.1 on Windows。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-114">Microsoft Teams PowerShell module is currently supported for use with PowerShell 5.1 on Windows.</span></span> <span data-ttu-id="cd8b6-115">请按照以下步骤安装模块：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-115">Follow these steps to install the module:</span></span> 

- <span data-ttu-id="cd8b6-116">更新到[Windows PowerShell 5.1。](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="cd8b6-116">Update to [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).</span></span> <span data-ttu-id="cd8b6-117">如果使用 1607 Windows 10版本，则已安装 PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-117">If you're on Windows 10 version 1607 or higher, you already have PowerShell 5.1 installed.</span></span> 
- <span data-ttu-id="cd8b6-118">安装[.NET Framework 4.7.2](/dotnet/framework/install)或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-118">Install [.NET Framework 4.7.2](/dotnet/framework/install) or later.</span></span> 
- <span data-ttu-id="cd8b6-119">运行以下命令以安装最新的 PowerShellGet：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-119">Run the following command to install the latest PowerShellGet:</span></span>
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- <span data-ttu-id="cd8b6-120">安装 Teams PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-120">Install the Teams PowerShell Module.</span></span>

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a><span data-ttu-id="cd8b6-121">脱机安装</span><span class="sxs-lookup"><span data-stu-id="cd8b6-121">Offline Installation</span></span> 

<span data-ttu-id="cd8b6-122">在某些环境中，无法连接到 PowerShell 库。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-122">In some environments, it's not possible to connect to the PowerShell Gallery.</span></span> <span data-ttu-id="cd8b6-123">在这些情况下，请按照以下手动 [安装步骤操作](https://aka.ms/psgallery-manualdownload)。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-123">In those situations, please follow these [manual installation steps](https://aka.ms/psgallery-manualdownload).</span></span>  

## <a name="sign-in"></a><span data-ttu-id="cd8b6-124">登录</span><span class="sxs-lookup"><span data-stu-id="cd8b6-124">Sign in</span></span>

<span data-ttu-id="cd8b6-125">若要开始使用 PowerShell Microsoft Teams，请通过 Azure 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-125">To start working with Microsoft Teams PowerShell module, sign in with your Azure credentials.</span></span>

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a><span data-ttu-id="cd8b6-126">更新 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="cd8b6-126">Update Teams PowerShell Module</span></span>

<span data-ttu-id="cd8b6-127">若要更新任何 PowerShell 模块，应使用相同的方法来安装该模块。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-127">To update any PowerShell module, you should use the same method used to install the module.</span></span> <span data-ttu-id="cd8b6-128">例如，如果最初使用 Install-Module，则应该使用 [Update-Module](/powershell/module/powershellget/update-module) 获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-128">For example, if you originally used Install-Module, then you should use [Update-Module](/powershell/module/powershellget/update-module) to get the latest version.</span></span>  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> <span data-ttu-id="cd8b6-129">如果Teams PowerShell 已导入 PowerShell 会话，则更新模块会失败。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-129">If Teams PowerShell has already been imported into your PowerShell session, updating the module will fail.</span></span> <span data-ttu-id="cd8b6-130">关闭 PowerShell，然后重新打开新的提升权限的 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-130">Close PowerShell and re-open a new elevated PowerShell session.</span></span>


## <a name="uninstall-teams-powershell"></a><span data-ttu-id="cd8b6-131">卸载 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd8b6-131">Uninstall Teams PowerShell</span></span>

<span data-ttu-id="cd8b6-132">若要卸载Microsoft Teams PowerShell，请打开新的 PowerShell 命令提示符并运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cd8b6-132">To uninstall Microsoft Teams PowerShell, open a new PowerShell command prompt and run the following:</span></span> 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a><span data-ttu-id="cd8b6-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cd8b6-133">Next Steps</span></span> 

<span data-ttu-id="cd8b6-134">现在，可以使用 PowerShell Microsoft Teams管理Microsoft Teams应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-134">Now you're ready to manage Microsoft Teams using Microsoft Teams PowerShell.</span></span> <span data-ttu-id="cd8b6-135">若要[开始Teams，Teams PowerShell](teams-powershell-managing-teams.md)管理服务。</span><span class="sxs-lookup"><span data-stu-id="cd8b6-135">See [Managing Teams with Teams PowerShell](teams-powershell-managing-teams.md) to get started.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="cd8b6-136">相关主题</span><span class="sxs-lookup"><span data-stu-id="cd8b6-136">Related topics</span></span>

[<span data-ttu-id="cd8b6-137">使用 Teams PowerShell Teams管理资源</span><span class="sxs-lookup"><span data-stu-id="cd8b6-137">Managing Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="cd8b6-138">TeamsPowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="cd8b6-138">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="cd8b6-139">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="cd8b6-139">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="cd8b6-140">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="cd8b6-140">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
