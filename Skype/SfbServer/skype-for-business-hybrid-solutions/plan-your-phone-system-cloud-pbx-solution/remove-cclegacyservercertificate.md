---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: 在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。
ms.openlocfilehash: f3fe17e8c6c559d1a2c8ab14543807f82c4b6813
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824278"
---
# <a name="remove-cclegacyservercertificate"></a><span data-ttu-id="99381-103">Remove-CcLegacyServerCertificate</span><span class="sxs-lookup"><span data-stu-id="99381-103">Remove-CcLegacyServerCertificate</span></span>
 
<span data-ttu-id="99381-104">在执行 Renew-CcCACertificate 或 Renew CcServerCertificate cmdlet 后，执行 Remove-CcLegacyServerCertificate cmdlet 可删除中央管理存储、中介服务器和边缘服务器上的旧服务器证书。</span><span class="sxs-lookup"><span data-stu-id="99381-104">The Remove-CcLegacyServerCertificate cmdlet removes legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.</span></span>
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a><span data-ttu-id="99381-105">示例</span><span class="sxs-lookup"><span data-stu-id="99381-105">Examples</span></span>
<span data-ttu-id="99381-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="99381-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="99381-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="99381-107">Example 1</span></span>

<span data-ttu-id="99381-108">以下示例在续订证书后删除为中央管理存储、中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="99381-108">The following example removes legacy certificates issued for the Central Management Store, Mediation Server, and Edge Server after you have renewed the certificates:</span></span>
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="99381-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="99381-109">Example 2</span></span>

<span data-ttu-id="99381-110">以下示例在续订证书后删除为中介服务器和边缘服务器颁发的旧证书：</span><span class="sxs-lookup"><span data-stu-id="99381-110">The next example removes certificates issued for Mediation Server and Edge Server after you have renewed the certificates:</span></span> 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a><span data-ttu-id="99381-111">参数</span><span class="sxs-lookup"><span data-stu-id="99381-111">Parameters</span></span>
<span data-ttu-id="99381-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="99381-112"><a name="Examples"> </a></span></span>

|<span data-ttu-id="99381-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="99381-113">**Parameter**</span></span>|<span data-ttu-id="99381-114">**必需**</span><span class="sxs-lookup"><span data-stu-id="99381-114">**Required**</span></span>|<span data-ttu-id="99381-115">**类型**</span><span class="sxs-lookup"><span data-stu-id="99381-115">**Type**</span></span>|<span data-ttu-id="99381-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="99381-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="99381-117">角色</span><span class="sxs-lookup"><span data-stu-id="99381-117">Roles</span></span> <br/> |<span data-ttu-id="99381-118">可选</span><span class="sxs-lookup"><span data-stu-id="99381-118">Optional</span></span>  <br/> |<span data-ttu-id="99381-119">System.Array</span><span class="sxs-lookup"><span data-stu-id="99381-119">System.Array</span></span>  <br/> | <span data-ttu-id="99381-120">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="99381-120">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="99381-121">输入类型</span><span class="sxs-lookup"><span data-stu-id="99381-121">Input Types</span></span>
<span data-ttu-id="99381-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99381-122"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="99381-p101">无。Remove-CcLegacyServerCertificate cmdlet 不接主线输入。</span><span class="sxs-lookup"><span data-stu-id="99381-p101">None. The Remove-CcLegacyServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="99381-125">返回类型</span><span class="sxs-lookup"><span data-stu-id="99381-125">Return Types</span></span>
<span data-ttu-id="99381-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99381-126"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="99381-127">无</span><span class="sxs-lookup"><span data-stu-id="99381-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99381-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99381-128">See also</span></span>
<span data-ttu-id="99381-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99381-129"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="99381-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="99381-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="99381-131">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="99381-131">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="99381-132">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="99381-132">Renew-CcCACertificate</span></span>](renew-cccacertificate.md)
  
[<span data-ttu-id="99381-133">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="99381-133">Update-CcCACertificate</span></span>](update-cccacertificate.md)
  

