---
title: 客户端版本策略
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。
ms.openlocfilehash: d63966c988ebe6041012764767faf9ff459273ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216058"
---
# <a name="client-version-policy"></a><span data-ttu-id="2af56-104">客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="2af56-104">Client Version Policy</span></span>

<span data-ttu-id="2af56-105">可以指定环境中支持的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="2af56-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="2af56-106">当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。</span><span class="sxs-lookup"><span data-stu-id="2af56-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="2af56-107">以最大利用业务服务器 Skype 中包含的功能和改进的整体用户体验，您可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="2af56-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="2af56-108">使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。</span><span class="sxs-lookup"><span data-stu-id="2af56-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2af56-109">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="2af56-109">Tasks you can perform</span></span>

<span data-ttu-id="2af56-110">您可以在“**客户端版本策略**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2af56-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="2af56-111">编辑默认 （**全局**） 客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="2af56-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="2af56-112">为特定站点或池创建客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="2af56-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="2af56-113">创建可分配给各个用户的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="2af56-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="2af56-114">由于匿名用户未与用户、站点或服务关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="2af56-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2af56-115">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="2af56-115">UI Reference</span></span>

<span data-ttu-id="2af56-116">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="2af56-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="2af56-117">**新**您可以创建一个或多个以下客户端版本策略：</span><span class="sxs-lookup"><span data-stu-id="2af56-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="2af56-118">站点策略</span><span class="sxs-lookup"><span data-stu-id="2af56-118">Site policy</span></span>

  - <span data-ttu-id="2af56-119">池策略</span><span class="sxs-lookup"><span data-stu-id="2af56-119">Pool policy</span></span>

  - <span data-ttu-id="2af56-120">用户策略</span><span class="sxs-lookup"><span data-stu-id="2af56-120">User policy</span></span>

- <span data-ttu-id="2af56-121">**编辑**您可以更改的任何客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="2af56-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="2af56-122">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2af56-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="2af56-123">**显示详细信息**此选项可打开一个对话框，您可以在其中更改客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="2af56-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="2af56-124">**选择全部**此选项可选择列表中所有客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="2af56-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="2af56-125">**删除**此选项可删除所有选定的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="2af56-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="2af56-126">**刷新**您可以刷新客户端版本策略列表以验证所有客户端版本策略的选项状态。</span><span class="sxs-lookup"><span data-stu-id="2af56-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="2af56-127">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[客户端互操作性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2af56-127">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="2af56-128">有关使用客户端版本策略的详细信息，请参阅操作文档中的[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2af56-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

