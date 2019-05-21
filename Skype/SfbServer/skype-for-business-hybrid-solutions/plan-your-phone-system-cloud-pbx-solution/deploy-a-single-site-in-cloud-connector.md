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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: 了解有关在云连接器版本中部署单个 PSTN 站点的信息。
ms.openlocfilehash: 10d9e5f286b00af8791097707dc0345e100e55d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287361"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="786c8-103">Deploy a single site in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="786c8-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="786c8-104">了解有关在云连接器版本中部署单个 PSTN 站点的信息。</span><span class="sxs-lookup"><span data-stu-id="786c8-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="786c8-105">你可以部署具有或不具有高可用性 (HA) 支持的 Skype for Business 云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="786c8-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="786c8-106">如果要启用 HA，你需要在一个站点中部署两个或更多设备。</span><span class="sxs-lookup"><span data-stu-id="786c8-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="786c8-107">你也可以在部署现有设备后将其转换为支持 HA。</span><span class="sxs-lookup"><span data-stu-id="786c8-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="786c8-108">部署第一个 Skype for Business 云连接器版本设备</span><span class="sxs-lookup"><span data-stu-id="786c8-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="786c8-109">要在站点中部署第一个设备，请以管理员身份打开 PowerShell 控制台并运行以下 cmdlet，以注册该设备：</span><span class="sxs-lookup"><span data-stu-id="786c8-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```
Register-CcAppliance
```

<span data-ttu-id="786c8-p102">按照说明提供租户管理员帐户名称和密码。请使用你为云连接器在线管理创建的帐户。此外，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和虚拟机管理员密码。</span><span class="sxs-lookup"><span data-stu-id="786c8-p102">Follow the instructions to provide the tenant admin account name and password. Use the account you have created for Cloud Connector online management. Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="786c8-113">在1.4.2 及更早版本中, 还按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。</span><span class="sxs-lookup"><span data-stu-id="786c8-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="786c8-114">在 2.0 版和更高版本中，还要按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。</span><span class="sxs-lookup"><span data-stu-id="786c8-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="786c8-115">要开始安装，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="786c8-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="786c8-116">将设备添加到现有站点</span><span class="sxs-lookup"><span data-stu-id="786c8-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="786c8-117">你可以通过向网站添加其他装置来扩展现有云连接器网站以支持 HA。</span><span class="sxs-lookup"><span data-stu-id="786c8-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="786c8-118">按照[准备云连接器设备](prepare-your-cloud-connector-appliance.md)中所述, 按照步骤准备云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="786c8-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="786c8-119">请注意，有些步骤仅限于部署中的第一个设备。</span><span class="sxs-lookup"><span data-stu-id="786c8-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="786c8-120">请确认站点目录已存在且已为支持 HA 进行了正确配置。</span><span class="sxs-lookup"><span data-stu-id="786c8-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="786c8-p104">仅在新添加的主机服务器上运行以下 cmdlet 以更新 Office 365 租户配置中的拓扑信息。如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行该 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="786c8-p104">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration. If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```
   Register-CcAppliance
   ```

3. <span data-ttu-id="786c8-p105">在每个主机服务器上运行以下 cmdlet 以更新现有设备中的拓扑。只在现有设备例上运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="786c8-p105">Update the topology on existing appliances by running the following cmdlet on each host server. Only run the cmdlet on the existing appliances.</span></span>
    
   ```
   Publish-CcAppliance
   ```

4. <span data-ttu-id="786c8-125">只在新添加的主机服务器上运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="786c8-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="786c8-126">请勿在现有设备上运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="786c8-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="786c8-127">如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="786c8-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="786c8-128">如果将站点目录设置为本地文件夹路径，则需为此文件夹定义文件共享，并对新设备上的站点目录使用 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="786c8-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="786c8-129">可将第一个设备站点目录保留为本地路径，或对其进行修改以使用到同一文件夹的共享的 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="786c8-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="786c8-130">如果共享站点目录的位置发生变化，则需卸载再重新安装之前安装的所有设备。</span><span class="sxs-lookup"><span data-stu-id="786c8-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="786c8-131">> 重要提示: CceService 帐户和 CABackupFile 帐户的密码在网站中部署的所有设备上必须相同, 以便装置可以访问网站目录中的网站目录共享和加密的 CA 备份文件。</span><span class="sxs-lookup"><span data-stu-id="786c8-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="786c8-132">从现有站点中删除设备</span><span class="sxs-lookup"><span data-stu-id="786c8-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="786c8-133">如果要从现有站点中删除设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="786c8-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="786c8-134">只在要从站点中删除的主机服务器上运行以下 cmdlet 以更新 Office 365 租户配置中的拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="786c8-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="786c8-135">只在要从中删除设备的所有虚拟机的主机服务器上运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="786c8-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```
   Uninstall-CcAppliance
   ```


