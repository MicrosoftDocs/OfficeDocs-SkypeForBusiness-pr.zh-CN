---
title: 呼叫寄存
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 当呼叫被取回时，该呼叫将转接到临时号码，呼叫将一直持续到有人取回或它退出。您需要配置一个表，该表包含要为已呼叫预留的分机号码范围。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 每个运行呼叫库应用程序的池都可以有一个或多个扩展范围。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: 30e0493c065c8bcd16b8d18a625c2650522ee8ee
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095396"
---
# <a name="call-park"></a><span data-ttu-id="e2725-106">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="e2725-106">Call Park</span></span>

<span data-ttu-id="e2725-107">当呼叫被取回时，该呼叫将转接到临时号码，呼叫将一直持续到有人取回或它退出。您需要配置一个表，该表包含要为已呼叫预留的分机号码范围。</span><span class="sxs-lookup"><span data-stu-id="e2725-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="e2725-108">这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。</span><span class="sxs-lookup"><span data-stu-id="e2725-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="e2725-109">每个运行呼叫库应用程序的池都可以有一个或多个扩展范围。</span><span class="sxs-lookup"><span data-stu-id="e2725-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="e2725-110">这些范围在部署中必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="e2725-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="e2725-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span><span class="sxs-lookup"><span data-stu-id="e2725-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e2725-112">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="e2725-112">Tasks you can perform</span></span>

<span data-ttu-id="e2725-113">您可以在“呼叫寄存”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e2725-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="e2725-114">创建新的号码范围</span><span class="sxs-lookup"><span data-stu-id="e2725-114">Create a new number range</span></span>

- <span data-ttu-id="e2725-115">更改现有号码范围</span><span class="sxs-lookup"><span data-stu-id="e2725-115">Change an existing number range</span></span>

- <span data-ttu-id="e2725-116">删除号码范围</span><span class="sxs-lookup"><span data-stu-id="e2725-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e2725-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="e2725-117">UI Reference</span></span>

<span data-ttu-id="e2725-118">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="e2725-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="e2725-119">**新建** 启动一个新的呼叫管理号码范围。</span><span class="sxs-lookup"><span data-stu-id="e2725-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="e2725-120">**编辑** 打开选定的号码范围进行编辑，选择列表中的所有号码范围，或删除选定的号码范围。</span><span class="sxs-lookup"><span data-stu-id="e2725-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="e2725-121">**刷新** 刷新号码范围列表。</span><span class="sxs-lookup"><span data-stu-id="e2725-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="e2725-122">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="e2725-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e2725-123">**名称** 标识号码范围的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="e2725-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="e2725-124">**起始范围** 范围的开始编号。</span><span class="sxs-lookup"><span data-stu-id="e2725-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="e2725-125">**结束范围** 范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="e2725-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="e2725-126">**目标** FQDN 的 (FQDN) 或托管号码范围的呼叫托管应用程序的应用程序服务的服务 ID。</span><span class="sxs-lookup"><span data-stu-id="e2725-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="e2725-127">有关呼叫等待特性和功能的详细信息，请参阅 Plan [for Call Park in Skype for Business 2015。](../../plan-your-deployment/enterprise-voice-solution/call-park.md)</span><span class="sxs-lookup"><span data-stu-id="e2725-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="e2725-128">有关使用呼叫等待号码范围的详细信息，请参阅 Configure [Phone Number Extensions for Parking Calls。](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)</span><span class="sxs-lookup"><span data-stu-id="e2725-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls).</span></span>