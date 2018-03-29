---
title: 创建新模板或编辑现有的客户端版本策略
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 要使最大使用功能包含在 Skype 业务服务器 2015年并改善整体用户体验，可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
ms.openlocfilehash: 6c1e895dc03d094013f41a34cb21a12a24928172
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="2f440-106">客户端版本策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="2f440-106">Client Version Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="2f440-107">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="2f440-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="2f440-108">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="2f440-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="2f440-109">要使最大使用功能包含在 Skype 业务服务器 2015年并改善整体用户体验，可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="2f440-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="2f440-110">使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。</span><span class="sxs-lookup"><span data-stu-id="2f440-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f440-p103">按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。</span><span class="sxs-lookup"><span data-stu-id="2f440-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="2f440-113">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="2f440-113">Tasks you can perform</span></span>

<span data-ttu-id="2f440-114">您可以在“**新建客户端版本策略**”或“**编辑客户端版本策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2f440-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>
  
- <span data-ttu-id="2f440-115">添加或修改客户端版本策略的名称或描述。</span><span class="sxs-lookup"><span data-stu-id="2f440-115">Add or modify the name or description of the client version policy.</span></span>
    
- <span data-ttu-id="2f440-116">添加或修改客户端版本策略的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="2f440-116">Add or modify client version rules for the client version policy.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="2f440-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="2f440-117">UI Reference</span></span>

<span data-ttu-id="2f440-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="2f440-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="2f440-119">**作用域**标识客户端版本策略的作用域 （网站、 池或用户）。</span><span class="sxs-lookup"><span data-stu-id="2f440-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>
    
- <span data-ttu-id="2f440-120">**名称**您可以添加或修改客户端版本策略的名称。</span><span class="sxs-lookup"><span data-stu-id="2f440-120">**Name** You can add or modify the name of the client version policy.</span></span>
    
- <span data-ttu-id="2f440-121">**说明**您可以添加说明，以帮助识别客户端版本的策略页上的列表中的策略。</span><span class="sxs-lookup"><span data-stu-id="2f440-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>
    
- <span data-ttu-id="2f440-122">**新**可以将新的客户端版本规则添加到策略中。</span><span class="sxs-lookup"><span data-stu-id="2f440-122">**New** You can add a new client version rule to the policy.</span></span>
    
- <span data-ttu-id="2f440-123">**显示详细信息**此选项将打开一个对话框，您可以在其中更改的客户端版本规则的选项。</span><span class="sxs-lookup"><span data-stu-id="2f440-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>
    
- <span data-ttu-id="2f440-124">**删除**此选项从策略中删除选定的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="2f440-124">**Remove** This option removes the selected client version rule from the policy.</span></span>
    
- <span data-ttu-id="2f440-125">**向上和向下箭头**此选项将选定的客户端版本中的规则上移或下移优先级。</span><span class="sxs-lookup"><span data-stu-id="2f440-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="2f440-126">按列出的顺序处理规则。</span><span class="sxs-lookup"><span data-stu-id="2f440-126">Rules are processed in the order listed.</span></span>
    
<span data-ttu-id="2f440-127">在客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Lync 2013 预览中的客户端互操作性](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f440-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="2f440-128">有关使用客户端版本策略的详细信息，请参阅操作文档中的[指定客户端版本支持您的组织中](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2f440-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

