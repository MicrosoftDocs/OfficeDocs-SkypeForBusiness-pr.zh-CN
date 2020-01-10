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
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003392"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="b9c46-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="b9c46-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="b9c46-104">Get-CcApplianceLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本设备的日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="b9c46-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="b9c46-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="b9c46-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="b9c46-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9c46-106">Parameters</span></span>

<span data-ttu-id="b9c46-107">无</span><span class="sxs-lookup"><span data-stu-id="b9c46-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="b9c46-108">示例</span><span class="sxs-lookup"><span data-stu-id="b9c46-108">Examples</span></span>
<span data-ttu-id="b9c46-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c46-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="b9c46-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="b9c46-110">Example 1</span></span>

<span data-ttu-id="b9c46-111">以下示例显示存储了云连接器当前装置的日志的当前文件夹：</span><span class="sxs-lookup"><span data-stu-id="b9c46-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="b9c46-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="b9c46-112">Detailed Description</span></span>
<span data-ttu-id="b9c46-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c46-113"></span></span>

<span data-ttu-id="b9c46-114">CcApplianceLogDirectory cmdlet 显示用于存储云连接器装置日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="b9c46-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="b9c46-115">默认文件夹为 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="b9c46-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="b9c46-116">可以通过使用 Set-CcApplianceDirectory cmdlet 来更改目录。</span><span class="sxs-lookup"><span data-stu-id="b9c46-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="b9c46-117">请注意：没有只更改日志文件夹位置而不更改设备目录的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9c46-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="b9c46-118">输入类型</span><span class="sxs-lookup"><span data-stu-id="b9c46-118">Input Types</span></span>
<span data-ttu-id="b9c46-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c46-119"></span></span>

<span data-ttu-id="b9c46-p102">无。Get-CcApplianceLogDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="b9c46-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b9c46-122">返回类型</span><span class="sxs-lookup"><span data-stu-id="b9c46-122">Return Types</span></span>
<span data-ttu-id="b9c46-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c46-123"></span></span>

<span data-ttu-id="b9c46-124">此命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="b9c46-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9c46-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9c46-125">See also</span></span>
<span data-ttu-id="b9c46-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b9c46-126"></span></span>

[<span data-ttu-id="b9c46-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="b9c46-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

