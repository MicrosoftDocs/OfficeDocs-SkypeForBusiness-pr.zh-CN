---
title: 从池中删除前端服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 前端服务器不能作为独立计算机存在。 它必须定义为前端池, 即使池中只有一台计算机。
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244293"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="33913-104">从池中删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="33913-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="33913-105">前端服务器不能作为独立计算机存在。</span><span class="sxs-lookup"><span data-stu-id="33913-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="33913-106">它必须定义为前端池, 即使池中只有一台计算机。</span><span class="sxs-lookup"><span data-stu-id="33913-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="33913-107">本主题将指导你完成从现有前端池删除单个前端服务器的过程。</span><span class="sxs-lookup"><span data-stu-id="33913-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="33913-108">如果前端服务器是池中的最后一个服务器, 或者如果你完全删除该池, 请参阅[删除前端池或标准版服务器](remove-front-end-pool-or-standard-edition-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33913-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="33913-109">删除前端池之前无需删除单个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="33913-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="33913-110">删除池时, 删除每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="33913-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="33913-111">从池中删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="33913-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="33913-112">在 Skype for Business 服务器2019前端服务器上, 打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="33913-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="33913-113">导航到 "旧版安装" 节点。</span><span class="sxs-lookup"><span data-stu-id="33913-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="33913-114">展开 "**企业版前端池**", 展开要删除的前端服务器的前端池, 右键单击要删除的前端服务器, 然后单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="33913-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

