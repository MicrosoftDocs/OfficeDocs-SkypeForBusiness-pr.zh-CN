---
title: 响应组工作流
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: 响应组由代理组、队列和工作流组成。 响应组工作流定义响应组应用程序收到电话呼叫时采取的操作。
ms.openlocfilehash: dc34ec69af86658c6624ada6a9f25ff3aaa61499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118761"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="bab92-104">响应组工作流</span><span class="sxs-lookup"><span data-stu-id="bab92-104">Response Groups Workflow</span></span>

<span data-ttu-id="bab92-105">响应组由代理组、队列和工作流组成。</span><span class="sxs-lookup"><span data-stu-id="bab92-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="bab92-106">响应组工作流定义响应组应用程序收到电话呼叫时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="bab92-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="bab92-107">"**响应组**  -  **工作流**"页显示为组织定义的所有响应组工作流的列表。</span><span class="sxs-lookup"><span data-stu-id="bab92-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bab92-108">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="bab92-108">Tasks you can perform</span></span>

<span data-ttu-id="bab92-109">可以从"响应组工作流"页执行  -  **以下** 任务：</span><span class="sxs-lookup"><span data-stu-id="bab92-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="bab92-110">创建或更改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="bab92-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="bab92-111">创建或更改互动工作流</span><span class="sxs-lookup"><span data-stu-id="bab92-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bab92-112">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="bab92-112">UI Reference</span></span>

<span data-ttu-id="bab92-113">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="bab92-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="bab92-114">**创建或编辑工作流** 打开响应组配置工具以创建或编辑工作流。</span><span class="sxs-lookup"><span data-stu-id="bab92-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="bab92-115">**刷新** 刷新工作流列表。</span><span class="sxs-lookup"><span data-stu-id="bab92-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="bab92-116">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="bab92-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="bab92-117">**名称** 分配给工作流的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="bab92-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="bab92-118">**服务** 承载 **工作流的 ApplicationServer** 服务。</span><span class="sxs-lookup"><span data-stu-id="bab92-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="bab92-119">**SIP 地址** 应答工作流呼叫的组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="bab92-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="bab92-120">**电话** 为到达此响应组而呼叫的电话号码。</span><span class="sxs-lookup"><span data-stu-id="bab92-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="bab92-121">**语言** 用于语音识别和文本到语音之间的语言。</span><span class="sxs-lookup"><span data-stu-id="bab92-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="bab92-122">**IVR** 指示工作流是一个寻线还是互动工作流。</span><span class="sxs-lookup"><span data-stu-id="bab92-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="bab92-123">**已启用** 指示是否激活工作流以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="bab92-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="bab92-124">有关响应组特性和功能的详细信息，请参阅规划文档中的 Plan [for the Response Group application in Skype for Business Server。](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)</span><span class="sxs-lookup"><span data-stu-id="bab92-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="bab92-125">有关使用响应组工作流的详细信息，请参阅操作文档中的[Managing Response Group Workflows。](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows)</span><span class="sxs-lookup"><span data-stu-id="bab92-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) in the Operations documentation.</span></span>