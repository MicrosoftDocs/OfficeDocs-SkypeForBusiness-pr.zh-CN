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
ms.openlocfilehash: f23a753df1a5c9f81b81bc0f1d7d33c01020b489
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="bc729-103">删除 CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bc729-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="bc729-104">在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。</span><span class="sxs-lookup"><span data-stu-id="bc729-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="bc729-105">示例</span><span class="sxs-lookup"><span data-stu-id="bc729-105">Examples</span></span>
<span data-ttu-id="bc729-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bc729-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="bc729-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="bc729-107">Example 1</span></span>

<span data-ttu-id="bc729-108">以下示例在续订证书后删除为中央管理存储、中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="bc729-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="bc729-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="bc729-109">Example 2</span></span>

<span data-ttu-id="bc729-110">以下示例在续订证书后删除为中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="bc729-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 

```

## <a name="parameters"></a><span data-ttu-id="bc729-111">参数</span><span class="sxs-lookup"><span data-stu-id="bc729-111">Parameters</span></span>
<span data-ttu-id="bc729-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bc729-112"></span></span>

|<span data-ttu-id="bc729-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="bc729-113">**Parameter**</span></span>|<span data-ttu-id="bc729-114">**必填**</span><span class="sxs-lookup"><span data-stu-id="bc729-114">**Required**</span></span>|<span data-ttu-id="bc729-115">**类型**</span><span class="sxs-lookup"><span data-stu-id="bc729-115">**Type**</span></span>|<span data-ttu-id="bc729-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="bc729-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="bc729-117">角色</span><span class="sxs-lookup"><span data-stu-id="bc729-117">Roles</span></span> <br/> |<span data-ttu-id="bc729-118">可选</span><span class="sxs-lookup"><span data-stu-id="bc729-118">Optional</span></span>  <br/> |<span data-ttu-id="bc729-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="bc729-119">System.Array</span></span>  <br/> | <span data-ttu-id="bc729-120">云连接器服务器角色阵列。</span><span class="sxs-lookup"><span data-stu-id="bc729-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="bc729-121">输入类型</span><span class="sxs-lookup"><span data-stu-id="bc729-121">Input Types</span></span>
<span data-ttu-id="bc729-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bc729-122"></span></span>

<span data-ttu-id="bc729-p101">无。Remove-CcLegacyServerCertificate cmdlet 不接主线输入。</span><span class="sxs-lookup"><span data-stu-id="bc729-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bc729-125">返回类型</span><span class="sxs-lookup"><span data-stu-id="bc729-125">Return Types</span></span>
<span data-ttu-id="bc729-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bc729-126"></span></span>

<span data-ttu-id="bc729-127">无</span><span class="sxs-lookup"><span data-stu-id="bc729-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bc729-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc729-128">See also</span></span>
<span data-ttu-id="bc729-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bc729-129"></span></span>

[<span data-ttu-id="bc729-130">续订 CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="bc729-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="bc729-131">重置-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bc729-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="bc729-132">续订 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bc729-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="bc729-133">更新 CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="bc729-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

