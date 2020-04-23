---
title: 在云连接器中部署单个网站
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
ms.openlocfilehash: cc508d21f9e39c215ce3c07403ab75e791e2414a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779348"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="ea1e5-103">在云连接器中部署单个网站</span><span class="sxs-lookup"><span data-stu-id="ea1e5-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="ea1e5-104">了解如何在云连接器版本中部署单个 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="ea1e5-105">您可以部署具有或不具有高可用性（HA）支持的 Skype for Business 云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="ea1e5-106">如果要启用 HA，则需要在站点中部署两个或更多个设备。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="ea1e5-107">您还可以在部署现有设备后将其转换为支持 HA。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="ea1e5-108">部署第一个 Skype for Business 云连接器版本设备</span><span class="sxs-lookup"><span data-stu-id="ea1e5-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="ea1e5-109">若要在站点中部署第一个设备，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet 来注册设备：</span><span class="sxs-lookup"><span data-stu-id="ea1e5-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="ea1e5-110">按照说明提供租户管理员帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="ea1e5-111">使用为云连接器在线管理创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="ea1e5-112">此外，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码以及虚拟机管理员密码。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="ea1e5-113">在1.4.2 版和早期版本中，还按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="ea1e5-114">在版本2.0 及更高版本中，还要按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="ea1e5-115">若要开始安装，请以管理员身份打开 PowerShell 控制台，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ea1e5-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="ea1e5-116">将设备添加到现有网站</span><span class="sxs-lookup"><span data-stu-id="ea1e5-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="ea1e5-117">您可以通过向站点添加其他设备来扩展现有云连接器网站，以支持 HA。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="ea1e5-118">按照[准备云连接器设备](prepare-your-cloud-connector-appliance.md)中所述的步骤准备云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="ea1e5-119">请注意，仅在部署中的第一台设备上需要一些步骤。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="ea1e5-120">确认网站目录存在，并且已正确配置 HA 支持。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="ea1e5-121">仅在新添加的主机服务器上运行以下 cmdlet，以更新 Office 365 组织配置中的拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-121">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 organization configuration.</span></span> <span data-ttu-id="ea1e5-122">如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ea1e5-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="ea1e5-123">通过在每台主机服务器上运行以下 cmdlet 来更新现有设备上的拓扑。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="ea1e5-124">仅在现有设备上运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="ea1e5-125">仅在新添加的主机服务器上运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="ea1e5-126">请勿在现有设备上运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="ea1e5-127">如果要同时添加多个设备，请逐个在每个新添加的主机服务器上运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="ea1e5-128">如果网站目录设置为本地文件夹路径，则需要为该文件夹定义文件共享，并在新设备上对网站目录使用 UNC 路径。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="ea1e5-129">你可以将第一个装置网站目录保留为本地路径，或将其修改为将共享的 UNC 路径用于同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="ea1e5-130">如果共享网站目录的位置发生更改，则需要卸载之前安装的所有设备，然后重新安装。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="ea1e5-131">> 重要说明： CceService 帐户和 CABackupFile 帐户的密码必须在网站中部署的所有设备上都相同，这样设备才能访问网站目录中的网站目录共享和加密的 CA 备份文件。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="ea1e5-132">从现有网站中删除设备</span><span class="sxs-lookup"><span data-stu-id="ea1e5-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="ea1e5-133">如果要从现有站点中删除设备，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea1e5-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="ea1e5-134">仅在要从网站中删除的主机服务器上运行以下 cmdlet，以更新 Office 365 组织配置中的拓扑信息。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="ea1e5-135">仅在要从中删除设备的所有虚拟机的主机服务器上运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea1e5-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


