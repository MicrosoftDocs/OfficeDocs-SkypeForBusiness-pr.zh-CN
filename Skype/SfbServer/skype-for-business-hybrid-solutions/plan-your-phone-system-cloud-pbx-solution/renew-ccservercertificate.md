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
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 'Renew-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 在云连接器 2.0 版和更高版本中，此命令已更改为 Update-CcServerCertificate。 '
ms.openlocfilehash: 47f2bbefa6510ae49e2e4a3ddc321e288dee266e
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003262"
---
# <a name="renew-ccservercertificate"></a><span data-ttu-id="46257-104">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="46257-104">Renew-CcServerCertificate</span></span>
 
<span data-ttu-id="46257-p102">Renew-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 在云连接器 2.0 版和更高版本中，此命令已更改为 Update-CcServerCertificate。 </span><span class="sxs-lookup"><span data-stu-id="46257-p102">The Renew-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired. This command was changed to Update-CcServerCertificate in Cloud Connector 2.0 and later releases.</span></span> 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="46257-107">示例</span><span class="sxs-lookup"><span data-stu-id="46257-107">Examples</span></span>
<span data-ttu-id="46257-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="46257-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="46257-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="46257-109">Example 1</span></span>

<span data-ttu-id="46257-110">以下示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="46257-110">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="46257-111">示例 2</span><span class="sxs-lookup"><span data-stu-id="46257-111">Example 2</span></span>

<span data-ttu-id="46257-112">以下示例在中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="46257-112">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="46257-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="46257-113">Detailed Description</span></span>
<span data-ttu-id="46257-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="46257-114"></span></span>

<span data-ttu-id="46257-115">颁发给中央管理存储、中介服务器和边缘服务器的云连接器内部证书在从证书颁发机构服务发出的两年后有效。</span><span class="sxs-lookup"><span data-stu-id="46257-115">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="46257-116">如果证书即将过期或已过期，请运行 Renew-CcServerCertificate cmdlet 来续订服务。</span><span class="sxs-lookup"><span data-stu-id="46257-116">If certificates are near expiration or already expired, run the Renew-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="46257-117">参数</span><span class="sxs-lookup"><span data-stu-id="46257-117">Parameters</span></span>
<span data-ttu-id="46257-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="46257-118"></span></span>

|<span data-ttu-id="46257-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="46257-119">**Parameter**</span></span>|<span data-ttu-id="46257-120">**必需**</span><span class="sxs-lookup"><span data-stu-id="46257-120">**Required**</span></span>|<span data-ttu-id="46257-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="46257-121">**Type**</span></span>|<span data-ttu-id="46257-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="46257-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="46257-123">角色</span><span class="sxs-lookup"><span data-stu-id="46257-123">Roles</span></span>  <br/> |<span data-ttu-id="46257-124">可选</span><span class="sxs-lookup"><span data-stu-id="46257-124">Optional</span></span>  <br/> |<span data-ttu-id="46257-125">System.Array</span><span class="sxs-lookup"><span data-stu-id="46257-125">System.Array</span></span>  <br/> | <span data-ttu-id="46257-126">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="46257-126">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="46257-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="46257-127">Input Types</span></span>
<span data-ttu-id="46257-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46257-128"></span></span>

<span data-ttu-id="46257-p104">无。Renew-CcServerCertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="46257-p104">None. The Renew-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="46257-131">返回类型</span><span class="sxs-lookup"><span data-stu-id="46257-131">Return Types</span></span>
<span data-ttu-id="46257-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46257-132"></span></span>

<span data-ttu-id="46257-133">无</span><span class="sxs-lookup"><span data-stu-id="46257-133">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="46257-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46257-134">See also</span></span>
<span data-ttu-id="46257-135"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="46257-135"></span></span>

[<span data-ttu-id="46257-136">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="46257-136">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="46257-137">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="46257-137">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="46257-138">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="46257-138">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

