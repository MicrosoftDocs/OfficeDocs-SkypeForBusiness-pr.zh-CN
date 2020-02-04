---
title: 响应组队列新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 响应组队列将呼叫保留到响应组，直到工程师应答呼叫。
ms.openlocfilehash: ae1809a725a8bcb343347975e432adc053ad1d66
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690807"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="6802f-103">响应组队列：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="6802f-103">Response Groups Queue: Create New or Edit Existing</span></span>

<span data-ttu-id="6802f-104">响应组队列将呼叫保留到响应组，直到工程师应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="6802f-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6802f-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="6802f-105">UI Reference</span></span>

<span data-ttu-id="6802f-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="6802f-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="6802f-107">**名称**每个队列必须有一个名称。</span><span class="sxs-lookup"><span data-stu-id="6802f-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="6802f-108">键入队列的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="6802f-108">Type a descriptive name for the queue.</span></span>

- <span data-ttu-id="6802f-109">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="6802f-109">**Description** This field is optional.</span></span> <span data-ttu-id="6802f-110">使用它提供有关队列的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="6802f-110">Use it to provide additional details about the queue.</span></span>

- <span data-ttu-id="6802f-111">**组**选择要分配给队列的代理组。</span><span class="sxs-lookup"><span data-stu-id="6802f-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="6802f-112">单击 "**选择**" 将代理组添加到列表。</span><span class="sxs-lookup"><span data-stu-id="6802f-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="6802f-113">单击 "**删除**"，从列表中删除所选的代理组。</span><span class="sxs-lookup"><span data-stu-id="6802f-113">Click **Remove** to delete the selected agent group from the list.</span></span>

    <span data-ttu-id="6802f-114">向上和向下箭头可在列表中向上和向下移动所选代理组。</span><span class="sxs-lookup"><span data-stu-id="6802f-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="6802f-115">代理组的顺序影响 Skype for Business 服务器搜索可用代理的顺序。</span><span class="sxs-lookup"><span data-stu-id="6802f-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="6802f-116">即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。</span><span class="sxs-lookup"><span data-stu-id="6802f-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>

- <span data-ttu-id="6802f-117">**启用队列超时**选中此复选框以指定呼叫者在代理应答呼叫之前等待保持的最长时间。</span><span class="sxs-lookup"><span data-stu-id="6802f-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="6802f-118">如果选择此选项，还需要指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="6802f-118">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="6802f-119">**超时时间（秒）** 选择或键入呼叫者在工程师应答呼叫之前可以等待的最大秒数。</span><span class="sxs-lookup"><span data-stu-id="6802f-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>

  - <span data-ttu-id="6802f-120">**通话操作**选择通话超时后出现的操作。您的选择是：</span><span class="sxs-lookup"><span data-stu-id="6802f-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>

  - <span data-ttu-id="6802f-121">**断开连接**</span><span class="sxs-lookup"><span data-stu-id="6802f-121">**Disconnect**</span></span>

  - <span data-ttu-id="6802f-122">**转发到语音邮件**如果选择此选项，请在 " **sip 地址**" 中以 sip<username> @ <domainname>格式键入语音邮件地址（例如，sip:bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="6802f-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="6802f-123">**转发到电话号码**如果选择此选项，则在 " **sip 地址**" 中，键入 sip 的格式的<number> @ <domainname>电话号码：（例如，sip:+14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="6802f-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="6802f-124">**转发到 SIP 地址**选择此选项可将呼叫转移到其他用户。</span><span class="sxs-lookup"><span data-stu-id="6802f-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="6802f-125">在 " **sip 地址**" 中，在 "设置 SIP 格式" 中键入<username>@<domainname>用户的 URI：。</span><span class="sxs-lookup"><span data-stu-id="6802f-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="6802f-126">**转发到另一个队列**如果选择此选项，请通过浏览找到通话超时时接收呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="6802f-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>

- <span data-ttu-id="6802f-127">**启用队列溢出**选中此复选框以指定队列可以保留的最大通话数。</span><span class="sxs-lookup"><span data-stu-id="6802f-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="6802f-128">如果选择此选项，还需要指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="6802f-128">If you select this option, you also need to specify the following:</span></span>

  - <span data-ttu-id="6802f-129">**最大通话次数**选择或键入队列可以保留的最大通话数。</span><span class="sxs-lookup"><span data-stu-id="6802f-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>

  - <span data-ttu-id="6802f-130">**转接呼叫**选择达到队列溢出阈值时要采取的措施。</span><span class="sxs-lookup"><span data-stu-id="6802f-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>

  - <span data-ttu-id="6802f-131">**通话操作**选择满足队列溢出阈值时发生的操作。</span><span class="sxs-lookup"><span data-stu-id="6802f-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="6802f-132">您的选择是：</span><span class="sxs-lookup"><span data-stu-id="6802f-132">Your choices are:</span></span>

  - <span data-ttu-id="6802f-133">**断开连接**</span><span class="sxs-lookup"><span data-stu-id="6802f-133">**Disconnect**</span></span>

  - <span data-ttu-id="6802f-134">**转发到语音邮件**如果选择此选项，请在 " **sip 地址**" 中以 sip<username> @ <domainname>格式键入语音邮件地址（例如，sip:bob@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="6802f-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>

  - <span data-ttu-id="6802f-135">**转发到电话号码**如果选择此选项，则在 " **sip 地址**" 中，键入 sip 的格式的<number> @ <domainname>电话号码：（例如，sip:+14255550121@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="6802f-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>

  - <span data-ttu-id="6802f-136">**转发到 SIP 地址**选择此选项可将呼叫转移到其他用户。</span><span class="sxs-lookup"><span data-stu-id="6802f-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="6802f-137">在 " **sip 地址**" 中，在 "设置 SIP 格式" 中键入<username>@<domainname>用户的 URI：。</span><span class="sxs-lookup"><span data-stu-id="6802f-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>

  - <span data-ttu-id="6802f-138">**转发到另一个队列**如果选择此选项，请浏览到满足队列溢出阈值时要接收呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="6802f-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>

<span data-ttu-id="6802f-139">有关响应组功能和功能的详细信息，请参阅计划文档中的[Skype For Business 服务器中的 "响应组应用程序](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)"。</span><span class="sxs-lookup"><span data-stu-id="6802f-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="6802f-140">有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6802f-140">For details about working with queues, see [Managing Response Group Queues](https://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>


