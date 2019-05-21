---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 'Update-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 '
ms.openlocfilehash: 34da35e607f8941da9c962386509f8a0b87ec122
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286878"
---
# <a name="update-ccservercertificate"></a><span data-ttu-id="8b88b-103">Update-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="8b88b-103">Update-CcServerCertificate</span></span>
 
<span data-ttu-id="8b88b-104">Update-CcServerCertificate cmdlet 用于在 Skype for Business 云连接器版本的证书即将过期或已过期时续订这些证书。 </span><span class="sxs-lookup"><span data-stu-id="8b88b-104">The Update-CcServerCertificate cmdlet renews the certificates for Skype for Business Cloud Connector Edition when they are near expiration or already expired.</span></span> 
  
```
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a><span data-ttu-id="8b88b-105">示例</span><span class="sxs-lookup"><span data-stu-id="8b88b-105">Examples</span></span>
<span data-ttu-id="8b88b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8b88b-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="8b88b-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="8b88b-107">Example 1</span></span>

<span data-ttu-id="8b88b-108">以下示例在中央管理存储、中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="8b88b-108">The following example renews the certificates for the Central Management Store, Mediation Server, and Edge Server when the certificates are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate
```

### <a name="example-2"></a><span data-ttu-id="8b88b-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="8b88b-109">Example 2</span></span>

<span data-ttu-id="8b88b-110">以下示例在中介服务器和边缘服务器的证书即将过期或已过期时续订这些证书：</span><span class="sxs-lookup"><span data-stu-id="8b88b-110">The next example renews the certificates for Mediation Server and Edge Server when they are near expiration or already expired:</span></span>
  
```
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a><span data-ttu-id="8b88b-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="8b88b-111">Detailed Description</span></span>
<span data-ttu-id="8b88b-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8b88b-112"></span></span>

<span data-ttu-id="8b88b-113">颁发给中央管理存储、中介服务器和边缘服务器的云连接器内部证书在从证书颁发机构服务发出的两年后有效。</span><span class="sxs-lookup"><span data-stu-id="8b88b-113">Cloud Connector internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years after they are issued from a Certificate Authority service.</span></span> <span data-ttu-id="8b88b-114">如果证书即将过期或已过期，请运行 Update-CcServerCertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="8b88b-114">If certificates are near expiration or already expired, run the Update-CcServerCertificate cmdlet to renew the certificates.</span></span> 
  
<span data-ttu-id="8b88b-115">在云连接器 2.0 版和更高版本中，此命令将替代 Renew-CcServerCertificate cmdle。</span><span class="sxs-lookup"><span data-stu-id="8b88b-115">This command replaces the Renew-CcServerCertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="8b88b-116">参数</span><span class="sxs-lookup"><span data-stu-id="8b88b-116">Parameters</span></span>
<span data-ttu-id="8b88b-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8b88b-117"></span></span>

|<span data-ttu-id="8b88b-118">**参数**</span><span class="sxs-lookup"><span data-stu-id="8b88b-118">**Parameter**</span></span>|<span data-ttu-id="8b88b-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="8b88b-119">**Required**</span></span>|<span data-ttu-id="8b88b-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="8b88b-120">**Type**</span></span>|<span data-ttu-id="8b88b-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="8b88b-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b88b-122">角色</span><span class="sxs-lookup"><span data-stu-id="8b88b-122">Roles</span></span>  <br/> |<span data-ttu-id="8b88b-123">可选</span><span class="sxs-lookup"><span data-stu-id="8b88b-123">Optional</span></span>  <br/> |<span data-ttu-id="8b88b-124">System.Array</span><span class="sxs-lookup"><span data-stu-id="8b88b-124">System.Array</span></span>  <br/> | <span data-ttu-id="8b88b-125">云连接器服务器角色的阵列。</span><span class="sxs-lookup"><span data-stu-id="8b88b-125">Array of Cloud Connector server roles.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="8b88b-126">输入类型</span><span class="sxs-lookup"><span data-stu-id="8b88b-126">Input Types</span></span>
<span data-ttu-id="8b88b-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8b88b-127"></span></span>

<span data-ttu-id="8b88b-p102">无。 Update-CcServerCertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="8b88b-p102">None. The Update-CcServerCertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8b88b-130">返回类型</span><span class="sxs-lookup"><span data-stu-id="8b88b-130">Return Types</span></span>
<span data-ttu-id="8b88b-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8b88b-131"></span></span>

<span data-ttu-id="8b88b-132">无</span><span class="sxs-lookup"><span data-stu-id="8b88b-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b88b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b88b-133">See also</span></span>
<span data-ttu-id="8b88b-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8b88b-134"></span></span>

[<span data-ttu-id="8b88b-135">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8b88b-135">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="8b88b-136">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="8b88b-136">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="8b88b-137">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="8b88b-137">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

