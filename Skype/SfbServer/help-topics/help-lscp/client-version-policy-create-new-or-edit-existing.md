---
title: 客户端版本策略新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 为了最大程度地利用 Skype for Business Server 2015 中包含的功能并改善用户的总体体验, 你可以使用客户端版本筛选器来限制你的环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
ms.openlocfilehash: f89089f34086a36c3e652bf8527ba4db7d108a11
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300012"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="b8c7c-106">客户端版本策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="b8c7c-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="b8c7c-107">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="b8c7c-108">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="b8c7c-109">为了最大程度地利用 Skype for Business Server 2015 中包含的功能并改善用户的总体体验, 你可以使用客户端版本筛选器来限制你的环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="b8c7c-110">使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8c7c-p103">按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b8c7c-113">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="b8c7c-113">Tasks you can perform</span></span>

<span data-ttu-id="b8c7c-114">您可以在“**新建客户端版本策略**”或“**编辑客户端版本策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b8c7c-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="b8c7c-115">添加或修改客户端版本策略的名称或描述。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="b8c7c-116">添加或修改客户端版本策略的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b8c7c-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="b8c7c-117">UI Reference</span></span>

<span data-ttu-id="b8c7c-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="b8c7c-119">**范围**标识客户端版本策略的范围 (网站、池或用户)。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="b8c7c-120">**名称**你可以添加或修改客户端版本策略的名称。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="b8c7c-121">**说明**你可以在 "客户端版本策略" 页上的列表中添加说明来帮助标识策略。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="b8c7c-122">**新**你可以将新的客户端版本规则添加到策略。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="b8c7c-123">**显示详细信息**此选项将打开一个对话框, 您可以在其中更改客户端版本规则的选项。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="b8c7c-124">**删除**此选项将从策略中删除所选的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="b8c7c-125">**向上键和向下键**此选项将按优先级向上或向下移动选定的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="b8c7c-126">按列出的顺序处理规则。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="b8c7c-p105">有关客户端与客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b8c7c-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

