---
title: Reset-CcCACertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ada7e55-df9b-4b4e-b752-2468f4e28b8a
description: Reset-CcCACertificate cmdlet 重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。
ms.openlocfilehash: 50c3b1afc29503b2b292ce578ea01b03aeeba368
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003252"
---
# <a name="reset-cccacertificate"></a><span data-ttu-id="8888e-103">Reset-CcCACertificate</span><span class="sxs-lookup"><span data-stu-id="8888e-103">Reset-CcCACertificate</span></span>
 
<span data-ttu-id="8888e-104">Reset-CcCACertificate cmdlet 重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书。</span><span class="sxs-lookup"><span data-stu-id="8888e-104">The Reset-CcCACertificate cmdlet reinstalls the Certification Authority Service AD Server to create a new root CA certificate.</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="parameters"></a><span data-ttu-id="8888e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8888e-105">Parameters</span></span>

<span data-ttu-id="8888e-106">无</span><span class="sxs-lookup"><span data-stu-id="8888e-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8888e-107">示例</span><span class="sxs-lookup"><span data-stu-id="8888e-107">Examples</span></span>
<span data-ttu-id="8888e-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8888e-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="8888e-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="8888e-109">Example 1</span></span>

<span data-ttu-id="8888e-110">以下示例重新安装证书颁发机构服务 AD 服务器以创建新的根 CA 证书：</span><span class="sxs-lookup"><span data-stu-id="8888e-110">The following example reinstalls the Certification Authority Service AD Server to create a new root CA certificate:</span></span>
  
```powershell
Reset-CcCACertificate
```

## <a name="detailed-description"></a><span data-ttu-id="8888e-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="8888e-111">Detailed Description</span></span>
<span data-ttu-id="8888e-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8888e-112"></span></span>

<span data-ttu-id="8888e-113">如果根 CA 证书已损坏或不再安全，则必须更新根 CA 证书和根 CA 颁发的所有证书。</span><span class="sxs-lookup"><span data-stu-id="8888e-113">If the root CA certificate is compromised or no longer secure, you must update the root CA certificate, and all certificates issued by the root CA.</span></span> <span data-ttu-id="8888e-114">Reset-CcCACertificate cmdlet 会吊销所有证书、卸载并重新安装证书颁发机构，然后清除与旧证书颁发机构服务相关的所有证书。</span><span class="sxs-lookup"><span data-stu-id="8888e-114">The Reset-CcCACertificate cmdlet revokes all certificates, uninstalls and reinstalls the Certificate Authority, and then cleans up all certificates related to the old Certification Authority service.</span></span> 
  
<span data-ttu-id="8888e-115">有关详细信息，请参阅有关云连接器部署疑难解答中的 "证书颁发机构证书或颁发给 CMS、中介服务器和边缘服务器的内部证书已过期或已泄露"。</span><span class="sxs-lookup"><span data-stu-id="8888e-115">For more information, see "Certificate authority certificates or internal certificates issued to CMS, Mediation Server, and Edge Server are near expiration or are compromised" in Troubleshooting your Cloud Connector deployment.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8888e-116">输入类型</span><span class="sxs-lookup"><span data-stu-id="8888e-116">Input Types</span></span>
<span data-ttu-id="8888e-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8888e-117"></span></span>

<span data-ttu-id="8888e-p102">无。Reset-CcCACertificate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="8888e-p102">None. The Reset-CcCACertificate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8888e-120">返回类型</span><span class="sxs-lookup"><span data-stu-id="8888e-120">Return Types</span></span>
<span data-ttu-id="8888e-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8888e-121"></span></span>

<span data-ttu-id="8888e-122">无。</span><span class="sxs-lookup"><span data-stu-id="8888e-122">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8888e-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8888e-123">See also</span></span>
<span data-ttu-id="8888e-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8888e-124"></span></span>

<span data-ttu-id="8888e-125">[Renew-CcCACertificate](renew-cccacertificate.md) 仅限于版本 1.4.2</span><span class="sxs-lookup"><span data-stu-id="8888e-125">[Renew-CcCACertificate](renew-cccacertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="8888e-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) 仅限于版本 1.4.2</span><span class="sxs-lookup"><span data-stu-id="8888e-126">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 1.4.2 only</span></span>
  
<span data-ttu-id="8888e-127">[Update-CcCACertificate](update-cccacertificate.md) 2.0 版及更高版本</span><span class="sxs-lookup"><span data-stu-id="8888e-127">[Update-CcCACertificate](update-cccacertificate.md) Version 2.0 and later</span></span>
  
<span data-ttu-id="8888e-128">[续订-CcServerCertificate](renew-ccservercertificate.md)版本2.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="8888e-128">[Renew-CcServerCertificate](renew-ccservercertificate.md) Version 2.0 and later</span></span>
  
[<span data-ttu-id="8888e-129">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="8888e-129">Export-CcRootCertificate</span></span>](export-ccrootcertificate.md)
  

