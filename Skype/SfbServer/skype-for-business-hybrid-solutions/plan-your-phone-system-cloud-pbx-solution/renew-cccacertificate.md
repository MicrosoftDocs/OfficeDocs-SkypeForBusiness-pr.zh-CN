---
title: Renew-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44da2f8d-0bf5-4f3e-b2e7-bb181dbbe646
description: Renew-CcCACertificate cmdlet 可续订即将过期或已过期的 Skype for Business 云连接器版本根 CA 证书。 在云连接器2.0 和更高版本中，此命令已更改为更新-CcCACertificate。
ms.openlocfilehash: 493b733eab9cbd8331a93d72dc4a865f3574fbe8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003272"
---
# <a name="renew-cccacertificate"></a><span data-ttu-id="e779d-104">Renew-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e779d-104">Renew-CcCACertificate</span></span>
 
<span data-ttu-id="e779d-105">Renew-CcCACertificate cmdlet 可续订即将过期或已过期的 Skype for Business 云连接器版本根 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="e779d-105">The Renew-CcCACertificate cmdlet renews the Skype for Business Cloud Connector Edition root CA certificate that is near expiration or already expired.</span></span> <span data-ttu-id="e779d-106">在云连接器2.0 和更高版本中，此命令已更改为更新-CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="e779d-106">This command was changed to Update-CcCACertificate in Cloud Connector 2.0 and later releases.</span></span>
  
```powershell
Renew-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="e779d-107">参数</span><span class="sxs-lookup"><span data-stu-id="e779d-107">Parameters</span></span>

<span data-ttu-id="e779d-108">无</span><span class="sxs-lookup"><span data-stu-id="e779d-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e779d-109">示例</span><span class="sxs-lookup"><span data-stu-id="e779d-109">Examples</span></span>
<span data-ttu-id="e779d-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e779d-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="e779d-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="e779d-111">Example 1</span></span>

<span data-ttu-id="e779d-112">以下示例续订根 CA 证书：</span><span class="sxs-lookup"><span data-stu-id="e779d-112">The following example renews the root CA certificate:</span></span> 
  
```powershell
Renew-CcCACertificate 
```

## <a name="detailed-description"></a><span data-ttu-id="e779d-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="e779d-113">Detailed Description</span></span>
<span data-ttu-id="e779d-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e779d-114"></span></span>

<span data-ttu-id="e779d-115">云连接器根 CA 证书的有效期是自安装证书颁发机构服务之日起的 5 年。</span><span class="sxs-lookup"><span data-stu-id="e779d-115">The Cloud Connector root CA certificate is valid for five years from the date that the Certificate Authority service is installed.</span></span>
  
<span data-ttu-id="e779d-p103">如果根证书即将过期或已过期，请运行 Renew-CcCACertificate cmdlet 来续订证书。续订了根证书后，将自动为 AD 服务器、中央管理存储及边缘服务器颁发新证书。</span><span class="sxs-lookup"><span data-stu-id="e779d-p103">If the root certificate is near expiration or already expired, run the Renew-CcCACertificate cmdlet to renew the certificate. After the root certificate is renewed, the AD Server, Central Management Store, and Edge Server will be issued new certificates automatically.</span></span>
  
<span data-ttu-id="e779d-118">如果同一 PSTN 站点中有多台设备，请在同一 PSTN 站点中的所有设备上运行 Renew-CcCACertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e779d-118">If there are multiple appliances in the same PSTN site, run the Renew-CcCACertificate cmdlet in all appliances of the same PSTN site.</span></span>
  
<span data-ttu-id="e779d-119">最后一步，运行 Export-CcRootCertificate 以将根证书导出为第一台设备上的本地文件，然后将导出的证书复制并安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="e779d-119">As the last step, run Export-CcRootCertificate to export the root certificate to a local file in the first appliance, then copy and install the exported certificate to your PSTN gateways.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e779d-120">输入类型</span><span class="sxs-lookup"><span data-stu-id="e779d-120">Input Types</span></span>
<span data-ttu-id="e779d-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e779d-121"></span></span>

<span data-ttu-id="e779d-p104">无。Renew-CcCACertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="e779d-p104">None. The Renew-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e779d-124">返回类型</span><span class="sxs-lookup"><span data-stu-id="e779d-124">Return Types</span></span>
<span data-ttu-id="e779d-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e779d-125"></span></span>

<span data-ttu-id="e779d-126">无</span><span class="sxs-lookup"><span data-stu-id="e779d-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e779d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e779d-127">See also</span></span>
<span data-ttu-id="e779d-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e779d-128"></span></span>

[<span data-ttu-id="e779d-129">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="e779d-129">Reset-CcCACertificate</span></span>](reset-cccacertificate.md)
  
[<span data-ttu-id="e779d-130">Renew-CcServerCertificate</span><span class="sxs-lookup"><span data-stu-id="e779d-130">Renew-CcServerCertificate</span></span>](renew-ccservercertificate.md)
  
[<span data-ttu-id="e779d-131">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="e779d-131">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

