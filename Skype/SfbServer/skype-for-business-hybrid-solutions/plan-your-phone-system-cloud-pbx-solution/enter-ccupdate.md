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
description: Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。 装置 isdrained — 即，所有现有呼叫将完成，但新呼叫被拒绝。
ms.openlocfilehash: f9b789bbd76bd3405617dc170af0695f9cbe94ed
ms.sourcegitcommit: baa4ecf69bdcf499b5b724246f3e9f45c6ca3b7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2018
ms.locfileid: "25450509"
---
# <a name="enter-ccupdate"></a><span data-ttu-id="ec745-104">输入 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="ec745-104">Enter-CcUpdate</span></span>
 
<span data-ttu-id="ec745-105">Enter-CcUpdate cmdlet 通过将 Skype for Business 云连接器版本主机服务器置于维护模式来为更新过程做准备。</span><span class="sxs-lookup"><span data-stu-id="ec745-105">The Enter-CcUpdate cmdlet prepares the Skype for Business Cloud Connector Edition host server for the update process by putting it in maintenance mode.</span></span> <span data-ttu-id="ec745-106">装置为"排空"— 即，所有现有呼叫将完成，但新呼叫被拒绝。</span><span class="sxs-lookup"><span data-stu-id="ec745-106">The appliance is "drained"—that is, all existing calls will complete, but new calls are rejected.</span></span> 
  
```
Enter-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="ec745-107">参数</span><span class="sxs-lookup"><span data-stu-id="ec745-107">Parameters</span></span>

<span data-ttu-id="ec745-108">无</span><span class="sxs-lookup"><span data-stu-id="ec745-108">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="ec745-109">示例</span><span class="sxs-lookup"><span data-stu-id="ec745-109">Examples</span></span>
<span data-ttu-id="ec745-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ec745-110"></span></span>

### <a name="example-1"></a><span data-ttu-id="ec745-111">示例 1</span><span class="sxs-lookup"><span data-stu-id="ec745-111">Example 1</span></span>

<span data-ttu-id="ec745-112">以下示例通过进入维护模式来为更新过程准备设备：</span><span class="sxs-lookup"><span data-stu-id="ec745-112">The following example prepares the appliance for the update process by entering maintenance mode:</span></span>
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="ec745-113">详细说明</span><span class="sxs-lookup"><span data-stu-id="ec745-113">Detailed Description</span></span>
<span data-ttu-id="ec745-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ec745-114"></span></span>

<span data-ttu-id="ec745-115">Enter CcUpdate cmdlet 将立即停止所有服务结束所有后续呼叫，则设备将拒绝任何新的呼叫，被转接到其他生产 appliance。</span><span class="sxs-lookup"><span data-stu-id="ec745-115">The Enter-CcUpdate cmdlet will immediately stop all services ending any ongoing calls and the appliance will reject any new calls, which are transferred to other production appliances.</span></span> <span data-ttu-id="ec745-116">你必须确保其余生产设备具有足够的能力来处理来自你准备更新的设备的呼叫。</span><span class="sxs-lookup"><span data-stu-id="ec745-116">You must ensure that the remaining production appliances have enough capacity to handle the calls from the appliance that you are preparing to update.</span></span>
  
<span data-ttu-id="ec745-p104">如果你的设备启用了自动更新，例如，Microsoft 发布了关键修补程序，维护模式将很有用。如果你决定关闭自动更新，但会定期执行手动更新，维护模式也很有用。</span><span class="sxs-lookup"><span data-stu-id="ec745-p104">Maintenance mode is useful if your appliance has automatic update enabled, for example, and Microsoft releases a critical hotfix. Maintenance mode is also useful if you decide to turn off automatic updates, but you perform manual updates on a consistent basis.</span></span>
  
<span data-ttu-id="ec745-119">安装了更新后，可以通过运行 Exit-CcUpdate cmdlet 将设备恢复到生产模式。</span><span class="sxs-lookup"><span data-stu-id="ec745-119">After installing the updates, the appliance can be brought back to production mode by running the Exit-CcUpdate cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec745-120">如果决定手动更新云连接器 appliance，您需要在 Microsoft 发布了下一版本后 60 天内对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="ec745-120">If you decide to manually update a Cloud Connector appliance, you need to update it within 60 days after Microsoft releases the next version.</span></span> <span data-ttu-id="ec745-121">Microsoft 支持发布的新版本后 60 天以前发布版云连接器</span><span class="sxs-lookup"><span data-stu-id="ec745-121">Microsoft supports the previously-released version of Cloud Connector for 60 days after the new version is released</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="ec745-122">输入类型</span><span class="sxs-lookup"><span data-stu-id="ec745-122">Input Types</span></span>
<span data-ttu-id="ec745-123"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec745-123"></span></span>

<span data-ttu-id="ec745-p106">无。Enter-CCUpdate cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="ec745-p106">None. The Enter-CCUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ec745-126">返回类型</span><span class="sxs-lookup"><span data-stu-id="ec745-126">Return Types</span></span>
<span data-ttu-id="ec745-127"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec745-127"></span></span>

<span data-ttu-id="ec745-128">无</span><span class="sxs-lookup"><span data-stu-id="ec745-128">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ec745-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec745-129">See also</span></span>
<span data-ttu-id="ec745-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ec745-130"></span></span>

[<span data-ttu-id="ec745-131">退出 CcUpdate</span><span class="sxs-lookup"><span data-stu-id="ec745-131">Exit-CcUpdate</span></span>](exit-ccupdate.md)
  

