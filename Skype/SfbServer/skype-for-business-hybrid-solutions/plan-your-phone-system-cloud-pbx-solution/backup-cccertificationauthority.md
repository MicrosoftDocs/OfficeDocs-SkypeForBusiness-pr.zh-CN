---
title: Backup-CcCertificationAuthority
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 47ed4559-fb63-42cd-8ecd-b7d1617e91d3
description: Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。
ms.openlocfilehash: 4e12b2349f5834866fc69442fb2947425416fe23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803802"
---
# <a name="backup-cccertificationauthority"></a><span data-ttu-id="5dece-103">Backup-CcCertificationAuthority</span><span class="sxs-lookup"><span data-stu-id="5dece-103">Backup-CcCertificationAuthority</span></span>
 
<span data-ttu-id="5dece-104">Backup-CcCertificationAuthority cmdlet 将 Skype for Business 云连接器版本证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5dece-104">The Backup-CcCertificationAuthority cmdlet backs up the Skype for Business Cloud Connector Edition certification authority service to a file and saves it to the CA folder under the site share directory.</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="parameters"></a><span data-ttu-id="5dece-105">参数</span><span class="sxs-lookup"><span data-stu-id="5dece-105">Parameters</span></span>

<span data-ttu-id="5dece-106">无</span><span class="sxs-lookup"><span data-stu-id="5dece-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5dece-107">示例</span><span class="sxs-lookup"><span data-stu-id="5dece-107">Examples</span></span>
<span data-ttu-id="5dece-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5dece-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5dece-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="5dece-109">Example 1</span></span>

<span data-ttu-id="5dece-110">以下 cmdlet 将证书颁发机构服务备份到一个文件中并将该文件保存到站点共享目录下的 CA 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5dece-110">The following example backs up the certification authority service to a file and saves it to the CA folder under the site share directory:</span></span>
  
```powershell
Backup-CcCertificationAuthority 
```

## <a name="detailed-description"></a><span data-ttu-id="5dece-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="5dece-111">Detailed Description</span></span>
<span data-ttu-id="5dece-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5dece-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="5dece-113">如果你计划在发生灾难的情况下重新部署云连接器设备，或者希望将设备移动到新硬件，则证书颁发机构备份可能很有用。</span><span class="sxs-lookup"><span data-stu-id="5dece-113">Certification authority backup can be useful if you plan to redeploy a Cloud Connector appliance with the same certificate in case of a disaster, or if you want to move the appliance to new hardware.</span></span> <span data-ttu-id="5dece-114">该命令将云连接器证书颁发机构服务的副本从广告服务器保存到 "\<SITEROOTDIRECTORY\>\CA\SfB CCE Root. p12"。</span><span class="sxs-lookup"><span data-stu-id="5dece-114">The command saves the copy of the Cloud Connector certification authority service from the AD Server to  "\<SiteRootDirectory\>\CA\SfB CCE Root.p12".</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5dece-115">输入类型</span><span class="sxs-lookup"><span data-stu-id="5dece-115">Input Types</span></span>
<span data-ttu-id="5dece-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5dece-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="5dece-p102">无。Backup-CcCertificationAuthority cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="5dece-p102">None. The Backup-CcCertificationAuthority cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5dece-119">返回类型</span><span class="sxs-lookup"><span data-stu-id="5dece-119">Return Types</span></span>
<span data-ttu-id="5dece-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5dece-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="5dece-121">无</span><span class="sxs-lookup"><span data-stu-id="5dece-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5dece-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dece-122">See also</span></span>
<span data-ttu-id="5dece-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5dece-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="5dece-124">Remove-CcCertificationAuthorityFile</span><span class="sxs-lookup"><span data-stu-id="5dece-124">Remove-CcCertificationAuthorityFile</span></span>](remove-cccertificationauthorityfile.md)
  

