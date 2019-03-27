---
title: 升级到新版本的云连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 了解如何升级你的云连接器版本部署。
ms.openlocfilehash: 5b3ca4b216bc376c9e23424fb978b5cd83e4aa41
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897648"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="77001-103">Upgrade to a new version of Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="77001-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="77001-104">了解如何升级你的云连接器版本部署。</span><span class="sxs-lookup"><span data-stu-id="77001-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="77001-p101">如果已设置联机管理租户帐户并启用自动更新，则现有 Skype for Business 云连接器版本的部署将根据你的自动更新时间窗口配置自动升级到较新版本。你也可以执行手动升级。</span><span class="sxs-lookup"><span data-stu-id="77001-p101">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration. You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="77001-107">云连接器 Edition 版本 1.4.1 和更高版本默认情况下执行自动更新。</span><span class="sxs-lookup"><span data-stu-id="77001-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="77001-108">如果您想要手动升级到最新版本 (2.1)，请参阅本主题后面的[升级到新版本的单个网站](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade)。</span><span class="sxs-lookup"><span data-stu-id="77001-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="77001-109">自动更新需要云连接器服务正在运行。</span><span class="sxs-lookup"><span data-stu-id="77001-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="77001-110">以下步骤介绍了自动更新过程：</span><span class="sxs-lookup"><span data-stu-id="77001-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="77001-111">自动更新过程将根据你为自动更新配置的计划运行。</span><span class="sxs-lookup"><span data-stu-id="77001-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="77001-112">操作系统更新任务</span><span class="sxs-lookup"><span data-stu-id="77001-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="77001-113">检查并将操作系统更新下载到所有云连接器 Vm。</span><span class="sxs-lookup"><span data-stu-id="77001-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="77001-114">安装和更新所有云连接器 Vm 逐个并重新启动。</span><span class="sxs-lookup"><span data-stu-id="77001-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="77001-115">云连接器 Vm 重新启动后，查看是否需要其他重新启动。</span><span class="sxs-lookup"><span data-stu-id="77001-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="77001-116">后云连接器 Vm 具有已成功修复，为云连接器主机计算机重复此过程。</span><span class="sxs-lookup"><span data-stu-id="77001-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="77001-117">云连接器主机上成功启动后，任何未处理的操作系统更新任务完成。</span><span class="sxs-lookup"><span data-stu-id="77001-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="77001-118">云连接器更新任务</span><span class="sxs-lookup"><span data-stu-id="77001-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="77001-119">从下载站点下载版本文件并检查。</span><span class="sxs-lookup"><span data-stu-id="77001-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="77001-120">下载新版本的 .msi 文件。</span><span class="sxs-lookup"><span data-stu-id="77001-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="77001-121">卸载旧的 msi 文件;安装新的 msi 文件。</span><span class="sxs-lookup"><span data-stu-id="77001-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="77001-122">下载新版本的 Skype 业务位。</span><span class="sxs-lookup"><span data-stu-id="77001-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="77001-123">通过调用 Register-CcAppliance 注册设备。</span><span class="sxs-lookup"><span data-stu-id="77001-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="77001-124">安装新的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="77001-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="77001-125">排出旧设备，并将网络连接切换到新设备。</span><span class="sxs-lookup"><span data-stu-id="77001-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="77001-126">当云连接器更新为新版本时，可能不会更新云连接器 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77001-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="77001-127">可以这样做，例如，如果在 PowerShell 窗口处于打开状态时自动更新，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="77001-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="77001-128">若要加载的更新的 cmdlet，您可以执行以下步骤： > 关闭 PowerShell 云连接器装置，任一操作，然后重新打开 PowerShell.> 或，您可以运行导入模块 CloudConnector-Force。</span><span class="sxs-lookup"><span data-stu-id="77001-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="77001-129">将单个站点升级到新版本</span><span class="sxs-lookup"><span data-stu-id="77001-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="77001-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="77001-130"></span></span>

<span data-ttu-id="77001-131">如果要升级的站点中只有一个设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77001-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="77001-132">卸载中的现有云连接器版本**Control Panel\>程序\>程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="77001-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="77001-133">安装新版本的 CloudConnector.msi 从[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)。</span><span class="sxs-lookup"><span data-stu-id="77001-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="77001-134">请确认你具有要安装的版本对应的 CloudConnector.ini 文件，并且已更新环境所需的所有值。</span><span class="sxs-lookup"><span data-stu-id="77001-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="77001-135">不能使用上一个版本中的 .ini 文件。</span><span class="sxs-lookup"><span data-stu-id="77001-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="77001-136">如果要升级云连接器，请参考主题[准备云连接器 appliance](prepare-your-cloud-connector-appliance.md) ，并确保 SiteName 和 EnableReferSupport 设置为正确值 CloudConnector.ini 文件中。</span><span class="sxs-lookup"><span data-stu-id="77001-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="77001-137">以管理员身份启动 PowerShell 控制台，然后运行以下 cmdlet 以注册当前设备：</span><span class="sxs-lookup"><span data-stu-id="77001-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="77001-138">运行以下 cmdlet 以下载最新版本：</span><span class="sxs-lookup"><span data-stu-id="77001-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="77001-139">运行以下 cmdlet 以开始安装：</span><span class="sxs-lookup"><span data-stu-id="77001-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="77001-140">运行以下 cmdlet 以激活新部署并禁用上一版本：</span><span class="sxs-lookup"><span data-stu-id="77001-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="77001-141">如果站点中有多个设备，请按照上述步骤逐个升级各设备。</span><span class="sxs-lookup"><span data-stu-id="77001-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="77001-142">如果您想要更新域管理员、 虚拟机管理员、 安全模式的管理员和租户管理员凭据，您可以使用_UpdateAllCredentials_参数来重置所有的凭据运行此 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="77001-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="77001-143">然后，在开始升级到新版本时，系统会提示你输入新凭据。</span><span class="sxs-lookup"><span data-stu-id="77001-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="77001-144">如果只想重置租户管理员凭据，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="77001-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="77001-145">将多个站点升级到新版本</span><span class="sxs-lookup"><span data-stu-id="77001-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="77001-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="77001-146"></span></span>

<span data-ttu-id="77001-p106">按照升级单个站点的步骤，每次升级部署中的一个站点。升级每个站点后，请确保[Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="77001-p106">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment. Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

