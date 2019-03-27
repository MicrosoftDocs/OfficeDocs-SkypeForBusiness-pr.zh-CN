---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'Update-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 '
ms.openlocfilehash: 92f914db04d3a3621624efd5b6a72e249b3eb19e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899657"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="1c5a5-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="1c5a5-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="1c5a5-104">Update-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 </span><span class="sxs-lookup"><span data-stu-id="1c5a5-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="1c5a5-105">示例</span><span class="sxs-lookup"><span data-stu-id="1c5a5-105">Examples</span></span>
<span data-ttu-id="1c5a5-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5a5-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="1c5a5-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="1c5a5-107">Example 1</span></span>

<span data-ttu-id="1c5a5-108">以下示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="1c5a5-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="1c5a5-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="1c5a5-109">Example 2</span></span>

<span data-ttu-id="1c5a5-110">以下示例在中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="1c5a5-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="1c5a5-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="1c5a5-111">Detailed Description</span></span>
<span data-ttu-id="1c5a5-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5a5-112"></span></span>

<span data-ttu-id="1c5a5-113">内部证书颁发给的中央管理存储、 中介服务器和边缘服务器的云连接器两年后从证书颁发机构服务颁发的有效。</span><span class="sxs-lookup"><span data-stu-id="1c5a5-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="1c5a5-114">如果证书即将过期或已过期，请运行 Update-CcServerCertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="1c5a5-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="1c5a5-115">在云连接器 2.0 版和更高版本中，此命令将替代 Renew-CcServerCertificate cmdle。</span><span class="sxs-lookup"><span data-stu-id="1c5a5-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1c5a5-116">参数</span><span class="sxs-lookup"><span data-stu-id="1c5a5-116">Parameters</span></span>
<span data-ttu-id="1c5a5-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5a5-117"></span></span>

|<span data-ttu-id="1c5a5-118">**参数**</span><span class="sxs-lookup"><span data-stu-id="1c5a5-118">**Parameter**</span></span>|<span data-ttu-id="1c5a5-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="1c5a5-119">**Required**</span></span>|<span data-ttu-id="1c5a5-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="1c5a5-120">**Type**</span></span>|<span data-ttu-id="1c5a5-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="1c5a5-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1c5a5-122">角色</span><span class="sxs-lookup"><span data-stu-id="1c5a5-122">Roles</span></span>  <br/> |<span data-ttu-id="1c5a5-123">可选</span><span class="sxs-lookup"><span data-stu-id="1c5a5-123">Optional</span></span>  <br/> |<span data-ttu-id="1c5a5-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="1c5a5-124">System.Array</span></span>  <br/> | <span data-ttu-id="1c5a5-125">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="1c5a5-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1c5a5-126">输入类型</span><span class="sxs-lookup"><span data-stu-id="1c5a5-126">Input Types</span></span>
<span data-ttu-id="1c5a5-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5a5-127"></span></span>

<span data-ttu-id="1c5a5-p102">无。 Update-CcServerCertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="1c5a5-p102">None. The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1c5a5-130">返回类型</span><span class="sxs-lookup"><span data-stu-id="1c5a5-130">Return Types</span></span>
<span data-ttu-id="1c5a5-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5a5-131"></span></span>

<span data-ttu-id="1c5a5-132">无</span><span class="sxs-lookup"><span data-stu-id="1c5a5-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c5a5-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c5a5-133">See also</span></span>
<span data-ttu-id="1c5a5-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1c5a5-134"></span></span>

[<span data-ttu-id="1c5a5-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="1c5a5-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="1c5a5-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="1c5a5-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="1c5a5-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="1c5a5-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

