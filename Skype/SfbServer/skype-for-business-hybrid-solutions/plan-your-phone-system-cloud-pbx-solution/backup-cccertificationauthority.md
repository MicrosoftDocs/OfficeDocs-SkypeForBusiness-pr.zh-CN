---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
ms.openlocfilehash: 2f85a4da58a586852b3331f1f8e482ee17e29e02
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886498"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="0c081-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="0c081-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="0c081-104">Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c081-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="0c081-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c081-105">Parameters</span></span>

<span data-ttu-id="0c081-106">无</span><span class="sxs-lookup"><span data-stu-id="0c081-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="0c081-107">示例</span><span class="sxs-lookup"><span data-stu-id="0c081-107">Examples</span></span>
<span data-ttu-id="0c081-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0c081-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="0c081-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="0c081-109">Example 1</span></span>

<span data-ttu-id="0c081-110">以下 cmdlet 将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c081-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="0c081-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="0c081-111">Detailed Description</span></span>
<span data-ttu-id="0c081-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0c081-112"></span></span>

<span data-ttu-id="0c081-113">如果您打算使用同一证书在发生灾难时为云连接器 appliance 重新部署或您要移动到新硬件的设备，证书颁发机构备份很有用。</span><span class="sxs-lookup"><span data-stu-id="0c081-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="0c081-114">该命令将云连接器证书颁发机构服务的副本保存从 AD 服务器到"\<SiteRootDirectory\>\CA\SfB CCE Root.p12"。</span><span class="sxs-lookup"><span data-stu-id="0c081-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="0c081-115">输入类型</span><span class="sxs-lookup"><span data-stu-id="0c081-115">Input Types</span></span>
<span data-ttu-id="0c081-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c081-116"></span></span>

<span data-ttu-id="0c081-p102">无。Backup-CcCertificationAuthority cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="0c081-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0c081-119">返回类型</span><span class="sxs-lookup"><span data-stu-id="0c081-119">Return Types</span></span>
<span data-ttu-id="0c081-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c081-120"></span></span>

<span data-ttu-id="0c081-121">无</span><span class="sxs-lookup"><span data-stu-id="0c081-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0c081-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c081-122">See also</span></span>
<span data-ttu-id="0c081-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0c081-123"></span></span>

[<span data-ttu-id="0c081-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="0c081-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

