---
title: 更多关于呼叫线路 ID 和主叫方名称的信息
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 了解在使用 "新的本地号码" 外接程序时，为什么需要添加可对帐户进行更改的授权人员。
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255395"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="2fd93-103">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="2fd93-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="2fd93-104">CallerID （通常称为），实际上包含两个面向用户的可识别信息片段：</span><span class="sxs-lookup"><span data-stu-id="2fd93-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="2fd93-105">电话号码 (通常称为 CLID 或呼叫线路 ID) </span><span class="sxs-lookup"><span data-stu-id="2fd93-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="2fd93-106">调用方名称 (通常称为 CNAM) ，最多可长达15个字符。</span><span class="sxs-lookup"><span data-stu-id="2fd93-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="2fd93-107">进行通话时，CLID (电话号码) 将路由到目的地的运营商 (也称为终止载波) 。</span><span class="sxs-lookup"><span data-stu-id="2fd93-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="2fd93-108">通话的 CNAM 信息可能与呼叫一起发送，也可能不会与呼叫一起发送，因为这取决于国家是如何实现的 CNAM (（如果所有) 都是如此）。</span><span class="sxs-lookup"><span data-stu-id="2fd93-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="2fd93-109">与通话的 CNAM 传递的可靠性因作为中间和/或终止运营商处理呼叫的国家和运营商而异。</span><span class="sxs-lookup"><span data-stu-id="2fd93-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="2fd93-110">CLID & CNAM 传输是终止载波的责任，因为终止运营商必须支持 CLID & CNAM 功能以及为两个值提供最新的记录。</span><span class="sxs-lookup"><span data-stu-id="2fd93-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="2fd93-111">在发起呼叫时 Microsoft 可靠地提供 CLID 值，但这些值在通过中间运营商或终止运营商传递后可能不会保持不变。</span><span class="sxs-lookup"><span data-stu-id="2fd93-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="2fd93-112">遗憾的是，在 CLID 值发生更改时，由中间或终止载波省略或截断，Microsoft 几乎不能在 recourse 公共电话网络中解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="2fd93-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="2fd93-113">CNAM 中的不一致可能由中间或终止运营商刷新权威数据库中的 CNAM 信息引起的，如美国的情况。</span><span class="sxs-lookup"><span data-stu-id="2fd93-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="2fd93-114">在没有 CNAM 权威数据库的国家/地区，单个运营商的做法还可能导致与通话的 CNAM 信息不完整的问题。</span><span class="sxs-lookup"><span data-stu-id="2fd93-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="2fd93-115">Microsoft 目前不支持除美国之外的其他国家/地区的原始 CNAM 信息。 "</span><span class="sxs-lookup"><span data-stu-id="2fd93-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="2fd93-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="2fd93-116">Related topics</span></span>


