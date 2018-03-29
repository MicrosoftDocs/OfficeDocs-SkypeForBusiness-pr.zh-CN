---
title: 呼叫寄存
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
description: 时路边一个调用，它转移到一个临时数字人检索或超时之前调用地点。您需要配置区域的保留排队电话的分机号码表。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 每个池运行调用公园应用程序可以有一个或多个范围的扩展。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: 710d923ae9c1e44320438334ad42a89d9d14062f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="call-park"></a><span data-ttu-id="aef20-106">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="aef20-106">Call Park</span></span>
 
<span data-ttu-id="aef20-107">时路边一个调用，它转移到一个临时数字人检索或超时之前调用地点。您需要配置区域的保留排队电话的分机号码表。</span><span class="sxs-lookup"><span data-stu-id="aef20-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="aef20-108">这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。</span><span class="sxs-lookup"><span data-stu-id="aef20-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="aef20-109">每个池运行调用公园应用程序可以有一个或多个范围的扩展。</span><span class="sxs-lookup"><span data-stu-id="aef20-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="aef20-110">这些范围在部署中必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="aef20-110">These ranges must be globally unique across your deployment.</span></span>
  
<span data-ttu-id="aef20-111">* * 调用公园 * * 页显示范围中的所有调用公园编号为您的组织定义的列表。</span><span class="sxs-lookup"><span data-stu-id="aef20-111">The ** Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="aef20-112">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="aef20-112">Tasks you can perform</span></span>

<span data-ttu-id="aef20-113">您可以在“**呼叫寄存**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="aef20-113">You can perform the following tasks from the **Call Park** page:</span></span>
  
- <span data-ttu-id="aef20-114">创建新的号码范围</span><span class="sxs-lookup"><span data-stu-id="aef20-114">Create a new number range</span></span>
    
- <span data-ttu-id="aef20-115">更改现有号码范围</span><span class="sxs-lookup"><span data-stu-id="aef20-115">Change an existing number range</span></span>
    
- <span data-ttu-id="aef20-116">删除号码范围</span><span class="sxs-lookup"><span data-stu-id="aef20-116">Delete a number range</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="aef20-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="aef20-117">UI Reference</span></span>

<span data-ttu-id="aef20-118">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="aef20-118">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="aef20-119">**新**开始一个新的调用公园编号范围。</span><span class="sxs-lookup"><span data-stu-id="aef20-119">**New** Starts a new Call Park number range.</span></span>
    
- <span data-ttu-id="aef20-120">**编辑**打开用于编辑所选编号范围，在列表中，选择所有的数字范围或删除所选的数字范围。</span><span class="sxs-lookup"><span data-stu-id="aef20-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>
    
- <span data-ttu-id="aef20-121">**刷新**刷新列表中的数字范围。</span><span class="sxs-lookup"><span data-stu-id="aef20-121">**Refresh** Refreshes the list of number ranges.</span></span>
    
<span data-ttu-id="aef20-122">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="aef20-122">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="aef20-123">**名称**唯一名称标识的范围。</span><span class="sxs-lookup"><span data-stu-id="aef20-123">**Name** The unique name that identifies the number range.</span></span>
    
- <span data-ttu-id="aef20-124">**范围的开始**范围的起始编号。</span><span class="sxs-lookup"><span data-stu-id="aef20-124">**Start range** The beginning number of the range.</span></span>
    
- <span data-ttu-id="aef20-125">**结束范围**范围的结束编号。</span><span class="sxs-lookup"><span data-stu-id="aef20-125">**End range** The ending number of the range.</span></span>
    
- <span data-ttu-id="aef20-126">**目标**完全合格的域名名称 (FQDN) 或服务 ID 编号范围内的调用公园应用程序宿主的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="aef20-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>
    
<span data-ttu-id="aef20-127">有关调用公园的特性和功能的详细信息，请参阅[规划中业务 2015年的 Skype 通话公园](../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="aef20-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="aef20-128">有关使用调用公园数字范围的详细信息，请参阅[配置电话号码停车调用扩展](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aef20-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](http://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>
  

