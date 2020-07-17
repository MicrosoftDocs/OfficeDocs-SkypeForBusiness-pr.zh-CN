---
title: 从池中删除前端服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 前端服务器不能作为独立计算机存在。 必须将其定义为前端池，即使池中只有一台计算机也是如此。
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752314"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="e5a70-104">从池中删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="e5a70-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="e5a70-105">前端服务器不能作为独立计算机存在。</span><span class="sxs-lookup"><span data-stu-id="e5a70-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="e5a70-106">必须将其定义为前端池，即使池中只有一台计算机也是如此。</span><span class="sxs-lookup"><span data-stu-id="e5a70-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="e5a70-107">本主题将指导您完成从现有前端池删除单个前端服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="e5a70-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="e5a70-108">如果前端服务器是池中的最后一台服务器，或者如果要完全删除池，请参阅[删除前端池或 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e5a70-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="e5a70-109">在删除前端池之前，无需删除单个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e5a70-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="e5a70-110">删除池时，会删除每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e5a70-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="e5a70-111">从池中删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="e5a70-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="e5a70-112">在 Skype for Business Server 2019 前端服务器上，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="e5a70-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="e5a70-113">导航到旧版安装节点。</span><span class="sxs-lookup"><span data-stu-id="e5a70-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="e5a70-114">展开 " **Enterprise Edition 前端池**"，再展开要删除的前端服务器的前端池，右键单击要删除的前端服务器，然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="e5a70-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

