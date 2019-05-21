---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Exit-CcUpdate cmdlet 用于在 Skype for Business 云连接器版本主机服务器上退出更新维护模式。
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287424"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="5c4b5-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="5c4b5-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="5c4b5-104">Exit-CcUpdate cmdlet 用于在 Skype for Business 云连接器版本主机服务器上退出更新维护模式。</span><span class="sxs-lookup"><span data-stu-id="5c4b5-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="5c4b5-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="5c4b5-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="5c4b5-106">参数</span><span class="sxs-lookup"><span data-stu-id="5c4b5-106">Parameters</span></span>

<span data-ttu-id="5c4b5-107">无</span><span class="sxs-lookup"><span data-stu-id="5c4b5-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="5c4b5-108">示例</span><span class="sxs-lookup"><span data-stu-id="5c4b5-108">Examples</span></span>
<span data-ttu-id="5c4b5-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5c4b5-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="5c4b5-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="5c4b5-110">Example 1</span></span>

<span data-ttu-id="5c4b5-111">以下命令将运行它的设备恢复到生产模式：</span><span class="sxs-lookup"><span data-stu-id="5c4b5-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="5c4b5-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="5c4b5-112">Detailed Description</span></span>
<span data-ttu-id="5c4b5-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="5c4b5-113"></span></span>

<span data-ttu-id="5c4b5-114">如果有通过指定 Enter-CcUpdate cmdlet 被置于维护模式的设备，Exit-CcUpdate cmdlet 可将这些设备恢复到生产模式。</span><span class="sxs-lookup"><span data-stu-id="5c4b5-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="5c4b5-115">有关将设备置于维护模式的详细信息，请参阅 Enter-CcUpdate。</span><span class="sxs-lookup"><span data-stu-id="5c4b5-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="5c4b5-116">输入类型</span><span class="sxs-lookup"><span data-stu-id="5c4b5-116">Input Types</span></span>
<span data-ttu-id="5c4b5-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5c4b5-117"></span></span>

<span data-ttu-id="5c4b5-p101">无。Exit-CcUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="5c4b5-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5c4b5-120">返回类型</span><span class="sxs-lookup"><span data-stu-id="5c4b5-120">Return Types</span></span>
<span data-ttu-id="5c4b5-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5c4b5-121"></span></span>

<span data-ttu-id="5c4b5-122">无</span><span class="sxs-lookup"><span data-stu-id="5c4b5-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5c4b5-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c4b5-123">See also</span></span>
<span data-ttu-id="5c4b5-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="5c4b5-124"></span></span>

[<span data-ttu-id="5c4b5-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="5c4b5-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

