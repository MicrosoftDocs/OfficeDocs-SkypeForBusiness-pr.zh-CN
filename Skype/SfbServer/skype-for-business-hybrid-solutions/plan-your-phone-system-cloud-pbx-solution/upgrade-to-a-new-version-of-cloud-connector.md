---
title: 升级至新版本的云连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 了解如何升级你的云连接器版本部署。
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359288"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="9b759-103">升级至新版本的云连接器</span><span class="sxs-lookup"><span data-stu-id="9b759-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="9b759-104">云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。</span><span class="sxs-lookup"><span data-stu-id="9b759-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="9b759-105">组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。</span><span class="sxs-lookup"><span data-stu-id="9b759-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="9b759-106">了解如何升级你的云连接器版本部署。</span><span class="sxs-lookup"><span data-stu-id="9b759-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="9b759-107">如果已设置了联机管理租户帐户并启用了自动更新，则现有的 Skype for Business 云连接器版本部署将根据您的自动更新时间窗口配置自动升级到较新的版本。</span><span class="sxs-lookup"><span data-stu-id="9b759-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="9b759-108">您还可以执行手动升级。</span><span class="sxs-lookup"><span data-stu-id="9b759-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="9b759-109">云连接器版本1.4.1 和更高版本在默认情况下将执行自动更新。</span><span class="sxs-lookup"><span data-stu-id="9b759-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="9b759-110">如果要 (2.1) 手动升级到最新版本，请参阅本主题后面的将 [单个网站升级到新版本](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 。</span><span class="sxs-lookup"><span data-stu-id="9b759-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="9b759-111">自动更新要求云连接器服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="9b759-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="9b759-112">以下步骤介绍了自动更新的过程：</span><span class="sxs-lookup"><span data-stu-id="9b759-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="9b759-113">自动更新过程将根据您为自动更新配置的计划运行。</span><span class="sxs-lookup"><span data-stu-id="9b759-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="9b759-114">操作系统更新任务</span><span class="sxs-lookup"><span data-stu-id="9b759-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="9b759-115">检查并下载所有云连接器虚拟机的操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="9b759-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="9b759-116">逐个安装和更新所有云连接器虚拟机并重新启动。</span><span class="sxs-lookup"><span data-stu-id="9b759-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="9b759-117">云连接器虚拟机重新启动后，检查是否需要再次重新启动。</span><span class="sxs-lookup"><span data-stu-id="9b759-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="9b759-118">成功修补云连接器虚拟机后，请对云连接器主机进行重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9b759-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="9b759-119">云连接器主机成功启动后，将完成任何未完成的操作系统更新任务。</span><span class="sxs-lookup"><span data-stu-id="9b759-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="9b759-120">云连接器更新任务</span><span class="sxs-lookup"><span data-stu-id="9b759-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="9b759-121">从下载网站下载并检查版本文件。</span><span class="sxs-lookup"><span data-stu-id="9b759-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="9b759-122">下载新的版本 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="9b759-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="9b759-123">卸载旧的 msi 文件;安装新的 msi 文件。</span><span class="sxs-lookup"><span data-stu-id="9b759-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="9b759-124">下载新版本的 Skype for Business bits。</span><span class="sxs-lookup"><span data-stu-id="9b759-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="9b759-125">通过调用 Register-ccappliance 注册设备。</span><span class="sxs-lookup"><span data-stu-id="9b759-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="9b759-126">安装新的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="9b759-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="9b759-127">排出旧设备，并切换到新设备的网络连接。</span><span class="sxs-lookup"><span data-stu-id="9b759-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="9b759-128">当云连接器更新到新版本时，可能不会更新云连接器 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b759-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="9b759-129">例如，如果在自动更新发生时 PowerShell 窗口保持打开状态，则会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="9b759-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="9b759-130">若要加载更新的 cmdlet，您可以执行以下任一步骤： > 在云连接器设备上关闭 PowerShell，然后重新打开 PowerShell。 > 或者，您可以运行 Import-Module Cloudconnector.ini-Force。</span><span class="sxs-lookup"><span data-stu-id="9b759-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="9b759-131">将单个网站升级到新版本</span><span class="sxs-lookup"><span data-stu-id="9b759-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="9b759-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="9b759-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="9b759-133">如果要升级的站点中只有一台设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9b759-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="9b759-134">在 "控制面板" 中卸载现有的云连接器版本。 \*\* \> 程序 \> 和功能\*\*。</span><span class="sxs-lookup"><span data-stu-id="9b759-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="9b759-135">从安装 CloudConnector.msi 的新版本 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。</span><span class="sxs-lookup"><span data-stu-id="9b759-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="9b759-136">确认您具有要安装的版本的 CloudConnector.ini 文件，并且已更新环境所需的所有值。</span><span class="sxs-lookup"><span data-stu-id="9b759-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="9b759-137">您不能使用以前版本中的 .ini 文件。</span><span class="sxs-lookup"><span data-stu-id="9b759-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="9b759-138">如果要升级云连接器，请参阅 " [准备云连接器" 设备](prepare-your-cloud-connector-appliance.md) 一主题，确保将 "SiteName" 和 "EnableReferSupport" 设置为 "CloudConnector.ini" 文件中的正确值。</span><span class="sxs-lookup"><span data-stu-id="9b759-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="9b759-139">以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以注册当前设备：</span><span class="sxs-lookup"><span data-stu-id="9b759-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="9b759-140">运行以下 cmdlet 以下载最新版本：</span><span class="sxs-lookup"><span data-stu-id="9b759-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="9b759-141">运行以下 cmdlet 以开始安装：</span><span class="sxs-lookup"><span data-stu-id="9b759-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="9b759-142">运行以下 cmdlet 以激活新部署并关闭以前的版本：</span><span class="sxs-lookup"><span data-stu-id="9b759-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="9b759-143">如果站点中有多个设备，请按照上述步骤逐个升级每个设备。</span><span class="sxs-lookup"><span data-stu-id="9b759-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="9b759-144">如果要更新域管理员、虚拟机管理员、安全模式管理员和租户管理员凭据，可以使用  _UpdateAllCredentials_ 参数运行 cmdlet 来重置所有凭据：</span><span class="sxs-lookup"><span data-stu-id="9b759-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="9b759-145">然后，在开始升级到新版本时，将会提升，以输入新的凭据。</span><span class="sxs-lookup"><span data-stu-id="9b759-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="9b759-146">如果您只想重置租户管理员凭据，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b759-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="9b759-147">将多个网站升级到新版本</span><span class="sxs-lookup"><span data-stu-id="9b759-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="9b759-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="9b759-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="9b759-149">按照升级单个网站的步骤操作，为部署中的每个网站一次升级一个网站。</span><span class="sxs-lookup"><span data-stu-id="9b759-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="9b759-150">在升级每个网站后，请确保并 [验证你的云连接器部署](validate-your-cloud-connector-deployment.md) 。</span><span class="sxs-lookup"><span data-stu-id="9b759-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

