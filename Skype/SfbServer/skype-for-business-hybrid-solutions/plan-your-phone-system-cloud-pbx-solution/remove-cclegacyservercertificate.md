---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: 在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。
ms.openlocfilehash: 5f148aa083b646565adf0158f34fb15314296170
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250883"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="0d3f2-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="0d3f2-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="0d3f2-104">在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。</span><span class="sxs-lookup"><span data-stu-id="0d3f2-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="0d3f2-105">示例</span><span class="sxs-lookup"><span data-stu-id="0d3f2-105">Examples</span></span>
<span data-ttu-id="0d3f2-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0d3f2-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="0d3f2-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="0d3f2-107">Example 1</span></span>

<span data-ttu-id="0d3f2-108">以下示例在续订证书后删除为中央管理存储、中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="0d3f2-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="0d3f2-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="0d3f2-109">Example 2</span></span>

<span data-ttu-id="0d3f2-110">以下示例在续订证书后删除为中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="0d3f2-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="0d3f2-111">参数</span><span class="sxs-lookup"><span data-stu-id="0d3f2-111">Parameters</span></span>
<span data-ttu-id="0d3f2-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0d3f2-112"></span></span>

|<span data-ttu-id="0d3f2-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="0d3f2-113">**Parameter**</span></span>|<span data-ttu-id="0d3f2-114">**必需**</span><span class="sxs-lookup"><span data-stu-id="0d3f2-114">**Required**</span></span>|<span data-ttu-id="0d3f2-115">**类型**</span><span class="sxs-lookup"><span data-stu-id="0d3f2-115">**Type**</span></span>|<span data-ttu-id="0d3f2-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="0d3f2-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0d3f2-117">角色</span><span class="sxs-lookup"><span data-stu-id="0d3f2-117">Roles</span></span> <br/> |<span data-ttu-id="0d3f2-118">可选</span><span class="sxs-lookup"><span data-stu-id="0d3f2-118">Optional</span></span>  <br/> |<span data-ttu-id="0d3f2-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="0d3f2-119">System.Array</span></span>  <br/> | <span data-ttu-id="0d3f2-120">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="0d3f2-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0d3f2-121">输入类型</span><span class="sxs-lookup"><span data-stu-id="0d3f2-121">Input Types</span></span>
<span data-ttu-id="0d3f2-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0d3f2-122"></span></span>

<span data-ttu-id="0d3f2-p101">无。Remove-CcLegacyServerCertificate cmdlet 不接主线输入。</span><span class="sxs-lookup"><span data-stu-id="0d3f2-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0d3f2-125">返回类型</span><span class="sxs-lookup"><span data-stu-id="0d3f2-125">Return Types</span></span>
<span data-ttu-id="0d3f2-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0d3f2-126"></span></span>

<span data-ttu-id="0d3f2-127">无</span><span class="sxs-lookup"><span data-stu-id="0d3f2-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d3f2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d3f2-128">See also</span></span>
<span data-ttu-id="0d3f2-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0d3f2-129"></span></span>

[<span data-ttu-id="0d3f2-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="0d3f2-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="0d3f2-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0d3f2-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="0d3f2-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0d3f2-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="0d3f2-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="0d3f2-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

