---
title: 客户端版本策略新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。
ms.openlocfilehash: c08c709d4a8db20a23580c5a5bfd2ceaf823e028
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691617"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="ffa8a-104">客户端版本策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="ffa8a-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="ffa8a-105">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="ffa8a-106">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="ffa8a-107">为了最大程度地利用 Skype for Business 服务器中包含的功能并提高总体用户体验，你可以使用客户端版本筛选器来限制你的环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="ffa8a-108">使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffa8a-p103">按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ffa8a-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="ffa8a-111">Tasks you can perform</span></span>

<span data-ttu-id="ffa8a-112">您可以在“**新建客户端版本策略**”或“**编辑客户端版本策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="ffa8a-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="ffa8a-113">添加或修改客户端版本策略的名称或描述。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="ffa8a-114">添加或修改客户端版本策略的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ffa8a-115">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="ffa8a-115">UI Reference</span></span>

<span data-ttu-id="ffa8a-116">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="ffa8a-117">**范围**标识客户端版本策略的范围（网站、池或用户）。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="ffa8a-118">**名称**你可以添加或修改客户端版本策略的名称。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="ffa8a-119">**说明**你可以在 "客户端版本策略" 页上的列表中添加说明来帮助标识策略。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="ffa8a-120">**新**你可以将新的客户端版本规则添加到策略。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="ffa8a-121">**显示详细信息**此选项将打开一个对话框，您可以在其中更改客户端版本规则的选项。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="ffa8a-122">**删除**此选项将从策略中删除所选的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="ffa8a-123">**向上键和向下键**此选项将按优先级向上或向下移动选定的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="ffa8a-124">按列出的顺序处理规则。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="ffa8a-125">有关客户端和客户端版本之间的互操作性的详细信息，请参阅[客户端互操作](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)</span><span class="sxs-lookup"><span data-stu-id="ffa8a-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="ffa8a-126">有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ffa8a-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

