---
title: 呼叫寄存
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 驻留呼叫后，它被传输到临时号码呼叫将保存，直到有人取回它或超时。您需要使用的保留用于寄存呼叫的分机号码范围配置的表。 这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。 运行呼叫寄存应用程序的每个池可以有一个或多个区域的扩展名。 这些范围在部署中必须是全局唯一的。
ms.openlocfilehash: 09ad7c71ee56b8d2604735257a73469e8143c105
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255582"
---
# <a name="call-park"></a><span data-ttu-id="f4722-106">呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="f4722-106">Call Park</span></span>

<span data-ttu-id="f4722-107">驻留呼叫后，它被传输到临时号码呼叫将保存，直到有人取回它或超时。您需要使用的保留用于寄存呼叫的分机号码范围配置的表。</span><span class="sxs-lookup"><span data-stu-id="f4722-107">When a call is parked, it is transferred to a temporary number where the call is held until someone retrieves it or it times out. You need to configure a table with the ranges of extension numbers that you are reserving for parked calls.</span></span> <span data-ttu-id="f4722-108">这些分机需要为虚拟分机（即未向其分配用户或电话的分机）。</span><span class="sxs-lookup"><span data-stu-id="f4722-108">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="f4722-109">运行呼叫寄存应用程序的每个池可以有一个或多个区域的扩展名。</span><span class="sxs-lookup"><span data-stu-id="f4722-109">Each pool that runs the Call Park application can have one or more ranges of extensions.</span></span> <span data-ttu-id="f4722-110">这些范围在部署中必须是全局唯一的。</span><span class="sxs-lookup"><span data-stu-id="f4722-110">These ranges must be globally unique across your deployment.</span></span>

<span data-ttu-id="f4722-111">**呼叫寄存**页上显示的所有呼叫寄存号码范围定义为您的组织的列表。</span><span class="sxs-lookup"><span data-stu-id="f4722-111">The **Call Park** page displays a list of all the Call Park number ranges that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f4722-112">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="f4722-112">Tasks you can perform</span></span>

<span data-ttu-id="f4722-113">您可以在“**呼叫寄存**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f4722-113">You can perform the following tasks from the **Call Park** page:</span></span>

- <span data-ttu-id="f4722-114">创建新的号码范围</span><span class="sxs-lookup"><span data-stu-id="f4722-114">Create a new number range</span></span>

- <span data-ttu-id="f4722-115">更改现有号码范围</span><span class="sxs-lookup"><span data-stu-id="f4722-115">Change an existing number range</span></span>

- <span data-ttu-id="f4722-116">删除号码范围</span><span class="sxs-lookup"><span data-stu-id="f4722-116">Delete a number range</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f4722-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="f4722-117">UI Reference</span></span>

<span data-ttu-id="f4722-118">下表介绍了该页上的各个命令。</span><span class="sxs-lookup"><span data-stu-id="f4722-118">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="f4722-119">**新**开始一个新的呼叫寄存号码范围。</span><span class="sxs-lookup"><span data-stu-id="f4722-119">**New** Starts a new Call Park number range.</span></span>

- <span data-ttu-id="f4722-120">**编辑**打开所选的号码范围以进行编辑，在列表中，选择全部号码范围或删除所选的号码范围。</span><span class="sxs-lookup"><span data-stu-id="f4722-120">**Edit** Opens the selected number range for editing, selects all number ranges in the list, or deletes the selected number range.</span></span>

- <span data-ttu-id="f4722-121">**刷新**刷新号码范围的列表。</span><span class="sxs-lookup"><span data-stu-id="f4722-121">**Refresh** Refreshes the list of number ranges.</span></span>

<span data-ttu-id="f4722-122">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="f4722-122">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f4722-123">**名称**标识号码范围的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="f4722-123">**Name** The unique name that identifies the number range.</span></span>

- <span data-ttu-id="f4722-124">**开始范围**该范围的开始号码。</span><span class="sxs-lookup"><span data-stu-id="f4722-124">**Start range** The beginning number of the range.</span></span>

- <span data-ttu-id="f4722-125">**结束范围**该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="f4722-125">**End range** The ending number of the range.</span></span>

- <span data-ttu-id="f4722-126">**目标**完全限定域名 (FQDN) 或服务 ID 的号码范围的呼叫寄存应用程序承载的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="f4722-126">**Destination** The fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application for the number range.</span></span>

<span data-ttu-id="f4722-127">有关呼叫寄存特性和功能的详细信息，请参阅[Plan for Business 的 Skype 中的呼叫寄存](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。</span><span class="sxs-lookup"><span data-stu-id="f4722-127">For details about Call Park features and capabilities, see [Plan for Call Park in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/call-park.md).</span></span> <span data-ttu-id="f4722-128">有关使用呼叫寄存号码范围的详细信息，请参阅[寄存呼叫配置电话号码的扩展](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f4722-128">For details about working with Call Park number ranges, see [Configure Phone Number Extensions for Parking Calls](https://technet.microsoft.com/library/fbf97624-9587-42a6-b276-1b69c574a74d.aspx).</span></span>


