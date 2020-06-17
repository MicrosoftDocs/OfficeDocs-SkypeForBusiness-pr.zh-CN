---
title: 重置呼叫允许控制
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
description: 如果旧版前端池承载呼叫允许控制（CAC），则必须将 CAC 托管到 Skype for Business Server 2019 池，然后才能删除旧版前端池。
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753294"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="0d126-103">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="0d126-103">Reset call admission control</span></span>

<span data-ttu-id="0d126-104">如果旧版前端池承载呼叫允许控制（CAC），则必须将 CAC 托管到 Skype for Business Server 2019 池，然后才能删除旧版前端池。</span><span class="sxs-lookup"><span data-stu-id="0d126-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="0d126-105">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="0d126-105">To reset CAC</span></span>

1. <span data-ttu-id="0d126-106">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="0d126-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0d126-107">右键单击站点节点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d126-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0d126-108">在“呼叫允许控制设置”\*\*\*\* 下，确保选择“启用呼叫允许控制”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0d126-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="0d126-109">在 "**前端池" 下运行呼叫允许控制（CAC）**，选择要承载 CAC 的 Skype For business Server 2019 池，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="0d126-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="0d126-110">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="0d126-110">Publish the topology.</span></span>
    

