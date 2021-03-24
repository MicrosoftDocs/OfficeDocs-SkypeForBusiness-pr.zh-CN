---
title: 客户端版本策略 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。
ms.openlocfilehash: 57c273198a9c88ae26540518c9f892b218b96118
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100688"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="0a20b-104">客户端版本策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="0a20b-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="0a20b-105">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="0a20b-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="0a20b-106">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="0a20b-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="0a20b-107">为了充分利用 Skype for Business Server 中包含的功能并改进整体用户体验，可以使用客户端版本筛选器来限制环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="0a20b-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="0a20b-108">使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。</span><span class="sxs-lookup"><span data-stu-id="0a20b-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a20b-p103">按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。</span><span class="sxs-lookup"><span data-stu-id="0a20b-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="0a20b-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="0a20b-111">Tasks you can perform</span></span>

<span data-ttu-id="0a20b-112">您可以在"新建客户端版本策略"或"编辑客户端版本策略"页上执行 **以下** 任务：</span><span class="sxs-lookup"><span data-stu-id="0a20b-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="0a20b-113">添加或修改客户端版本策略的名称或说明。</span><span class="sxs-lookup"><span data-stu-id="0a20b-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="0a20b-114">添加或修改客户端版本策略的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="0a20b-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0a20b-115">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="0a20b-115">UI Reference</span></span>

<span data-ttu-id="0a20b-116">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="0a20b-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="0a20b-117">**范围** 标识客户端 (站点、池或) 作用域。</span><span class="sxs-lookup"><span data-stu-id="0a20b-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="0a20b-118">**名称** 可以添加或修改客户端版本策略的名称。</span><span class="sxs-lookup"><span data-stu-id="0a20b-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="0a20b-119">**说明** 可以添加说明以帮助在"客户端版本策略"页上的列表中标识策略。</span><span class="sxs-lookup"><span data-stu-id="0a20b-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="0a20b-120">**新建** 可以将新的客户端版本规则添加到策略。</span><span class="sxs-lookup"><span data-stu-id="0a20b-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="0a20b-121">**显示详细信息** 此选项将打开一个对话框，您可以在其中更改客户端版本规则的选项。</span><span class="sxs-lookup"><span data-stu-id="0a20b-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="0a20b-122">**删除** 此选项从策略中删除所选的客户端版本规则。</span><span class="sxs-lookup"><span data-stu-id="0a20b-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="0a20b-123">**向上和向下箭头** 此选项将所选客户端版本规则优先级上移或下移。</span><span class="sxs-lookup"><span data-stu-id="0a20b-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="0a20b-124">将按列出的顺序处理规则。</span><span class="sxs-lookup"><span data-stu-id="0a20b-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="0a20b-125">有关客户端和客户端版本之间的互操作性的详细信息，请参阅客户端 [互操作性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)。</span><span class="sxs-lookup"><span data-stu-id="0a20b-125">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013).</span></span> <span data-ttu-id="0a20b-126">有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)。</span><span class="sxs-lookup"><span data-stu-id="0a20b-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>