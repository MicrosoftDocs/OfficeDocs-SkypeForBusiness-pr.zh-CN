---
title: 从池中删除前端服务器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 前端服务器不能作为独立计算机上存在。 它必须被定义为前端池，即使池中只有一台计算机。
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028941"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="1638c-104">从池中删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="1638c-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="1638c-105">前端服务器不能作为独立计算机上存在。</span><span class="sxs-lookup"><span data-stu-id="1638c-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="1638c-106">它必须被定义为前端池，即使池中只有一台计算机。</span><span class="sxs-lookup"><span data-stu-id="1638c-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="1638c-107">本主题将指导您完成从现有的前端池删除单个前端服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="1638c-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="1638c-108">如果在前端服务器池中的最后一个服务器或要完全删除该池，请参阅[删除前端池或 Standard Edition server](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1638c-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="1638c-109">没有无需删除单个前端服务器，之前先删除前端池。</span><span class="sxs-lookup"><span data-stu-id="1638c-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="1638c-110">删除池时，您将删除每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="1638c-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="1638c-111">若要从池中删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="1638c-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="1638c-112">在业务 Server 2019 前端服务器的 Skype，打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="1638c-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="1638c-113">导航到旧的安装节点。</span><span class="sxs-lookup"><span data-stu-id="1638c-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="1638c-114">展开**Enterprise Edition 前端池**，展开前端池与前端服务器所需若要删除，右键单击前端服务器要删除，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="1638c-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

