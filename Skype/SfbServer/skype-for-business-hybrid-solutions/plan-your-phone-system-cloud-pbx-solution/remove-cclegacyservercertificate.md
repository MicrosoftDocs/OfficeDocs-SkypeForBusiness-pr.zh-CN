---
title: 删除 CcLegacyServerCertificate
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
ms.openlocfilehash: dc52351d9c66ff310329da62dbd69da74b19c222
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569838"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="199a5-103">删除 CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="199a5-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="199a5-104">在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。</span><span class="sxs-lookup"><span data-stu-id="199a5-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="199a5-105">示例</span><span class="sxs-lookup"><span data-stu-id="199a5-105">Examples</span></span>
<span data-ttu-id="199a5-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="199a5-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="199a5-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="199a5-107">Example 1</span></span>

<span data-ttu-id="199a5-108">以下示例在续订证书后删除为中央管理存储、中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="199a5-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="199a5-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="199a5-109">Example 2</span></span>

<span data-ttu-id="199a5-110">以下示例在续订证书后删除为中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="199a5-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="199a5-111">参数</span><span class="sxs-lookup"><span data-stu-id="199a5-111">Parameters</span></span>
<span data-ttu-id="199a5-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="199a5-112"></span></span>

|<span data-ttu-id="199a5-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="199a5-113">**Parameter**</span></span>|<span data-ttu-id="199a5-114">**必填**</span><span class="sxs-lookup"><span data-stu-id="199a5-114">**Required**</span></span>|<span data-ttu-id="199a5-115">**类型**</span><span class="sxs-lookup"><span data-stu-id="199a5-115">**Type**</span></span>|<span data-ttu-id="199a5-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="199a5-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="199a5-117">角色</span><span class="sxs-lookup"><span data-stu-id="199a5-117">Roles</span></span> <br/> |<span data-ttu-id="199a5-118">可选</span><span class="sxs-lookup"><span data-stu-id="199a5-118">Optional</span></span>  <br/> |<span data-ttu-id="199a5-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="199a5-119">System.Array</span></span>  <br/> | <span data-ttu-id="199a5-120">云连接器服务器角色阵列。</span><span class="sxs-lookup"><span data-stu-id="199a5-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="199a5-121">输入类型</span><span class="sxs-lookup"><span data-stu-id="199a5-121">Input Types</span></span>
<span data-ttu-id="199a5-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="199a5-122"></span></span>

<span data-ttu-id="199a5-p101">无。Remove-CcLegacyServerCertificate cmdlet 不接主线输入。</span><span class="sxs-lookup"><span data-stu-id="199a5-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="199a5-125">返回类型</span><span class="sxs-lookup"><span data-stu-id="199a5-125">Return Types</span></span>
<span data-ttu-id="199a5-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="199a5-126"></span></span>

<span data-ttu-id="199a5-127">无</span><span class="sxs-lookup"><span data-stu-id="199a5-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="199a5-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="199a5-128">See also</span></span>
<span data-ttu-id="199a5-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="199a5-129"></span></span>

[<span data-ttu-id="199a5-130">续订 CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="199a5-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="199a5-131">重置 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="199a5-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="199a5-132">续订 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="199a5-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="199a5-133">更新 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="199a5-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

