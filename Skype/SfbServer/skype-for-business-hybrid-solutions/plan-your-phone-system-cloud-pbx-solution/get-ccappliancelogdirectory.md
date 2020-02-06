---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800822"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="47cb9-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="47cb9-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="47cb9-104">Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="47cb9-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="47cb9-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="47cb9-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="47cb9-106">参数</span><span class="sxs-lookup"><span data-stu-id="47cb9-106">Parameters</span></span>

<span data-ttu-id="47cb9-107">无</span><span class="sxs-lookup"><span data-stu-id="47cb9-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="47cb9-108">示例</span><span class="sxs-lookup"><span data-stu-id="47cb9-108">Examples</span></span>
<span data-ttu-id="47cb9-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47cb9-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="47cb9-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="47cb9-110">Example 1</span></span>

<span data-ttu-id="47cb9-111">以下示例显示存储了云连接器当前装置的日志的当前文件夹：</span><span class="sxs-lookup"><span data-stu-id="47cb9-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="47cb9-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="47cb9-112">Detailed Description</span></span>
<span data-ttu-id="47cb9-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="47cb9-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="47cb9-114">CcApplianceLogDirectory cmdlet 显示用于存储云连接器装置日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="47cb9-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="47cb9-115">默认文件夹为 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="47cb9-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="47cb9-116">可以通过使用 Set-CcApplianceDirectory cmdlet 来更改目录。</span><span class="sxs-lookup"><span data-stu-id="47cb9-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="47cb9-117">请注意：没有只更改日志文件夹位置而不更改设备目录的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="47cb9-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="47cb9-118">输入类型</span><span class="sxs-lookup"><span data-stu-id="47cb9-118">Input Types</span></span>
<span data-ttu-id="47cb9-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="47cb9-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="47cb9-p102">无。Get-CcApplianceLogDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="47cb9-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="47cb9-122">返回类型</span><span class="sxs-lookup"><span data-stu-id="47cb9-122">Return Types</span></span>
<span data-ttu-id="47cb9-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="47cb9-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="47cb9-124">此命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="47cb9-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47cb9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47cb9-125">See also</span></span>
<span data-ttu-id="47cb9-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="47cb9-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="47cb9-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="47cb9-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

