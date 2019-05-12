---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter CcUpdate cmdlet 准备通过将其放在维护模式下的更新过程的商务云连接器版主机服务器的 Skype。 装置 isdrained — 即，所有现有呼叫将完成，但新呼叫被拒绝。
ms.openlocfilehash: 42c8f7fa668fa94040276e7749e93b5832d511cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929429"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="f91bb-104">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="f91bb-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="f91bb-105">Enter CcUpdate cmdlet 准备通过将其放在维护模式下的更新过程的商务云连接器版主机服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="f91bb-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="f91bb-106">装置为"排空"— 即，所有现有呼叫将完成，但新呼叫被拒绝。</span><span class="sxs-lookup"><span data-stu-id="f91bb-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="f91bb-107">参数</span><span class="sxs-lookup"><span data-stu-id="f91bb-107">Parameters</span></span>

<span data-ttu-id="f91bb-108">无</span><span class="sxs-lookup"><span data-stu-id="f91bb-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f91bb-109">示例</span><span class="sxs-lookup"><span data-stu-id="f91bb-109">Examples</span></span>
<span data-ttu-id="f91bb-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f91bb-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="f91bb-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="f91bb-111">Example 1</span></span>

<span data-ttu-id="f91bb-112">以下示例通过进入维护模式来为更新过程准备设备：</span><span class="sxs-lookup"><span data-stu-id="f91bb-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="f91bb-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="f91bb-113">Detailed Description</span></span>
<span data-ttu-id="f91bb-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f91bb-114"></span></span>

<span data-ttu-id="f91bb-115">Enter CcUpdate cmdlet 将立即停止所有服务结束所有后续呼叫，则设备将拒绝任何新的呼叫，被转接到其他生产 appliance。</span><span class="sxs-lookup"><span data-stu-id="f91bb-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="f91bb-116">您必须确保剩余的生产 appliance 具有足够的容量来处理来自您准备要更新的设备呼叫。</span><span class="sxs-lookup"><span data-stu-id="f91bb-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="f91bb-p104">如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。</span><span class="sxs-lookup"><span data-stu-id="f91bb-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="f91bb-119">安装后将更新，设备可以将其重新为生产模式通过运行退出 CcUpdate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f91bb-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f91bb-120">如果决定手动更新云连接器 appliance，您需要在 Microsoft 发布了下一版本后 60 天内对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="f91bb-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="f91bb-121">Microsoft 支持发布的新版本后 60 天以前发布版云连接器</span><span class="sxs-lookup"><span data-stu-id="f91bb-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="f91bb-122">输入类型</span><span class="sxs-lookup"><span data-stu-id="f91bb-122">Input Types</span></span>
<span data-ttu-id="f91bb-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f91bb-123"></span></span>

<span data-ttu-id="f91bb-p106">无。Enter-CCUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="f91bb-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f91bb-126">返回类型</span><span class="sxs-lookup"><span data-stu-id="f91bb-126">Return Types</span></span>
<span data-ttu-id="f91bb-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f91bb-127"></span></span>

<span data-ttu-id="f91bb-128">无</span><span class="sxs-lookup"><span data-stu-id="f91bb-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f91bb-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f91bb-129">See also</span></span>
<span data-ttu-id="f91bb-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f91bb-130"></span></span>

[<span data-ttu-id="f91bb-131">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="f91bb-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

