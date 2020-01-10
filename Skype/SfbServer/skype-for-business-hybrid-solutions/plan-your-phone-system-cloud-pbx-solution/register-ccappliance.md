---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: Register-CcAppliance cmdlet 将设备信息注册到联机租户配置中的 PSTN 站点。 必须先注册设备，Skype for Business 云连接器版本管理服务才能对其进行部署和管理。
ms.openlocfilehash: 93f1fe59a199214615c5ecdf8445f6c363ce6bbe
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003302"
---
# <a name="register-ccappliance"></a><span data-ttu-id="a171b-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a171b-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="a171b-105">Register-CcAppliance cmdlet 将设备信息注册到联机租户配置中的 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="a171b-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="a171b-106">必须先注册设备，Skype for Business 云连接器版本管理服务才能对其进行部署和管理。</span><span class="sxs-lookup"><span data-stu-id="a171b-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="a171b-107">示例</span><span class="sxs-lookup"><span data-stu-id="a171b-107">Examples</span></span>
<span data-ttu-id="a171b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a171b-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="a171b-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="a171b-109">Example 1</span></span>

<span data-ttu-id="a171b-110">以下示例将当前设备信息注册到联机租户配置：</span><span class="sxs-lookup"><span data-stu-id="a171b-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="a171b-111">示例 2</span><span class="sxs-lookup"><span data-stu-id="a171b-111">Example 2</span></span>

<span data-ttu-id="a171b-112">以下示例在本地检查用于注册的配置，而不连接到联机租户配置：</span><span class="sxs-lookup"><span data-stu-id="a171b-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="a171b-113">示例 3</span><span class="sxs-lookup"><span data-stu-id="a171b-113">Example 3</span></span>

<span data-ttu-id="a171b-114">以下示例将当前设备以名称“Appliance1”注册到 PSTN 站点“Site1”：</span><span class="sxs-lookup"><span data-stu-id="a171b-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="a171b-115">详细说明</span><span class="sxs-lookup"><span data-stu-id="a171b-115">Detailed Description</span></span>
<span data-ttu-id="a171b-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a171b-116"></span></span>

<span data-ttu-id="a171b-117">必须提供租户管理员帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="a171b-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="a171b-118">请使用你为云连接器在线管理创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="a171b-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="a171b-119">在版本1.4.2 及更早版本中，按照说明提供外部证书密码、安全模式管理员密码、域管理员密码和 VM 管理员密码。</span><span class="sxs-lookup"><span data-stu-id="a171b-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="a171b-120">在 2.0 版和更高版本中，按照说明提供外部证书密码、CceService 密码和 CABackupFile 密码。</span><span class="sxs-lookup"><span data-stu-id="a171b-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="a171b-121">注册结束后，重新启动云连接器管理服务，并以 CceService 帐户身份登录服务。</span><span class="sxs-lookup"><span data-stu-id="a171b-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="a171b-p104">CloudConnector.ini 文件中与边缘服务器外部 FQDN 组合在一起的 SiteName 被视为 PSTN 站点标识。如果注册站点时既未使用 SiteName 也未使用边缘服务器外部 FQDN，将在联机租户配置中为此设备创建新站点。如果找到 PSTN 站点标识，PSTN 站点将使用此标识，并且设备将注册到此 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="a171b-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="a171b-125">在下面的情况下，cmdlet 将失败，并指示 Site1 已注册。</span><span class="sxs-lookup"><span data-stu-id="a171b-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="a171b-126">SiteName 为 Site1 且边缘服务器外部 FQDN 为 edgserver1.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a171b-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="a171b-127">其 SiteName 为 Site1 且边缘服务器外部 FQDN 为 edgserver.contoso.com 的 PSTN 站点。</span><span class="sxs-lookup"><span data-stu-id="a171b-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="a171b-128">其 SiteName 为 NewSite 且边缘服务器外部 FQDN 为 edgserver1.contoso.com 的 PSTN 站点已注册。</span><span class="sxs-lookup"><span data-stu-id="a171b-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="a171b-p105">CloudConnector.ini 文件中与中介服务器 FQDN 组合在一起的 ApplianceName 被视为设备标识。如果注册设备时既未使用 ApplianceName 也未使用中介服务器外部 FQDN，将在联机租户配置中创建新设备。如果设备已注册，cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="a171b-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="a171b-132">在下面的情况下，cmdlet 将失败，并指示设备已注册。</span><span class="sxs-lookup"><span data-stu-id="a171b-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="a171b-133">ApplianceName 为 Appliance1 且中介服务器 FQDN 为 ms1.vdomain.com。</span><span class="sxs-lookup"><span data-stu-id="a171b-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="a171b-134">在当前 PSTN 站点中，如果其名称为 Appliance1 且中介服务器 FQDN 为 ms.vdomain.com 的设备或其名称为 NewAppliance 且中介服务器 FQDN 为 ms1.vdomain.com 的设备已注册。</span><span class="sxs-lookup"><span data-stu-id="a171b-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="a171b-135">参数</span><span class="sxs-lookup"><span data-stu-id="a171b-135">Parameters</span></span>
<span data-ttu-id="a171b-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a171b-136"></span></span>

|<span data-ttu-id="a171b-137">**参数**</span><span class="sxs-lookup"><span data-stu-id="a171b-137">**Parameter**</span></span>|<span data-ttu-id="a171b-138">**必需**</span><span class="sxs-lookup"><span data-stu-id="a171b-138">**Required**</span></span>|<span data-ttu-id="a171b-139">**类型**</span><span class="sxs-lookup"><span data-stu-id="a171b-139">**Type**</span></span>|<span data-ttu-id="a171b-140">**说明**</span><span class="sxs-lookup"><span data-stu-id="a171b-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a171b-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="a171b-141">SiteName</span></span>  <br/> |<span data-ttu-id="a171b-142">可选</span><span class="sxs-lookup"><span data-stu-id="a171b-142">Optional</span></span>  <br/> |<span data-ttu-id="a171b-143">System.String</span><span class="sxs-lookup"><span data-stu-id="a171b-143">System.String</span></span>  <br/> |<span data-ttu-id="a171b-p106">向其注册设备的 PSTN 站点名称。默认值是 CloudConnector.ini 文件中的 SiteName 值。</span><span class="sxs-lookup"><span data-stu-id="a171b-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="a171b-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="a171b-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="a171b-147">可选</span><span class="sxs-lookup"><span data-stu-id="a171b-147">Optional</span></span>  <br/> |<span data-ttu-id="a171b-148">System.String</span><span class="sxs-lookup"><span data-stu-id="a171b-148">System.String</span></span>  <br/> |<span data-ttu-id="a171b-p107">当前设备的名称。默认值是主机服务器的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="a171b-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="a171b-151">本地</span><span class="sxs-lookup"><span data-stu-id="a171b-151">Local</span></span>  <br/> |<span data-ttu-id="a171b-152">可选</span><span class="sxs-lookup"><span data-stu-id="a171b-152">Optional</span></span>  <br/> |<span data-ttu-id="a171b-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a171b-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a171b-154">在本地检查用于注册的配置，而不连接到联机租户配置。</span><span class="sxs-lookup"><span data-stu-id="a171b-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a171b-155">输入类型</span><span class="sxs-lookup"><span data-stu-id="a171b-155">Input Types</span></span>
<span data-ttu-id="a171b-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a171b-156"></span></span>

<span data-ttu-id="a171b-p108">无。Register-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="a171b-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a171b-159">返回类型</span><span class="sxs-lookup"><span data-stu-id="a171b-159">Return Types</span></span>
<span data-ttu-id="a171b-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a171b-160"></span></span>

<span data-ttu-id="a171b-161">无</span><span class="sxs-lookup"><span data-stu-id="a171b-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a171b-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a171b-162">See also</span></span>
<span data-ttu-id="a171b-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a171b-163"></span></span>

[<span data-ttu-id="a171b-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a171b-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="a171b-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a171b-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="a171b-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a171b-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="a171b-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="a171b-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

