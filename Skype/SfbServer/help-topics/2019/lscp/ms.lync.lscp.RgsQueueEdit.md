---
title: 响应组队列创建新的或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsQueueEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cbdde536-8668-4a08-9862-8615e8691fd7
ROBOTS: NOINDEX, NOFOLLOW
description: 响应组队列保留对响应组呼叫，直到代理应答呼叫。
ms.openlocfilehash: 7c56554571d09279ce896798d6c7e21dae5f9f3d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993493"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="482f0-103">响应组队列：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="482f0-103">Response Groups Queue: Create New or Edit Existing</span></span>
 
<span data-ttu-id="482f0-104">响应组队列保留对响应组呼叫，直到代理应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="482f0-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="482f0-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="482f0-105">UI Reference</span></span>

<span data-ttu-id="482f0-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="482f0-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="482f0-107">**名称**每个队列必须有一个名称。</span><span class="sxs-lookup"><span data-stu-id="482f0-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="482f0-108">键入队列的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="482f0-108">Type a descriptive name for the queue.</span></span>
    
- <span data-ttu-id="482f0-109">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="482f0-109">**Description** This field is optional.</span></span> <span data-ttu-id="482f0-110">使用它来提供有关队列的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="482f0-110">Use it to provide additional details about the queue.</span></span>
    
- <span data-ttu-id="482f0-111">**组**选择您想要分配给队列的代理组。</span><span class="sxs-lookup"><span data-stu-id="482f0-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="482f0-112">单击**选择**要添加到列表的代理组。</span><span class="sxs-lookup"><span data-stu-id="482f0-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="482f0-113">单击**删除**以从列表中删除选定的代理组。</span><span class="sxs-lookup"><span data-stu-id="482f0-113">Click **Remove** to delete the selected agent group from the list.</span></span>
    
    <span data-ttu-id="482f0-114">向上和向下箭头可在列表中向上和向下移动所选代理组。</span><span class="sxs-lookup"><span data-stu-id="482f0-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="482f0-115">代理组的顺序影响业务服务器 Skype 搜索可用代理的顺序。</span><span class="sxs-lookup"><span data-stu-id="482f0-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="482f0-116">即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。</span><span class="sxs-lookup"><span data-stu-id="482f0-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>
    
- <span data-ttu-id="482f0-117">**启用队列超时**选中此复选框，以指定的呼叫者处于保持状态状态之前要等待代理应答呼叫的时间最长时段。</span><span class="sxs-lookup"><span data-stu-id="482f0-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="482f0-118">如果选择此选项，您还需要指定以下：</span><span class="sxs-lookup"><span data-stu-id="482f0-118">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="482f0-119">**超时时段 （秒）** 选择或键入最大呼叫者等待代理应答呼叫的秒数。</span><span class="sxs-lookup"><span data-stu-id="482f0-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>
    
  - <span data-ttu-id="482f0-120">**呼叫操作**选择呼叫超时时时发生的操作。您选择的是：</span><span class="sxs-lookup"><span data-stu-id="482f0-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>
    
  - <span data-ttu-id="482f0-121">**断开连接**</span><span class="sxs-lookup"><span data-stu-id="482f0-121">**Disconnect**</span></span>
    
  - <span data-ttu-id="482f0-122">**转接到语音邮件**如果选择此选项，请在**SIP 地址**中，键入语音邮件地址格式 sip:<username> @ <domainname> (例如，sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="482f0-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="482f0-123">**转接到电话号码**如果选择此选项，在**SIP 地址**中键入该电话号码格式 sip:<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="482f0-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="482f0-124">**转接到 SIP 地址**选择此选项可将呼叫转接至另一个用户。</span><span class="sxs-lookup"><span data-stu-id="482f0-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="482f0-125">在**SIP 地址**，键入格式 sip 用户的 URI:<username>@<domainname>。</span><span class="sxs-lookup"><span data-stu-id="482f0-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="482f0-126">**转接至其他队列**如果选择此选项，浏览到队列接收呼叫的呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="482f0-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>
    
- <span data-ttu-id="482f0-127">**启用队列溢出**选中此复选框，若要指定队列可以容纳的呼叫的最大次数。</span><span class="sxs-lookup"><span data-stu-id="482f0-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="482f0-128">如果选择此选项，您还需要指定以下：</span><span class="sxs-lookup"><span data-stu-id="482f0-128">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="482f0-129">**最大呼叫数**选择或键入的呼叫队列可以容纳的最大数。</span><span class="sxs-lookup"><span data-stu-id="482f0-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>
    
  - <span data-ttu-id="482f0-130">**将呼叫转接**选择达到队列溢出阈值时执行操作的呼叫。</span><span class="sxs-lookup"><span data-stu-id="482f0-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>
    
  - <span data-ttu-id="482f0-131">**呼叫操作**选择达到队列溢出阈值时，发生此事件的操作。</span><span class="sxs-lookup"><span data-stu-id="482f0-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="482f0-132">您选择的是：</span><span class="sxs-lookup"><span data-stu-id="482f0-132">Your choices are:</span></span>
    
  - <span data-ttu-id="482f0-133">**断开连接**</span><span class="sxs-lookup"><span data-stu-id="482f0-133">**Disconnect**</span></span>
    
  - <span data-ttu-id="482f0-134">**转接到语音邮件**如果选择此选项，请在**SIP 地址**中，键入语音邮件地址格式 sip:<username> @ <domainname> (例如，sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="482f0-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="482f0-135">**转接到电话号码**如果选择此选项，在**SIP 地址**中键入该电话号码格式 sip:<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="482f0-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="482f0-136">**转接到 SIP 地址**选择此选项可将呼叫转接至另一个用户。</span><span class="sxs-lookup"><span data-stu-id="482f0-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="482f0-137">在**SIP 地址**，键入格式 sip 用户的 URI:<username>@<domainname>。</span><span class="sxs-lookup"><span data-stu-id="482f0-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="482f0-138">**转接至其他队列**如果选择此选项，浏览到在达到队列溢出阈值时接收呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="482f0-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>
    
<span data-ttu-id="482f0-139">有关响应组特性和功能的详细信息，请参阅规划文档中的[计划中的业务服务器 Skype 的响应组应用程序](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="482f0-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="482f0-140">有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="482f0-140">For details about working with queues, see [Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>
  

