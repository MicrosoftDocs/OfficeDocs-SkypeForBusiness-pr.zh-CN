---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824126"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="d6206-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6206-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="d6206-104">Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。</span><span class="sxs-lookup"><span data-stu-id="d6206-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="d6206-105">示例</span><span class="sxs-lookup"><span data-stu-id="d6206-105">Examples</span></span>
<span data-ttu-id="d6206-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d6206-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d6206-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="d6206-107">Example 1</span></span>

<span data-ttu-id="d6206-108">以下示例从联机租户配置中注销当前设备：</span><span class="sxs-lookup"><span data-stu-id="d6206-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="d6206-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="d6206-109">Example 2</span></span>

<span data-ttu-id="d6206-110">以下示例检查用于在本地注销的配置，而不必连接到联机租户配置：</span><span class="sxs-lookup"><span data-stu-id="d6206-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="d6206-111">示例 3</span><span class="sxs-lookup"><span data-stu-id="d6206-111">Example 3</span></span>

<span data-ttu-id="d6206-112">以下示例向 PSTN 站点“Site1”注销名称为“Appliance1”的当前设备：</span><span class="sxs-lookup"><span data-stu-id="d6206-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="d6206-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="d6206-113">Detailed Description</span></span>
<span data-ttu-id="d6206-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d6206-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d6206-p101">与 Register-CcAppliance cmdlet 类似，CloudConnector.ini 文件中与边缘服务器外部 FQDN 组合在一起的 SiteName 被视为 PSTN 站点标识。同样，CloudConnector.ini 文件中与中介服务器 FQDN 组合在一起的 ApplianceName 被视为设备标识。</span><span class="sxs-lookup"><span data-stu-id="d6206-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="d6206-117">设备注销后，重新启动云连接器管理服务，并以 NetworkService 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d6206-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d6206-118">参数</span><span class="sxs-lookup"><span data-stu-id="d6206-118">Parameters</span></span>
<span data-ttu-id="d6206-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d6206-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="d6206-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="d6206-120">**Parameter**</span></span>|<span data-ttu-id="d6206-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="d6206-121">**Required**</span></span>|<span data-ttu-id="d6206-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="d6206-122">**Type**</span></span>|<span data-ttu-id="d6206-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="d6206-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d6206-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="d6206-124">SiteName</span></span> <br/> |<span data-ttu-id="d6206-125">可选</span><span class="sxs-lookup"><span data-stu-id="d6206-125">Optional</span></span>  <br/> |<span data-ttu-id="d6206-126">System.String</span><span class="sxs-lookup"><span data-stu-id="d6206-126">System.String</span></span>  <br/> |<span data-ttu-id="d6206-p102">在其中注册设备的 PSTN 站点名称。默认值是 CloudConnector.ini 文件中的 SiteName 值。</span><span class="sxs-lookup"><span data-stu-id="d6206-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="d6206-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="d6206-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="d6206-130">可选</span><span class="sxs-lookup"><span data-stu-id="d6206-130">Optional</span></span>  <br/> |<span data-ttu-id="d6206-131">System.String</span><span class="sxs-lookup"><span data-stu-id="d6206-131">System.String</span></span>  <br/> |<span data-ttu-id="d6206-p103">当前设备的名称。默认值是主机服务器的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="d6206-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="d6206-134">本地</span><span class="sxs-lookup"><span data-stu-id="d6206-134">Local</span></span>  <br/> |<span data-ttu-id="d6206-135">可选</span><span class="sxs-lookup"><span data-stu-id="d6206-135">Optional</span></span>  <br/> |<span data-ttu-id="d6206-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d6206-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d6206-137">检查用于在本地注册的配置，不必连接到联机租户配置。</span><span class="sxs-lookup"><span data-stu-id="d6206-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d6206-138">输入类型</span><span class="sxs-lookup"><span data-stu-id="d6206-138">Input Types</span></span>
<span data-ttu-id="d6206-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d6206-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d6206-p104">无。Unregister-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="d6206-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d6206-142">返回类型</span><span class="sxs-lookup"><span data-stu-id="d6206-142">Return Types</span></span>
<span data-ttu-id="d6206-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d6206-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d6206-144">无</span><span class="sxs-lookup"><span data-stu-id="d6206-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d6206-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6206-145">See also</span></span>
<span data-ttu-id="d6206-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d6206-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d6206-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6206-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d6206-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6206-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d6206-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6206-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="d6206-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d6206-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

