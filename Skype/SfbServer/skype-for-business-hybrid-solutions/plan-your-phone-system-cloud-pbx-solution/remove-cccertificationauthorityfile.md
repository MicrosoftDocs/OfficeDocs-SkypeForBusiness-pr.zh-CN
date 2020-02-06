---
title: Remove-CcCertificationAuthorityFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3600af8d-04de-4b9a-88ac-2491ca06494d
description: CcCertificationAuthorityFile cmdlet 将在适用于 Skype for business 云连接器版本的网站共享目录下的 CA 文件夹中删除证书颁发机构服务备份文件。
ms.openlocfilehash: 49a8f0f313b4153288ebdf037a41dc92f30e60d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824288"
---
# <a name="remove-cccertificationauthorityfile"></a><span data-ttu-id="5f87b-103">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="5f87b-103">Remove-CcCertificationAuthorityFile</span></span>
 
<span data-ttu-id="5f87b-104">CcCertificationAuthorityFile cmdlet 将在 Skype for business Cloud Connector Edition 的网站共享&lt;目录&gt;下的 CA 文件夹中删除证书颁发机构服务备份文件 "SiteRootDirectory \CA\SfB CCE Root. p12"。</span><span class="sxs-lookup"><span data-stu-id="5f87b-104">The Remove-CcCertificationAuthorityFile cmdlet removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory for Skype for Business Cloud Connector Edition.</span></span> 
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="parameters"></a><span data-ttu-id="5f87b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f87b-105">Parameters</span></span>

<span data-ttu-id="5f87b-106">无</span><span class="sxs-lookup"><span data-stu-id="5f87b-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5f87b-107">示例</span><span class="sxs-lookup"><span data-stu-id="5f87b-107">Examples</span></span>
<span data-ttu-id="5f87b-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5f87b-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5f87b-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="5f87b-109">Example 1</span></span>

<span data-ttu-id="5f87b-110">以下示例将在网站共享目录下的 CA 文件夹&lt;中&gt;删除证书颁发机构服务备份文件 "SiteRootDirectory \CA\SfB CCE Root. p12"：</span><span class="sxs-lookup"><span data-stu-id="5f87b-110">The following example removes the certification authority service backup file "&lt;SiteRootDirectory&gt;\CA\SfB CCE Root.p12" in the CA folder under the site share directory:</span></span>
  
```powershell
Remove-CcCertificationAuthorityFile
```

## <a name="input-types"></a><span data-ttu-id="5f87b-111">输入类型</span><span class="sxs-lookup"><span data-stu-id="5f87b-111">Input Types</span></span>
<span data-ttu-id="5f87b-112"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5f87b-112"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5f87b-p101">无。Remove-CcCertificationAuthorityFile cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="5f87b-p101">None. The Remove-CcCertificationAuthorityFile cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5f87b-115">返回类型</span><span class="sxs-lookup"><span data-stu-id="5f87b-115">Return Types</span></span>
<span data-ttu-id="5f87b-116"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5f87b-116"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5f87b-117">无</span><span class="sxs-lookup"><span data-stu-id="5f87b-117">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f87b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f87b-118">See also</span></span>
<span data-ttu-id="5f87b-119"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5f87b-119"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="5f87b-120">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="5f87b-120">Backup-CcCertificationAuthority</span></span>](backup-cccertificationauthority.md)
  

