---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。
ms.openlocfilehash: d1298454bb347356718fdf24d6761acfea1b71b1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890358"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="27e09-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="27e09-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="27e09-104">Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="27e09-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="27e09-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="27e09-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="27e09-106">参数</span><span class="sxs-lookup"><span data-stu-id="27e09-106">Parameters</span></span>

<span data-ttu-id="27e09-107">无</span><span class="sxs-lookup"><span data-stu-id="27e09-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="27e09-108">示例</span><span class="sxs-lookup"><span data-stu-id="27e09-108">Examples</span></span>
<span data-ttu-id="27e09-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="27e09-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="27e09-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="27e09-110">Example 1</span></span>

<span data-ttu-id="27e09-111">下面的示例显示当前文件夹存储为当前 appliance 云连接器的日志：</span><span class="sxs-lookup"><span data-stu-id="27e09-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="27e09-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="27e09-112">Detailed Description</span></span>
<span data-ttu-id="27e09-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="27e09-113"></span></span>

<span data-ttu-id="27e09-114">Get CcApplianceLogDirectory cmdlet 显示在当前目录为云连接器 appliance 日志存储在何处。</span><span class="sxs-lookup"><span data-stu-id="27e09-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="27e09-115">默认文件夹已 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="27e09-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="27e09-116">可以通过使用 Set-CcApplianceDirectory cmdlet 来更改目录。</span><span class="sxs-lookup"><span data-stu-id="27e09-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="27e09-117">请注意：没有只更改日志文件夹位置而不更改设备目录的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27e09-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="27e09-118">输入类型</span><span class="sxs-lookup"><span data-stu-id="27e09-118">Input Types</span></span>
<span data-ttu-id="27e09-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27e09-119"></span></span>

<span data-ttu-id="27e09-p102">无。Get-CcApplianceLogDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="27e09-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="27e09-122">返回类型</span><span class="sxs-lookup"><span data-stu-id="27e09-122">Return Types</span></span>
<span data-ttu-id="27e09-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27e09-123"></span></span>

<span data-ttu-id="27e09-124">此命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="27e09-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="27e09-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27e09-125">See also</span></span>
<span data-ttu-id="27e09-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="27e09-126"></span></span>

[<span data-ttu-id="27e09-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="27e09-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

