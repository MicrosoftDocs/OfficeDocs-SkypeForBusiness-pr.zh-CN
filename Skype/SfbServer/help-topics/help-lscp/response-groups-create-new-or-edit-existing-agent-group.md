---
title: 创建新的响应组或编辑现有代理组
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsGroupEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79eaaf6c-6928-4925-8220-c7ada6b37205
description: 代理组定义可应答针对响应组（称为代理）的呼叫的人员以及应用于组中所有代理的设置。
ms.openlocfilehash: 4ae2869e335bc8d7d8b774f7daf7f5915dcba462
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-create-new-or-edit-existing-agent-group"></a><span data-ttu-id="b2413-103">响应组：创建新的或编辑现有的代理组</span><span class="sxs-lookup"><span data-stu-id="b2413-103">Response Groups: Create New or Edit Existing Agent Group</span></span>
 
<span data-ttu-id="b2413-104">代理组定义可应答针对响应组（称为代理）的呼叫的人员以及应用于组中所有代理的设置。</span><span class="sxs-lookup"><span data-stu-id="b2413-104">Agent groups define who can answer calls to a response group (known as agents) and the settings that apply to all the agents in the group.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="b2413-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="b2413-105">UI Reference</span></span>

<span data-ttu-id="b2413-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="b2413-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="b2413-107">**名称**每个代理组需要唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="b2413-107">**Name** Each agent group requires a unique name.</span></span> <span data-ttu-id="b2413-108">请使用描述性名称标识的组中的功能。</span><span class="sxs-lookup"><span data-stu-id="b2413-108">Use a descriptive name that identifies the group's function.</span></span> <span data-ttu-id="b2413-109">例如，帮助台。</span><span class="sxs-lookup"><span data-stu-id="b2413-109">For example, Help Desk.</span></span>
    
- <span data-ttu-id="b2413-110">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="b2413-110">**Description** This field is optional.</span></span> <span data-ttu-id="b2413-111">使用它来提供其他有关组的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2413-111">Use it to provide additional details about the group.</span></span>
    
- <span data-ttu-id="b2413-112">**参与策略**指定代理是登录到响应组中的方法：</span><span class="sxs-lookup"><span data-stu-id="b2413-112">**Participation policy** Specify the way that agents are to sign into the response group:</span></span>
    
  - <span data-ttu-id="b2413-p103">选择“**非正式**”指定组中的代理无需登录和注销。非正式代理登录后，将自动登录。默认设置为“**非正式**”。</span><span class="sxs-lookup"><span data-stu-id="b2413-p103">Select **Informal** to specify that the agents in the group do not need to sign in and out. Informal agents are automatically signed in when they sign in. The default is **Informal**.</span></span>
    
  - <span data-ttu-id="b2413-115">选择**正式**指定的组中的代理程序必须签署入和签出。当选中此选项时，代理将单击菜单项在客户端打开浏览器并显示网页控制台用于签名和签出。</span><span class="sxs-lookup"><span data-stu-id="b2413-115">Select **Formal** to specify that the agents in the group must sign in and out. When you select this option, agents click a menu item in the client to open a browser and display a web page console for signing in and out.</span></span>
    
- <span data-ttu-id="b2413-116">**警报的时间 （秒）**指定要提供给下一个可用代理调用之前响铃代理的秒数。</span><span class="sxs-lookup"><span data-stu-id="b2413-116">**Alert time (seconds)** Specify the number of seconds to ring an agent before offering the call to the next available agent.</span></span> <span data-ttu-id="b2413-117">值必须至少为 10 秒钟、 有不少于 180 秒的时间。</span><span class="sxs-lookup"><span data-stu-id="b2413-117">The value must be at least 10 seconds and less than 180 seconds.</span></span> <span data-ttu-id="b2413-118">默认值为 20 秒。</span><span class="sxs-lookup"><span data-stu-id="b2413-118">The default is 20 seconds.</span></span>
    
- <span data-ttu-id="b2413-119">**路由方法**选择用于确定代理接收的调用顺序的方法：</span><span class="sxs-lookup"><span data-stu-id="b2413-119">**Routing method** Select the method for determining the order in which agents receive calls:</span></span>
    
  - <span data-ttu-id="b2413-120">选择“**最长空闲时间**”可将新呼叫优先路由至空闲（处于“**空闲**”或“**非活动**”的状态）时间最长的代理。</span><span class="sxs-lookup"><span data-stu-id="b2413-120">Select **Longest idle** to offer a new call first to the agent who has been idle (has had a presence of **Available** or **Inactive**) the longest.</span></span>
    
  - <span data-ttu-id="b2413-p105">选择“**并行**”可将新呼叫同时路由至所有空闲的代理。呼叫将发往第一个接受该呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="b2413-p105">Select **Parallel** to offer a new call to all available agents at the same time. The call is sent to the first agent who accepts it.</span></span>
    
  - <span data-ttu-id="b2413-123">选择“**循环**”可将新呼叫轮流路由至每个代理。</span><span class="sxs-lookup"><span data-stu-id="b2413-123">Select **Round robin** to offer a new call to each agent in turn.</span></span>
    
  - <span data-ttu-id="b2413-124">选择“**串行**”将新呼叫始终按照“**代理**”列表中代理的排列顺序路由至代理。</span><span class="sxs-lookup"><span data-stu-id="b2413-124">Select **Serial** to always offer a new call to agents in the order in which they are listed in the **Agent** list.</span></span>
    
  - <span data-ttu-id="b2413-125">选择**助理**提供新调用签名中的所有代理和响应组应用程序在同一时间，而不考虑其当前的状态。</span><span class="sxs-lookup"><span data-stu-id="b2413-125">Select **Attendant** to offer a new call to all agents who are signed in and the Response Group application at the same time, regardless of their current presence.</span></span> <span data-ttu-id="b2413-126">助理和代理可以看到所有呼叫等待并可以回答任何顺序等待调用配置的客户端用户。</span><span class="sxs-lookup"><span data-stu-id="b2413-126">Attendants and client users who are configured as agents can see all the calls that are waiting and can answer waiting calls in any order.</span></span> <span data-ttu-id="b2413-127">呼叫将发往第一个接受该呼叫的代理，其他助理和用户不会再看到此呼叫。</span><span class="sxs-lookup"><span data-stu-id="b2413-127">The call is sent to the first agent who accepts it, and the other attendants and users no longer see the call.</span></span>
    
- <span data-ttu-id="b2413-128">**代理**选择下列方式之一将响应组中的代理的用户：</span><span class="sxs-lookup"><span data-stu-id="b2413-128">**Agents** Select the users who are to be agents for the response group in one of the following ways:</span></span>
    
  - <span data-ttu-id="b2413-129">选择**使用现有的电子邮件通讯组列表**可使用 Exchange 通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b2413-129">Select **Use an existing email distribution list** to use an Exchange distribution list.</span></span> <span data-ttu-id="b2413-130">在“**通讯组列表地址**”中键入该通讯组列表的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b2413-130">Type the email address of the distribution list in **Distribution list address**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b2413-p108">只能为每个代理组选择一个通讯组列表。如果通讯组列表包括嵌套的通讯组列表，则该嵌套的通讯组列表将不会被包括在代理组中。</span><span class="sxs-lookup"><span data-stu-id="b2413-p108">You can select only one distribution list for an agent group. If the distribution list includes nested distribution lists, the nested distribution lists are not included in the agent group.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="b2413-133">通讯组列表中代理排列的顺序将影响代理接收呼叫以进行循环和串行路由的顺序。</span><span class="sxs-lookup"><span data-stu-id="b2413-133">The order in which agents are listed in the distribution list affects the order in which agents receive calls for round robin and serial routing.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="b2413-134">隐藏成员身份或隐藏的列表可能会变得可见于响应组管理员或用户。</span><span class="sxs-lookup"><span data-stu-id="b2413-134">Hidden memberships or hidden lists might become visible to Response Group administrators or users.</span></span> <span data-ttu-id="b2413-135">有关详细信息，请参阅[创建或修改业务 2015年的 Skype 在代理组](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b2413-135">For details, see [Create or modify an agent group in Skype for Business 2015](../../deploy/deploy-enterprise-voice/create-or-modify-an-agent-group.md).</span></span> 
  
  - <span data-ttu-id="b2413-p110">选择“**定义自定义代理组**”可选择您要分配为响应组代理的用户。单击“**选择**”可将代理添加到列表中。单击“**删除**”可从列表中删除所选代理。</span><span class="sxs-lookup"><span data-stu-id="b2413-p110">Select **Define a custom group of agents** to select the users you want to assign as agents for the response group. Click **Select** to add an agent to the list. Click **Remove** to delete a selected agent from the list.</span></span>
    
    <span data-ttu-id="b2413-p111">向上和向下箭头可在代理列表中向上和向下移动所选代理。列表中代理的排列顺序将影响代理接收呼叫以进行循环和串行路由的顺序。</span><span class="sxs-lookup"><span data-stu-id="b2413-p111">The up and down arrows move a selected agent up and down in the agent list. The order of agents in the list affects the order in which agents receive calls for round robin and serial routing.</span></span>
    
<span data-ttu-id="b2413-141">有关响应组的特性和功能的详细信息，请参阅规划文档中[规划业务服务器 2015年的 Skype 的响应组应用程序](../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="b2413-141">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="b2413-142">有关使用代理组的详细信息，请参阅在运营文档资料的[管理代理组](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b2413-142">For details about working with agent groups, see [Managing Agent Groups](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>
  

