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
description: 按照本主题中的步骤修改现有 Skype for Business Cloud Connector Edition 1.4.1 或更高版本的部署配置。
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799432"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="e73e8-103">Modify the configuration of an existing Cloud Connector deployment</span><span class="sxs-lookup"><span data-stu-id="e73e8-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="e73e8-104">按照本主题中的步骤修改现有 Skype for Business Cloud Connector Edition 1.4.1 或更高版本的部署配置。</span><span class="sxs-lookup"><span data-stu-id="e73e8-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="e73e8-105">修改单个站点的配置</span><span class="sxs-lookup"><span data-stu-id="e73e8-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="e73e8-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="e73e8-107">如果站点中仅有一个设备，并且你在部署设备之后想要更改配置设置，你可以修改 CloudConnector.ini 文件并重新开始部署。</span><span class="sxs-lookup"><span data-stu-id="e73e8-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="e73e8-108">运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="e73e8-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e73e8-109">运行以下 cmdlet 以注销该设备：</span><span class="sxs-lookup"><span data-stu-id="e73e8-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e73e8-110">更新设备目录中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="e73e8-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e73e8-111">运行以下 cmdlet 更新配置：（此步骤仅适用于版本 2; 对于以前的版本，请跳到下一步。）</span><span class="sxs-lookup"><span data-stu-id="e73e8-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e73e8-112">运行以下 cmdlet 以重新注册该设备：</span><span class="sxs-lookup"><span data-stu-id="e73e8-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="e73e8-113">运行以下 cmdlet 以安装 Skype for Business 云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="e73e8-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="e73e8-114">如果站点中有多台设备，则需执行以下步骤：修改 CloudConnector.ini 文件，并逐一重新部署设备。</span><span class="sxs-lookup"><span data-stu-id="e73e8-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="e73e8-115">运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机： </span><span class="sxs-lookup"><span data-stu-id="e73e8-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="e73e8-116">运行以下 cmdlet 以注销该设备：</span><span class="sxs-lookup"><span data-stu-id="e73e8-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="e73e8-117">更新设备目录中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="e73e8-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="e73e8-118">运行以下 cmdlet 更新配置：（此步骤仅适用于版本 2; 对于以前的版本，请跳到下一步。）</span><span class="sxs-lookup"><span data-stu-id="e73e8-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="e73e8-119">运行以下 cmdlet 以重新注册该设备：</span><span class="sxs-lookup"><span data-stu-id="e73e8-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="e73e8-120">对站点中的所有其他设备运行以下 cmdlet，以获取最新配置：</span><span class="sxs-lookup"><span data-stu-id="e73e8-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="e73e8-121">运行以下 cmdlet 以在当前设备上重新部署云连接器：</span><span class="sxs-lookup"><span data-stu-id="e73e8-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="e73e8-122">修改多个站点的配置</span><span class="sxs-lookup"><span data-stu-id="e73e8-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="e73e8-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="e73e8-124">若要在部署中修改多个网站的配置，请按照单个网站的步骤进行操作，一次更新一个网站。</span><span class="sxs-lookup"><span data-stu-id="e73e8-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a><span data-ttu-id="e73e8-125">修改 Office 365 租户的配置以启用自动更新</span><span class="sxs-lookup"><span data-stu-id="e73e8-125">Modify the configuration of your Office 365 tenant to enable automatic updates</span></span>
<span data-ttu-id="e73e8-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="e73e8-127">若要启用操作系统自动更新和 Bits 自动更新，必须使用 Skype for Business 租户管理员帐户进行联机管理，并使用租户远程 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e73e8-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="e73e8-128">如果你禁用了操作系统自动更新或 Bits 自动更新，则你的主机和虚拟机可能会错过重要的 Windows 更新，并且云连接器将不会自动升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="e73e8-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="e73e8-129">强烈建议启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="e73e8-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="e73e8-130">网站的 EnableAutoUpdate 属性需要设置为 true （默认值）。</span><span class="sxs-lookup"><span data-stu-id="e73e8-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="e73e8-131">运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：</span><span class="sxs-lookup"><span data-stu-id="e73e8-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="e73e8-132">为租户创建自动更新时间窗口。</span><span class="sxs-lookup"><span data-stu-id="e73e8-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="e73e8-p103">时间窗口可以是每日、每周和每月。所有时间窗口都需要指定开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="e73e8-p103">The time window can be daily, weekly and monthly. All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="e73e8-135">对于每日时间窗口，只需要指定开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="e73e8-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="e73e8-136">对于每周时间窗口，需要指定星期几，可以是一天或多天。</span><span class="sxs-lookup"><span data-stu-id="e73e8-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="e73e8-p104">对于每月时间窗口，可以是两种类型。第一种类型是指定月中几号，可以是一天。第二种类型是指定月中哪周和星期几，两者都可以是单个项或多个项。</span><span class="sxs-lookup"><span data-stu-id="e73e8-p104">For a monthly time window, there can be two types. The first type is to specify the day of the month, which can be a single day. The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="e73e8-p105">最多可为每个租户定义 20 个时间窗口。系统会为新租户创建默认时间窗口以用作操作系统更新和 Bits 更新的默认时间窗口。运行以下 cmdlet 以设置每日、每周或每月时间窗口：</span><span class="sxs-lookup"><span data-stu-id="e73e8-p105">Each tenant can have 20 time windows defined. The default time window will be created for a new tenant as the default time window for operating system update and Bits update. Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="e73e8-143">将更新时间窗口分配给站点。 </span><span class="sxs-lookup"><span data-stu-id="e73e8-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="e73e8-p106">位更新时间窗口和操作系统更新时间窗口是单独配置的。 可以为位更新和操作系统更新分配单个或多个时间窗口。 可以将每个时间窗口分配给不同站点和不同用途（位更新和操作系统更新）。 运行以下 cmdlet 为站点设置时间窗口： </span><span class="sxs-lookup"><span data-stu-id="e73e8-p106">The Bits update time and OS update time windows are configured separately. Both of them can be assigned single or multiple time windows. Each time window can be assigned to different sites and different purpose (Bits update and OS update). Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="e73e8-148">更新专用租户管理员凭据</span><span class="sxs-lookup"><span data-stu-id="e73e8-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="e73e8-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="e73e8-150">Office 365 租户 for Cloud Connector 中的管理更改是从具有所需权限的帐户进行的。</span><span class="sxs-lookup"><span data-stu-id="e73e8-150">Administrative changes in the Office 365 tenant for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="e73e8-151">在2.0 之前的云连接器版本中，该帐户是专用的全局租户管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="e73e8-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="e73e8-152">在云连接器版本2.0 和更高版本中，该帐户可以是具有 Skype for Business 管理员权限的 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="e73e8-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="e73e8-153">如果你的管理员帐户凭据在 Office 365 中发生更改，你还需要通过在你部署的每个云连接器装置上运行以下管理员 PowerShell 命令来更新云连接器中的本地缓存凭据：</span><span class="sxs-lookup"><span data-stu-id="e73e8-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="e73e8-154">更新主机服务器的密码</span><span class="sxs-lookup"><span data-stu-id="e73e8-154">Update the password for the host server</span></span>
<span data-ttu-id="e73e8-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e73e8-156">本节仅适用于云连接器 2.0 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="e73e8-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="e73e8-157">所有云连接器凭据均存储在以下文件中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="e73e8-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e73e8-158">当主机服务器上的密码更改时，需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="e73e8-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="e73e8-159">若要在云连接器设备上更新本地存储的凭据，请使用[CcCredential](get-cccredential.md)和[CcCredential](set-cccredential.md) cmdlet，然后按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="e73e8-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="e73e8-160">运行以下命令，以检索稍后将需要的密码：</span><span class="sxs-lookup"><span data-stu-id="e73e8-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="e73e8-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e73e8-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e73e8-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e73e8-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="e73e8-163">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="e73e8-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="e73e8-164">在主机服务器上更改帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="e73e8-165">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="e73e8-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="e73e8-166">删除以下文件： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="e73e8-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="e73e8-167">以管理员身份启动 PowerShell 控制台，然后运行 "Register-CcAppliance" 以在描述后重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e73e8-168">请务必输入之前输入的用于云连接器部署的相同密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="e73e8-p110">默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e73e8-p110">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="e73e8-171">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="e73e8-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="e73e8-172">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e73e8-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e73e8-173">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="e73e8-174">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="e73e8-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="e73e8-175">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e73e8-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="e73e8-176">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="e73e8-177">更新 CceService 帐户的密码</span><span class="sxs-lookup"><span data-stu-id="e73e8-177">Update the password for the CceService account</span></span>
<span data-ttu-id="e73e8-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="e73e8-179">此部分适用于云连接器版本2.0.1 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="e73e8-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="e73e8-180">云连接器服务运行云连接器管理服务。</span><span class="sxs-lookup"><span data-stu-id="e73e8-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="e73e8-181">CceService 帐户在云连接器版本部署期间创建并存储在以下文件中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>和%SystemDrive%\Programdata\Cloudconnector\credentials。。CceService "。</span><span class="sxs-lookup"><span data-stu-id="e73e8-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="e73e8-182">若要确保所有设备都可以访问网站目录共享，CceService 帐户的密码在网站中部署的所有设备上必须是相同的。</span><span class="sxs-lookup"><span data-stu-id="e73e8-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="e73e8-183">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="e73e8-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="e73e8-184">默认情况下，CceService 帐户配置为 "密码永不过期"。</span><span class="sxs-lookup"><span data-stu-id="e73e8-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="e73e8-185">更新密码时，Microsoft 建议保留此配置。</span><span class="sxs-lookup"><span data-stu-id="e73e8-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="e73e8-186">你应该在非高峰使用期和自动更新时间窗口（bits 或 Windows 更新）外更新密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="e73e8-187">更新密码时，设备需要排出并重新启动，这需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="e73e8-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="e73e8-188">重新启动装置将中断自动更新操作。</span><span class="sxs-lookup"><span data-stu-id="e73e8-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="e73e8-189">更改 CceService 帐户密码时，你需要指定所有凭据并在本地存储的文件中更新它们。</span><span class="sxs-lookup"><span data-stu-id="e73e8-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="e73e8-190">对于属于同一 PSTN 站点的每个装置，您将需要指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e73e8-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="e73e8-191">运行以下命令以检索稍后将使用的帐户名称和密码：</span><span class="sxs-lookup"><span data-stu-id="e73e8-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="e73e8-192">运行 CcUpdate cmdlet 以耗尽装置并将其移动到手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="e73e8-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="e73e8-193">更新主服务器上的 CceService 帐户密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="e73e8-194">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="e73e8-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="e73e8-195">运行 CcCredentials cmdlet 以在描述之后重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="e73e8-196">请确保输入的密码与你在云连接器部署之前输入的密码相同，但 CceService 帐户除外。</span><span class="sxs-lookup"><span data-stu-id="e73e8-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="e73e8-197">对于 CceService 帐户，请输入您的新密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="e73e8-198">请确保 CceService 帐户的新密码对于 PSTN 站点中的所有设备都是相同的。</span><span class="sxs-lookup"><span data-stu-id="e73e8-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="e73e8-p116">默认情况下，VmAdmin 和 DomainAdmin 与 CceService 使用相同的密码。如果第 1 步中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e73e8-p116">By default, VmAdmin and DomainAdmin use the same password as CceService. If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="e73e8-201">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="e73e8-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="e73e8-202">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e73e8-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e73e8-203">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="e73e8-204">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="e73e8-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="e73e8-205">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e73e8-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="e73e8-206">当系统提示输入新帐户凭据时，请输入第 1 步中返回的用作 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e73e8-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="e73e8-207">运行 CcUpdate cmdlet，将设备移出手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="e73e8-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="e73e8-208">在同一 PSTN 站点中的所有装置上完成这些步骤后，在 "网站根目录" 中删除以下文件：</span><span class="sxs-lookup"><span data-stu-id="e73e8-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="e73e8-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="e73e8-209">CcLockFile</span></span>
    
    - <span data-ttu-id="e73e8-210">Site_\<Edge 外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="e73e8-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e73e8-211">Tenant_\<Edge 外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="e73e8-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="e73e8-212">TenantConfigLock_\<Edge 外部 Sip 池 fqdn\></span><span class="sxs-lookup"><span data-stu-id="e73e8-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="e73e8-213">添加新 SIP 域 </span><span class="sxs-lookup"><span data-stu-id="e73e8-213">Add a new SIP domain</span></span>
<span data-ttu-id="e73e8-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="e73e8-215">若要向现有云连接器部署添加新的 SIP 域（或多个 SIP 域），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e73e8-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e73e8-216">确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e73e8-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e73e8-217">有关如何在 Office 365 中设置域的详细信息，请参阅[将域添加到 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="e73e8-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e73e8-218">用新的 SIP 域或域更新云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="e73e8-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="e73e8-219">使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。适用于你的云连接器配置中定义的每个 SIP 域的域。</span><span class="sxs-lookup"><span data-stu-id="e73e8-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e73e8-220">按如下所述设置新边缘外部证书的路径：</span><span class="sxs-lookup"><span data-stu-id="e73e8-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e73e8-221">按照说明[修改单个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite)或[修改多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。</span><span class="sxs-lookup"><span data-stu-id="e73e8-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="e73e8-222">输入主 SIP 域</span><span class="sxs-lookup"><span data-stu-id="e73e8-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="e73e8-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="e73e8-224">如果需要在云连接器部署中更改主要 SIP 域，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e73e8-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="e73e8-225">确保你已完成在 Office 365 中更新域的步骤并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="e73e8-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="e73e8-226">有关如何在 Office 365 中设置域的详细信息，请参阅[将域添加到 office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。</span><span class="sxs-lookup"><span data-stu-id="e73e8-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="e73e8-227">用新的 SIP 域更新云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="e73e8-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="e73e8-228">使用 sip 的其他 SAN 名称请求新的 Edge 外部证书。适用于你的云连接器配置中定义的每个 SIP 域的域。</span><span class="sxs-lookup"><span data-stu-id="e73e8-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="e73e8-229">按如下所述设置新边缘外部证书的路径：</span><span class="sxs-lookup"><span data-stu-id="e73e8-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="e73e8-230">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 来删除网站中每个设备的租户注册：</span><span class="sxs-lookup"><span data-stu-id="e73e8-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="e73e8-231">通过在 Skype for Business Online PowerShell 中运行以下 cmdlet 来删除每个网站的网站注册：</span><span class="sxs-lookup"><span data-stu-id="e73e8-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="e73e8-232">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 来卸载每个装置：</span><span class="sxs-lookup"><span data-stu-id="e73e8-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="e73e8-233">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet 来注册每个设备：</span><span class="sxs-lookup"><span data-stu-id="e73e8-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="e73e8-234">通过在云连接器上的管理员 PowerShell 中运行以下 cmdlet，逐个安装每个装置：</span><span class="sxs-lookup"><span data-stu-id="e73e8-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="e73e8-235">将外部边缘证书替换为新证书</span><span class="sxs-lookup"><span data-stu-id="e73e8-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="e73e8-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="e73e8-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="e73e8-237">当你需要替换云连接器装置上的外部边缘证书时，你需要获取新的边缘证书，准备包含私钥和完整证书链的 PFX 文件，然后在每个设备上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e73e8-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="e73e8-238">通过使用 CcUpdate cmdlet 将设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="e73e8-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="e73e8-239">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e73e8-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="e73e8-240">如果新证书的密码与旧证书的密码相同，则导入将成功。</span><span class="sxs-lookup"><span data-stu-id="e73e8-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="e73e8-241">如果密码不同，你将收到错误，指出密码错误，你将需要通过运行带有-Local 参数的 CcAppliance cmdlet 来重置密码，然后重复步骤2。</span><span class="sxs-lookup"><span data-stu-id="e73e8-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="e73e8-242">通过使用 CcUpdate cmdlet 使设备退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="e73e8-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

