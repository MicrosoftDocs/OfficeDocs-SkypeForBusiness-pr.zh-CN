---
title: 修改现有云连接器部署的配置
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 按照本主题中的步骤修改现有 Skype for Business 云连接器 Edition 1.4.1 或更高版本部署的配置。
ms.openlocfilehash: 4c2c0b8ad5340cd4ae4275f1ac009bf3d9d3ec0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018003"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="0e615-103">修改现有云连接器部署的配置</span><span class="sxs-lookup"><span data-stu-id="0e615-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="0e615-104">按照本主题中的步骤修改现有 Skype for Business 云连接器 Edition 1.4.1 或更高版本部署的配置。</span><span class="sxs-lookup"><span data-stu-id="0e615-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="0e615-105">修改单个网站的配置</span><span class="sxs-lookup"><span data-stu-id="0e615-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="0e615-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="0e615-107">如果站点中只有一个设备，则在部署设备后若要更改配置设置，可以修改 Cloudconnector.ini 文件并重新启动部署。</span><span class="sxs-lookup"><span data-stu-id="0e615-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="0e615-108">运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="0e615-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="0e615-109">运行以下 cmdlet 以注销设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="0e615-110">更新设备目录中的 Cloudconnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="0e615-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="0e615-111">运行以下 cmdlet 以更新配置：（此步骤仅适用于版本 2; 对于早期版本，请跳至下一步。）</span><span class="sxs-lookup"><span data-stu-id="0e615-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="0e615-112">运行以下 cmdlet 再次注册设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="0e615-113">运行以下 cmdlet 以安装 Skype for Business 云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="0e615-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="0e615-114">如果站点中有多个设备，您需要执行以下步骤，修改 Cloudconnector.ini 文件，然后逐个重新部署这些设备。</span><span class="sxs-lookup"><span data-stu-id="0e615-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="0e615-115">运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="0e615-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="0e615-116">运行以下 cmdlet 以注销设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="0e615-117">更新设备目录中的 Cloudconnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="0e615-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="0e615-118">运行以下 cmdlet 以更新配置：（此步骤仅适用于版本 2; 对于早期版本，请跳至下一步。）</span><span class="sxs-lookup"><span data-stu-id="0e615-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="0e615-119">运行以下 cmdlet 再次注册设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="0e615-120">在站点中的所有其他设备上运行以下 cmdlet，以获取最新配置：</span><span class="sxs-lookup"><span data-stu-id="0e615-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="0e615-121">运行以下 cmdlet 以在当前设备上重新部署云连接器：</span><span class="sxs-lookup"><span data-stu-id="0e615-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="0e615-122">修改多个网站的配置</span><span class="sxs-lookup"><span data-stu-id="0e615-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="0e615-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="0e615-124">若要修改部署中多个站点的配置，请按照单个站点的步骤操作，一次更新一个站点。</span><span class="sxs-lookup"><span data-stu-id="0e615-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="0e615-125">修改 Office 365 租户的配置以启用自动更新</span><span class="sxs-lookup"><span data-stu-id="0e615-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="0e615-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="0e615-127">若要启用操作系统自动更新和 Bits 自动更新，必须使用 Skype for Business 租户管理员帐户进行联机管理，并使用租户远程 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e615-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="0e615-128">如果您禁用了操作系统自动更新或 Bits 自动更新，则主机和虚拟机可能会错过重要的 Windows 更新，并且云连接器将不会自动升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="0e615-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="0e615-129">强烈建议您启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="0e615-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="0e615-130">需要将网站的 EnableAutoUpdate 属性设置为 true （默认值）。</span><span class="sxs-lookup"><span data-stu-id="0e615-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="0e615-131">运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：</span><span class="sxs-lookup"><span data-stu-id="0e615-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="0e615-132">为租户创建自动更新时间窗口。</span><span class="sxs-lookup"><span data-stu-id="0e615-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="0e615-133">时间窗口可以是每天、每周和每月。</span><span class="sxs-lookup"><span data-stu-id="0e615-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="0e615-134">所有时间窗口都需要一个开始时间和一个持续时间。</span><span class="sxs-lookup"><span data-stu-id="0e615-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="0e615-135">对于每日时间窗口，仅需要开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="0e615-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="0e615-136">对于每周时间窗口，需要一周天数，可以是一天或多天。</span><span class="sxs-lookup"><span data-stu-id="0e615-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="0e615-137">对于每月时间窗口，可以有两种类型。</span><span class="sxs-lookup"><span data-stu-id="0e615-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="0e615-138">第一种类型是指定月中的某一天，该日期可以是一天。</span><span class="sxs-lookup"><span data-stu-id="0e615-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="0e615-139">第二种类型是指定一个月中的周数以及一周中的天数，这两个值可以是单个项目，也可以是多个项目。</span><span class="sxs-lookup"><span data-stu-id="0e615-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="0e615-140">每个租户都可以定义20个时间窗口。</span><span class="sxs-lookup"><span data-stu-id="0e615-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="0e615-141">将为新租户创建默认时间窗口作为操作系统更新和 Bits 更新的默认时间窗口。</span><span class="sxs-lookup"><span data-stu-id="0e615-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="0e615-142">运行以下 cmdlet 以设置每日、每周或每月时间窗口：</span><span class="sxs-lookup"><span data-stu-id="0e615-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="0e615-143">将更新时间窗口分配给网站。</span><span class="sxs-lookup"><span data-stu-id="0e615-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="0e615-144">Bits 更新时间和 OS 更新时间窗口是单独配置的。</span><span class="sxs-lookup"><span data-stu-id="0e615-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="0e615-145">可以为它们分配一个或多个时间窗口。</span><span class="sxs-lookup"><span data-stu-id="0e615-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="0e615-146">每个时间窗口可分配给不同的网站和不同的用途（Bits 更新和 OS 更新）。</span><span class="sxs-lookup"><span data-stu-id="0e615-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="0e615-147">运行以下 cmdlet 来设置网站的时间窗口：</span><span class="sxs-lookup"><span data-stu-id="0e615-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="0e615-148">更新专用租户管理员凭据</span><span class="sxs-lookup"><span data-stu-id="0e615-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="0e615-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="0e615-150">Office 365 租户 for 云连接器中的管理更改是从具有所需权限的帐户进行的。</span><span class="sxs-lookup"><span data-stu-id="0e615-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="0e615-151">在2.0 之前的云连接器版本中，该帐户是专用的全局租户管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="0e615-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="0e615-152">在云连接器版本2.0 及更高版本中，该帐户可以是具有 Skype for Business 管理员权限的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="0e615-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="0e615-153">如果您的管理员帐户凭据在 Office 365 中更改，您还需要在部署的每个云连接器设备上运行以下管理员 PowerShell 命令，以更新云连接器中的本地缓存凭据：</span><span class="sxs-lookup"><span data-stu-id="0e615-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="0e615-154">更新主机服务器的密码</span><span class="sxs-lookup"><span data-stu-id="0e615-154">Update the password for the host server</span></span>
<span data-ttu-id="0e615-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="0e615-156">本节适用于云连接器版本2.0 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="0e615-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="0e615-157">所有云连接器凭据都存储在以下文件中： "%Systemdrive%\programdata\cloudconnector\credentials. .xml\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="0e615-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="0e615-158">当主机服务器上的密码更改时，您将需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="0e615-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="0e615-159">若要在云连接器设备上更新本地存储的凭据，请使用[set-cccredential](get-cccredential.md)和[set-cccredential](set-cccredential.md) cmdlet，并执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0e615-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="0e615-160">运行以下命令以检索稍后将需要的密码：</span><span class="sxs-lookup"><span data-stu-id="0e615-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="0e615-161">Set-cccredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="0e615-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="0e615-162">Set-cccredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="0e615-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="0e615-163">Set-cccredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="0e615-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="0e615-164">更改您的帐户在主机服务器上的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="0e615-165">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="0e615-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="0e615-166">删除以下文件： "%Systemdrive%\programdata\cloudconnector\credentials. .xml\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="0e615-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="0e615-167">以管理员身份启动 PowerShell 控制台，然后运行 "Register-ccappliance-Local" 以在说明后面重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="0e615-168">请确保输入的密码与您在云连接器部署之前输入的密码相同。</span><span class="sxs-lookup"><span data-stu-id="0e615-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="0e615-169">默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="0e615-170">如果在步骤1中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0e615-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="0e615-171">运行 Set-cccredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e615-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="0e615-172">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="0e615-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="0e615-173">当系统提示输入新帐户凭据时，请输入第1步中返回的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="0e615-174">运行 Set-cccredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e615-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="0e615-175">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="0e615-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="0e615-176">当系统提示输入新帐户凭据时，请输入第1步中返回的 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="0e615-177">更新 CceService 帐户的密码</span><span class="sxs-lookup"><span data-stu-id="0e615-177">Update the password for the CceService account</span></span>
<span data-ttu-id="0e615-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="0e615-179">本节适用于云连接器2.0.1 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="0e615-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="0e615-180">云连接器服务运行云连接器管理服务。</span><span class="sxs-lookup"><span data-stu-id="0e615-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="0e615-181">在云连接器版本部署过程中创建 CceService 帐户，并将其存储在以下文件中： "%Systemdrive%\programdata\cloudconnector\credentials. .xml\<CurrentUser\>"和"%SystemDrive%\Programdata\Cloudconnector\credentials。。CceService "。</span><span class="sxs-lookup"><span data-stu-id="0e615-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="0e615-182">若要确保所有设备都能访问网站目录共享，CceService 帐户的密码必须在网站中部署的所有设备上都相同。</span><span class="sxs-lookup"><span data-stu-id="0e615-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="0e615-183">请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="0e615-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="0e615-184">默认情况下，CceService 帐户配置为 "密码永不过期"。</span><span class="sxs-lookup"><span data-stu-id="0e615-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="0e615-185">更新密码时，Microsoft 建议保留此配置。</span><span class="sxs-lookup"><span data-stu-id="0e615-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="0e615-186">应在非高峰使用期和自动更新时间窗口之外的 bits 或 Windows 更新中更新密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="0e615-187">当您更新密码时，设备需要耗尽并重新启动，这需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="0e615-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="0e615-188">重新启动设备将会中断自动更新操作。</span><span class="sxs-lookup"><span data-stu-id="0e615-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="0e615-189">当您更改 CceService 帐户密码时，您需要指定所有凭据并在本地存储的文件中进行更新。</span><span class="sxs-lookup"><span data-stu-id="0e615-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="0e615-190">对于属于同一个 PSTN 站点的每个设备，您需要指定以下各项：</span><span class="sxs-lookup"><span data-stu-id="0e615-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="0e615-191">运行以下命令以检索稍后将使用的帐户名称和密码：</span><span class="sxs-lookup"><span data-stu-id="0e615-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="0e615-192">运行 Enter-ccupdate cmdlet 以耗尽设备并将其移动到手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="0e615-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="0e615-193">更新主机服务器上的 CceService 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="0e615-194">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="0e615-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="0e615-195">运行 CcCredentials cmdlet，以在说明后面重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="0e615-196">请确保输入的密码与您在云连接器部署之前输入的密码相同（CceService 帐户除外）。</span><span class="sxs-lookup"><span data-stu-id="0e615-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="0e615-197">对于 CceService 帐户，请输入新密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="0e615-198">确保 PSTN 站点中所有设备的 CceService 帐户的新密码是相同的。</span><span class="sxs-lookup"><span data-stu-id="0e615-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="0e615-199">默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="0e615-200">如果在步骤1中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0e615-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="0e615-201">运行 Set-cccredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e615-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="0e615-202">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="0e615-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="0e615-203">当系统提示输入新帐户凭据时，请输入第1步中返回的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="0e615-204">运行 Set-cccredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e615-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="0e615-205">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="0e615-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="0e615-206">当系统提示输入新帐户凭据时，请输入第1步中返回的 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="0e615-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="0e615-207">运行 Enter-ccupdate cmdlet 以将设备移出手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="0e615-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="0e615-208">在同一 PSTN 站点中的所有设备上完成这些步骤后，请删除站点根目录中的以下文件：</span><span class="sxs-lookup"><span data-stu-id="0e615-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="0e615-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="0e615-209">CcLockFile</span></span>
    
    - <span data-ttu-id="0e615-210">Site_\<边缘外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="0e615-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="0e615-211">Tenant_\<边缘外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="0e615-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="0e615-212">TenantConfigLock_\<边缘外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="0e615-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="0e615-213">添加新的 SIP 域</span><span class="sxs-lookup"><span data-stu-id="0e615-213">Add a new SIP domain</span></span>
<span data-ttu-id="0e615-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="0e615-215">若要向现有云连接器部署添加新的 SIP 域（或多个 SIP 域），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e615-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="0e615-216">请确保已完成在 Office 365 中更新域的步骤，并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="0e615-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="0e615-217">有关如何在 Office 365 中设置域的详细信息，请参阅[Add a domain To Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="0e615-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="0e615-218">使用新的 SIP 域或域更新云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="0e615-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="0e615-219">使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。在你的云连接器配置中定义的每个 SIP 域的域。</span><span class="sxs-lookup"><span data-stu-id="0e615-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="0e615-220">设置新的边缘外部证书的路径，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e615-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="0e615-221">按照说明[修改单个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)或[修改多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。</span><span class="sxs-lookup"><span data-stu-id="0e615-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="0e615-222">修改主要 SIP 域</span><span class="sxs-lookup"><span data-stu-id="0e615-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="0e615-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="0e615-224">如果您需要在云连接器部署中更改主要 SIP 域，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e615-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="0e615-225">请确保已完成在 Office 365 中更新域的步骤，并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="0e615-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="0e615-226">有关如何在 Office 365 中设置域的详细信息，请参阅[Add a domain To Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="0e615-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="0e615-227">使用新的 SIP 域更新云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="0e615-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="0e615-228">使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。在你的云连接器配置中定义的每个 SIP 域的域。</span><span class="sxs-lookup"><span data-stu-id="0e615-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="0e615-229">设置新的边缘外部证书的路径，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e615-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="0e615-230">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet，删除网站中每个设备的租户注册：</span><span class="sxs-lookup"><span data-stu-id="0e615-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="0e615-231">通过在 Skype for Business Online PowerShell 中运行以下 cmdlet 来删除每个网站的网站注册：</span><span class="sxs-lookup"><span data-stu-id="0e615-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="0e615-232">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 卸载每个设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="0e615-233">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 注册每个设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="0e615-234">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet，逐一安装每个设备：</span><span class="sxs-lookup"><span data-stu-id="0e615-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="0e615-235">将外部边缘证书替换为新证书</span><span class="sxs-lookup"><span data-stu-id="0e615-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="0e615-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="0e615-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="0e615-237">当您需要替换云连接器设备上的外部边缘证书时，您需要获取新的边缘证书，准备 PFX 文件，其中包含私钥和完整证书链，然后在每台设备上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e615-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="0e615-238">使用 Enter-ccupdate cmdlet 将设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="0e615-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="0e615-239">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0e615-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="0e615-240">如果新证书的密码与旧证书的密码相同，则导入将成功。</span><span class="sxs-lookup"><span data-stu-id="0e615-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="0e615-241">如果密码不同，您将收到错误消息，指出密码错误，您需要通过运行带有-Local 参数的 Register-ccappliance cmdlet 来重置密码，然后重复步骤2。</span><span class="sxs-lookup"><span data-stu-id="0e615-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="0e615-242">使用 Enter-ccupdate cmdlet 使设备退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="0e615-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

