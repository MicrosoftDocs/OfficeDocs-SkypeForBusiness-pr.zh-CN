---
title: 使用 MSI 安装 Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882035"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="01375-103">使用 MSI 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01375-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="01375-104">为了使用 System Center Configuration Manager、组策略或任何第三方分发机制进行广泛部署，Microsoft 提供了 MSI 文件（[32 位](https://aka.ms/teams32bitmsi)和 [64 位](https://aka.ms/teams64bitmsi)），管理员可以使用这些文件批量部署 Teams 来选择用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="01375-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="01375-105">管理员可以使用这些文件远程部署 Teams，这样，用户不必手动下载 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="01375-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="01375-106">部署后，用户登录相应计算机时将会自动启动 Teams。</span><span class="sxs-lookup"><span data-stu-id="01375-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="01375-107">建议你将程序包部署到计算机上，以便计算机的所有新用户也会受益于此部署。</span><span class="sxs-lookup"><span data-stu-id="01375-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="01375-108">要详细了解 SCCM，请参阅 [System Center Configuration Manager 简介](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="01375-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="01375-109">部署过程（推荐）</span><span class="sxs-lookup"><span data-stu-id="01375-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="01375-110">检索最新程序包。</span><span class="sxs-lookup"><span data-stu-id="01375-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="01375-111">使用 MSI 预填充的默认值。</span><span class="sxs-lookup"><span data-stu-id="01375-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="01375-112">部署到计算机（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="01375-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="01375-113">Microsoft Teams MSI 程序包工作方式</span><span class="sxs-lookup"><span data-stu-id="01375-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="01375-114">Teams MSI 将安装程序放在 Program Files 中。</span><span class="sxs-lookup"><span data-stu-id="01375-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="01375-115">每当用户登录新的 Windows 用户配置文件时，将启动该安装程序，并会在该用户的 appdata 文件夹中安装一份 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="01375-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="01375-116">如果用户的 appdata 文件夹中已安装 Teams 应用，MSI 安装程序将对该用户跳过该过程。</span><span class="sxs-lookup"><span data-stu-id="01375-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="01375-117">请勿使用 MSI 部署更新，因为客户端在检测到服务提供了新版本时会自动更新。</span><span class="sxs-lookup"><span data-stu-id="01375-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="01375-118">要重新部署最新的安装程序，请使用下文所述的 MSI 重新部署过程。</span><span class="sxs-lookup"><span data-stu-id="01375-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="01375-119">如果部署早期版本的 MSI 程序包，将会在可能的情况下为用户自动更新客户端。</span><span class="sxs-lookup"><span data-stu-id="01375-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="01375-120">如果部署的版本太低，MSI 将会在用户能够使用 Teams 之前触发应用更新。</span><span class="sxs-lookup"><span data-stu-id="01375-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="01375-121">建议不要更改默认安装位置，因为这可能会中断更新流。</span><span class="sxs-lookup"><span data-stu-id="01375-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="01375-122">版本太低最终会导致用户无法访问服务。</span><span class="sxs-lookup"><span data-stu-id="01375-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="01375-123">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="01375-123">Target computer requirements</span></span>

- <span data-ttu-id="01375-124">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="01375-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="01375-125">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="01375-125">Windows 7 or later</span></span>
- <span data-ttu-id="01375-126">每个用户配置文件 3 GB 磁盘空间（推荐）</span><span class="sxs-lookup"><span data-stu-id="01375-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="01375-127">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="01375-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="01375-128">如果用户从其用户配置文件中卸载 Teams，MSI 安装程序将会跟踪该用户了卸载 Teams 应用，因此不再为该用户配置文件安装 Teams。</span><span class="sxs-lookup"><span data-stu-id="01375-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="01375-129">要在卸载了 Teams 的特定计算机上为此用户重新部署 Teams，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01375-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="01375-130">卸载为每个用户配置文件安装的 Teams 应用。</span><span class="sxs-lookup"><span data-stu-id="01375-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="01375-131">卸载后，递归地删除 %localappdata%\Microsoft\Teams\ 下面的目录。</span><span class="sxs-lookup"><span data-stu-id="01375-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="01375-132">将 MSI 程序包重新部署到该特定计算机。</span><span class="sxs-lookup"><span data-stu-id="01375-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="01375-133">你可以使用我们的 [Microsoft Teams 部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)脚本通过 SCCM 完成步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="01375-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

