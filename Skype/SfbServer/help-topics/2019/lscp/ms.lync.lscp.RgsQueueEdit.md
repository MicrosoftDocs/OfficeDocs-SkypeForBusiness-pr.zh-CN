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
description: 响应组队列保留对响应组呼叫，直到代理应答呼叫。
ms.openlocfilehash: c9ae9953248804de592f05243ef5a11009c7e045
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988353"
---
# <a name="response-groups-queue-create-new-or-edit-existing"></a><span data-ttu-id="403a4-103">响应组队列：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="403a4-103">Response Groups Queue: Create New or Edit Existing</span></span>
 
<span data-ttu-id="403a4-104">响应组队列保留对响应组呼叫，直到代理应答呼叫。</span><span class="sxs-lookup"><span data-stu-id="403a4-104">Response Group queues hold calls to a response group until an agent answers the call.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="403a4-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="403a4-105">UI Reference</span></span>

<span data-ttu-id="403a4-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="403a4-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="403a4-107">**名称**每个队列必须有一个名称。</span><span class="sxs-lookup"><span data-stu-id="403a4-107">**Name** Each queue must have a name.</span></span> <span data-ttu-id="403a4-108">键入队列的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="403a4-108">Type a descriptive name for the queue.</span></span>
    
- <span data-ttu-id="403a4-109">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="403a4-109">**Description** This field is optional.</span></span> <span data-ttu-id="403a4-110">使用它来提供有关队列的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="403a4-110">Use it to provide additional details about the queue.</span></span>
    
- <span data-ttu-id="403a4-111">**组**选择您想要分配给队列的代理组。</span><span class="sxs-lookup"><span data-stu-id="403a4-111">**Groups** Select the agent groups that you want to assign to the queue.</span></span> <span data-ttu-id="403a4-112">单击**选择**要添加到列表的代理组。</span><span class="sxs-lookup"><span data-stu-id="403a4-112">Click **Select** to add agent groups to the list.</span></span> <span data-ttu-id="403a4-113">单击**删除**以从列表中删除选定的代理组。</span><span class="sxs-lookup"><span data-stu-id="403a4-113">Click **Remove** to delete the selected agent group from the list.</span></span>
    
    <span data-ttu-id="403a4-114">向上和向下箭头可在列表中向上和向下移动所选代理组。</span><span class="sxs-lookup"><span data-stu-id="403a4-114">The up and down arrows move a selected agent group up and down in the list.</span></span> <span data-ttu-id="403a4-115">代理组的顺序影响业务服务器 Skype 搜索可用代理的顺序。</span><span class="sxs-lookup"><span data-stu-id="403a4-115">The order of agent groups affects the order in which Skype for Business Server searches for an available agent.</span></span> <span data-ttu-id="403a4-116">即，首先搜索列表中的第一个组以查找可用代理，随后是第二个组，依此类推。</span><span class="sxs-lookup"><span data-stu-id="403a4-116">That is, the first group in the list is searched first for an available agent, followed by the second group, and so on.</span></span>
    
- <span data-ttu-id="403a4-117">**启用队列超时**选中此复选框，以指定的呼叫者处于保持状态状态之前要等待代理应答呼叫的时间最长时段。</span><span class="sxs-lookup"><span data-stu-id="403a4-117">**Enable queue time-out** Select this check box to specify a maximum period of time for a caller to wait on hold before an agent answers the call.</span></span> <span data-ttu-id="403a4-118">如果选择此选项，您还需要指定以下：</span><span class="sxs-lookup"><span data-stu-id="403a4-118">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="403a4-119">**超时时段 （秒）** 选择或键入最大呼叫者等待代理应答呼叫的秒数。</span><span class="sxs-lookup"><span data-stu-id="403a4-119">**Time-out period (seconds)** Select or type the maximum number of seconds a caller can wait before an agent answers the call.</span></span>
    
  - <span data-ttu-id="403a4-120">**呼叫操作**选择呼叫超时时时发生的操作。您选择的是：</span><span class="sxs-lookup"><span data-stu-id="403a4-120">**Call action** Select the action that occurs when a call times out. Your choices are:</span></span>
    
  - <span data-ttu-id="403a4-121">**断开连接**</span><span class="sxs-lookup"><span data-stu-id="403a4-121">**Disconnect**</span></span>
    
  - <span data-ttu-id="403a4-122">**转接到语音邮件**如果选择此选项，请在**SIP 地址**中，键入语音邮件地址格式 sip:<username> @ <domainname> (例如，sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="403a4-122">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="403a4-123">**转接到电话号码**如果选择此选项，在**SIP 地址**中键入该电话号码格式 sip:<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="403a4-123">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="403a4-124">**转接到 SIP 地址**选择此选项可将呼叫转接至另一个用户。</span><span class="sxs-lookup"><span data-stu-id="403a4-124">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="403a4-125">在**SIP 地址**，键入格式 sip 用户的 URI:<username>@<domainname>。</span><span class="sxs-lookup"><span data-stu-id="403a4-125">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="403a4-126">**转接至其他队列**如果选择此选项，浏览到队列接收呼叫的呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="403a4-126">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the calls time out.</span></span>
    
- <span data-ttu-id="403a4-127">**启用队列溢出**选中此复选框，若要指定队列可以容纳的呼叫的最大次数。</span><span class="sxs-lookup"><span data-stu-id="403a4-127">**Enable queue overflow** Select this check box to specify a maximum number of calls that the queue can hold.</span></span> <span data-ttu-id="403a4-128">如果选择此选项，您还需要指定以下：</span><span class="sxs-lookup"><span data-stu-id="403a4-128">If you select this option, you also need to specify the following:</span></span>
    
  - <span data-ttu-id="403a4-129">**最大呼叫数**选择或键入的呼叫队列可以容纳的最大数。</span><span class="sxs-lookup"><span data-stu-id="403a4-129">**Maximum number of calls** Select or type the maximum number of calls the queue can hold.</span></span>
    
  - <span data-ttu-id="403a4-130">**将呼叫转接**选择达到队列溢出阈值时执行操作的呼叫。</span><span class="sxs-lookup"><span data-stu-id="403a4-130">**Forward the call** Select which call is to take action when the queue overflow threshold is met.</span></span>
    
  - <span data-ttu-id="403a4-131">**呼叫操作**选择达到队列溢出阈值时，发生此事件的操作。</span><span class="sxs-lookup"><span data-stu-id="403a4-131">**Call action** Select the action that occurs when the queue overflow threshold is met.</span></span> <span data-ttu-id="403a4-132">您选择的是：</span><span class="sxs-lookup"><span data-stu-id="403a4-132">Your choices are:</span></span>
    
  - <span data-ttu-id="403a4-133">**断开连接**</span><span class="sxs-lookup"><span data-stu-id="403a4-133">**Disconnect**</span></span>
    
  - <span data-ttu-id="403a4-134">**转接到语音邮件**如果选择此选项，请在**SIP 地址**中，键入语音邮件地址格式 sip:<username> @ <domainname> (例如，sip:bob@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="403a4-134">**Forward to voice mail** If you select this option, in **SIP address**, type a voice mail address in the format sip:<username>@<domainname> (for example, sip:bob@contoso.com).</span></span>
    
  - <span data-ttu-id="403a4-135">**转接到电话号码**如果选择此选项，在**SIP 地址**中键入该电话号码格式 sip:<number> @ <domainname> (例如，sip:+14255550121@contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="403a4-135">**Forward to telephone number** If you select this option, in **SIP address** type the telephone number in the format sip:<number>@<domainname> (for example, sip:+14255550121@contoso.com).</span></span>
    
  - <span data-ttu-id="403a4-136">**转接到 SIP 地址**选择此选项可将呼叫转接至另一个用户。</span><span class="sxs-lookup"><span data-stu-id="403a4-136">**Forward to SIP address** Select this option to forward the call to another user.</span></span> <span data-ttu-id="403a4-137">在**SIP 地址**，键入格式 sip 用户的 URI:<username>@<domainname>。</span><span class="sxs-lookup"><span data-stu-id="403a4-137">In **SIP address**, type the URI for the user in the format sip:<username>@<domainname>.</span></span>
    
  - <span data-ttu-id="403a4-138">**转接至其他队列**如果选择此选项，浏览到在达到队列溢出阈值时接收呼叫的队列。</span><span class="sxs-lookup"><span data-stu-id="403a4-138">**Forward to another queue** If you select this option, browse to the queue that is to receive calls when the queue overflow threshold is met.</span></span>
    
<span data-ttu-id="403a4-139">有关响应组特性和功能的详细信息，请参阅[规划响应组应用程序中的业务服务器 Skype](../../../plan-your-deployment/enterprise-voice-solution/response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="403a4-139">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md).</span></span> <span data-ttu-id="403a4-140">有关使用队列的详细信息，请参阅操作文档中的[Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="403a4-140">For details about working with queues, see [Managing Response Group Queues](http://technet.microsoft.com/library/1e91720c-ab67-4dfb-b30c-0ef2a8012310.aspx) in the Operations documentation.</span></span>
  

