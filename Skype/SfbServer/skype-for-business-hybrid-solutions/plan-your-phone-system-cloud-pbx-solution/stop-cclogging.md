---
title: Stop-CcLogging
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
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Stop-CcLogging cmdlet 用于停止为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824156"
---
# <a name="stop-cclogging"></a><span data-ttu-id="7ad48-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="7ad48-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="7ad48-104">Stop-CcLogging cmdlet 用于停止为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="7ad48-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="7ad48-105">示例</span><span class="sxs-lookup"><span data-stu-id="7ad48-105">Examples</span></span>
<span data-ttu-id="7ad48-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad48-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="7ad48-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="7ad48-107">Example 1</span></span>

<span data-ttu-id="7ad48-108">以下示例停止生成传入和传出呼叫日志：</span><span class="sxs-lookup"><span data-stu-id="7ad48-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="7ad48-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="7ad48-109">Example 2</span></span>

<span data-ttu-id="7ad48-110">以下示例停止生成传入和传出呼叫日志，并清除缓存文件：</span><span class="sxs-lookup"><span data-stu-id="7ad48-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="7ad48-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="7ad48-111">Detailed Description</span></span>
<span data-ttu-id="7ad48-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad48-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="7ad48-113">Stop-CcLogging cmdlet 用于停止设备上的传入和传出呼叫的日志记录。</span><span class="sxs-lookup"><span data-stu-id="7ad48-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="7ad48-114">默认情况下，日志记录将在四个小时后自动停止。</span><span class="sxs-lookup"><span data-stu-id="7ad48-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="7ad48-115">参数</span><span class="sxs-lookup"><span data-stu-id="7ad48-115">Parameters</span></span>
<span data-ttu-id="7ad48-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad48-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="7ad48-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="7ad48-117">**Parameter**</span></span>|<span data-ttu-id="7ad48-118">**必需**</span><span class="sxs-lookup"><span data-stu-id="7ad48-118">**Required**</span></span>|<span data-ttu-id="7ad48-119">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ad48-119">**Type**</span></span>|<span data-ttu-id="7ad48-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ad48-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7ad48-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="7ad48-121">RemoveCache</span></span> <br/> | <span data-ttu-id="7ad48-122">可选</span><span class="sxs-lookup"><span data-stu-id="7ad48-122">Optional</span></span> <br/> | <span data-ttu-id="7ad48-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7ad48-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="7ad48-124">删除日志记录缓存文件。</span><span class="sxs-lookup"><span data-stu-id="7ad48-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="7ad48-125">输入类型</span><span class="sxs-lookup"><span data-stu-id="7ad48-125">Input Types</span></span>
<span data-ttu-id="7ad48-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad48-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="7ad48-p102">无。Stop-CcLogging cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="7ad48-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7ad48-129">返回类型</span><span class="sxs-lookup"><span data-stu-id="7ad48-129">Return Types</span></span>
<span data-ttu-id="7ad48-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad48-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="7ad48-131">无</span><span class="sxs-lookup"><span data-stu-id="7ad48-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ad48-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ad48-132">See also</span></span>
<span data-ttu-id="7ad48-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7ad48-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="7ad48-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="7ad48-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="7ad48-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="7ad48-135">Start-CcLogging</span></span>](start-cclogging.md)
  

