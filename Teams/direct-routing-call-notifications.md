---
title: 电话系统直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: 直接路由呼叫通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 07efe11d304107a5a8606a07f5d1c2a7a130bc0b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "37595333"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="96db6-103">管理呼叫通知</span><span class="sxs-lookup"><span data-stu-id="96db6-103">Manage call notifications</span></span>

<span data-ttu-id="96db6-104">本文介绍如何管理用户的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="96db6-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="96db6-105">你可以将呼叫终结点配置到两个团队和第三方专用分支交换（PBX）或会话边界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="96db6-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="96db6-106">例如，如果您想要同时向用户的手机和桌面电话发送呼叫，这很有用。</span><span class="sxs-lookup"><span data-stu-id="96db6-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="96db6-107">在下图中，用户 Irena 有两个终结点：</span><span class="sxs-lookup"><span data-stu-id="96db6-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="96db6-108">团队终结点</span><span class="sxs-lookup"><span data-stu-id="96db6-108">A Teams endpoint</span></span>
- <span data-ttu-id="96db6-109">连接到第三方 SBC 的 SIP 电话</span><span class="sxs-lookup"><span data-stu-id="96db6-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="96db6-110">当呼叫到达时，SBC 将电话系统直接路由和第三方 SBC 之间的通话派生在一起。</span><span class="sxs-lookup"><span data-stu-id="96db6-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![显示分叉团队终结点的图表](media/direct-routing-call-notification-1.png)

<span data-ttu-id="96db6-112">如果在分叉2上接受呼叫（由第三方 SBC），团队将生成 "未接来电" 通知。</span><span class="sxs-lookup"><span data-stu-id="96db6-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="96db6-113">你可以通过将 SBC 配置为在分叉1上发送取消，从而阻止 "未接来电" 通知，如下所示：</span><span class="sxs-lookup"><span data-stu-id="96db6-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="96db6-114">原因： SIP;原因 = 200; 文本 "通话在别处完成"</span><span class="sxs-lookup"><span data-stu-id="96db6-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="96db6-115">请注意，呼叫将不会在 Microsoft Phone 系统的呼叫详细记录中注册为成功通话。</span><span class="sxs-lookup"><span data-stu-id="96db6-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="96db6-116">该呼叫将注册为 "尝试"，最终 SIP 代码为 "487"、最终 Microsoft 子代码 "540200" 和最终 SIP 代码短语 "在别处完成通话"。</span><span class="sxs-lookup"><span data-stu-id="96db6-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>   <span data-ttu-id="96db6-117">（若要查看呼叫详细记录，请转到团队管理员门户、分析和报表、使用情况报告，并选择 PSNT 用法。）</span><span class="sxs-lookup"><span data-stu-id="96db6-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSNT Usage.)</span></span>


<span data-ttu-id="96db6-118">下图显示了分叉1的 SIP 阶梯、解释调用流以及取消消息中的预期原因。</span><span class="sxs-lookup"><span data-stu-id="96db6-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![显示分叉团队终结点的图表](media/direct-routing-call-notification-2.png)
