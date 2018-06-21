---
title: 响应组工作流
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: 响应组组成代理组、 队列和工作流。 响应组工作流定义响应组应用程序接收电话呼叫时执行的操作。
ms.openlocfilehash: 6af4d40b75ae090cd3e99746ea111e3d804aed60
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19997022"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="b7610-104">响应组工作流</span><span class="sxs-lookup"><span data-stu-id="b7610-104">Response Groups Workflow</span></span>
 
<span data-ttu-id="b7610-105">响应组组成代理组、 队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="b7610-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="b7610-106">响应组工作流定义响应组应用程序接收电话呼叫时执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b7610-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span> 
  
<span data-ttu-id="b7610-107">**响应组** - **工作流**页显示一个为组织定义的所有响应组工作流的列表。</span><span class="sxs-lookup"><span data-stu-id="b7610-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="b7610-108">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="b7610-108">Tasks you can perform</span></span>

<span data-ttu-id="b7610-109">您可以在**响应组**执行以下任务 - **工作流**页：</span><span class="sxs-lookup"><span data-stu-id="b7610-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>
  
- <span data-ttu-id="b7610-110">创建或更改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="b7610-110">Create or change a hunt group workflow</span></span>
    
- <span data-ttu-id="b7610-111">创建或更改互动工作流</span><span class="sxs-lookup"><span data-stu-id="b7610-111">Create or change an interactive workflow</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="b7610-112">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="b7610-112">UI Reference</span></span>

<span data-ttu-id="b7610-113">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="b7610-113">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="b7610-114">**创建或编辑工作流**打开响应组配置工具创建或编辑工作流。</span><span class="sxs-lookup"><span data-stu-id="b7610-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>
    
- <span data-ttu-id="b7610-115">**刷新**刷新工作流的列表。</span><span class="sxs-lookup"><span data-stu-id="b7610-115">**Refresh** Refreshes the list of workflows.</span></span>
    
<span data-ttu-id="b7610-116">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="b7610-116">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="b7610-117">**名称**分配给工作流的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="b7610-117">**Name** The unique name that is assigned to the workflow.</span></span>
    
- <span data-ttu-id="b7610-118">**服务**承载工作流的**ApplicationServer**服务。</span><span class="sxs-lookup"><span data-stu-id="b7610-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>
    
- <span data-ttu-id="b7610-119">**SIP 地址**将应答工作流呼叫的组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="b7610-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>
    
- <span data-ttu-id="b7610-120">**电话**调用它以接通此响应组的电话号码。</span><span class="sxs-lookup"><span data-stu-id="b7610-120">**Telephone** The phone number that is called to reach this response group.</span></span>
    
- <span data-ttu-id="b7610-121">**语言**用于语音识别和文本到语音转换的语言。</span><span class="sxs-lookup"><span data-stu-id="b7610-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>
    
- <span data-ttu-id="b7610-122">**IVR**指示工作流是否寻线还是互动工作流。</span><span class="sxs-lookup"><span data-stu-id="b7610-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>
    
- <span data-ttu-id="b7610-123">**启用**指示是否激活工作流接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="b7610-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>
    
<span data-ttu-id="b7610-124">有关响应组特性和功能的详细信息，请参阅[规划响应组应用程序中的业务服务器 Skype](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b7610-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md).</span></span> <span data-ttu-id="b7610-125">有关使用响应组工作流的详细信息，请参阅操作文档中的[管理响应组工作流](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b7610-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>
  

