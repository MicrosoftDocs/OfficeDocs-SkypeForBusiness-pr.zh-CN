---
title: 安装 Microsoft 团队使用 MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理员可以使用批量团队 MSI 部署 Microsoft 团队选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882035"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="fef0b-103">安装 Microsoft 团队使用 MSI</span><span class="sxs-lookup"><span data-stu-id="fef0b-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="fef0b-104">若要使用广泛部署 System Center Configuration Manager，组策略或任何第三方分发机制，Microsoft 提供了管理员可以使用批量部署团队选择的 MSI 文件 （ [32 位](https://aka.ms/teams32bitmsi)和[64 位](https://aka.ms/teams64bitmsi)）用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="fef0b-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="fef0b-105">管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。</span><span class="sxs-lookup"><span data-stu-id="fef0b-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="fef0b-106">在部署时，团队将自动启动的所有用户登录的计算机。</span><span class="sxs-lookup"><span data-stu-id="fef0b-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="fef0b-107">我们建议您部署包到计算机，这样的计算机的所有新用户也将从此部署中获益。</span><span class="sxs-lookup"><span data-stu-id="fef0b-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="fef0b-108">若要了解有关 SCCM 的详细信息，请参阅[Introduction 到 System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="fef0b-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="fef0b-109">部署过程 （推荐）</span><span class="sxs-lookup"><span data-stu-id="fef0b-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="fef0b-110">检索的最新程序包。</span><span class="sxs-lookup"><span data-stu-id="fef0b-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="fef0b-111">使用默认值由 MSI 预填充。</span><span class="sxs-lookup"><span data-stu-id="fef0b-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="fef0b-112">部署到计算机时可能。</span><span class="sxs-lookup"><span data-stu-id="fef0b-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="fef0b-113">Microsoft 团队 MSI 数据包的工作原理</span><span class="sxs-lookup"><span data-stu-id="fef0b-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="fef0b-114">团队 MSI 将安装程序置于 Program Files。</span><span class="sxs-lookup"><span data-stu-id="fef0b-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="fef0b-115">只要用户迹象到新的 Windows 用户配置文件，将启动安装程序和团队应用程序的副本将安装该用户的应用程序数据文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fef0b-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="fef0b-116">如果用户已安装应用程序数据文件夹中的团队应用程序，MSI 安装程序将跳过该用户的过程。</span><span class="sxs-lookup"><span data-stu-id="fef0b-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="fef0b-117">不要使用 MSI 部署更新，因为客户端检测到新版本可从服务时将自动更新。</span><span class="sxs-lookup"><span data-stu-id="fef0b-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="fef0b-118">若要重新部署最新的安装程序，请使用如下所述的 MSI 中重新部署的过程。</span><span class="sxs-lookup"><span data-stu-id="fef0b-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="fef0b-119">如果您部署的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。</span><span class="sxs-lookup"><span data-stu-id="fef0b-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="fef0b-120">如果部署获取非常旧版本，MSI 将触发应用程序更新之前用户能够使用团队。</span><span class="sxs-lookup"><span data-stu-id="fef0b-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="fef0b-121">我们不建议您更改默认安装位置，因为这可能会中断的更新流程。</span><span class="sxs-lookup"><span data-stu-id="fef0b-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="fef0b-122">具有太旧版本最终将阻止用户访问服务。</span><span class="sxs-lookup"><span data-stu-id="fef0b-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="fef0b-123">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="fef0b-123">Target computer requirements</span></span>

- <span data-ttu-id="fef0b-124">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fef0b-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="fef0b-125">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="fef0b-125">Windows 7 or later</span></span>
- <span data-ttu-id="fef0b-126">3 GB 的磁盘空间，每个用户配置文件 （推荐）</span><span class="sxs-lookup"><span data-stu-id="fef0b-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="fef0b-127">清理和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="fef0b-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="fef0b-128">如果用户从其用户配置文件中卸载团队，MSI 安装程序将跟踪用户已卸载团队应用程序和不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="fef0b-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="fef0b-129">若要重新团队部署为此用户其中它已卸载特定计算机上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fef0b-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="fef0b-130">卸载团队应用程序安装每个用户配置文件。</span><span class="sxs-lookup"><span data-stu-id="fef0b-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="fef0b-131">卸载后，删除目录以递归方式 %localappdata%\microsoft\teams\ 下。</span><span class="sxs-lookup"><span data-stu-id="fef0b-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="fef0b-132">重新部署特定计算机的 MSI 数据包。</span><span class="sxs-lookup"><span data-stu-id="fef0b-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="fef0b-133">您可以使用我们[的 Microsoft 团队部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)的脚本完成通过 SCCM 的步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="fef0b-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

