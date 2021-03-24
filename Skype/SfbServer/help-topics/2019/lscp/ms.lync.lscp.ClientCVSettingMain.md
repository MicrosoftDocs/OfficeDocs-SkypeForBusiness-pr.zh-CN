---
title: 客户端版本配置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 除了指定希望在环境中支持的客户端版本之外，还可以指定尚未定义版本策略的客户端的默认操作。这样可以限制在环境中使用的客户端版本，从而帮助您控制与支持多个客户端版本相关的成本。
ms.openlocfilehash: 69d8c15688e6afce2f1e92cebc20ad8fb6bc7464
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100648"
---
# <a name="client-version-configuration"></a><span data-ttu-id="7e208-104">客户端版本配置</span><span class="sxs-lookup"><span data-stu-id="7e208-104">Client Version Configuration</span></span>

<span data-ttu-id="7e208-p102">除了指定希望在环境中支持的客户端版本之外，还可以指定尚未定义版本策略的客户端的默认操作。这样可以限制在环境中使用的客户端版本，从而帮助您控制与支持多个客户端版本相关的成本。</span><span class="sxs-lookup"><span data-stu-id="7e208-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7e208-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="7e208-107">Tasks you can perform</span></span>

<span data-ttu-id="7e208-108">您可以在“客户端版本配置”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="7e208-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="7e208-109">编辑默认的全局 **()** 客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="7e208-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="7e208-110">为特定站点创建客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="7e208-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="7e208-111">启用和禁用现有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="7e208-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="7e208-112">由于匿名用户未与站点关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="7e208-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7e208-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="7e208-113">UI Reference</span></span>

<span data-ttu-id="7e208-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="7e208-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="7e208-115">**新建** 您可以为特定站点创建客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="7e208-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="7e208-116">**编辑** 可以更改任何客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="7e208-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="7e208-117">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7e208-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="7e208-118">**显示详细信息** 此选项将打开一个对话框，您可以在其中更改客户端版本配置的选项。</span><span class="sxs-lookup"><span data-stu-id="7e208-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="7e208-119">**全选** 此选项选择列表中的所有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="7e208-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="7e208-120">**删除** 此选项将删除所有选定的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="7e208-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="7e208-121">**刷新** 可以刷新客户端版本配置列表以验证所有客户端版本配置的选项状态。</span><span class="sxs-lookup"><span data-stu-id="7e208-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="7e208-122">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的 Client [Interoperability。](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)</span><span class="sxs-lookup"><span data-stu-id="7e208-122">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="7e208-123">有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)。</span><span class="sxs-lookup"><span data-stu-id="7e208-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>