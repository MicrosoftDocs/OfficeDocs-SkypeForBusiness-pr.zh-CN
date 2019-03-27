---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Exit-CcUpdate cmdlet 用于在 Skype for Business 云连接器版本主机服务器上退出更新维护模式。
ms.openlocfilehash: 7ac36e9cbab8e479a4ec7b070b773b3585370e8f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926537"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="7d7ae-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="7d7ae-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="7d7ae-104">Exit-CcUpdate cmdlet 用于在 Skype for Business 云连接器版本主机服务器上退出更新维护模式。</span><span class="sxs-lookup"><span data-stu-id="7d7ae-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="7d7ae-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="7d7ae-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="7d7ae-106">参数</span><span class="sxs-lookup"><span data-stu-id="7d7ae-106">Parameters</span></span>

<span data-ttu-id="7d7ae-107">无</span><span class="sxs-lookup"><span data-stu-id="7d7ae-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7d7ae-108">示例</span><span class="sxs-lookup"><span data-stu-id="7d7ae-108">Examples</span></span>
<span data-ttu-id="7d7ae-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7d7ae-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="7d7ae-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="7d7ae-110">Example 1</span></span>

<span data-ttu-id="7d7ae-111">以下命令将运行它的设备恢复到生产模式：</span><span class="sxs-lookup"><span data-stu-id="7d7ae-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="7d7ae-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="7d7ae-112">Detailed Description</span></span>
<span data-ttu-id="7d7ae-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d7ae-113"></span></span>

<span data-ttu-id="7d7ae-114">如果有通过指定 Enter-CcUpdate cmdlet 被置于维护模式的设备，Exit-CcUpdate cmdlet 可将这些设备恢复到生产模式。</span><span class="sxs-lookup"><span data-stu-id="7d7ae-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="7d7ae-115">有关将设备置于维护模式的详细信息，请参阅 Enter-CcUpdate。</span><span class="sxs-lookup"><span data-stu-id="7d7ae-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="7d7ae-116">输入类型</span><span class="sxs-lookup"><span data-stu-id="7d7ae-116">Input Types</span></span>
<span data-ttu-id="7d7ae-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d7ae-117"></span></span>

<span data-ttu-id="7d7ae-p101">无。Exit-CcUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="7d7ae-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7d7ae-120">返回类型</span><span class="sxs-lookup"><span data-stu-id="7d7ae-120">Return Types</span></span>
<span data-ttu-id="7d7ae-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d7ae-121"></span></span>

<span data-ttu-id="7d7ae-122">无</span><span class="sxs-lookup"><span data-stu-id="7d7ae-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7d7ae-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d7ae-123">See also</span></span>
<span data-ttu-id="7d7ae-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d7ae-124"></span></span>

[<span data-ttu-id="7d7ae-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="7d7ae-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

