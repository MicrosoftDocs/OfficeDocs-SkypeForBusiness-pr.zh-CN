---
title: 卸载-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 325e21d28ef87f9d27e87721452bc3d67d197169
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="22028-103">卸载-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="22028-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="22028-104">Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。</span><span class="sxs-lookup"><span data-stu-id="22028-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="22028-105">示例</span><span class="sxs-lookup"><span data-stu-id="22028-105">Examples</span></span>
<span data-ttu-id="22028-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="22028-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="22028-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="22028-107">Example 1</span></span>

<span data-ttu-id="22028-108">下面的示例漏下后，从主机服务器卸载云接头装置：</span><span class="sxs-lookup"><span data-stu-id="22028-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="22028-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="22028-109">Example 2</span></span>

<span data-ttu-id="22028-110">下一个示例中漏下后，强行卸载主机服务器上正在运行的云接头装置，即使耗尽过程失败：</span><span class="sxs-lookup"><span data-stu-id="22028-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="22028-111">示例 3</span><span class="sxs-lookup"><span data-stu-id="22028-111">Example 3</span></span>

<span data-ttu-id="22028-112">下一个示例卸载云连接器备份版本，而无需用户确认：</span><span class="sxs-lookup"><span data-stu-id="22028-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="22028-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="22028-113">Detailed Description</span></span>
<span data-ttu-id="22028-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="22028-114"></span></span>

<span data-ttu-id="22028-115">如果您要卸载的云连接器当前运行的版本，排出服务首先让并发呼叫完成卸载虚拟机之前的中介服务器和边缘服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="22028-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="22028-116">如果你要卸载备份版本，则不执行排出操作。</span><span class="sxs-lookup"><span data-stu-id="22028-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="22028-117">参数</span><span class="sxs-lookup"><span data-stu-id="22028-117">Parameters</span></span>
<span data-ttu-id="22028-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="22028-118"></span></span>

|<span data-ttu-id="22028-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="22028-119">**Parameter**</span></span>|<span data-ttu-id="22028-120">**必填**</span><span class="sxs-lookup"><span data-stu-id="22028-120">**Required**</span></span>|<span data-ttu-id="22028-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="22028-121">**Type**</span></span>|<span data-ttu-id="22028-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="22028-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="22028-123">版本</span><span class="sxs-lookup"><span data-stu-id="22028-123">Version</span></span> <br/> | <span data-ttu-id="22028-124">可选</span><span class="sxs-lookup"><span data-stu-id="22028-124">Optional</span></span> <br/> |<span data-ttu-id="22028-125">System.String</span><span class="sxs-lookup"><span data-stu-id="22028-125">System.String</span></span>  <br/> | <span data-ttu-id="22028-126">将从主机服务器卸载的云连接器的版本。</span><span class="sxs-lookup"><span data-stu-id="22028-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="22028-127">如果未指定，将卸载当前正在运行的版本。</span><span class="sxs-lookup"><span data-stu-id="22028-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="22028-128">强制</span><span class="sxs-lookup"><span data-stu-id="22028-128">Force</span></span>  <br/> |<span data-ttu-id="22028-129">可选</span><span class="sxs-lookup"><span data-stu-id="22028-129">Optional</span></span>  <br/> |<span data-ttu-id="22028-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="22028-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="22028-p103">如果卸载当前正在运行的版本，将先尝试在中介服务器和边缘服务器上排出服务，然后卸载虚拟机。如果指定“Force”开关，即使排出服务失败，也会卸载虚拟机。此参数仅用于卸载当前正在运行的版本。</span><span class="sxs-lookup"><span data-stu-id="22028-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="22028-134">确认</span><span class="sxs-lookup"><span data-stu-id="22028-134">Confirm</span></span>  <br/> |<span data-ttu-id="22028-135">可选</span><span class="sxs-lookup"><span data-stu-id="22028-135">Optional</span></span>  <br/> |<span data-ttu-id="22028-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="22028-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="22028-137">要求用户确认要卸载虚拟机。</span><span class="sxs-lookup"><span data-stu-id="22028-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="22028-138">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="22028-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="22028-139">输入类型</span><span class="sxs-lookup"><span data-stu-id="22028-139">Input Types</span></span>
<span data-ttu-id="22028-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="22028-140"></span></span>

<span data-ttu-id="22028-p105">无。Uninstall-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="22028-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="22028-143">返回类型</span><span class="sxs-lookup"><span data-stu-id="22028-143">Return Types</span></span>
<span data-ttu-id="22028-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="22028-144"></span></span>

<span data-ttu-id="22028-145">无</span><span class="sxs-lookup"><span data-stu-id="22028-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="22028-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22028-146">See also</span></span>
<span data-ttu-id="22028-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="22028-147"></span></span>

[<span data-ttu-id="22028-148">安装 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="22028-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="22028-149">将发布 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="22028-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="22028-150">注册 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="22028-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="22028-151">取消注册 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="22028-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

