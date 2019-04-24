---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Set-CcApplianceDirectory cmdlet 用于设置 Skype for Business 云连接器版本主机服务器上的工作目录。所有部署文件都存储在此目录中。
ms.openlocfilehash: 16c9c858d770b7d4a74c9030ebdc760f5a9f25e9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250837"
---
# <a name="set-ccappliancedirectory"></a><span data-ttu-id="4b23d-104">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4b23d-104">Set-CcApplianceDirectory</span></span>
 
<span data-ttu-id="4b23d-p102">Set-CcApplianceDirectory cmdlet 用于设置 Skype for Business 云连接器版本主机服务器上的工作目录。所有部署文件都存储在此目录中。</span><span class="sxs-lookup"><span data-stu-id="4b23d-p102">The Set-CcApplianceDirectory cmdlet sets the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span>
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="4b23d-107">示例</span><span class="sxs-lookup"><span data-stu-id="4b23d-107">Examples</span></span>
<span data-ttu-id="4b23d-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4b23d-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="4b23d-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="4b23d-109">Example 1</span></span>

<span data-ttu-id="4b23d-110">下面的示例将主机服务器上的工作目录设置为 c:\cloudconnector\applianceroot：</span><span class="sxs-lookup"><span data-stu-id="4b23d-110">The following example sets the working directory on the host server to c:\cloudconnector\applianceroot:</span></span>
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a><span data-ttu-id="4b23d-111">参数</span><span class="sxs-lookup"><span data-stu-id="4b23d-111">Parameters</span></span>
<span data-ttu-id="4b23d-112"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4b23d-112"></span></span>

|<span data-ttu-id="4b23d-113">**参数**</span><span class="sxs-lookup"><span data-stu-id="4b23d-113">**Parameter**</span></span>|<span data-ttu-id="4b23d-114">**必需**</span><span class="sxs-lookup"><span data-stu-id="4b23d-114">**Required**</span></span>|<span data-ttu-id="4b23d-115">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b23d-115">**Type**</span></span>|<span data-ttu-id="4b23d-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="4b23d-116">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="4b23d-117">路径</span><span class="sxs-lookup"><span data-stu-id="4b23d-117">Path</span></span> <br/> | <span data-ttu-id="4b23d-118">必需</span><span class="sxs-lookup"><span data-stu-id="4b23d-118">Required</span></span> <br/> |<span data-ttu-id="4b23d-119">System.String</span><span class="sxs-lookup"><span data-stu-id="4b23d-119">System.String</span></span>  <br/> | <span data-ttu-id="4b23d-120">指定所有部署文件的存储路径。</span><span class="sxs-lookup"><span data-stu-id="4b23d-120">Specifies the path where all deployment files are stored.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4b23d-121">输入类型</span><span class="sxs-lookup"><span data-stu-id="4b23d-121">Input Types</span></span>
<span data-ttu-id="4b23d-122"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4b23d-122"></span></span>

<span data-ttu-id="4b23d-p103">无。Set-CCApplianceDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="4b23d-p103">None. The Set-CcApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4b23d-125">返回类型</span><span class="sxs-lookup"><span data-stu-id="4b23d-125">Return Types</span></span>
<span data-ttu-id="4b23d-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4b23d-126"></span></span>

<span data-ttu-id="4b23d-127">无</span><span class="sxs-lookup"><span data-stu-id="4b23d-127">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b23d-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b23d-128">See also</span></span>
<span data-ttu-id="4b23d-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4b23d-129"></span></span>

<span data-ttu-id="4b23d-130">无</span><span class="sxs-lookup"><span data-stu-id="4b23d-130">None</span></span>
  

