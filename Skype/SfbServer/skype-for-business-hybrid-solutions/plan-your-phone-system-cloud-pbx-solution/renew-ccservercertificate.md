---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'Renew-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 在云连接器 2.0 版和更高版本中，此命令已更改为 Update-CcServerCertificate。 '
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824258"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="75c59-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="75c59-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="75c59-p102">Renew-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 在云连接器 2.0 版和更高版本中，此命令已更改为 Update-CcServerCertificate。 </span><span class="sxs-lookup"><span data-stu-id="75c59-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="75c59-107">示例</span><span class="sxs-lookup"><span data-stu-id="75c59-107">Examples</span></span>
<span data-ttu-id="75c59-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="75c59-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="75c59-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="75c59-109">Example 1</span></span>

<span data-ttu-id="75c59-110">以下示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="75c59-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="75c59-111">示例 2</span><span class="sxs-lookup"><span data-stu-id="75c59-111">Example 2</span></span>

<span data-ttu-id="75c59-112">以下示例在中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="75c59-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="75c59-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="75c59-113">Detailed Description</span></span>
<span data-ttu-id="75c59-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="75c59-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="75c59-115">颁发给中央管理存储、中介服务器和边缘服务器的云连接器内部证书在从证书颁发机构服务发出的两年后有效。</span><span class="sxs-lookup"><span data-stu-id="75c59-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="75c59-116">如果证书即将过期或已过期，请运行 Renew-CcServerCertificate cmdlet 来续订服务。</span><span class="sxs-lookup"><span data-stu-id="75c59-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="75c59-117">参数</span><span class="sxs-lookup"><span data-stu-id="75c59-117">Parameters</span></span>
<span data-ttu-id="75c59-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="75c59-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="75c59-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="75c59-119">**Parameter**</span></span>|<span data-ttu-id="75c59-120">**必需**</span><span class="sxs-lookup"><span data-stu-id="75c59-120">**Required**</span></span>|<span data-ttu-id="75c59-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="75c59-121">**Type**</span></span>|<span data-ttu-id="75c59-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="75c59-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75c59-123">角色</span><span class="sxs-lookup"><span data-stu-id="75c59-123">Roles</span></span>  <br/> |<span data-ttu-id="75c59-124">可选</span><span class="sxs-lookup"><span data-stu-id="75c59-124">Optional</span></span>  <br/> |<span data-ttu-id="75c59-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="75c59-125">System.Array</span></span>  <br/> | <span data-ttu-id="75c59-126">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="75c59-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="75c59-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="75c59-127">Input Types</span></span>
<span data-ttu-id="75c59-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="75c59-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="75c59-p104">无。Renew-CcServerCertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="75c59-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="75c59-131">返回类型</span><span class="sxs-lookup"><span data-stu-id="75c59-131">Return Types</span></span>
<span data-ttu-id="75c59-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="75c59-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="75c59-133">无</span><span class="sxs-lookup"><span data-stu-id="75c59-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75c59-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75c59-134">See also</span></span>
<span data-ttu-id="75c59-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="75c59-135"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="75c59-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="75c59-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="75c59-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="75c59-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="75c59-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="75c59-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

