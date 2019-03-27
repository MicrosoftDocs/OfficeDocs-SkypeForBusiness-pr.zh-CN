---
title: 客户端版本策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 地利用最大的业务服务器 2015 Skype 中包含的功能和改进的整体用户体验，您可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
ms.openlocfilehash: 80494c52aa20175a74daac7b094600bb4590d92a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885067"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="36516-106">客户端版本策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="36516-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="36516-107">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="36516-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="36516-108">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="36516-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="36516-109">地利用最大的业务服务器 2015 Skype 中包含的功能和改进的整体用户体验，您可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="36516-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="36516-110">使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。</span><span class="sxs-lookup"><span data-stu-id="36516-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36516-p103">按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。</span><span class="sxs-lookup"><span data-stu-id="36516-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="36516-113">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="36516-113">Tasks you can perform</span></span>

<span data-ttu-id="36516-114">您可以在“**新建客户端版本策略**”或“**编辑客户端版本策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="36516-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="36516-115">添加或修改客户端版本策略的名称或描述。</span><span class="sxs-lookup"><span data-stu-id="36516-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="36516-116">添加或修改客户端版本策略的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="36516-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="36516-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="36516-117">UI Reference</span></span>

<span data-ttu-id="36516-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="36516-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="36516-119">**范围**标识客户端版本策略的范围 （站点、 池或用户）。</span><span class="sxs-lookup"><span data-stu-id="36516-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="36516-120">**名称**您可以添加或修改客户端版本策略的名称。</span><span class="sxs-lookup"><span data-stu-id="36516-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="36516-121">**说明**您可以添加描述以帮助标识客户端版本策略页上的列表中的策略。</span><span class="sxs-lookup"><span data-stu-id="36516-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="36516-122">**新**您可以向策略添加新的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="36516-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="36516-123">**显示详细信息**此选项可打开一个对话框，您可以在其中更改客户端版本规则的选项。</span><span class="sxs-lookup"><span data-stu-id="36516-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="36516-124">**删除**此选项从策略中删除选定的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="36516-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="36516-125">**上下箭头**此选项将选定的客户端版本中的规则向上或向下优先级。</span><span class="sxs-lookup"><span data-stu-id="36516-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="36516-126">规则中列出的顺序进行处理。</span><span class="sxs-lookup"><span data-stu-id="36516-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="36516-p105">有关客户端与客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36516-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

