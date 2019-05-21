---
title: 呼叫寄存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 当呼叫停止时, 它将被转移到一个临时号码中, 该号码一直保持通话, 直到有人将其检索或超时。您需要使用您为寄存的呼叫保留的分机号码范围配置表。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 运行呼叫驻留应用程序的每个池可以有一个或多个扩展区域。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: d325b1dd2066bd35f6dc9003de4c026a7f925a72
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290134"
---
# <a name="call-park"></a><span data-ttu-id="9443a-106">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="9443a-106">Call Park</span></span>

<span data-ttu-id="9443a-107">当呼叫停止时, 它将被转移到一个临时号码中, 该号码一直保持通话, 直到有人将其检索或超时。您需要使用您为寄存的呼叫保留的分机号码范围配置表。</span><span class="sxs-lookup"><span data-stu-id="9443a-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="9443a-108">这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。</span><span class="sxs-lookup"><span data-stu-id="9443a-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="9443a-109">运行呼叫驻留应用程序的每个池可以有一个或多个扩展区域。</span><span class="sxs-lookup"><span data-stu-id="9443a-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="9443a-110">这些范围在部署中必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="9443a-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="9443a-111">"**呼叫驻留**" 页面显示为您的组织定义的所有呼叫寄存号码范围的列表。</span><span class="sxs-lookup"><span data-stu-id="9443a-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9443a-112">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="9443a-112">Tasks you can perform</span></span>

<span data-ttu-id="9443a-113">您可以在“**呼叫寄存**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="9443a-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="9443a-114">创建新的号码范围</span><span class="sxs-lookup"><span data-stu-id="9443a-114">Create a new number range</span></span>

- <span data-ttu-id="9443a-115">更改现有号码范围</span><span class="sxs-lookup"><span data-stu-id="9443a-115">Change an existing number range</span></span>

- <span data-ttu-id="9443a-116">删除号码范围</span><span class="sxs-lookup"><span data-stu-id="9443a-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9443a-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="9443a-117">UI Reference</span></span>

<span data-ttu-id="9443a-118">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="9443a-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="9443a-119">**新**开始新的通话寄存号码范围。</span><span class="sxs-lookup"><span data-stu-id="9443a-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="9443a-120">**编辑**打开所选的数字范围进行编辑, 选择列表中的所有数字范围, 或删除选定的数字范围。</span><span class="sxs-lookup"><span data-stu-id="9443a-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="9443a-121">**刷新**刷新数字范围列表。</span><span class="sxs-lookup"><span data-stu-id="9443a-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="9443a-122">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="9443a-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="9443a-123">**名称**标识数字范围的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="9443a-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="9443a-124">**开始范围**区域的起始编号。</span><span class="sxs-lookup"><span data-stu-id="9443a-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="9443a-125">**结束范围**范围的结束编号。</span><span class="sxs-lookup"><span data-stu-id="9443a-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="9443a-126">**目标**为数字范围托管呼叫寄存应用程序的应用程序服务的完全限定的域名 (FQDN) 或服务 ID。</span><span class="sxs-lookup"><span data-stu-id="9443a-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="9443a-127">有关呼叫寄存功能和功能的详细信息, 请参阅[在 Skype For business 中计划通话寄存](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="9443a-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="9443a-128">有关使用呼叫寄存号码范围的详细信息, 请参阅[配置停车通话的电话号码扩展](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9443a-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


