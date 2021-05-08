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
f1.keywords:
- NOCSH
description: 直接路由呼叫通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0320ebc6abfc0e3f3d720fbab03abc698b26849c
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341806"
---
# <a name="manage-call-notifications"></a><span data-ttu-id="f6172-103">管理呼叫通知</span><span class="sxs-lookup"><span data-stu-id="f6172-103">Manage call notifications</span></span>

<span data-ttu-id="f6172-104">本文介绍如何管理用户的呼叫通知。</span><span class="sxs-lookup"><span data-stu-id="f6172-104">This article describes how to manage call notifications for your users.</span></span> <span data-ttu-id="f6172-105">可以将呼叫终结点配置为同时Teams第三方专用分支 Exchange (PBX) 或会话边界控制器 (SBC) 。</span><span class="sxs-lookup"><span data-stu-id="f6172-105">You can configure call endpoints to both Teams and to a third-party Private Branch Exchange (PBX) or Session Border Controller (SBC).</span></span>  <span data-ttu-id="f6172-106">这非常有用，例如，如果要同时向用户的移动电话和桌面电话发送呼叫。</span><span class="sxs-lookup"><span data-stu-id="f6172-106">This is useful, for example, if you want to send a call to a user's mobile and desk phones at the same time.</span></span>   

<span data-ttu-id="f6172-107">下图中，用户 Irena 有两个终结点：</span><span class="sxs-lookup"><span data-stu-id="f6172-107">In the following diagram, user Irena has two endpoints:</span></span>

- <span data-ttu-id="f6172-108">Teams终结点</span><span class="sxs-lookup"><span data-stu-id="f6172-108">A Teams endpoint</span></span>
- <span data-ttu-id="f6172-109">连接到第三方 SBC 的 SIP 电话</span><span class="sxs-lookup"><span data-stu-id="f6172-109">A SIP phone connected to a third-party SBC</span></span>

<span data-ttu-id="f6172-110">当呼叫到达时，SBC 将分叉电话系统直接路由和第三方 SBC 之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f6172-110">When a call arrives, the SBC forks the call between Phone System Direct Routing and the third-party SBC.</span></span>


![显示分叉Teams的示意图](media/direct-routing-call-notification-1.png)

<span data-ttu-id="f6172-112">如果第三方 SBC (在分叉 2 上接受) ，Teams将生成"未接呼叫"通知。</span><span class="sxs-lookup"><span data-stu-id="f6172-112">If the call is accepted on Fork 2 (by the third-party SBC), Teams will generate a “Missed Call” notification.</span></span>  

<span data-ttu-id="f6172-113">可以通过将 SBC 配置为在分叉 1 上发送取消来阻止"错过的呼叫"通知，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f6172-113">You can prevent the “Missed Call” notification by configuring the SBC to send a Cancel on Fork 1 as follows:</span></span>

<span data-ttu-id="f6172-114">原因：SIP;cause=200;text"Callcompleted else"</span><span class="sxs-lookup"><span data-stu-id="f6172-114">REASON: SIP; cause=200;text”Call completed elsewhere”</span></span> 

<span data-ttu-id="f6172-115">请注意，呼叫不会在系统呼叫详细信息记录中注册Microsoft 电话成功调用。</span><span class="sxs-lookup"><span data-stu-id="f6172-115">Note that the call will not be registered in the call detail records of Microsoft Phone System as a successful call.</span></span> <span data-ttu-id="f6172-116">该调用将注册为最终 SIP 代码"487"、最终 Microsoft 子代码"540200"和最终 SIP 代码短语"已在其他位置完成呼叫"的"尝试"。</span><span class="sxs-lookup"><span data-stu-id="f6172-116">The call will be registered as an “Attempt” with Final SIP Code “487”, Final Microsoft subcode “540200”, and Final SIP Code Phrase “Call completed elsewhere”.</span></span>  <span data-ttu-id="f6172-117"> (要查看呼叫详细信息记录，请转到 Teams 管理门户、分析和报告、使用情况报告，然后选择"PSTN 使用情况.) </span><span class="sxs-lookup"><span data-stu-id="f6172-117">(To view the call detail records, go the Teams Admin portal, Analytics and Reports, Usage Reports, and select PSTN Usage.)</span></span>


<span data-ttu-id="f6172-118">下图演示了分叉 1 的 SIP 阶梯，解释了呼叫流以及"取消"消息中的预期原因。</span><span class="sxs-lookup"><span data-stu-id="f6172-118">The diagram below illustrates the SIP ladder for Fork 1, explains the call flow, and the expected REASON in the Cancel message.</span></span> 

![显示分叉Teams的示意图](media/direct-routing-call-notification-2.png)
