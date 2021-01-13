---
title: 客户端版本策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 为了充分利用 Skype for Business Server 2015 中包含的功能并改进整体用户体验，可以使用客户端版本筛选器来限制环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
ms.openlocfilehash: 7147df6d6f2460c1b341cced6a9ecc207943da8d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833392"
---
# <a name="client-version-policy"></a><span data-ttu-id="bd3a8-106">客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="bd3a8-106">Client Version Policy</span></span>

<span data-ttu-id="bd3a8-107">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="bd3a8-108">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="bd3a8-109">为了充分利用 Skype for Business Server 2015 中包含的功能并改进整体用户体验，可以使用客户端版本筛选器来限制环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="bd3a8-110">使用客户端版本筛选器还有助于降低与支持多个客户端版本关联的成本。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="bd3a8-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="bd3a8-111">Tasks you can perform</span></span>

<span data-ttu-id="bd3a8-112">您可以在“客户端版本策略”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bd3a8-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="bd3a8-113">编辑默认 ( **全局**) 客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="bd3a8-114">为特定站点或池创建客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="bd3a8-115">创建可分配给各个用户的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="bd3a8-116">由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="bd3a8-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="bd3a8-117">UI Reference</span></span>

<span data-ttu-id="bd3a8-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="bd3a8-119">**新建** 可以创建以下一个或多个客户端版本策略：</span><span class="sxs-lookup"><span data-stu-id="bd3a8-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="bd3a8-120">站点策略</span><span class="sxs-lookup"><span data-stu-id="bd3a8-120">Site policy</span></span>

  - <span data-ttu-id="bd3a8-121">池策略</span><span class="sxs-lookup"><span data-stu-id="bd3a8-121">Pool policy</span></span>

  - <span data-ttu-id="bd3a8-122">用户策略</span><span class="sxs-lookup"><span data-stu-id="bd3a8-122">User policy</span></span>

- <span data-ttu-id="bd3a8-123">**编辑** 您可以更改任何客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="bd3a8-124">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bd3a8-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="bd3a8-125">**显示详细信息** 此选项将打开一个对话框，您可以在其中更改客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="bd3a8-126">**全选** 此选项选择列表中的所有客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="bd3a8-127">**删除** 此选项将删除所有选定的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="bd3a8-128">**刷新** 可以刷新客户端版本策略列表以验证所有客户端版本策略的选项状态。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="bd3a8-129">有关客户端和客户端版本之间的交互性的详细信息，请参阅规划文档中的 [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="bd3a8-130">有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bd3a8-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

