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
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: Start-CcLogging cmdlet 用于为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。
ms.openlocfilehash: 6e77ff347ca72a9aa31ad7bcb5a0330a8ea17a9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286920"
---
# <a name="start-cclogging"></a><span data-ttu-id="36e71-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="36e71-103">Start-CcLogging</span></span>
 
<span data-ttu-id="36e71-104">Start-CcLogging cmdlet 用于为 Skype for Business 云连接器版本设备生成传入和传出呼叫日志。</span><span class="sxs-lookup"><span data-stu-id="36e71-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="36e71-105">参数</span><span class="sxs-lookup"><span data-stu-id="36e71-105">Parameters</span></span>

<span data-ttu-id="36e71-106">无</span><span class="sxs-lookup"><span data-stu-id="36e71-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="36e71-107">示例</span><span class="sxs-lookup"><span data-stu-id="36e71-107">Examples</span></span>
<span data-ttu-id="36e71-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="36e71-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="36e71-109">示例 1</span><span class="sxs-lookup"><span data-stu-id="36e71-109">Example 1</span></span>

<span data-ttu-id="36e71-110">以下示例生成传入和传出呼叫日志：</span><span class="sxs-lookup"><span data-stu-id="36e71-110">The following example generates the incoming and outgoing call log:</span></span>
  
```
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="36e71-111">详细说明</span><span class="sxs-lookup"><span data-stu-id="36e71-111">Detailed Description</span></span>
<span data-ttu-id="36e71-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="36e71-112"></span></span>

<span data-ttu-id="36e71-113">CcLogging cmdlet 为管理员提供了一种在云连接器设备上开始记录传入和传出调用的方法。</span><span class="sxs-lookup"><span data-stu-id="36e71-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="36e71-114">默认情况下，日志记录将在四个小时后自动停止。</span><span class="sxs-lookup"><span data-stu-id="36e71-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="36e71-115">输入类型</span><span class="sxs-lookup"><span data-stu-id="36e71-115">Input Types</span></span>
<span data-ttu-id="36e71-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36e71-116"></span></span>

<span data-ttu-id="36e71-p102">无。Start-CcLogging cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="36e71-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="36e71-119">返回类型</span><span class="sxs-lookup"><span data-stu-id="36e71-119">Return Types</span></span>
<span data-ttu-id="36e71-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36e71-120"></span></span>

<span data-ttu-id="36e71-121">无</span><span class="sxs-lookup"><span data-stu-id="36e71-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36e71-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36e71-122">See also</span></span>
<span data-ttu-id="36e71-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36e71-123"></span></span>

[<span data-ttu-id="36e71-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="36e71-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="36e71-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="36e71-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

