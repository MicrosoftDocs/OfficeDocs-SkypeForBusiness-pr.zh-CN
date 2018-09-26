---
title: 重置呼叫允许控制
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧的前端池承载呼叫允许控制 (CAC)，您必须移动 CAC 承载到业务服务器 2019年池 Skype，然后才能删除旧的前端池。
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027317"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="0d34d-103">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="0d34d-103">Reset call admission control</span></span>

<span data-ttu-id="0d34d-104">如果旧的前端池承载呼叫允许控制 (CAC)，您必须移动 CAC 承载到业务服务器 2019年池 Skype，然后才能删除旧的前端池。</span><span class="sxs-lookup"><span data-stu-id="0d34d-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="0d34d-105">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="0d34d-105">To reset CAC</span></span>

1. <span data-ttu-id="0d34d-106">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="0d34d-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0d34d-107">右键单击网站节点，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="0d34d-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="0d34d-108">在**呼叫允许控制设置**中，确保选择**Enable Call Admission Control** 。</span><span class="sxs-lookup"><span data-stu-id="0d34d-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="0d34d-109">**要运行呼叫允许控制 (CAC) 的前端池**下, 选择用于承载 CAC，业务服务器 2019年池 Skype，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0d34d-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="0d34d-110">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="0d34d-110">Publish the topology.</span></span>
    

