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
description: 了解如何升级云连接器版本部署。
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109128"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="c8e4a-103">升级至新版本的云连接器</span><span class="sxs-lookup"><span data-stu-id="c8e4a-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="c8e4a-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c8e4a-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c8e4a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="c8e4a-106">了解如何升级云连接器版本部署。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="c8e4a-107">如果已设置联机管理租户帐户并启用自动更新，则 Skype for Business 云连接器版本的现有部署将自动升级到较新版本，根据自动更新时间窗口配置。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="c8e4a-108">您也可以执行手动升级。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="c8e4a-109">默认情况下，云连接器版本 1.4.1 版和更高版本执行自动更新。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="c8e4a-110">如果要手动升级到最新版本 (2.1) ，请参阅本主题稍后将单个网站升级到新版本。 [](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)</span><span class="sxs-lookup"><span data-stu-id="c8e4a-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="c8e4a-111">自动更新要求云连接器服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="c8e4a-112">以下步骤介绍了自动更新过程：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="c8e4a-113">自动更新过程将按照为自动更新配置的计划运行。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="c8e4a-114">操作系统更新任务</span><span class="sxs-lookup"><span data-stu-id="c8e4a-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="c8e4a-115">检查操作系统更新并下载到所有云连接器 VM。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="c8e4a-116">一个接一个地安装并更新所有云连接器 VM，然后重新启动。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="c8e4a-117">在云连接器 VM 重启后，请检查以查看是否还需要重新启动。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="c8e4a-118">成功修补云连接器 VM 后，对云连接器主机重复此过程。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="c8e4a-119">云连接器主机成功启动后，任何未完成的操作系统更新任务都已完成。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="c8e4a-120">云连接器更新任务</span><span class="sxs-lookup"><span data-stu-id="c8e4a-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="c8e4a-121">从下载网站下载并检查版本文件。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="c8e4a-122">下载新版本的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="c8e4a-123">卸载旧的 msi 文件;安装新的 msi 文件。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="c8e4a-124">下载新版本的 Skype for Business bits。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="c8e4a-125">通过调用 Register-CcAppliance 注册设备。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="c8e4a-126">安装新的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="c8e4a-127">排出旧设备，将网络连接切换到新设备。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="c8e4a-128">当云连接器更新到新内部版本时，可能无法更新云连接器 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="c8e4a-129">例如，如果 PowerShell 窗口在自动更新发生时是打开的，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="c8e4a-130">若要加载更新的 cmdlet，可以执行下列任一步骤：> 关闭云连接器设备的 PowerShell，然后重新打开 PowerShell.> 或者，你可以运行 Import-Module CloudConnector -Force。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="c8e4a-131">将单个网站升级到新版本</span><span class="sxs-lookup"><span data-stu-id="c8e4a-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="c8e4a-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e4a-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="c8e4a-133">如果站点中只有一个要升级的设备，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="c8e4a-134">卸载控制面板程序程序和功能中的现有云 **\> \> 连接器版本**。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="c8e4a-135">从 安装新版本的 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) CloudConnector.msi。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="c8e4a-136">确认你具有要CloudConnector.ini的版本的文件，并且已更新环境的所有必需值。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="c8e4a-137">不能使用以前版本中的 .ini 文件。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="c8e4a-138">如果要升级云连接器，请参阅主题准备云连接器设备，并确保[](prepare-your-cloud-connector-appliance.md)在云连接器文件中将 SiteName 和 EnableReferSupport 设置为正确的CloudConnector.ini值。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="c8e4a-139">以管理员角色启动 PowerShell 控制台并运行以下 cmdlet 以注册当前设备：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="c8e4a-140">运行以下 cmdlet 以下载最新版本：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="c8e4a-141">运行以下 cmdlet 以开始安装：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="c8e4a-142">运行以下 cmdlet 以激活新部署并关闭以前的版本：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="c8e4a-143">如果站点中存在多个设备，请按照上述步骤分别升级每台设备。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="c8e4a-144">如果要更新域管理员、虚拟机管理员、安全模式管理员和租户管理员凭据，可以使用  _UpdateAllCredentials_ 参数运行 cmdlet 以重置所有凭据：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="c8e4a-145">然后，当你开始升级到新版本时，你将被提升为输入新的凭据。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="c8e4a-146">如果只想重置租户管理员凭据，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c8e4a-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="c8e4a-147">将多个网站升级到新版本</span><span class="sxs-lookup"><span data-stu-id="c8e4a-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="c8e4a-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="c8e4a-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="c8e4a-149">按照升级单个站点的步骤操作，为部署中的每个站点一次升级一个站点。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="c8e4a-150">请确保在升级 [每个站点后验证](validate-your-cloud-connector-deployment.md) 云连接器部署。</span><span class="sxs-lookup"><span data-stu-id="c8e4a-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
