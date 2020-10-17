---
title: Lync Server 2013：管理响应组工作流
description: Lync Server 2013：管理响应组工作流。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group workflows
ms:assetid: 42cfccdd-2844-4875-b4e3-813e1df15f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520986(v=OCS.15)
ms:contentKeyID: 48183974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2223fed2b5b030a2c92e0b958ae8545a7717f848
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560408"
---
# <a name="managing-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="0ac96-103">在 Lync Server 2013 中管理响应组工作流</span><span class="sxs-lookup"><span data-stu-id="0ac96-103">Managing Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac96-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0ac96-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0ac96-105">响应组工作流定义从电话响铃到代理应答呼叫的时间的呼叫行为。</span><span class="sxs-lookup"><span data-stu-id="0ac96-105">A Response Group workflow defines the behavior of a call from the time that the phone rings to the time that an agent answers the call.</span></span> <span data-ttu-id="0ac96-106">工作流包括队列和路由信息，还包括智能寻线或互动语音响应 (IVR) 信息。</span><span class="sxs-lookup"><span data-stu-id="0ac96-106">The workflow includes queue and routing information, and includes either hunt group or interactive voice response (IVR) information.</span></span>

<span data-ttu-id="0ac96-107">本节中的主题确定了用于设计 IVR 工作流的最佳实践，并说明了如何创建自定义的工作时间和假日集、如何创建或修改工作流以及如何删除工作组。</span><span class="sxs-lookup"><span data-stu-id="0ac96-107">Topics in this section identify best practices for designing IVR workflows, and explain how to create customized business hours and holiday sets, how to create or modify workflows, and how to delete workgroups.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0ac96-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="0ac96-108">In This Section</span></span>

  - [<span data-ttu-id="0ac96-109">在 Lync Server 2013 中设计交互式语音响应呼叫流</span><span class="sxs-lookup"><span data-stu-id="0ac96-109">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="0ac96-110"> (可选) 在 Lync Server 2013 中定义响应组工作时间</span><span class="sxs-lookup"><span data-stu-id="0ac96-110">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="0ac96-111"> (可选) 在 Lync Server 2013 中定义响应组假日集</span><span class="sxs-lookup"><span data-stu-id="0ac96-111">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="0ac96-112">在 Lync Server 2013 中创建或修改工作流</span><span class="sxs-lookup"><span data-stu-id="0ac96-112">Create or modify a workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-workflow.md)

  - [<span data-ttu-id="0ac96-113">在 Lync Server 2013 中删除工作流</span><span class="sxs-lookup"><span data-stu-id="0ac96-113">Delete a workflow in Lync Server 2013</span></span>](lync-server-2013-delete-a-workflow.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

