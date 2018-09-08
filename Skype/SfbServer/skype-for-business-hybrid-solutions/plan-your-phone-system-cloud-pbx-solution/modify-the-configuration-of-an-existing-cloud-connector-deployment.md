---
title: 修改现有云连接器部署的配置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 按照本主题可修改现有的 Skype 商务云连接器版 1.4.1 或更高版本的部署的配置中的步骤。
ms.openlocfilehash: fe226e67f6f492e0fae7473156908cd4a5147ea2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885801"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="73506-103">修改现有云连接器部署的配置</span><span class="sxs-lookup"><span data-stu-id="73506-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="73506-104">按照本主题可修改现有的 Skype 商务云连接器版 1.4.1 或更高版本的部署的配置中的步骤。</span><span class="sxs-lookup"><span data-stu-id="73506-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="73506-105">修改单个站点的配置</span><span class="sxs-lookup"><span data-stu-id="73506-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="73506-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-106"></span></span>

<span data-ttu-id="73506-107">如果站点中仅有一个设备，并且你在部署设备之后想要更改配置设置，你可以修改 CloudConnector.ini 文件并重新开始部署。</span><span class="sxs-lookup"><span data-stu-id="73506-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="73506-108">运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="73506-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
  ```
  Uninstall-CcAppliance
  ```

2. <span data-ttu-id="73506-109">运行以下 cmdlet 以注销该设备：</span><span class="sxs-lookup"><span data-stu-id="73506-109">Run the following cmdlet to unregister the appliance:</span></span>
    
  ```
  Unregister-CcAppliance
  ```

3. <span data-ttu-id="73506-110">更新设备目录中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="73506-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="73506-111">运行以下 cmdlet 以更新配置: （此步骤仅适用的版本 2; 早期版本，请跳到下一步。）</span><span class="sxs-lookup"><span data-stu-id="73506-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
  ```
   Import-CcConfiguration 
  ```

5. <span data-ttu-id="73506-112">运行以下 cmdlet 以重新注册该设备：</span><span class="sxs-lookup"><span data-stu-id="73506-112">Run the following cmdlet to register the appliance again:</span></span>
    
  ```
  Register-CcAppliance
  ```

6. <span data-ttu-id="73506-113">运行以下 cmdlet 以安装 Skype for Business 云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="73506-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
  ```
  Install-CcAppliance
  ```

<span data-ttu-id="73506-114">如果站点中有多台设备，则需执行以下步骤：修改 CloudConnector.ini 文件，并逐一重新部署设备。</span><span class="sxs-lookup"><span data-stu-id="73506-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="73506-115">运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="73506-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
  ```
  Uninstall-CcAppliance
  ```

2. <span data-ttu-id="73506-116">运行以下 cmdlet 以注销该设备：</span><span class="sxs-lookup"><span data-stu-id="73506-116">Run the following cmdlet to unregister the appliance:</span></span>
    
  ```
  Unregister-CcAppliance
  ```

3. <span data-ttu-id="73506-117">更新设备目录中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="73506-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="73506-118">运行以下 cmdlet 以更新配置: （此步骤仅适用的版本 2; 早期版本，请跳到下一步。）</span><span class="sxs-lookup"><span data-stu-id="73506-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
  ```
   Import-CcConfiguration 
  ```

5. <span data-ttu-id="73506-119">运行以下 cmdlet 以重新注册该设备：</span><span class="sxs-lookup"><span data-stu-id="73506-119">Run the following cmdlet to register the appliance again:</span></span>
    
  ```
  Register-CcAppliance
  ```

6. <span data-ttu-id="73506-120">对站点中的所有其他设备运行以下 cmdlet，以获取最新配置：</span><span class="sxs-lookup"><span data-stu-id="73506-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
  ```
  Publish-CcAppliance
  ```

7. <span data-ttu-id="73506-121">运行以下 cmdlet，以在当前的设备上重新部署云连接器：</span><span class="sxs-lookup"><span data-stu-id="73506-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
  ```
  Install-CcAppliance
  ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="73506-122">修改多个站点的配置</span><span class="sxs-lookup"><span data-stu-id="73506-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="73506-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-123"></span></span>

<span data-ttu-id="73506-124">要修改部署中的多个站点的配置，请按照单个网站，一次更新一个站点的步骤。</span><span class="sxs-lookup"><span data-stu-id="73506-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="73506-125">修改 Office 365 租户的配置以启用自动更新</span><span class="sxs-lookup"><span data-stu-id="73506-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="73506-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-126"></span></span>

<span data-ttu-id="73506-127">若要启用操作系统自动更新和位自动更新，必须使用 Skype 的业务租户管理员帐户的在线管理和使用租户远程 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="73506-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="73506-128">如果您禁用操作系统自动更新或位自动更新，您的主机和虚拟机可能会错过重要的 Windows 更新，和云连接器不会自动升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="73506-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="73506-129">强烈建议启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="73506-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="73506-130">网站的 EnableAutoUpdate 属性必须设置为 true （默认值）。</span><span class="sxs-lookup"><span data-stu-id="73506-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="73506-131">运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：</span><span class="sxs-lookup"><span data-stu-id="73506-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
  ```
  Get-CsHybridPSTNSite -Identity <SiteName>
  ```

2. <span data-ttu-id="73506-132">为租户创建自动更新时间窗口。</span><span class="sxs-lookup"><span data-stu-id="73506-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="73506-p103">时间窗口可以是每日、每周和每月。所有时间窗口都需要指定开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="73506-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
  - <span data-ttu-id="73506-135">对于每日时间窗口，只需要指定开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="73506-135">For a daily time window, only start time and duration are needed.</span></span> 
    
  - <span data-ttu-id="73506-136">对于每周时间窗口，需要指定星期几，可以是一天或多天。</span><span class="sxs-lookup"><span data-stu-id="73506-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
  - <span data-ttu-id="73506-p104">对于每月时间窗口，可以是两种类型。第一种类型是指定月中几号，可以是一天。第二种类型是指定月中哪周和星期几，两者都可以是单个项或多个项。</span><span class="sxs-lookup"><span data-stu-id="73506-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
  - <span data-ttu-id="73506-p105">最多可为每个租户定义 20 个时间窗口。系统会为新租户创建默认时间窗口以用作操作系统更新和 Bits 更新的默认时间窗口。运行以下 cmdlet 以设置每日、每周或每月时间窗口：</span><span class="sxs-lookup"><span data-stu-id="73506-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
  ```
  New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
  ```

  - <span data-ttu-id="73506-143">将更新时间窗口分配给站点。</span><span class="sxs-lookup"><span data-stu-id="73506-143">Assign update time windows to the site.</span></span> 
    
    <span data-ttu-id="73506-144">位更新时间窗口和操作系统更新时间窗口是单独配置的。</span><span class="sxs-lookup"><span data-stu-id="73506-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="73506-145">可以为位更新和操作系统更新分配单个或多个时间窗口。</span><span class="sxs-lookup"><span data-stu-id="73506-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="73506-146">可以将每个时间窗口分配给不同站点和不同用途（位更新和操作系统更新）。</span><span class="sxs-lookup"><span data-stu-id="73506-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="73506-147">运行以下 cmdlet 为站点设置时间窗口：</span><span class="sxs-lookup"><span data-stu-id="73506-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
  ```
  Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
  ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="73506-148">更新专用租户管理员凭据</span><span class="sxs-lookup"><span data-stu-id="73506-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="73506-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-149"></span></span>

<span data-ttu-id="73506-150">从具有所需权限的帐户进行管理云连接器为 Office 365 租户中的更改。</span><span class="sxs-lookup"><span data-stu-id="73506-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="73506-151">在云连接器 2.0 之前的版本，该帐户是专用全局租户管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="73506-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="73506-152">在云连接器版本 2.0 及更高版本中，该帐户可以是具有 Skype 业务管理员权限的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="73506-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="73506-153">如果在 Office 365 中更改您的管理员帐户凭据，您还需要通过运行以下管理员 PowerShell 命令已部署的每台云连接器装置更新云 Connector 中的本地缓存的凭据：</span><span class="sxs-lookup"><span data-stu-id="73506-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="73506-154">更新主机服务器的密码</span><span class="sxs-lookup"><span data-stu-id="73506-154">Update the password for the host server</span></span>
<span data-ttu-id="73506-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-155"></span></span>

> [!NOTE]
> <span data-ttu-id="73506-156">本节仅适用于云连接器 2.0 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="73506-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="73506-157">所有云连接器凭据都存储在以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="73506-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="73506-158">当主机服务器上的密码更改时，您将需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="73506-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="73506-159">若要更新云连接器装置上本地存储的凭据，请使用[Get-CcCredential](get-cccredential.md)和[设置 CcCredential](set-cccredential.md) cmdlet，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="73506-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="73506-160">运行以下命令，以检索稍后将需要的密码：</span><span class="sxs-lookup"><span data-stu-id="73506-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
  - <span data-ttu-id="73506-161">Get CcCredential-AccountType DomainAdmin DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="73506-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
  - <span data-ttu-id="73506-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="73506-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
  - <span data-ttu-id="73506-163">Get CcCredential-AccountType CceService DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="73506-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="73506-164">在主机服务器上更改帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="73506-165">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="73506-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="73506-166">删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="73506-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="73506-167">启动作为管理员，PowerShell 控制台，然后运行"注册 CcAppliance-本地"以重新输入以下说明的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="73506-168">确保您输入您之前输入云连接器部署的同一密码。</span><span class="sxs-lookup"><span data-stu-id="73506-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="73506-p110">默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="73506-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="73506-171">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="73506-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="73506-172">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="73506-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="73506-173">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="73506-174">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="73506-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="73506-175">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="73506-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="73506-176">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="73506-177">更新 CceService 帐户的密码</span><span class="sxs-lookup"><span data-stu-id="73506-177">Update the password for the CceService account</span></span>
<span data-ttu-id="73506-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-178"></span></span>

> [!NOTE]
> <span data-ttu-id="73506-179">本节是适用于云连接器 2.0.1 版及更高版本。</span><span class="sxs-lookup"><span data-stu-id="73506-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="73506-180">云连接器服务运行云连接器管理服务。</span><span class="sxs-lookup"><span data-stu-id="73506-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="73506-181">云连接器 Edition 部署过程中创建的 CceService 帐户并将其存储在以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"和"%systemdrive%\programdata\cloudconnector\credentials...CceService.xml"。</span><span class="sxs-lookup"><span data-stu-id="73506-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="73506-182">若要确保所有装置可都访问网站目录共享，CceService 帐户的密码必须部署在网站的所有装置相同。</span><span class="sxs-lookup"><span data-stu-id="73506-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="73506-183">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="73506-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="73506-184">默认情况下，CceService 帐户被配置为"密码永不过期"。</span><span class="sxs-lookup"><span data-stu-id="73506-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="73506-185">更新密码时，Microsoft 建议保留此配置。</span><span class="sxs-lookup"><span data-stu-id="73506-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="73506-186">在非高峰使用时段和位或 Windows update 的自动更新时间范围之外，您应更新密码。</span><span class="sxs-lookup"><span data-stu-id="73506-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="73506-187">更新密码时，设备需要排空和重新启动，这需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="73506-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="73506-188">重新启动设备将中断自动更新操作。</span><span class="sxs-lookup"><span data-stu-id="73506-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="73506-189">CceService 帐户密码更改时，您将需要指定所有的凭据，并存储在本地文件中对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="73506-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="73506-190">对于每个装置属于相同的 PSTN 网站，您需要指定以下：</span><span class="sxs-lookup"><span data-stu-id="73506-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="73506-191">运行以下命令以检索的帐户名称和稍后将用的密码：</span><span class="sxs-lookup"><span data-stu-id="73506-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
  ```
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

2. <span data-ttu-id="73506-192">运行 Enter CcUpdate cmdlet 排出设备，并将其移到手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="73506-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="73506-193">更新主机服务器上的 CceService 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="73506-194">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="73506-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="73506-195">运行还原 CcCredentials cmdlet 重新输入以下说明的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="73506-196">确保您输入您之前输入云连接器部署除外 CceService 帐户相同的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="73506-197">对于 CceService 帐户中，输入新密码。</span><span class="sxs-lookup"><span data-stu-id="73506-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="73506-198">确保 CceService 帐户的新密码是相同的 PSTN 网站中的所有设备。</span><span class="sxs-lookup"><span data-stu-id="73506-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="73506-p116">默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="73506-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
1. <span data-ttu-id="73506-201">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="73506-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  - <span data-ttu-id="73506-202">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="73506-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  - <span data-ttu-id="73506-203">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="73506-204">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="73506-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
  - <span data-ttu-id="73506-205">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="73506-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  - <span data-ttu-id="73506-206">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="73506-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
7. <span data-ttu-id="73506-207">运行退出 CcUpdate cmdlet 将移动设备脱离手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="73506-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
8. <span data-ttu-id="73506-208">完成相同的 PSTN 网站中的所有装置这些步骤后，删除网站的根目录中的以下文件：</span><span class="sxs-lookup"><span data-stu-id="73506-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
  - <span data-ttu-id="73506-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="73506-209">CcLockFile</span></span>
    
  - <span data-ttu-id="73506-210">Site_\<边缘外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="73506-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
  - <span data-ttu-id="73506-211">Tenant_\<边缘外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="73506-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
  - <span data-ttu-id="73506-212">TenantConfigLock_\<边缘外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="73506-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="73506-213">添加新 SIP 域 </span><span class="sxs-lookup"><span data-stu-id="73506-213">Add a new SIP domain</span></span>
<span data-ttu-id="73506-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-214"></span></span>

<span data-ttu-id="73506-215">要添加到现有的云连接器部署一个新的 SIP 域 （或多个 SIP 域），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73506-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="73506-216">确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="73506-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="73506-217">有关如何设置您在 Office 365 中的域的详细信息，请参阅[添加到 Office 365 域](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="73506-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="73506-218">更新云连接器配置文件的新的 SIP 域或域。</span><span class="sxs-lookup"><span data-stu-id="73506-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="73506-219">请求具有其他 SAN sip.domain 云连接器配置中定义的每个 SIP 域的名称的新边缘外部证书。</span><span class="sxs-lookup"><span data-stu-id="73506-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="73506-220">按如下所述设置新边缘外部证书的路径：</span><span class="sxs-lookup"><span data-stu-id="73506-220">Set the path for the new Edge external certificate as follows:</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    <span data-ttu-id="73506-221">按照说明[修改单个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)或[修改多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。</span><span class="sxs-lookup"><span data-stu-id="73506-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="73506-222">输入主 SIP 域</span><span class="sxs-lookup"><span data-stu-id="73506-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="73506-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-223"></span></span>

<span data-ttu-id="73506-224">如果您需要更改云连接器部署中的主 SIP 域，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="73506-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="73506-225">确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="73506-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="73506-226">有关如何设置您在 Office 365 中的域的详细信息，请参阅[添加到 Office 365 域](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="73506-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="73506-227">更新新的 SIP 域与云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="73506-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="73506-228">请求具有其他 SAN sip.domain 云连接器配置中定义的每个 SIP 域的名称的新边缘外部证书。</span><span class="sxs-lookup"><span data-stu-id="73506-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="73506-229">按如下所述设置新边缘外部证书的路径：</span><span class="sxs-lookup"><span data-stu-id="73506-229">Set the path for the new Edge external certificate as follows:</span></span>
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    <span data-ttu-id="73506-230">删除站点中的每个装置的租户注册，通过运行以下 cmdlet 在管理员 PowerShell 云连接器上：</span><span class="sxs-lookup"><span data-stu-id="73506-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
  ```
  Unregister-CcAppliance
  ```

6. 
    
    <span data-ttu-id="73506-231">通过在 Skype for Business Online PowerShell 中运行以下 cmdlet 来删除每个网站的网站注册：</span><span class="sxs-lookup"><span data-stu-id="73506-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
  ```
  Remove-CsHybridPSTNSite
  ```

7. 
    
    <span data-ttu-id="73506-232">卸载每个设备上云连接器管理员 PowerShell 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="73506-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

8. 
    
     <span data-ttu-id="73506-233">通过运行以下 cmdlet 在管理员 PowerShell 云连接器上注册每个设备：</span><span class="sxs-lookup"><span data-stu-id="73506-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
  ```
  Register-ccAppliance
  ```

9. 
    
     <span data-ttu-id="73506-234">安装每个设备，逐个，通过云连接器上管理员 PowerShell 中运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="73506-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
  ```
  Install-CcAppliance
  ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="73506-235">外部边缘证书替换为新的证书</span><span class="sxs-lookup"><span data-stu-id="73506-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="73506-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="73506-236"></span></span>

<span data-ttu-id="73506-237">当您需要替换云连接器 appliance 上的外部边缘证书时，需要获取新的边缘证书，准备包含私钥和完整的证书链的 PFX 文件，然后执行以下每个设备：</span><span class="sxs-lookup"><span data-stu-id="73506-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="73506-238">使用 Enter CcUpdate cmdlet 置于维护模式下设备。</span><span class="sxs-lookup"><span data-stu-id="73506-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="73506-239">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="73506-239">Run the following command:</span></span> 
    
  ```
  Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
  ```

3. 
    
    <span data-ttu-id="73506-240">如果旧相同的新证书的密码，将会导致导入成功。</span><span class="sxs-lookup"><span data-stu-id="73506-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="73506-241">如果密码不同，您将收到错误密码不正确，并且您将需要通过运行注册 CcAppliance cmdlet 重置密码使用-本地参数，然后重复步骤 2。</span><span class="sxs-lookup"><span data-stu-id="73506-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="73506-242">使用退出 CcUpdate cmdlet 执行脱离维护模式 appliance。</span><span class="sxs-lookup"><span data-stu-id="73506-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

