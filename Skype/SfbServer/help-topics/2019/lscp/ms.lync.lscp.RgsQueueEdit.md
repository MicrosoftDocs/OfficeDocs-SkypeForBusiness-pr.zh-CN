---
title: 响应组队列创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 响应组队列保留对响应组的呼叫，直到代理应答呼叫。
ms.openlocfilehash: 097c28db7f2ae52d7ab0b362e828c8f05e132481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808192"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="b3ec1-103">响应组队列：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="b3ec1-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="b3ec1-104">响应组队列保留对响应组的呼叫，直到代理应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b3ec1-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="b3ec1-105">UI Reference</span></span>

<span data-ttu-id="b3ec1-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b3ec1-107">**名称** 每个队列都必须有一个名称。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="b3ec1-108">键入队列的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="b3ec1-109">**说明** 此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-109">**Description** This field is optional.</span></span> <span data-ttu-id="b3ec1-110">使用它提供有关队列的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="b3ec1-111">**组** 选择要分配给队列的代理组。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="b3ec1-112">单击 **"** 选择"将代理组添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="b3ec1-113">单击 **"** 删除"从列表中删除所选代理组。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="b3ec1-114">向上和向下箭头可在列表中向上和向下移动所选代理组。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="b3ec1-115">代理组的顺序会影响 Skype for Business Server 搜索可用代理的顺序。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="b3ec1-116">即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="b3ec1-117">**启用队列退出** 选中此复选框可指定呼叫者在代理应答呼叫之前等待等待的最长时间段。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="b3ec1-118">如果选择此选项，则还需要指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="b3ec1-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="b3ec1-119">**时间段 (秒)** 选择或键入呼叫者在代理应答呼叫之前可以等待的最大秒数。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="b3ec1-120">**呼叫操作** 选择呼叫退出时发生的操作。你的选择是：</span><span class="sxs-lookup"><span data-stu-id="b3ec1-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="b3ec1-121">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="b3ec1-121">**Disconnect**</span></span>

  - <span data-ttu-id="b3ec1-122">**转发到语音邮件** 如果选择此选项，请在 **SIP** 地址中键入 sip 格式的语音邮件地址： (<username> @ <domainname> 例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="b3ec1-123">**转发到电话号码** 如果选择此选项，请在 **SIP** 地址中键入格式为 sip 的电话号码： (<number> @ <domainname> 例如，sip:+14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="b3ec1-124">**转发到 SIP 地址** 选择此选项将呼叫转发给其他用户。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="b3ec1-125">在 **SIP 地址** 中，以 sip： 格式键入用户的 URI。 <username> @ <domainname></span><span class="sxs-lookup"><span data-stu-id="b3ec1-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="b3ec1-126">**转发到另一个队列** 如果选择此选项，请浏览到将在呼叫退出时接收呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="b3ec1-127">**启用队列溢出** 选中此复选框可指定队列可以保留的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="b3ec1-128">如果选择此选项，则还需要指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="b3ec1-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="b3ec1-129">**最大呼叫数** 选择或键入队列可以保留的最大呼叫数。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="b3ec1-130">**转发呼叫** 选择在达到队列溢出阈值时要采取措施的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="b3ec1-131">**呼叫操作** 选择在达到队列溢出阈值时发生的操作。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="b3ec1-132">选项包括：</span><span class="sxs-lookup"><span data-stu-id="b3ec1-132">Your choices are:</span></span>

  - <span data-ttu-id="b3ec1-133">**Disconnect**</span><span class="sxs-lookup"><span data-stu-id="b3ec1-133">**Disconnect**</span></span>

  - <span data-ttu-id="b3ec1-134">**转发到语音邮件** 如果选择此选项，请在 **SIP** 地址中键入 sip 格式的语音邮件地址： (<username> @ <domainname> 例如，sip:bob@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="b3ec1-135">**转发到电话号码** 如果选择此选项，请在 **SIP** 地址中键入格式为 sip 的电话号码： (<number> @ <domainname> 例如，sip:+14255550121@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="b3ec1-136">**转发到 SIP 地址** 选择此选项将呼叫转发给其他用户。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="b3ec1-137">在 **SIP 地址** 中，以 sip： 格式键入用户的 URI。 <username> @ <domainname></span><span class="sxs-lookup"><span data-stu-id="b3ec1-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="b3ec1-138">**转发到另一个队列** 如果选择此选项，请浏览到在达到队列溢出阈值时接收呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="b3ec1-139">有关响应组特性和功能的详细信息，请参阅规划文档中[的 Plan for the Response Group application in Skype for Business Server。](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)</span><span class="sxs-lookup"><span data-stu-id="b3ec1-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="b3ec1-140">有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b3ec1-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


