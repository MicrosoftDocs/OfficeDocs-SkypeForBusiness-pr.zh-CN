---
title: 客户端版本配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: 除了指定你希望在你的环境中支持的客户端版本外，你还可以为尚未定义版本策略的客户端指定默认操作。 这使你可以限制在你的环境中使用的客户端版本，从而帮助你控制与支持多个客户端版本相关联的成本。
ms.openlocfilehash: 46969857647a51dd092e3131dd3c24b71b810a2d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700437"
---
# <a name="client-version-configuration"></a><span data-ttu-id="6ae01-104">客户端版本配置</span><span class="sxs-lookup"><span data-stu-id="6ae01-104">Client Version Configuration</span></span>

<span data-ttu-id="6ae01-105">除了指定你希望在你的环境中支持的客户端版本外，你还可以为尚未定义版本策略的客户端指定默认操作。</span><span class="sxs-lookup"><span data-stu-id="6ae01-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="6ae01-106">这使你可以限制在你的环境中使用的客户端版本，从而帮助你控制与支持多个客户端版本相关联的成本。</span><span class="sxs-lookup"><span data-stu-id="6ae01-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6ae01-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="6ae01-107">Tasks you can perform</span></span>

<span data-ttu-id="6ae01-108">可以在**客户端版本配置**页面上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6ae01-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="6ae01-109">编辑默认（**全局**）客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="6ae01-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="6ae01-110">为特定网站创建客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="6ae01-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="6ae01-111">启用和禁用现有的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="6ae01-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="6ae01-112">由于匿名用户不与网站关联，因此匿名用户仅受全局级别策略的影响。</span><span class="sxs-lookup"><span data-stu-id="6ae01-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6ae01-113">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="6ae01-113">UI Reference</span></span>

<span data-ttu-id="6ae01-114">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="6ae01-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="6ae01-115">**新**你可以为特定网站创建客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="6ae01-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="6ae01-116">**编辑**你可以更改任何客户端版本策略的选项。</span><span class="sxs-lookup"><span data-stu-id="6ae01-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="6ae01-117">使用此选项，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ae01-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="6ae01-118">**显示详细信息**此选项将打开一个对话框，你可以在其中更改客户端版本配置的选项。</span><span class="sxs-lookup"><span data-stu-id="6ae01-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="6ae01-119">**全选**此选项选择列表中的所有客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="6ae01-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="6ae01-120">**Delete**此选项将删除所有选定的客户端版本配置。</span><span class="sxs-lookup"><span data-stu-id="6ae01-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="6ae01-121">**刷新**你可以刷新客户端版本配置列表来验证所有客户端版本配置的选项的状态。</span><span class="sxs-lookup"><span data-stu-id="6ae01-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="6ae01-p104">有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。有关使用客户端版本配置的详细信息，请参阅操作文档中的[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6ae01-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

