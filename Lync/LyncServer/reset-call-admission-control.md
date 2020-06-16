---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccd809e8c0670535723692fd35e05fd4230ddc67
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="a5200-102">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="a5200-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5200-103">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="a5200-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="a5200-104">如果 Lync Server 2010 前端池承载呼叫允许控制（CAC），则必须先将 CAC 托管到 Lync Server 2013 池，然后才能删除 Lync Server 2010 前端池。</span><span class="sxs-lookup"><span data-stu-id="a5200-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="a5200-105">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="a5200-105">To reset CAC</span></span>

1.  <span data-ttu-id="a5200-106">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="a5200-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="a5200-107">右键单击站点节点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a5200-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="a5200-108">在“呼叫允许控制设置”\*\*\*\* 下，确保选择“启用呼叫允许控制”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a5200-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="a5200-109">在 "**前端池" 下运行呼叫允许控制（CAC）**，选择要承载 CAC 的 Lync Server 2013 池，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a5200-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="a5200-110">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="a5200-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

