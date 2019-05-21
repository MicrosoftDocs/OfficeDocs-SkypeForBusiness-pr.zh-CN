---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: 337c5c489846facb1da3c177cac7a965d7550ae5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286892"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="b32e4-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b32e4-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="b32e4-104">Uninstall-CcAppliance cmdlet 用于从主机服务器中卸载正在运行的 Skype for Business 云连接器版本设备。</span><span class="sxs-lookup"><span data-stu-id="b32e4-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="b32e4-105">示例</span><span class="sxs-lookup"><span data-stu-id="b32e4-105">Examples</span></span>
<span data-ttu-id="b32e4-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b32e4-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b32e4-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="b32e4-107">Example 1</span></span>

<span data-ttu-id="b32e4-108">下面的示例从主服务器中耗尽和卸载云连接器装置:</span><span class="sxs-lookup"><span data-stu-id="b32e4-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="b32e4-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="b32e4-109">Example 2</span></span>

<span data-ttu-id="b32e4-110">下一个示例将排出并强制卸载主机服务器上正在运行的云连接器装置, 即使排出过程失败:</span><span class="sxs-lookup"><span data-stu-id="b32e4-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="b32e4-111">示例 3</span><span class="sxs-lookup"><span data-stu-id="b32e4-111">Example 3</span></span>

<span data-ttu-id="b32e4-112">下一示例在没有用户确认的情况下卸载云连接器备份版本:</span><span class="sxs-lookup"><span data-stu-id="b32e4-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="b32e4-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="b32e4-113">Detailed Description</span></span>
<span data-ttu-id="b32e4-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b32e4-114"></span></span>

<span data-ttu-id="b32e4-115">如果你卸载的是当前运行的云连接器版本, 将首先在中介服务器和 Edge 服务器上运行排水管服务, 以便在卸载虚拟机之前, 让并发调用完成。</span><span class="sxs-lookup"><span data-stu-id="b32e4-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="b32e4-116">如果你要卸载备份版本，则不执行排出操作。</span><span class="sxs-lookup"><span data-stu-id="b32e4-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b32e4-117">参数</span><span class="sxs-lookup"><span data-stu-id="b32e4-117">Parameters</span></span>
<span data-ttu-id="b32e4-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b32e4-118"></span></span>

|<span data-ttu-id="b32e4-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="b32e4-119">**Parameter**</span></span>|<span data-ttu-id="b32e4-120">**必需**</span><span class="sxs-lookup"><span data-stu-id="b32e4-120">**Required**</span></span>|<span data-ttu-id="b32e4-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="b32e4-121">**Type**</span></span>|<span data-ttu-id="b32e4-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="b32e4-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b32e4-123">版本</span><span class="sxs-lookup"><span data-stu-id="b32e4-123">Version</span></span> <br/> | <span data-ttu-id="b32e4-124">可选</span><span class="sxs-lookup"><span data-stu-id="b32e4-124">Optional</span></span> <br/> |<span data-ttu-id="b32e4-125">System.String</span><span class="sxs-lookup"><span data-stu-id="b32e4-125">System.String</span></span>  <br/> | <span data-ttu-id="b32e4-126">将从主机服务器卸载的云连接器的版本。</span><span class="sxs-lookup"><span data-stu-id="b32e4-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="b32e4-127">如果未指定，将卸载当前正在运行的版本。</span><span class="sxs-lookup"><span data-stu-id="b32e4-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="b32e4-128">强制</span><span class="sxs-lookup"><span data-stu-id="b32e4-128">Force</span></span>  <br/> |<span data-ttu-id="b32e4-129">可选</span><span class="sxs-lookup"><span data-stu-id="b32e4-129">Optional</span></span>  <br/> |<span data-ttu-id="b32e4-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b32e4-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b32e4-p103">如果卸载当前正在运行的版本，将先尝试在中介服务器和边缘服务器上排出服务，然后卸载虚拟机。如果指定“Force”开关，即使排出服务失败，也会卸载虚拟机。此参数仅用于卸载当前正在运行的版本。</span><span class="sxs-lookup"><span data-stu-id="b32e4-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="b32e4-134">确认</span><span class="sxs-lookup"><span data-stu-id="b32e4-134">Confirm</span></span>  <br/> |<span data-ttu-id="b32e4-135">可选</span><span class="sxs-lookup"><span data-stu-id="b32e4-135">Optional</span></span>  <br/> |<span data-ttu-id="b32e4-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b32e4-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="b32e4-137">询问用户确认以卸载虚拟机。</span><span class="sxs-lookup"><span data-stu-id="b32e4-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="b32e4-138">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="b32e4-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b32e4-139">输入类型</span><span class="sxs-lookup"><span data-stu-id="b32e4-139">Input Types</span></span>
<span data-ttu-id="b32e4-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b32e4-140"></span></span>

<span data-ttu-id="b32e4-p105">无。Uninstall-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="b32e4-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b32e4-143">返回类型</span><span class="sxs-lookup"><span data-stu-id="b32e4-143">Return Types</span></span>
<span data-ttu-id="b32e4-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b32e4-144"></span></span>

<span data-ttu-id="b32e4-145">无</span><span class="sxs-lookup"><span data-stu-id="b32e4-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b32e4-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b32e4-146">See also</span></span>
<span data-ttu-id="b32e4-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b32e4-147"></span></span>

[<span data-ttu-id="b32e4-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b32e4-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="b32e4-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b32e4-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="b32e4-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b32e4-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="b32e4-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="b32e4-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

