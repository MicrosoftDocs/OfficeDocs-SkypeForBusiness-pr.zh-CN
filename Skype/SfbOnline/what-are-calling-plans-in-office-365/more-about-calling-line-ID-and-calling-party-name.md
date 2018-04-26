---
title: 有关调用行 ID 和调用方名称的详细信息
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 了解为什么您需要添加获得授权的人员都可以使用新的本地数字端口订单向导时对帐户进行更改。
ms.openlocfilehash: 1174ba5837bb91c3251232ab48fa63c343425ac1
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="ba1e0-103">有关调用行 ID 和调用方名称的详细信息</span><span class="sxs-lookup"><span data-stu-id="ba1e0-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="ba1e0-104">来电显示，通常被认为，实际上包括两个面向用户的标识元素的信息：</span><span class="sxs-lookup"><span data-stu-id="ba1e0-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="ba1e0-105">电话号码 （通常称为 CLID 或调用行 ID）</span><span class="sxs-lookup"><span data-stu-id="ba1e0-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="ba1e0-106">调用方名称 （通常称为 CNAM） 可达 15 个字符的长度。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="ba1e0-107">时进行调用，CLID （电话号码） 将被路由到目的地的承运人 （也称为终止承运人）。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="ba1e0-108">调用的 CNAM 信息可能也因为这取决于 （如果在所有） 国家/地区已实现 CNAM 的方式不可能呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="ba1e0-109">与调用 CNAM 交付的可靠性取决于国家/地区和处理该调用，或者作为中介的运营商和 （或） 终止运营商。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="ba1e0-110">CLID & CNAM 传输是终止承运人的责任，只要终止运营商必须支持 CLID & CNAM 功能以及为这两个值提供最新的记录。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="ba1e0-111">Microsoft 能够可靠地提供 CLID 值时发出呼叫，但是这些值可能不会保持不变后通过中间的承运人或承运人终止。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="ba1e0-112">遗憾的是，万一 CLID 值更改、 忽略或截断的中间或终止的运营商，那么 Microsoft 已纠正公共电话网络中的此类问题小到没有解决方法。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="ba1e0-113">CNAM 中的不一致性可能致刷新 CNAM 信息权威数据库，如美国的情况中的中间或终止运营商的延迟。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="ba1e0-114">在国家没有为 CNAM 权威数据库，其中各个运营商的做法也会导致原封不动通过调用到达 CNAM 信息的问题。</span><span class="sxs-lookup"><span data-stu-id="ba1e0-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="ba1e0-115">Microsoft 目前不支持原始 CNAM 信息在美国以外的国家。"</span><span class="sxs-lookup"><span data-stu-id="ba1e0-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba1e0-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="ba1e0-116">Related topics</span></span>


