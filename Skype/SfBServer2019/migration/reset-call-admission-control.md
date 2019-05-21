---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧版前端池是托管呼叫许可控制 (CAC), 则必须先将 CAC 托管版迁移到 Skype for business Server 2019 池, 然后才能删除旧的前端池。
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307096"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="8b4fe-103">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="8b4fe-103">Reset call admission control</span></span>

<span data-ttu-id="8b4fe-104">如果旧版前端池是托管呼叫许可控制 (CAC), 则必须先将 CAC 托管版迁移到 Skype for business Server 2019 池, 然后才能删除旧的前端池。</span><span class="sxs-lookup"><span data-stu-id="8b4fe-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="8b4fe-105">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="8b4fe-105">To reset CAC</span></span>

1. <span data-ttu-id="8b4fe-106">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="8b4fe-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="8b4fe-107">右键单击 "网站" 节点, 然后单击 "**编辑属性**"。</span><span class="sxs-lookup"><span data-stu-id="8b4fe-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="8b4fe-108">在 "**呼叫许可控制" 设置**下, 请确保已选中 "**启用呼叫许可控制**"。</span><span class="sxs-lookup"><span data-stu-id="8b4fe-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="8b4fe-109">在 "**前端池" 下运行呼叫许可控制 (CAC)**, 选择要托管 CAC 的 Skype For business Server 2019 池, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="8b4fe-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8b4fe-110">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="8b4fe-110">Publish the topology.</span></span>
    

