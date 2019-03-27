---
title: Update-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5b474789-75de-443c-89bd-de89be55a1dd
description: 'Update-CcCACertificate cmdlet 可续订即将过期或已过期的 Skype for Business 云连接器版本根 CA 证书。 '
ms.openlocfilehash: d123474240fb18ffcb6c1c037cc5407eb4c6c4e3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877931"
---
# <a name="update-cccacertificate"></a><span data-ttu-id="cd136-103">Update-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="cd136-103">Update-CcCACertificate</span></span>
 
<span data-ttu-id="cd136-104">Update-CcCACertificate cmdlet 可续订即将过期或已过期的 Skype for Business 云连接器版本根 CA 证书。 </span><span class="sxs-lookup"><span data-stu-id="cd136-104">The Update-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> 
  
```
Update-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="cd136-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd136-105">Parameters</span></span>

<span data-ttu-id="cd136-106">无。</span><span class="sxs-lookup"><span data-stu-id="cd136-106">None.</span></span>
  
## <a name="examples"></a><span data-ttu-id="cd136-107">示例</span><span class="sxs-lookup"><span data-stu-id="cd136-107">Examples</span></span>
<span data-ttu-id="cd136-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cd136-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="cd136-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="cd136-109">Example 1</span></span>

<span data-ttu-id="cd136-110">以下示例续订根 CA 证书：</span><span class="sxs-lookup"><span data-stu-id="cd136-110">The following example renews the root CA certificate:</span></span> 
  
```
Update-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="cd136-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="cd136-111">Detailed Description</span></span>
<span data-ttu-id="cd136-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cd136-112"></span></span>

<span data-ttu-id="cd136-113">云连接器根 CA 证书的有效期是自安装证书颁发机构服务之日起的 5 年。</span><span class="sxs-lookup"><span data-stu-id="cd136-113">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="cd136-p101">如果根证书即将过期或已过期，请运行 Update-CcCACertificate cmdlet 来续订证书。 续订了根证书后，将自动为 AD 服务器、中央管理存储及边缘服务器颁发新证书。</span><span class="sxs-lookup"><span data-stu-id="cd136-p101">If the root certificate is near expiration or already expired, run the Update-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="cd136-116">如果同一 PSTN 站点中有多台设备，请在同一 PSTN 站点中的所有设备上运行 Update-CcCACertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cd136-116">If there are multiple appliances in the same PSTN site, run the Update-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="cd136-117">最后一步，运行 Export-CcRootCertificate 以将根证书导出为第一台设备上的本地文件，然后将导出的证书复制并安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="cd136-117">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
<span data-ttu-id="cd136-118">在云连接器 2.0 版和更高版本中，此命令将替代 Renew-CcCACertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cd136-118">This command replaces the Renew-CcCACertificate cmdlet in Cloud Connector 2.0 and later releases.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="cd136-119">输入类型</span><span class="sxs-lookup"><span data-stu-id="cd136-119">Input Types</span></span>
<span data-ttu-id="cd136-120"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cd136-120"></span></span>

<span data-ttu-id="cd136-p102">无。 Update-CcCACertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="cd136-p102">None. The Update-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cd136-123">返回类型</span><span class="sxs-lookup"><span data-stu-id="cd136-123">Return Types</span></span>
<span data-ttu-id="cd136-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cd136-124"></span></span>

<span data-ttu-id="cd136-125">无。</span><span class="sxs-lookup"><span data-stu-id="cd136-125">None.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cd136-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd136-126">See also</span></span>
<span data-ttu-id="cd136-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cd136-127"></span></span>

[<span data-ttu-id="cd136-128">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="cd136-128">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="cd136-129">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="cd136-129">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="cd136-130">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="cd136-130">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

