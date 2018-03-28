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
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="9f4eb-103">安装 Microsoft 小组使用 MSI</span><span class="sxs-lookup"><span data-stu-id="9f4eb-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="9f4eb-104">利用系统中心配置管理器中，或组策略或广泛部署的任何第三方分发机制，Microsoft 提供了管理员能够利用批量部署期间的 MSI 文件 （ [32 位](http://aka.ms/teams32bitmsi)和[64 位](http://aka.ms/teams64bitmsi)）若要选择用户或计算机的 Microsoft 小组。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="9f4eb-105">管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="9f4eb-106">在部署时，团队将自动启动对于登录在该计算机上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="9f4eb-107">建议您将程序包都部署到机器的因此到的计算机的所有新用户也将受益于该部署。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="9f4eb-108">若要了解有关 SCCM 的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="9f4eb-109">引入到系统中心配置管理器</span><span class="sxs-lookup"><span data-stu-id="9f4eb-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="9f4eb-110">部署过程 （建议）</span><span class="sxs-lookup"><span data-stu-id="9f4eb-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="9f4eb-111">获取最新的包</span><span class="sxs-lookup"><span data-stu-id="9f4eb-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="9f4eb-112">使用预设的 MSI 的默认值</span><span class="sxs-lookup"><span data-stu-id="9f4eb-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="9f4eb-113">部署到计算机时可能</span><span class="sxs-lookup"><span data-stu-id="9f4eb-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="9f4eb-114">Microsoft 的团队 MSI 包的工作原理</span><span class="sxs-lookup"><span data-stu-id="9f4eb-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="9f4eb-115">团队 MSI 将在程序文件的安装程序。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="9f4eb-116">只要到新的 Windows 用户配置文件用户迹象，安装程序将启动，一份工作组应用程序将被安装在该用户的应用程序数据文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="9f4eb-117">如果用户已有的团队应用程序安装在应用程序数据文件夹中，MSI 安装程序将跳过该用户的过程。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="9f4eb-118">不利用 MSI 部署更新，当它检测到新的版本，则可从该服务，客户端将自动更新。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="9f4eb-119">若要重新部署最新的安装程序，请使用重新部署 MSI 如下所述的过程。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="9f4eb-120">如果您部署中的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="9f4eb-121">获取部署非常旧的版本，如果 MSI 将触发应用程序更新之前用户可使用团队。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="9f4eb-122">不建议您更改任何安装位置，因为这可能会中断更新流。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="9f4eb-123">它然后最终将阻止用户访问该服务。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="9f4eb-124">目标计算机的要求：</span><span class="sxs-lookup"><span data-stu-id="9f4eb-124">Target machine requirements:</span></span>

1. <span data-ttu-id="9f4eb-125">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9f4eb-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="9f4eb-126">Windows 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="9f4eb-126">Windows 7 or later</span></span>
2. <span data-ttu-id="9f4eb-127">32 GB 的磁盘空间，每个用户配置文件 （推荐）</span><span class="sxs-lookup"><span data-stu-id="9f4eb-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="9f4eb-128">全新 up\redeployment 过程</span><span class="sxs-lookup"><span data-stu-id="9f4eb-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="9f4eb-129">如果用户对其用户配置文件卸载来自团队，MSI 安装程序将跟踪用户已卸载团队的应用程序，并且不再为该用户配置文件安装团队。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="9f4eb-130">为此它所在的特定机器上的用户卸载您重新部署团队将需要：</span><span class="sxs-lookup"><span data-stu-id="9f4eb-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="9f4eb-131">卸载团队为每个用户配置文件安装的应用程序</span><span class="sxs-lookup"><span data-stu-id="9f4eb-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="9f4eb-132">卸载后，删除在 %localappdata%\Microsoft\Teams\ 下，目录递归</span><span class="sxs-lookup"><span data-stu-id="9f4eb-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="9f4eb-133">重新部署到该特定计算机中的 MSI 程序包</span><span class="sxs-lookup"><span data-stu-id="9f4eb-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="9f4eb-134">您可以利用我们的[Microsoft 小组部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)脚本来完成通过 SCCM 此步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="9f4eb-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

