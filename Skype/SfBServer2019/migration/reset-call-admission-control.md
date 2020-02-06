---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果旧版前端池是托管呼叫许可控制（CAC），则必须先将 CAC 托管版迁移到 Skype for business Server 2019 池，然后才能删除旧的前端池。
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812800"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="f0bd0-103">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="f0bd0-103">Reset call admission control</span></span>

<span data-ttu-id="f0bd0-104">如果旧版前端池是托管呼叫许可控制（CAC），则必须先将 CAC 托管版迁移到 Skype for business Server 2019 池，然后才能删除旧的前端池。</span><span class="sxs-lookup"><span data-stu-id="f0bd0-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="f0bd0-105">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="f0bd0-105">To reset CAC</span></span>

1. <span data-ttu-id="f0bd0-106">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f0bd0-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="f0bd0-107">右键单击 "网站" 节点，然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="f0bd0-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="f0bd0-108">在 "**呼叫许可控制" 设置**下，请确保已选中 "**启用呼叫许可控制**"。</span><span class="sxs-lookup"><span data-stu-id="f0bd0-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="f0bd0-109">在 "**前端池" 下运行呼叫许可控制（CAC）**，选择要托管 CAC 的 Skype For business Server 2019 池，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="f0bd0-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="f0bd0-110">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="f0bd0-110">Publish the topology.</span></span>
    

