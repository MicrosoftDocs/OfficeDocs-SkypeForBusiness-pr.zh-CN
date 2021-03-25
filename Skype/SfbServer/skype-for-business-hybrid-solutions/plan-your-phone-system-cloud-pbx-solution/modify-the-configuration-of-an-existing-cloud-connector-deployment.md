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
description: 按照本主题中的步骤修改现有 Skype for Business 云连接器版本 1.4.1 或更高版本部署的配置。
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109168"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="1ab57-103">修改现有云连接器部署的配置</span><span class="sxs-lookup"><span data-stu-id="1ab57-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="1ab57-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="1ab57-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="1ab57-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="1ab57-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="1ab57-106">按照本主题中的步骤修改现有 Skype for Business 云连接器版本 1.4.1 或更高版本部署的配置。</span><span class="sxs-lookup"><span data-stu-id="1ab57-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="1ab57-107">修改单个网站的配置</span><span class="sxs-lookup"><span data-stu-id="1ab57-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="1ab57-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="1ab57-109">如果站点中只有一个设备，当你想要在部署设备后更改配置设置时，你可以修改 CloudConnector.ini 文件，然后重新开始部署。</span><span class="sxs-lookup"><span data-stu-id="1ab57-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="1ab57-110">运行以下 cmdlet 以卸载主机服务器上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="1ab57-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="1ab57-111">运行以下 cmdlet 以注销设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="1ab57-112">更新CloudConnector.ini目录中的安装文件。</span><span class="sxs-lookup"><span data-stu-id="1ab57-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="1ab57-113">运行以下 cmdlet 以更新配置： (此步骤仅适用于版本 2;对于早期版本，请跳到下一步。) </span><span class="sxs-lookup"><span data-stu-id="1ab57-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="1ab57-114">再次运行以下 cmdlet 以注册设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="1ab57-115">运行以下 cmdlet 以安装 Skype for Business 云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="1ab57-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="1ab57-116">如果站点中存在多个设备，则需要按照以下步骤操作、修改 CloudConnector.ini 文件，然后一个一个地重新部署设备。</span><span class="sxs-lookup"><span data-stu-id="1ab57-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="1ab57-117">运行以下 cmdlet 以卸载当前设备上的所有现有虚拟机：</span><span class="sxs-lookup"><span data-stu-id="1ab57-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="1ab57-118">运行以下 cmdlet 以注销设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="1ab57-119">更新CloudConnector.ini目录中的安装文件。</span><span class="sxs-lookup"><span data-stu-id="1ab57-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="1ab57-120">运行以下 cmdlet 以更新配置： (此步骤仅适用于版本 2;对于早期版本，请跳到下一步。) </span><span class="sxs-lookup"><span data-stu-id="1ab57-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="1ab57-121">再次运行以下 cmdlet 以注册设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="1ab57-122">对站点中的所有其他设备运行以下 cmdlet，以获取最新配置：</span><span class="sxs-lookup"><span data-stu-id="1ab57-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="1ab57-123">运行以下 cmdlet 以在当前设备中重新部署云连接器：</span><span class="sxs-lookup"><span data-stu-id="1ab57-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="1ab57-124">修改多个网站的配置</span><span class="sxs-lookup"><span data-stu-id="1ab57-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="1ab57-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="1ab57-126">若要修改部署中多个站点的配置，请按照单个站点的步骤操作，一次更新一个站点。</span><span class="sxs-lookup"><span data-stu-id="1ab57-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="1ab57-127">修改 Microsoft 365 或 Office 365 组织的配置以启用自动更新</span><span class="sxs-lookup"><span data-stu-id="1ab57-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="1ab57-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="1ab57-129">若要启用操作系统自动更新和 Bits 自动更新，必须使用 Skype for Business 租户管理员帐户进行联机管理，并使用租户远程 PowerShell，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1ab57-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="1ab57-130">如果禁用操作系统自动更新或 Bits 自动更新，主机和虚拟机可能会错过重要的 Windows 更新，并且云连接器不会自动升级到新版本。</span><span class="sxs-lookup"><span data-stu-id="1ab57-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="1ab57-131">强烈建议您启用自动更新。</span><span class="sxs-lookup"><span data-stu-id="1ab57-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="1ab57-132">网站的 EnableAutoUpdate 属性需要设置为 true， (默认值) 。</span><span class="sxs-lookup"><span data-stu-id="1ab57-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="1ab57-133">运行以下 cmdlet 以确保 EnableAutoUpdate 设置为 true：</span><span class="sxs-lookup"><span data-stu-id="1ab57-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="1ab57-134">为租户创建自动更新时间窗口。</span><span class="sxs-lookup"><span data-stu-id="1ab57-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="1ab57-135">时间窗口可以是每天、每周和每月。</span><span class="sxs-lookup"><span data-stu-id="1ab57-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="1ab57-136">所有时间窗口都需要开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="1ab57-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="1ab57-137">对于每日时间窗口，只需要开始时间和持续时间。</span><span class="sxs-lookup"><span data-stu-id="1ab57-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="1ab57-138">对于每周时间窗口，需要一周中的几天，可以是一天或多天。</span><span class="sxs-lookup"><span data-stu-id="1ab57-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="1ab57-139">对于每月时间窗口，可以有两种类型。</span><span class="sxs-lookup"><span data-stu-id="1ab57-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="1ab57-140">第一种类型是指定月中的哪一天，可以是一天。</span><span class="sxs-lookup"><span data-stu-id="1ab57-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="1ab57-141">第二种类型是指定一个月的星期数以及一周中的哪几天，这两者都可以是单个项目或多个项目。</span><span class="sxs-lookup"><span data-stu-id="1ab57-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="1ab57-142">每个租户可以定义 20 个时间窗口。</span><span class="sxs-lookup"><span data-stu-id="1ab57-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="1ab57-143">将为新租户创建默认时间窗口，作为操作系统更新和 Bits 更新的默认时间窗口。</span><span class="sxs-lookup"><span data-stu-id="1ab57-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="1ab57-144">运行以下 cmdlet () 设置每日、每周或每月时间窗口：</span><span class="sxs-lookup"><span data-stu-id="1ab57-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="1ab57-145">将更新时间窗口分配给网站。</span><span class="sxs-lookup"><span data-stu-id="1ab57-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="1ab57-146">位更新时间和操作系统更新时间窗口是单独配置的。</span><span class="sxs-lookup"><span data-stu-id="1ab57-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="1ab57-147">这两个窗口都可以分配一个或多个时间窗口。</span><span class="sxs-lookup"><span data-stu-id="1ab57-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="1ab57-148">可以将每个时间窗口分配给不同的站点，并使用不同的 (位更新和操作系统更新) 。</span><span class="sxs-lookup"><span data-stu-id="1ab57-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="1ab57-149">运行以下 cmdlet 设置网站的时间窗口：</span><span class="sxs-lookup"><span data-stu-id="1ab57-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="1ab57-150">更新专用租户管理员凭据</span><span class="sxs-lookup"><span data-stu-id="1ab57-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="1ab57-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="1ab57-152">云连接器的 Microsoft 365 或 Office 365 组织的管理更改通过具有所需权限的帐户进行。</span><span class="sxs-lookup"><span data-stu-id="1ab57-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="1ab57-153">在 2.0 以前的云连接器版本中，该帐户是专用全局租户管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="1ab57-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="1ab57-154">在云连接器 2.0 版及更高版本中，该帐户可以是具有 Skype for Business 管理员权限的 Microsoft 365 或 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="1ab57-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="1ab57-155">如果你的管理员帐户凭据在 Microsoft 365 或 Office 365 中更改，则还需要更新云连接器中本地缓存的凭据，只需在已部署的每个云连接器设备上运行以下管理员 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="1ab57-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="1ab57-156">更新主机服务器的密码</span><span class="sxs-lookup"><span data-stu-id="1ab57-156">Update the password for the host server</span></span>
<span data-ttu-id="1ab57-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="1ab57-158">本部分适用于云连接器 2.0 版和更高版本。</span><span class="sxs-lookup"><span data-stu-id="1ab57-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="1ab57-159">所有云连接器凭据都存储在以下文件中："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"。</span><span class="sxs-lookup"><span data-stu-id="1ab57-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="1ab57-160">当主机服务器上密码更改时，您需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="1ab57-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="1ab57-161">若要更新云连接器设备本地存储的凭据，请使用 [Get-CcCredential](get-cccredential.md) 和 [Set-CcCredential](set-cccredential.md) cmdlet 并按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="1ab57-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="1ab57-162">运行以下命令以检索稍后将需要的密码：</span><span class="sxs-lookup"><span data-stu-id="1ab57-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="1ab57-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="1ab57-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="1ab57-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="1ab57-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="1ab57-165">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="1ab57-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="1ab57-166">更改主机服务器上帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="1ab57-167">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="1ab57-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="1ab57-168">删除以下文件："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"。</span><span class="sxs-lookup"><span data-stu-id="1ab57-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="1ab57-169">以管理员角色启动 PowerShell 控制台，然后运行"Register-CcAppliance -Local"，按照说明重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="1ab57-170">请务必输入之前为云连接器部署输入的相同密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="1ab57-171">默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="1ab57-172">如果步骤 1 中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1ab57-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="1ab57-173">运行 Set-CcCredential -AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ab57-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="1ab57-174">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="1ab57-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="1ab57-175">当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="1ab57-176">运行 Set-CcCredential -AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ab57-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="1ab57-177">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="1ab57-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="1ab57-178">当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="1ab57-179">更新 CceService 帐户的密码</span><span class="sxs-lookup"><span data-stu-id="1ab57-179">Update the password for the CceService account</span></span>
<span data-ttu-id="1ab57-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="1ab57-181">此部分适用于云连接器版本 2.0.1 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="1ab57-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="1ab57-182">云连接器服务运行云连接器管理服务。</span><span class="sxs-lookup"><span data-stu-id="1ab57-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="1ab57-183">CceService 帐户在云连接器版本部署期间创建，并存储在以下文件中："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"和"%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml"。</span><span class="sxs-lookup"><span data-stu-id="1ab57-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="1ab57-184">为了确保所有设备都可以访问站点目录共享，在站点内部署的所有设备上，CceService 帐户的密码必须相同。</span><span class="sxs-lookup"><span data-stu-id="1ab57-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="1ab57-185">请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="1ab57-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="1ab57-186">默认情况下，CceService 帐户配置为"密码永不过期"。</span><span class="sxs-lookup"><span data-stu-id="1ab57-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="1ab57-187">更新密码时，Microsoft 建议保留此配置。</span><span class="sxs-lookup"><span data-stu-id="1ab57-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="1ab57-188">你应该在非高峰使用时段以及位或 Windows 更新的自动更新时间窗口之外更新密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="1ab57-189">更新密码时，设备需要排出并重启，这需要花费一些时间。</span><span class="sxs-lookup"><span data-stu-id="1ab57-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="1ab57-190">重新启动设备将中断自动更新操作。</span><span class="sxs-lookup"><span data-stu-id="1ab57-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="1ab57-191">更改 CceService 帐户密码时，将需要指定所有凭据，并在本地存储的文件中更新它们。</span><span class="sxs-lookup"><span data-stu-id="1ab57-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="1ab57-192">对于属于同一 PSTN 站点的每台设备，你将需要指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="1ab57-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="1ab57-193">运行以下命令以检索您将稍后使用的帐户名称和密码：</span><span class="sxs-lookup"><span data-stu-id="1ab57-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="1ab57-194">运行 Enter-CcUpdate cmdlet 以排出设备，将其移动到手动维护模式。</span><span class="sxs-lookup"><span data-stu-id="1ab57-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="1ab57-195">更新主机服务器上 CceService 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="1ab57-196">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="1ab57-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="1ab57-197">运行 Restore-CcCredentials cmdlet，按照说明重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="1ab57-198">请确保输入之前为云连接器部署输入的相同密码，CceService 帐户除外。</span><span class="sxs-lookup"><span data-stu-id="1ab57-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="1ab57-199">对于 CceService 帐户，输入新密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="1ab57-200">确保 CceService 帐户的新密码与 PSTN 站点中所有设备的密码相同。</span><span class="sxs-lookup"><span data-stu-id="1ab57-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="1ab57-201">默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="1ab57-202">如果步骤 1 中返回的 DomainAdmin、VMAdmin 和 CceService 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1ab57-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="1ab57-203">运行 Set-CcCredential -AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ab57-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="1ab57-204">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="1ab57-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="1ab57-205">当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="1ab57-206">运行 Set-CcCredential -AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ab57-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="1ab57-207">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="1ab57-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="1ab57-208">当系统提示输入新帐户凭据时，请输入步骤 1 中返回的 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="1ab57-209">运行 Exit-CcUpdate cmdlet 以将设备从手动维护模式移开。</span><span class="sxs-lookup"><span data-stu-id="1ab57-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="1ab57-210">在同一 PSTN 站点的所有设备上完成这些步骤后，删除站点根目录中的以下文件：</span><span class="sxs-lookup"><span data-stu-id="1ab57-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="1ab57-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="1ab57-211">CcLockFile</span></span>
    
    - <span data-ttu-id="1ab57-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="1ab57-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="1ab57-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="1ab57-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="1ab57-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="1ab57-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="1ab57-215">添加新 SIP 域</span><span class="sxs-lookup"><span data-stu-id="1ab57-215">Add a new SIP domain</span></span>
<span data-ttu-id="1ab57-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="1ab57-217">若要将新的 SIP 域 (或多个 SIP) 添加到现有云连接器部署中，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1ab57-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="1ab57-218">请确保你已完成在 Microsoft 365 或 Office 365 中更新域的步骤，并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="1ab57-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="1ab57-219">若要详细了解如何在 Microsoft 365 或 Office 365 中设置域，请参阅将域添加到[Microsoft 365 或 Office 365。](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="1ab57-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="1ab57-220">使用新的 SIP 域更新云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ab57-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="1ab57-221">为云连接器配置中定义的每个 SIP 域请求具有 sip.domain 的其他 SAN 名称的新边缘外部证书。</span><span class="sxs-lookup"><span data-stu-id="1ab57-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="1ab57-222">设置新边缘外部证书的路径，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ab57-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="1ab57-223">按照说明 [修改单个站点的](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 配置或修改 [多个网站的配置](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)。</span><span class="sxs-lookup"><span data-stu-id="1ab57-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="1ab57-224">修改主 SIP 域</span><span class="sxs-lookup"><span data-stu-id="1ab57-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="1ab57-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="1ab57-226">如果需要更改云连接器部署中的主 SIP 域，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1ab57-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="1ab57-227">请确保你已完成在 Microsoft 365 或 Office 365 中更新域的步骤，并且能够添加 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="1ab57-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="1ab57-228">若要详细了解如何在 Microsoft 365 或 Office 365 中设置域，请参阅将域添加到[Microsoft 365 或 Office 365。](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</span><span class="sxs-lookup"><span data-stu-id="1ab57-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="1ab57-229">使用新的 SIP 域更新云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="1ab57-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="1ab57-230">为云连接器配置中定义的每个 SIP 域请求具有 sip.domain 的其他 SAN 名称的新边缘外部证书。</span><span class="sxs-lookup"><span data-stu-id="1ab57-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="1ab57-231">设置新边缘外部证书的路径，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1ab57-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="1ab57-232">在云连接器上的管理员 PowerShell 中运行以下 cmdlet，删除站点中每台设备的租户注册：</span><span class="sxs-lookup"><span data-stu-id="1ab57-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="1ab57-233">在 Skype for Business Online PowerShell 中运行以下 cmdlet，删除每个站点的站点注册：</span><span class="sxs-lookup"><span data-stu-id="1ab57-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="1ab57-234">在云连接器上的管理员 PowerShell 中运行以下 cmdlet 卸载每台设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="1ab57-235">在云连接器上的管理员 PowerShell 中运行以下 cmdlet 注册每台设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="1ab57-236">在云连接器上的管理员 PowerShell 中运行以下 cmdlet，分别安装每台设备：</span><span class="sxs-lookup"><span data-stu-id="1ab57-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="1ab57-237">将外部边缘证书替换为新证书</span><span class="sxs-lookup"><span data-stu-id="1ab57-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="1ab57-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="1ab57-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="1ab57-239">当你需要替换云连接器设备上的外部边缘证书时，你将需要获取新的边缘证书，准备包含私钥和完整证书链的 PFX 文件，然后在每个设备上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1ab57-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="1ab57-240">使用 cmdlet 将设备置于维护Enter-CcUpdate模式。</span><span class="sxs-lookup"><span data-stu-id="1ab57-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="1ab57-241">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="1ab57-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="1ab57-242">如果新证书的密码与旧证书相同，则导入将成功。</span><span class="sxs-lookup"><span data-stu-id="1ab57-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="1ab57-243">如果密码不同，您将收到密码错误的错误，并且您需要通过运行带 -Local 参数的 Register-CcAppliance cmdlet，然后重复步骤 2 来重置密码。</span><span class="sxs-lookup"><span data-stu-id="1ab57-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="1ab57-244">使用 Exit -CcUpdate cmdlet 使设备退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="1ab57-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
