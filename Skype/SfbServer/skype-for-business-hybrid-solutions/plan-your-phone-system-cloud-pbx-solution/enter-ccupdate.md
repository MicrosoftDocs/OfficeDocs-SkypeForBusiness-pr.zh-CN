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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: CcUpdate cmdlet 通过将其置于维护模式来为更新过程准备 Skype for business 云连接器 Edition 主机服务器。 本装置将立即停止所有服务、停止任何正在进行的呼叫，并拒绝任何新呼叫。
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802172"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="2474c-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="2474c-104">Enter-CcUpdate</span></span>

<span data-ttu-id="2474c-105">CcUpdate cmdlet 通过将其置于维护模式来为更新过程准备 Skype for business 云连接器 Edition 主机服务器。</span><span class="sxs-lookup"><span data-stu-id="2474c-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="2474c-106">本装置将立即停止所有服务、停止任何正在进行的呼叫，并拒绝任何新呼叫。</span><span class="sxs-lookup"><span data-stu-id="2474c-106">The appliance immediately stops all services, ending any ongoing calls and rejecting any new calls.</span></span>
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="2474c-107">参数</span><span class="sxs-lookup"><span data-stu-id="2474c-107">Parameters</span></span>

<span data-ttu-id="2474c-108">无</span><span class="sxs-lookup"><span data-stu-id="2474c-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2474c-109">示例</span><span class="sxs-lookup"><span data-stu-id="2474c-109">Examples</span></span>
<span data-ttu-id="2474c-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2474c-110"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2474c-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="2474c-111">Example 1</span></span>

<span data-ttu-id="2474c-112">以下示例通过进入维护模式来为更新过程准备设备：</span><span class="sxs-lookup"><span data-stu-id="2474c-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="2474c-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="2474c-113">Detailed Description</span></span>
<span data-ttu-id="2474c-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2474c-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2474c-115">CcUpdate cmdlet 将立即停止所有终止任何正在进行的通话的服务，并且装置将拒绝任何新呼叫，这些呼叫将被转移到其他生产装置。</span><span class="sxs-lookup"><span data-stu-id="2474c-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="2474c-116">你必须确保剩余的生产设备有足够的容量来处理你准备更新的装置的通话。</span><span class="sxs-lookup"><span data-stu-id="2474c-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="2474c-p104">如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。</span><span class="sxs-lookup"><span data-stu-id="2474c-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="2474c-119">安装更新后，设备可以通过运行 CcUpdate cmdlet 恢复到生产模式。</span><span class="sxs-lookup"><span data-stu-id="2474c-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2474c-120">如果你决定手动更新云连接器设备，则需要在 Microsoft 发布下一个版本后的60天内更新它。</span><span class="sxs-lookup"><span data-stu-id="2474c-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="2474c-121">发布新版本后，Microsoft 支持以前发布的适用于60天的云连接器版本</span><span class="sxs-lookup"><span data-stu-id="2474c-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="2474c-122">输入类型</span><span class="sxs-lookup"><span data-stu-id="2474c-122">Input Types</span></span>
<span data-ttu-id="2474c-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2474c-123"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2474c-p106">无。Enter-CCUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="2474c-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2474c-126">返回类型</span><span class="sxs-lookup"><span data-stu-id="2474c-126">Return Types</span></span>
<span data-ttu-id="2474c-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2474c-127"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2474c-128">无</span><span class="sxs-lookup"><span data-stu-id="2474c-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2474c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2474c-129">See also</span></span>
<span data-ttu-id="2474c-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2474c-130"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="2474c-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="2474c-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

