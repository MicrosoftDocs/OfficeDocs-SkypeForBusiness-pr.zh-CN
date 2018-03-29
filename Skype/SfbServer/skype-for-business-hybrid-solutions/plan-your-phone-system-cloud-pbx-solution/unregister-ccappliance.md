---
title: 取消注册 CcAppliance
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
ms.openlocfilehash: 21bd0a7dffc6a395f829af68a61dfd7523d2c09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="1ef3b-103">取消注册 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1ef3b-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="1ef3b-104">Unregister-CcAppliance cmdlet 在联机租户配置中从 PSTN 站点注销 Skype for Business 云连接器版本设备。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="1ef3b-105">示例</span><span class="sxs-lookup"><span data-stu-id="1ef3b-105">Examples</span></span>
<span data-ttu-id="1ef3b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef3b-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="1ef3b-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="1ef3b-107">Example 1</span></span>

<span data-ttu-id="1ef3b-108">以下示例从联机租户配置中注销当前设备：</span><span class="sxs-lookup"><span data-stu-id="1ef3b-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="1ef3b-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="1ef3b-109">Example 2</span></span>

<span data-ttu-id="1ef3b-110">下一个示例将检查本地注销未连接到联机的客户端配置的配置：</span><span class="sxs-lookup"><span data-stu-id="1ef3b-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="1ef3b-111">示例 3</span><span class="sxs-lookup"><span data-stu-id="1ef3b-111">Example 3</span></span>

<span data-ttu-id="1ef3b-112">下一个示例将注销当前的装置名为"Appliance1"到 PSTN 站点"Site1":</span><span class="sxs-lookup"><span data-stu-id="1ef3b-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="1ef3b-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="1ef3b-113">Detailed Description</span></span>
<span data-ttu-id="1ef3b-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef3b-114"></span></span>

<span data-ttu-id="1ef3b-p101">与 Register-CcAppliance cmdlet 类似，CloudConnector.ini 文件中与边缘服务器外部 FQDN 组合在一起的 SiteName 被视为 PSTN 站点标识。同样，CloudConnector.ini 文件中与中介服务器 FQDN 组合在一起的 ApplianceName 被视为设备标识。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="1ef3b-117">该装置注销后，重新启动云连接器管理服务和日志上为网络服务帐户。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1ef3b-118">参数</span><span class="sxs-lookup"><span data-stu-id="1ef3b-118">Parameters</span></span>
<span data-ttu-id="1ef3b-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef3b-119"></span></span>

|<span data-ttu-id="1ef3b-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="1ef3b-120">**Parameter**</span></span>|<span data-ttu-id="1ef3b-121">**必填**</span><span class="sxs-lookup"><span data-stu-id="1ef3b-121">**Required**</span></span>|<span data-ttu-id="1ef3b-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="1ef3b-122">**Type**</span></span>|<span data-ttu-id="1ef3b-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="1ef3b-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1ef3b-124">站点名</span><span class="sxs-lookup"><span data-stu-id="1ef3b-124">SiteName</span></span> <br/> |<span data-ttu-id="1ef3b-125">可选</span><span class="sxs-lookup"><span data-stu-id="1ef3b-125">Optional</span></span>  <br/> |<span data-ttu-id="1ef3b-126">System.String</span><span class="sxs-lookup"><span data-stu-id="1ef3b-126">System.String</span></span>  <br/> |<span data-ttu-id="1ef3b-p102">在其中注册设备的 PSTN 站点名称。默认值是 CloudConnector.ini 文件中的 SiteName 值。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="1ef3b-129">装置名称</span><span class="sxs-lookup"><span data-stu-id="1ef3b-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="1ef3b-130">可选</span><span class="sxs-lookup"><span data-stu-id="1ef3b-130">Optional</span></span>  <br/> |<span data-ttu-id="1ef3b-131">System.String</span><span class="sxs-lookup"><span data-stu-id="1ef3b-131">System.String</span></span>  <br/> |<span data-ttu-id="1ef3b-p103">当前设备的名称。默认值是主机服务器的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="1ef3b-134">本地</span><span class="sxs-lookup"><span data-stu-id="1ef3b-134">Local</span></span>  <br/> |<span data-ttu-id="1ef3b-135">可选</span><span class="sxs-lookup"><span data-stu-id="1ef3b-135">Optional</span></span>  <br/> |<span data-ttu-id="1ef3b-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1ef3b-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1ef3b-137">检查用于在本地注册的配置，不必连接到联机租户配置。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1ef3b-138">输入类型</span><span class="sxs-lookup"><span data-stu-id="1ef3b-138">Input Types</span></span>
<span data-ttu-id="1ef3b-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef3b-139"></span></span>

<span data-ttu-id="1ef3b-p104">无。Unregister-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="1ef3b-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1ef3b-142">返回类型</span><span class="sxs-lookup"><span data-stu-id="1ef3b-142">Return Types</span></span>
<span data-ttu-id="1ef3b-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef3b-143"></span></span>

<span data-ttu-id="1ef3b-144">无</span><span class="sxs-lookup"><span data-stu-id="1ef3b-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1ef3b-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef3b-145">See also</span></span>
<span data-ttu-id="1ef3b-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1ef3b-146"></span></span>

[<span data-ttu-id="1ef3b-147">注册 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1ef3b-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="1ef3b-148">安装 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1ef3b-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="1ef3b-149">卸载-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1ef3b-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="1ef3b-150">将发布 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="1ef3b-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

