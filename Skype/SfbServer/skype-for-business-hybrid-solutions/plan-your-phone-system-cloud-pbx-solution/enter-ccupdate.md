---
title: 输入 CcUpdate
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。 装置 isdrained — — 也就是说，完成将现有的所有调用，但新的呼叫都将被拒绝。
ms.openlocfilehash: ed9f3f614829cd5b6bc2cd5499c6889258d67531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enter-ccupdate"></a><span data-ttu-id="62599-104">输入 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="62599-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="62599-105">Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。</span><span class="sxs-lookup"><span data-stu-id="62599-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="62599-106">该装置"排放"— — 即完成将现有的所有调用，但会拒绝新的电话。</span><span class="sxs-lookup"><span data-stu-id="62599-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="62599-107">参数</span><span class="sxs-lookup"><span data-stu-id="62599-107">Parameters</span></span>

<span data-ttu-id="62599-108">无</span><span class="sxs-lookup"><span data-stu-id="62599-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="62599-109">示例</span><span class="sxs-lookup"><span data-stu-id="62599-109">Examples</span></span>
<span data-ttu-id="62599-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="62599-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="62599-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="62599-111">Example 1</span></span>

<span data-ttu-id="62599-112">以下示例通过进入维护模式来为更新过程准备设备：</span><span class="sxs-lookup"><span data-stu-id="62599-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="62599-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="62599-113">Detailed Description</span></span>
<span data-ttu-id="62599-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="62599-114"></span></span>

<span data-ttu-id="62599-115">输入 CcUpdate cmdlet 将确保云接头装置上所有正在运行的调用将完成，但设备将拒绝任何新呼叫，将转移到其它生产装置。</span><span class="sxs-lookup"><span data-stu-id="62599-115">The Enter-CcUpdate cmdlet will ensure that all running calls on a Cloud Connector appliance will complete, but the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="62599-116">使用此 cmdlet 可以在不影响最终用户呼叫的情况下更新设备。</span><span class="sxs-lookup"><span data-stu-id="62599-116">This cmdlet enables you to update an appliance without affecting end users calls.</span></span> <span data-ttu-id="62599-117">你必须确保其余生产设备具有足够的能力来处理来自你准备更新的设备的呼叫。</span><span class="sxs-lookup"><span data-stu-id="62599-117">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="62599-p104">如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。</span><span class="sxs-lookup"><span data-stu-id="62599-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="62599-120">安装了更新后，可以通过运行 Exit-CcUpdate cmdlet 将设备恢复到生产模式。</span><span class="sxs-lookup"><span data-stu-id="62599-120">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="62599-121">如果决定手动更新云接头装置，您需要在 Microsoft 发布的下一个版本后 60 天内对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="62599-121">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="62599-122">新版本发布后的 60 天内，Microsoft 支持云连接器的此前发布版本</span><span class="sxs-lookup"><span data-stu-id="62599-122">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="62599-123">输入类型</span><span class="sxs-lookup"><span data-stu-id="62599-123">Input Types</span></span>
<span data-ttu-id="62599-124"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62599-124"></span></span>

<span data-ttu-id="62599-p106">无。Enter-CCUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="62599-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="62599-127">返回类型</span><span class="sxs-lookup"><span data-stu-id="62599-127">Return Types</span></span>
<span data-ttu-id="62599-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62599-128"></span></span>

<span data-ttu-id="62599-129">无</span><span class="sxs-lookup"><span data-stu-id="62599-129">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="62599-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62599-130">See also</span></span>
<span data-ttu-id="62599-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="62599-131"></span></span>

[<span data-ttu-id="62599-132">退出-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="62599-132">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

