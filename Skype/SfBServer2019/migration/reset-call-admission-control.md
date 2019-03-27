---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧的前端池承载呼叫允许控制 (CAC)，您必须移动 CAC 承载到业务服务器 2019年池 Skype，然后才能删除旧的前端池。
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895773"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="d2eff-103">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="d2eff-103">Reset call admission control</span></span>

<span data-ttu-id="d2eff-104">如果旧的前端池承载呼叫允许控制 (CAC)，您必须移动 CAC 承载到业务服务器 2019年池 Skype，然后才能删除旧的前端池。</span><span class="sxs-lookup"><span data-stu-id="d2eff-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="d2eff-105">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="d2eff-105">To reset CAC</span></span>

1. <span data-ttu-id="d2eff-106">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="d2eff-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d2eff-107">右键单击网站节点，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="d2eff-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="d2eff-108">在**呼叫允许控制设置**中，确保选择**Enable Call Admission Control** 。</span><span class="sxs-lookup"><span data-stu-id="d2eff-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="d2eff-109">**要运行呼叫允许控制 (CAC) 的前端池**下, 选择用于承载 CAC，业务服务器 2019年池 Skype，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d2eff-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d2eff-110">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="d2eff-110">Publish the topology.</span></span>
    

