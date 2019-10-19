---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: CcUpdate cmdlet 通过将其置于维护模式来为更新过程准备 Skype for business 云连接器 Edition 主机服务器。 本装置将立即停止所有服务、停止任何正在进行的呼叫，并拒绝任何新呼叫。
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "34740056"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="13c20-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="13c20-104">Enter-CcUpdate</span></span>

<span data-ttu-id="13c20-105">CcUpdate cmdlet 通过将其置于维护模式来为更新过程准备 Skype for business 云连接器 Edition 主机服务器。</span><span class="sxs-lookup"><span data-stu-id="13c20-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="13c20-106">本装置将立即停止所有服务、停止任何正在进行的呼叫，并拒绝任何新呼叫。</span><span class="sxs-lookup"><span data-stu-id="13c20-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="13c20-107">参数</span><span class="sxs-lookup"><span data-stu-id="13c20-107">Parameters</span></span>

<span data-ttu-id="13c20-108">无</span><span class="sxs-lookup"><span data-stu-id="13c20-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="13c20-109">示例</span><span class="sxs-lookup"><span data-stu-id="13c20-109">Examples</span></span>
<span data-ttu-id="13c20-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="13c20-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="13c20-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="13c20-111">Example 1</span></span>

<span data-ttu-id="13c20-112">以下示例通过进入维护模式来为更新过程准备设备：</span><span class="sxs-lookup"><span data-stu-id="13c20-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="13c20-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="13c20-113">Detailed Description</span></span>
<span data-ttu-id="13c20-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="13c20-114"></span></span>

<span data-ttu-id="13c20-115">CcUpdate cmdlet 将立即停止所有终止任何正在进行的通话的服务，并且装置将拒绝任何新呼叫，这些呼叫将被转移到其他生产装置。</span><span class="sxs-lookup"><span data-stu-id="13c20-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="13c20-116">你必须确保剩余的生产设备有足够的容量来处理你准备更新的装置的通话。</span><span class="sxs-lookup"><span data-stu-id="13c20-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="13c20-p104">如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。</span><span class="sxs-lookup"><span data-stu-id="13c20-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="13c20-119">安装更新后，设备可以通过运行 CcUpdate cmdlet 恢复到生产模式。</span><span class="sxs-lookup"><span data-stu-id="13c20-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13c20-120">如果你决定手动更新云连接器设备，则需要在 Microsoft 发布下一个版本后的60天内更新它。</span><span class="sxs-lookup"><span data-stu-id="13c20-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="13c20-121">发布新版本后，Microsoft 支持以前发布的适用于60天的云连接器版本</span><span class="sxs-lookup"><span data-stu-id="13c20-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="13c20-122">输入类型</span><span class="sxs-lookup"><span data-stu-id="13c20-122">Input Types</span></span>
<span data-ttu-id="13c20-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="13c20-123"></span></span>

<span data-ttu-id="13c20-p106">无。Enter-CCUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="13c20-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="13c20-126">返回类型</span><span class="sxs-lookup"><span data-stu-id="13c20-126">Return Types</span></span>
<span data-ttu-id="13c20-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="13c20-127"></span></span>

<span data-ttu-id="13c20-128">无</span><span class="sxs-lookup"><span data-stu-id="13c20-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="13c20-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13c20-129">See also</span></span>
<span data-ttu-id="13c20-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="13c20-130"></span></span>

[<span data-ttu-id="13c20-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="13c20-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

