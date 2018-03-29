---
title: 将发布 CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: Publish-CcAppliance cmdlet 从联机租户配置中获取高可用性信息，并将其发布到主机服务器上的 Skype for Business 云连接器版本设备。
ms.openlocfilehash: c0a2639156a0794ec34fd62a58027255d24d461e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="publish-ccappliance"></a><span data-ttu-id="86ef9-103">将发布 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="86ef9-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="86ef9-104">Publish-CcAppliance cmdlet 从联机租户配置中获取高可用性信息，并将其发布到主机服务器上的 Skype for Business 云连接器版本设备。</span><span class="sxs-lookup"><span data-stu-id="86ef9-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="86ef9-105">参数</span><span class="sxs-lookup"><span data-stu-id="86ef9-105">Parameters</span></span>

<span data-ttu-id="86ef9-106">无</span><span class="sxs-lookup"><span data-stu-id="86ef9-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="86ef9-107">示例</span><span class="sxs-lookup"><span data-stu-id="86ef9-107">Examples</span></span>
<span data-ttu-id="86ef9-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="86ef9-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="86ef9-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="86ef9-109">Example 1</span></span>

<span data-ttu-id="86ef9-110">下面的示例获取从联机租户配置高可用性的信息，并将其发布到主机服务器上云接头装置：</span><span class="sxs-lookup"><span data-stu-id="86ef9-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="86ef9-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="86ef9-111">Detailed Description</span></span>
<span data-ttu-id="86ef9-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="86ef9-112"></span></span>

<span data-ttu-id="86ef9-p101">高可用性信息包括 PSTN 站点的中介服务器 FQDN 和 IP 地址。向 AD 服务器添加有关中介服务器 IP 地址的新 DNS A 记录。用新拓扑项来更新中央管理存储中的中介服务器 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="86ef9-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="86ef9-116">输入类型</span><span class="sxs-lookup"><span data-stu-id="86ef9-116">Input Types</span></span>
<span data-ttu-id="86ef9-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86ef9-117"></span></span>

<span data-ttu-id="86ef9-118">无。</span><span class="sxs-lookup"><span data-stu-id="86ef9-118">None.</span></span> <span data-ttu-id="86ef9-119">Publish-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="86ef9-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="86ef9-120">返回类型</span><span class="sxs-lookup"><span data-stu-id="86ef9-120">Return Types</span></span>
<span data-ttu-id="86ef9-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86ef9-121"></span></span>

<span data-ttu-id="86ef9-122">无</span><span class="sxs-lookup"><span data-stu-id="86ef9-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86ef9-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86ef9-123">See also</span></span>
<span data-ttu-id="86ef9-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86ef9-124"></span></span>

[<span data-ttu-id="86ef9-125">安装 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="86ef9-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="86ef9-126">卸载-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="86ef9-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="86ef9-127">注册 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="86ef9-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="86ef9-128">取消注册 CcAppliance</span><span class="sxs-lookup"><span data-stu-id="86ef9-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

