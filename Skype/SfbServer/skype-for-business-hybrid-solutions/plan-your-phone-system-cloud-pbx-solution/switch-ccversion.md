---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 'Switch-CcVersion cmdlet 可将正在运行的设备断开连接，并切换到新部署的设备或备份设备。 '
ms.openlocfilehash: e63c5ea6d74e979f7fc9fe5a4c5eae97a0689e1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286927"
---
# <a name="switch-ccversion"></a><span data-ttu-id="0c720-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="0c720-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="0c720-104">Switch-CcVersion cmdlet 可将正在运行的设备断开连接，并切换到新部署的设备或备份设备。 </span><span class="sxs-lookup"><span data-stu-id="0c720-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="0c720-105">示例</span><span class="sxs-lookup"><span data-stu-id="0c720-105">Examples</span></span>
<span data-ttu-id="0c720-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0c720-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="0c720-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="0c720-107">Example 1</span></span>

<span data-ttu-id="0c720-108">以下示例将排出当前正在运行的设备的服务，然后切换到新部署的设备或备份设备：</span><span class="sxs-lookup"><span data-stu-id="0c720-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="0c720-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="0c720-109">Example 2</span></span>

<span data-ttu-id="0c720-110">下一个示例将排出当前正在运行的设备的服务，并在排出服务失败时强制停止服务。</span><span class="sxs-lookup"><span data-stu-id="0c720-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="0c720-111">然后，该命令将切换到新部署的设备或备份设备。</span><span class="sxs-lookup"><span data-stu-id="0c720-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="0c720-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="0c720-112">Detailed Description</span></span>
<span data-ttu-id="0c720-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c720-113"></span></span>

<span data-ttu-id="0c720-114">CcVersion cmdlet 用于在中介服务器和 Edge 服务器上消耗云连接器服务。</span><span class="sxs-lookup"><span data-stu-id="0c720-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="0c720-115">所有正在运行的呼叫都将完成，但设备将拒绝任何新呼叫。</span><span class="sxs-lookup"><span data-stu-id="0c720-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="0c720-116">排出后，cmdlet 会从企业和 Internet 网络中断开正在运行的设备，关闭属于该设备的所有虚拟机，然后将备份设备连接至企业和 Internet 网络。</span><span class="sxs-lookup"><span data-stu-id="0c720-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0c720-117">参数</span><span class="sxs-lookup"><span data-stu-id="0c720-117">Parameters</span></span>
<span data-ttu-id="0c720-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c720-118"></span></span>

|<span data-ttu-id="0c720-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="0c720-119">**Parameter**</span></span>|<span data-ttu-id="0c720-120">**必需**</span><span class="sxs-lookup"><span data-stu-id="0c720-120">**Required**</span></span>|<span data-ttu-id="0c720-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="0c720-121">**Type**</span></span>|<span data-ttu-id="0c720-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="0c720-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0c720-123">Force</span><span class="sxs-lookup"><span data-stu-id="0c720-123">Force</span></span> <br/> | <span data-ttu-id="0c720-124">可选</span><span class="sxs-lookup"><span data-stu-id="0c720-124">Optional</span></span> <br/> |<span data-ttu-id="0c720-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0c720-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="0c720-126"> 在排出服务失败时强制停止服务。</span><span class="sxs-lookup"><span data-stu-id="0c720-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0c720-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="0c720-127">Input Types</span></span>
<span data-ttu-id="0c720-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c720-128"></span></span>

<span data-ttu-id="0c720-129">无</span><span class="sxs-lookup"><span data-stu-id="0c720-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0c720-130">返回类型</span><span class="sxs-lookup"><span data-stu-id="0c720-130">Return Types</span></span>
<span data-ttu-id="0c720-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c720-131"></span></span>

<span data-ttu-id="0c720-132">无</span><span class="sxs-lookup"><span data-stu-id="0c720-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c720-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c720-133">See also</span></span>
<span data-ttu-id="0c720-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c720-134"></span></span>

<span data-ttu-id="0c720-135">无</span><span class="sxs-lookup"><span data-stu-id="0c720-135">None</span></span>
  

