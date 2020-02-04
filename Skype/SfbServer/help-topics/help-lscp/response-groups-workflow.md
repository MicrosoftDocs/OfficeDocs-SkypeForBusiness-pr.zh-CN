---
title: 响应组工作流
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: 响应组由代理组、队列和工作流组成。 响应组工作流定义响应组应用程序接收电话呼叫时执行的操作。
ms.openlocfilehash: 2d32ed7ca2cc793603b0d426bc8b223075d086a4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699747"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="d8e1b-104">响应组工作流</span><span class="sxs-lookup"><span data-stu-id="d8e1b-104">Response Groups Workflow</span></span>

<span data-ttu-id="d8e1b-105">响应组由代理组、队列和工作流组成。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="d8e1b-106">响应组工作流定义响应组应用程序接收电话呼叫时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="d8e1b-107">"**响应组** - **工作流**" 页面显示为你的组织定义的所有响应组工作流的列表。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d8e1b-108">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="d8e1b-108">Tasks you can perform</span></span>

<span data-ttu-id="d8e1b-109">可以从 "**响应组** - **工作流**" 页面执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d8e1b-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="d8e1b-110">创建或更改查寻组工作流</span><span class="sxs-lookup"><span data-stu-id="d8e1b-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="d8e1b-111">创建或更改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="d8e1b-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d8e1b-112">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="d8e1b-112">UI Reference</span></span>

<span data-ttu-id="d8e1b-113">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="d8e1b-114">**创建或编辑工作流**打开 "响应组配置" 工具以创建或编辑工作流。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="d8e1b-115">**刷新**刷新工作流列表。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="d8e1b-116">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="d8e1b-117">**名称**分配给工作流的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="d8e1b-118">**服务**托管工作流的**ApplicationServer**服务。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="d8e1b-119">**SIP 地址**将应答工作流的通话的组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="d8e1b-120">**电话**呼叫到达此响应组的电话号码。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="d8e1b-121">**语言**用于语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="d8e1b-122">**IVR**指示工作流是查寻组还是交互式工作流。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="d8e1b-123">**已启用**指示是否已激活工作流以接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="d8e1b-124">有关响应组功能和功能的详细信息，请参阅规划文档中的[Skype For Business Server 2015 中的 "响应组" 应用计划](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="d8e1b-125">有关使用响应组工作流的详细信息，请参阅操作文档中的[管理响应组工作流](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d8e1b-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


