---
title: 重置呼叫允许控制
description: 重置呼叫允许控制。
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
ms.openlocfilehash: c4539cda453de6249be3a9b9b61521ecf478cb70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551238"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="24087-103">重置呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="24087-103">Reset call admission control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24087-104">_**上次修改的主题：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="24087-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="24087-105">如果 Lync Server 2010 前端池承载呼叫允许控制 (CAC) ，则必须将 CAC 托管到 Lync Server 2013 池，然后才能删除 Lync Server 2010 前端池。</span><span class="sxs-lookup"><span data-stu-id="24087-105">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="24087-106">重置 CAC</span><span class="sxs-lookup"><span data-stu-id="24087-106">To reset CAC</span></span>

1.  <span data-ttu-id="24087-107">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="24087-107">Open Topology Builder.</span></span>

2.  <span data-ttu-id="24087-108">右键单击站点节点，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="24087-108">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="24087-109">在“呼叫允许控制设置”\*\*\*\* 下，确保选择“启用呼叫允许控制”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="24087-109">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="24087-110">在 "前端池" 下， \*\*运行 "呼叫允许控制" (CAC) \*\*，选择要承载 CAC 的 Lync Server 2013 池，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="24087-110">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="24087-111">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="24087-111">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

