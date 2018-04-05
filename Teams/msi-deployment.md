---
title: 安装 Microsoft 小组使用 MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 管理员可以使用批量团队 MSI 部署 Microsoft 小组要选择用户或计算机。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a2031a567b96db6987c6c9c035631f17fd3d03f
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="0ed2d-103">安装 Microsoft 小组使用 MSI</span><span class="sxs-lookup"><span data-stu-id="0ed2d-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="0ed2d-104">若要使用系统中心配置管理器，或组策略中或任何第三方分发机制的广泛部署，Microsoft 提供了管理员可以使用批量部署团队选择的 MSI 文件 （ [32 位](http://aka.ms/teams32bitmsi)和[64 位](http://aka.ms/teams64bitmsi)）用户或计算机。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-104">To use System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or machines.</span></span> <span data-ttu-id="0ed2d-105">管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="0ed2d-106">在部署时，团队将自动发布的登录该计算机的所有用户。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="0ed2d-107">我们建议您部署包到计算机，使计算机的所有新用户也将受益于该部署。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-107">We recommend that you deploy the package to the machine, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="0ed2d-108">若要了解有关 SCCM 的详细信息，请参阅[引入到系统中心配置管理器](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="0ed2d-109">部署过程 （推荐）</span><span class="sxs-lookup"><span data-stu-id="0ed2d-109">Deployment Procedure (Recommended)</span></span>
1. <span data-ttu-id="0ed2d-110">获取最新的包</span><span class="sxs-lookup"><span data-stu-id="0ed2d-110">Retrieve the latest package</span></span>
2. <span data-ttu-id="0ed2d-111">使用预设的 MSI 的默认值</span><span class="sxs-lookup"><span data-stu-id="0ed2d-111">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="0ed2d-112">部署到计算机时可能</span><span class="sxs-lookup"><span data-stu-id="0ed2d-112">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="0ed2d-113">Microsoft 的团队 MSI 包的工作原理</span><span class="sxs-lookup"><span data-stu-id="0ed2d-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="0ed2d-114">团队 MSI 将在程序文件的安装程序。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="0ed2d-115">只要到新的 Windows 用户配置文件用户迹象，安装程序将启动，一份工作组应用程序将被安装在该用户的应用程序数据文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="0ed2d-116">如果用户已有的团队应用程序安装在应用程序数据文件夹中，MSI 安装程序将跳过该用户的过程。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="0ed2d-117">不使用 MSI 部署更新，当它检测到新的版本，则可从该服务，客户端将自动更新。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-117">Do not use the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="0ed2d-118">若要重新部署最新的安装程序，请使用重新部署 MSI 如下所述的过程。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="0ed2d-119">如果您部署中的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="0ed2d-120">获取部署非常旧的版本，如果 MSI 将触发应用程序更新之前用户可使用团队。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="0ed2d-121">我们不建议您更改默认安装位置，因为这可能会中断更新流程。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="0ed2d-122">它然后最终将阻止用户访问该服务。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-122">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="0ed2d-123">目标计算机要求</span><span class="sxs-lookup"><span data-stu-id="0ed2d-123">Target machine requirements</span></span>

1. <span data-ttu-id="0ed2d-124">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0ed2d-124">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="0ed2d-125">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="0ed2d-125">Windows 7 or later</span></span>
2. <span data-ttu-id="0ed2d-126">3 GB 的磁盘空间，每个用户配置文件 （推荐）</span><span class="sxs-lookup"><span data-stu-id="0ed2d-126">3GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="0ed2d-127">清洁和重新部署过程</span><span class="sxs-lookup"><span data-stu-id="0ed2d-127">Clean up and redeployment Procedure</span></span>
<span data-ttu-id="0ed2d-128">如果用户从其用户配置文件卸载团队，MSI 安装程序将跟踪用户已卸载团队的应用程序，并且不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="0ed2d-129">若要为此用户卸载其中的特定机器上重新部署团队，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ed2d-129">To redeploy Teams for this user on a particular machine where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="0ed2d-130">卸载团队为每个用户配置文件安装的应用程序</span><span class="sxs-lookup"><span data-stu-id="0ed2d-130">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="0ed2d-131">卸载后，删除在 %localappdata%\Microsoft\Teams\ 下，目录递归</span><span class="sxs-lookup"><span data-stu-id="0ed2d-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="0ed2d-132">重新部署到该特定计算机中的 MSI 程序包</span><span class="sxs-lookup"><span data-stu-id="0ed2d-132">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="0ed2d-133">可以使用[Microsoft 小组部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)脚本来完成通过 SCCM 的步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="0ed2d-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

