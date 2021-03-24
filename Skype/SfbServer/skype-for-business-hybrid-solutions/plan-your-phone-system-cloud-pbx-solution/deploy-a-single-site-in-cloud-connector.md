---
title: 在云连接器中部署单个站点
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: 了解如何在云连接器版本中部署单个 PSTN 站点。
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094830"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="50439-103">在云连接器中部署单个站点</span><span class="sxs-lookup"><span data-stu-id="50439-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="50439-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="50439-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="50439-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="50439-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="50439-106">了解如何在云连接器版本中部署单个 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="50439-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="50439-107">你可以部署 Skype for Business 云连接器版本，支持或不支持高可用性 (HA) 版本。</span><span class="sxs-lookup"><span data-stu-id="50439-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="50439-108">如果要启用 HA，则需要在站点内部署两台或多部设备。</span><span class="sxs-lookup"><span data-stu-id="50439-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="50439-109">还可以在部署现有设备后将其转换为支持 HA。</span><span class="sxs-lookup"><span data-stu-id="50439-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="50439-110">部署第一台 Skype for Business 云连接器版本设备</span><span class="sxs-lookup"><span data-stu-id="50439-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="50439-111">若要在站点中部署第一个设备，请以管理员角色打开 PowerShell 控制台并运行以下 cmdlet 以注册该设备：</span><span class="sxs-lookup"><span data-stu-id="50439-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="50439-112">按照说明提供租户管理员帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="50439-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="50439-113">使用你为云连接器联机管理创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="50439-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="50439-114">此外，请按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。</span><span class="sxs-lookup"><span data-stu-id="50439-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="50439-115">在 1.4.2 版及更早版本中，还按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。</span><span class="sxs-lookup"><span data-stu-id="50439-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="50439-116">在 2.0 版及更高版本中，还按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。</span><span class="sxs-lookup"><span data-stu-id="50439-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="50439-117">若要开始安装，请以管理员角色打开 PowerShell 控制台并运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50439-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="50439-118">将设备添加到现有站点</span><span class="sxs-lookup"><span data-stu-id="50439-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="50439-119">可以通过向站点添加其他设备来扩展现有云连接器站点以支持 HA。</span><span class="sxs-lookup"><span data-stu-id="50439-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="50439-120">按照准备云连接器设备 中所述的步骤准备 [云连接器设备](prepare-your-cloud-connector-appliance.md)。</span><span class="sxs-lookup"><span data-stu-id="50439-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="50439-121">请注意，只有部署中的第一个设备需要执行某些步骤。</span><span class="sxs-lookup"><span data-stu-id="50439-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="50439-122">确认站点目录存在且已正确配置为支持 HA。</span><span class="sxs-lookup"><span data-stu-id="50439-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="50439-123">仅在新添加的主机服务器上运行以下 cmdlet，以更新 Microsoft 365 或 Office 365 组织配置中的拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="50439-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="50439-124">如果要同时添加多个设备，请在每个新添加的主机服务器上分别运行 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="50439-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="50439-125">在每个主机服务器上运行以下 cmdlet，更新现有设备上的拓扑。</span><span class="sxs-lookup"><span data-stu-id="50439-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="50439-126">仅对现有设备运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50439-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="50439-127">仅在新添加的主机服务器上运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50439-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="50439-128">不要对现有设备运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50439-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="50439-129">如果要同时添加多个设备，请在每个新添加的主机服务器上分别运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50439-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="50439-130">如果站点目录设置为本地文件夹路径，则需要为此文件夹定义文件共享，并使用新设备中的站点目录的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="50439-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="50439-131">你可以将第一个设备站点目录保留为本地路径，或修改它以使用共享到同一文件夹的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="50439-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="50439-132">如果共享网站目录的位置发生更改，则需要卸载之前安装的任何设备，然后重新安装。</span><span class="sxs-lookup"><span data-stu-id="50439-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="50439-133">>重要说明：在站点内部署的所有设备上，CceService 帐户和 CABackupFile 帐户的密码必须相同，以便设备可以访问站点目录中的站点目录共享和加密的 CA 备份文件。</span><span class="sxs-lookup"><span data-stu-id="50439-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="50439-134">从现有站点删除设备</span><span class="sxs-lookup"><span data-stu-id="50439-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="50439-135">如果要从现有站点删除设备：</span><span class="sxs-lookup"><span data-stu-id="50439-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="50439-136">仅在要从站点中删除的主机服务器上运行以下 cmdlet，以更新 Microsoft 365 或 Office 365 组织配置中的拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="50439-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="50439-137">仅在要从中删除设备的所有虚拟机的主机服务器上运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="50439-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```