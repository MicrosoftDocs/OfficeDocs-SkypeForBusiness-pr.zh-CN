---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'Renew-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 在云连接器 2.0 版和更高版本中，此命令已更改为 Update-CcServerCertificate。 '
ms.openlocfilehash: ad366bdf7f6c27552a8e7621ee9244762dd864eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894815"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="52e70-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="52e70-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="52e70-p102">Renew-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 在云连接器 2.0 版和更高版本中，此命令已更改为 Update-CcServerCertificate。 </span><span class="sxs-lookup"><span data-stu-id="52e70-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="52e70-107">示例</span><span class="sxs-lookup"><span data-stu-id="52e70-107">Examples</span></span>
<span data-ttu-id="52e70-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52e70-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="52e70-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="52e70-109">Example 1</span></span>

<span data-ttu-id="52e70-110">以下示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="52e70-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="52e70-111">示例 2</span><span class="sxs-lookup"><span data-stu-id="52e70-111">Example 2</span></span>

<span data-ttu-id="52e70-112">以下示例在中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="52e70-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="52e70-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="52e70-113">Detailed Description</span></span>
<span data-ttu-id="52e70-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="52e70-114"></span></span>

<span data-ttu-id="52e70-115">内部证书颁发给的中央管理存储、 中介服务器和边缘服务器的云连接器两年后从证书颁发机构服务颁发的有效。</span><span class="sxs-lookup"><span data-stu-id="52e70-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="52e70-116">如果证书即将过期或已过期，请运行 Renew-CcServerCertificate cmdlet 来续订服务。</span><span class="sxs-lookup"><span data-stu-id="52e70-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="52e70-117">参数</span><span class="sxs-lookup"><span data-stu-id="52e70-117">Parameters</span></span>
<span data-ttu-id="52e70-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="52e70-118"></span></span>

|<span data-ttu-id="52e70-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="52e70-119">**Parameter**</span></span>|<span data-ttu-id="52e70-120">**必需**</span><span class="sxs-lookup"><span data-stu-id="52e70-120">**Required**</span></span>|<span data-ttu-id="52e70-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="52e70-121">**Type**</span></span>|<span data-ttu-id="52e70-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="52e70-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52e70-123">角色</span><span class="sxs-lookup"><span data-stu-id="52e70-123">Roles</span></span>  <br/> |<span data-ttu-id="52e70-124">可选</span><span class="sxs-lookup"><span data-stu-id="52e70-124">Optional</span></span>  <br/> |<span data-ttu-id="52e70-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="52e70-125">System.Array</span></span>  <br/> | <span data-ttu-id="52e70-126">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="52e70-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="52e70-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="52e70-127">Input Types</span></span>
<span data-ttu-id="52e70-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52e70-128"></span></span>

<span data-ttu-id="52e70-p104">无。Renew-CcServerCertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="52e70-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="52e70-131">返回类型</span><span class="sxs-lookup"><span data-stu-id="52e70-131">Return Types</span></span>
<span data-ttu-id="52e70-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52e70-132"></span></span>

<span data-ttu-id="52e70-133">无</span><span class="sxs-lookup"><span data-stu-id="52e70-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52e70-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52e70-134">See also</span></span>
<span data-ttu-id="52e70-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52e70-135"></span></span>

[<span data-ttu-id="52e70-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="52e70-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="52e70-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="52e70-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="52e70-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="52e70-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

