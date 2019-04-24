---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging cmdlet 用于停止为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250630"
---
# <a name="stop-cclogging"></a><span data-ttu-id="f3211-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="f3211-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="f3211-104">Stop-CcLogging cmdlet 用于停止为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="f3211-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="f3211-105">示例</span><span class="sxs-lookup"><span data-stu-id="f3211-105">Examples</span></span>
<span data-ttu-id="f3211-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f3211-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="f3211-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="f3211-107">Example 1</span></span>

<span data-ttu-id="f3211-108">以下示例停止生成传入和传出呼叫日志：</span><span class="sxs-lookup"><span data-stu-id="f3211-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="f3211-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="f3211-109">Example 2</span></span>

<span data-ttu-id="f3211-110">以下示例停止生成传入和传出呼叫日志，并清除缓存文件：</span><span class="sxs-lookup"><span data-stu-id="f3211-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="f3211-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="f3211-111">Detailed Description</span></span>
<span data-ttu-id="f3211-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f3211-112"></span></span>

<span data-ttu-id="f3211-113">Stop-CcLogging cmdlet 用于停止设备上的传入和传出呼叫的日志记录。</span><span class="sxs-lookup"><span data-stu-id="f3211-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="f3211-114">默认情况下，日志记录将在四个小时后自动停止。</span><span class="sxs-lookup"><span data-stu-id="f3211-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f3211-115">参数</span><span class="sxs-lookup"><span data-stu-id="f3211-115">Parameters</span></span>
<span data-ttu-id="f3211-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f3211-116"></span></span>

|<span data-ttu-id="f3211-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="f3211-117">**Parameter**</span></span>|<span data-ttu-id="f3211-118">**必需**</span><span class="sxs-lookup"><span data-stu-id="f3211-118">**Required**</span></span>|<span data-ttu-id="f3211-119">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3211-119">**Type**</span></span>|<span data-ttu-id="f3211-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3211-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f3211-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="f3211-121">RemoveCache</span></span> <br/> | <span data-ttu-id="f3211-122">可选</span><span class="sxs-lookup"><span data-stu-id="f3211-122">Optional</span></span> <br/> | <span data-ttu-id="f3211-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="f3211-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="f3211-124">删除日志记录缓存文件。</span><span class="sxs-lookup"><span data-stu-id="f3211-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f3211-125">输入类型</span><span class="sxs-lookup"><span data-stu-id="f3211-125">Input Types</span></span>
<span data-ttu-id="f3211-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3211-126"></span></span>

<span data-ttu-id="f3211-p102">无。Stop-CcLogging cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="f3211-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f3211-129">返回类型</span><span class="sxs-lookup"><span data-stu-id="f3211-129">Return Types</span></span>
<span data-ttu-id="f3211-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3211-130"></span></span>

<span data-ttu-id="f3211-131">无</span><span class="sxs-lookup"><span data-stu-id="f3211-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f3211-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3211-132">See also</span></span>
<span data-ttu-id="f3211-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f3211-133"></span></span>

[<span data-ttu-id="f3211-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="f3211-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="f3211-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="f3211-135">Start-CcLogging</span></span>](start-cclogging.md)
  

