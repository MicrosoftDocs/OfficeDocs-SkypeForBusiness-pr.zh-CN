---
title: Unregister-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 6ee21f66c2b189aff8c8aa7d831369536618b18c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892002"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="7ef51-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7ef51-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="7ef51-104">Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。</span><span class="sxs-lookup"><span data-stu-id="7ef51-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="7ef51-105">示例</span><span class="sxs-lookup"><span data-stu-id="7ef51-105">Examples</span></span>
<span data-ttu-id="7ef51-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7ef51-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="7ef51-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="7ef51-107">Example 1</span></span>

<span data-ttu-id="7ef51-108">以下示例从联机租户配置中注销当前设备：</span><span class="sxs-lookup"><span data-stu-id="7ef51-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="7ef51-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="7ef51-109">Example 2</span></span>

<span data-ttu-id="7ef51-110">以下示例检查用于在本地注销的配置，而不必连接到联机租户配置：</span><span class="sxs-lookup"><span data-stu-id="7ef51-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="7ef51-111">示例 3</span><span class="sxs-lookup"><span data-stu-id="7ef51-111">Example 3</span></span>

<span data-ttu-id="7ef51-112">以下示例向 PSTN 站点“Site1”注销名称为“Appliance1”的当前设备：</span><span class="sxs-lookup"><span data-stu-id="7ef51-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="7ef51-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="7ef51-113">Detailed Description</span></span>
<span data-ttu-id="7ef51-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7ef51-114"></span></span>

<span data-ttu-id="7ef51-p101">与 Register-CcAppliance cmdlet 类似，CloudConnector.ini 文件中与边缘服务器外部 FQDN 组合在一起的 SiteName 被视为 PSTN 站点标识。同样，CloudConnector.ini 文件中与中介服务器 FQDN 组合在一起的 ApplianceName 被视为设备标识。</span><span class="sxs-lookup"><span data-stu-id="7ef51-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="7ef51-117">未注册设备后，重新启动云连接器管理服务和日志上为 NetworkService 帐户。</span><span class="sxs-lookup"><span data-stu-id="7ef51-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7ef51-118">参数</span><span class="sxs-lookup"><span data-stu-id="7ef51-118">Parameters</span></span>
<span data-ttu-id="7ef51-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7ef51-119"></span></span>

|<span data-ttu-id="7ef51-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="7ef51-120">**Parameter**</span></span>|<span data-ttu-id="7ef51-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="7ef51-121">**Required**</span></span>|<span data-ttu-id="7ef51-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ef51-122">**Type**</span></span>|<span data-ttu-id="7ef51-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ef51-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7ef51-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="7ef51-124">SiteName</span></span> <br/> |<span data-ttu-id="7ef51-125">可选</span><span class="sxs-lookup"><span data-stu-id="7ef51-125">Optional</span></span>  <br/> |<span data-ttu-id="7ef51-126">System.String</span><span class="sxs-lookup"><span data-stu-id="7ef51-126">System.String</span></span>  <br/> |<span data-ttu-id="7ef51-p102">在其中注册设备的 PSTN 站点名称。默认值是 CloudConnector.ini 文件中的 SiteName 值。</span><span class="sxs-lookup"><span data-stu-id="7ef51-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="7ef51-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="7ef51-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="7ef51-130">可选</span><span class="sxs-lookup"><span data-stu-id="7ef51-130">Optional</span></span>  <br/> |<span data-ttu-id="7ef51-131">System.String</span><span class="sxs-lookup"><span data-stu-id="7ef51-131">System.String</span></span>  <br/> |<span data-ttu-id="7ef51-p103">当前设备的名称。默认值是主机服务器的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="7ef51-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="7ef51-134">本地</span><span class="sxs-lookup"><span data-stu-id="7ef51-134">Local</span></span>  <br/> |<span data-ttu-id="7ef51-135">可选</span><span class="sxs-lookup"><span data-stu-id="7ef51-135">Optional</span></span>  <br/> |<span data-ttu-id="7ef51-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7ef51-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="7ef51-137">检查用于在本地注册的配置，不必连接到联机租户配置。</span><span class="sxs-lookup"><span data-stu-id="7ef51-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7ef51-138">输入类型</span><span class="sxs-lookup"><span data-stu-id="7ef51-138">Input Types</span></span>
<span data-ttu-id="7ef51-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ef51-139"></span></span>

<span data-ttu-id="7ef51-p104">无。Unregister-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="7ef51-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7ef51-142">返回类型</span><span class="sxs-lookup"><span data-stu-id="7ef51-142">Return Types</span></span>
<span data-ttu-id="7ef51-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ef51-143"></span></span>

<span data-ttu-id="7ef51-144">无</span><span class="sxs-lookup"><span data-stu-id="7ef51-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ef51-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ef51-145">See also</span></span>
<span data-ttu-id="7ef51-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ef51-146"></span></span>

[<span data-ttu-id="7ef51-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7ef51-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="7ef51-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7ef51-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="7ef51-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7ef51-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="7ef51-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="7ef51-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

