---
title: Lync Server 2013：创建响应组工作流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f927d5257c3e4217c8f16f3e5138d075d91b858c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="aa1b4-102">在 Lync Server 2013 中创建响应组工作流</span><span class="sxs-lookup"><span data-stu-id="aa1b4-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa1b4-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="aa1b4-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="aa1b4-p101">工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。工作流指定用于保留呼叫的队列，并指定用于智能寻线的路由方法或用于互动响应组的问题和答案。工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="aa1b4-107">您可以使用响应组配置工具来创建工作流。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="aa1b4-108">您可以从 Lync Server 控制面板的 "响应组" 页访问响应组配置工具。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa1b4-109">必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa1b4-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="aa1b4-110">In This Section</span></span>

  - [<span data-ttu-id="aa1b4-111">在 Lync Server 2013 中创建或修改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="aa1b4-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="aa1b4-112">在 Lync Server 2013 中设计交互式语音响应呼叫流</span><span class="sxs-lookup"><span data-stu-id="aa1b4-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="aa1b4-113">在 Lync Server 2013 中创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="aa1b4-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="aa1b4-114">相关部分</span><span class="sxs-lookup"><span data-stu-id="aa1b4-114">Related Sections</span></span>

  - [<span data-ttu-id="aa1b4-115">创建响应组代理组 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa1b4-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="aa1b4-116">在 Lync Server 2013 中创建响应组队列</span><span class="sxs-lookup"><span data-stu-id="aa1b4-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

