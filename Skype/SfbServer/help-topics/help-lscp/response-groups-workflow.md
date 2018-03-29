---
title: 响应组工作流
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: 响应组组成代理组、 队列和工作流。 响应组的工作流定义响应组应用程序接收电话呼叫时所执行的操作。
ms.openlocfilehash: d4fa4f946c8dd54d0abab6bea41cc632f780f747
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-workflow"></a><span data-ttu-id="3a92c-104">响应组工作流</span><span class="sxs-lookup"><span data-stu-id="3a92c-104">Response Groups Workflow</span></span>
 
<span data-ttu-id="3a92c-105">响应组组成代理组、 队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="3a92c-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="3a92c-106">响应组的工作流定义响应组应用程序接收电话呼叫时所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3a92c-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span> 
  
<span data-ttu-id="3a92c-107">**响应组** - **工作流**页面显示为您的组织定义的所有响应组工作流的列表。</span><span class="sxs-lookup"><span data-stu-id="3a92c-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="3a92c-108">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="3a92c-108">Tasks you can perform</span></span>

<span data-ttu-id="3a92c-109">您可以从**响应组**中执行下列任务 - **工作流**页面：</span><span class="sxs-lookup"><span data-stu-id="3a92c-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>
  
- <span data-ttu-id="3a92c-110">创建或更改的查寻组工作流</span><span class="sxs-lookup"><span data-stu-id="3a92c-110">Create or change a hunt group workflow</span></span>
    
- <span data-ttu-id="3a92c-111">创建或更改交互式的工作流</span><span class="sxs-lookup"><span data-stu-id="3a92c-111">Create or change an interactive workflow</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="3a92c-112">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="3a92c-112">UI Reference</span></span>

<span data-ttu-id="3a92c-113">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="3a92c-113">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="3a92c-114">**创建或编辑工作流**打开响应组配置工具创建或编辑工作流。</span><span class="sxs-lookup"><span data-stu-id="3a92c-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>
    
- <span data-ttu-id="3a92c-115">**刷新**刷新工作流的列表。</span><span class="sxs-lookup"><span data-stu-id="3a92c-115">**Refresh** Refreshes the list of workflows.</span></span>
    
<span data-ttu-id="3a92c-116">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="3a92c-116">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="3a92c-117">**名称**向工作流分配唯一名称。</span><span class="sxs-lookup"><span data-stu-id="3a92c-117">**Name** The unique name that is assigned to the workflow.</span></span>
    
- <span data-ttu-id="3a92c-118">**服务**承载工作流**应用程序服务器**服务。</span><span class="sxs-lookup"><span data-stu-id="3a92c-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>
    
- <span data-ttu-id="3a92c-119">**SIP 地址**将应答呼叫到工作流组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="3a92c-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>
    
- <span data-ttu-id="3a92c-120">**电话**调用以到达此响应组电话号码。</span><span class="sxs-lookup"><span data-stu-id="3a92c-120">**Telephone** The phone number that is called to reach this response group.</span></span>
    
- <span data-ttu-id="3a92c-121">**语言**使用语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="3a92c-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>
    
- <span data-ttu-id="3a92c-122">**IVR**指示工作流是否查寻组或交互式的工作流。</span><span class="sxs-lookup"><span data-stu-id="3a92c-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>
    
- <span data-ttu-id="3a92c-123">**启用**指示是否启用工作流来接听电话。</span><span class="sxs-lookup"><span data-stu-id="3a92c-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>
    
<span data-ttu-id="3a92c-124">有关响应组的特性和功能的详细信息，请参阅规划文档中[规划业务服务器 2015年的 Skype 的响应组应用程序](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="3a92c-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="3a92c-125">有关使用工作流响应组的详细信息，请参阅[管理响应组工作流](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx)操作文档中。</span><span class="sxs-lookup"><span data-stu-id="3a92c-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>
  

