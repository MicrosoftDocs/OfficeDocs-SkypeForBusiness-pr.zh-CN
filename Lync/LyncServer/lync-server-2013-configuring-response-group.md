---
title: Lync Server 2013：配置响应组
description: Lync Server 2013：配置响应组。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547928"
---
# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="d4fe2-103">在 Lync Server 2013 中配置响应组</span><span class="sxs-lookup"><span data-stu-id="d4fe2-103">Configuring Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4fe2-104">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="d4fe2-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="d4fe2-105">响应组是一个企业语音功能，可将传入呼叫路由并排队给一组人员（称为 *代理*，如技术支持或客户服务桌面）。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-105">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="d4fe2-106">响应组所需的组件将在部署企业语音时在前端服务器或 Standard Edition Server 中自动安装并启用。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-106">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d4fe2-107">要使响应组对用户可用，必须依次配置代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-107">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="d4fe2-108">此外，响应组管理员还可以将现有工作流的配置委派给响应组管理器，然后可以修改和重新配置工作流及其关联的代理组和队列。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-108">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="d4fe2-109">本部分将指导您完成 Lync Server 2013 响应组的配置。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-109">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="d4fe2-110">它假定您已阅读与响应组相关的规划部分，并已部署企业版服务器或具有企业语音的 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-110">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d4fe2-111">有关使用 Lync Server 命令行管理程序创建响应组的详细信息，包括示例脚本，请参阅中的 "使用 Lync Server 命令行管理程序创建您的第一个响应组" <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> 。</span><span class="sxs-lookup"><span data-stu-id="d4fe2-111">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4fe2-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="d4fe2-112">In This Section</span></span>

  - [<span data-ttu-id="d4fe2-113">Lync Server 2013 中的响应组配置权限和先决条件</span><span class="sxs-lookup"><span data-stu-id="d4fe2-113">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="d4fe2-114">Lync Server 2013 中响应组的部署过程</span><span class="sxs-lookup"><span data-stu-id="d4fe2-114">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="d4fe2-115">Lync Server 2013 中的工作流创建方案概述</span><span class="sxs-lookup"><span data-stu-id="d4fe2-115">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="d4fe2-116">创建响应组代理组 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4fe2-116">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="d4fe2-117">在 Lync Server 2013 中创建响应组队列</span><span class="sxs-lookup"><span data-stu-id="d4fe2-117">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="d4fe2-118"> (可选) 在 Lync Server 2013 中定义响应组工作时间</span><span class="sxs-lookup"><span data-stu-id="d4fe2-118">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="d4fe2-119"> (可选) 在 Lync Server 2013 中定义响应组假日集</span><span class="sxs-lookup"><span data-stu-id="d4fe2-119">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="d4fe2-120">在 Lync Server 2013 中创建响应组工作流</span><span class="sxs-lookup"><span data-stu-id="d4fe2-120">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="d4fe2-121"> (可选) 在 Lync Server 2013 中验证响应组部署</span><span class="sxs-lookup"><span data-stu-id="d4fe2-121">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4fe2-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4fe2-122">See Also</span></span>


[<span data-ttu-id="d4fe2-123">在 Lync Server 2013 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="d4fe2-123">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

