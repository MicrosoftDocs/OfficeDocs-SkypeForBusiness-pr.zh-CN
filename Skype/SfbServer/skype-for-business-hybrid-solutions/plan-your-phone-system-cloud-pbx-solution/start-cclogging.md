---
title: Start-CcLogging
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
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Start-CcLogging cmdlet 用于为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
ms.openlocfilehash: bf84b55484e7f1d4f557730408676e337063a040
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824166"
---
# <a name="start-cclogging"></a><span data-ttu-id="99ceb-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="99ceb-103">Start-CcLogging</span></span>
 
<span data-ttu-id="99ceb-104">Start-CcLogging cmdlet 用于为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="99ceb-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="99ceb-105">参数</span><span class="sxs-lookup"><span data-stu-id="99ceb-105">Parameters</span></span>

<span data-ttu-id="99ceb-106">无</span><span class="sxs-lookup"><span data-stu-id="99ceb-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="99ceb-107">示例</span><span class="sxs-lookup"><span data-stu-id="99ceb-107">Examples</span></span>
<span data-ttu-id="99ceb-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="99ceb-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="99ceb-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="99ceb-109">Example 1</span></span>

<span data-ttu-id="99ceb-110">以下示例生成传入和传出呼叫日志：</span><span class="sxs-lookup"><span data-stu-id="99ceb-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="99ceb-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="99ceb-111">Detailed Description</span></span>
<span data-ttu-id="99ceb-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="99ceb-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="99ceb-113">CcLogging cmdlet 为管理员提供了一种在云连接器设备上开始记录传入和传出调用的方法。</span><span class="sxs-lookup"><span data-stu-id="99ceb-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="99ceb-114">默认情况下，日志记录将在四个小时后自动停止。</span><span class="sxs-lookup"><span data-stu-id="99ceb-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="99ceb-115">输入类型</span><span class="sxs-lookup"><span data-stu-id="99ceb-115">Input Types</span></span>
<span data-ttu-id="99ceb-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99ceb-116"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="99ceb-p102">无。Start-CcLogging cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="99ceb-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="99ceb-119">返回类型</span><span class="sxs-lookup"><span data-stu-id="99ceb-119">Return Types</span></span>
<span data-ttu-id="99ceb-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99ceb-120"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="99ceb-121">无</span><span class="sxs-lookup"><span data-stu-id="99ceb-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="99ceb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99ceb-122">See also</span></span>
<span data-ttu-id="99ceb-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="99ceb-123"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="99ceb-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="99ceb-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="99ceb-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="99ceb-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

