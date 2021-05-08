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
description: 了解使用"新建本地号码端口订单"向导时为何需要添加可更改帐户的授权人员。
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255395"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="3bd6c-103">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="3bd6c-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="3bd6c-104">CallerID（通常称为）实际上包含两个面向用户的可识别信息片段：</span><span class="sxs-lookup"><span data-stu-id="3bd6c-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="3bd6c-105">电话号码 (通常称为 CLID 或呼叫线路 ID) </span><span class="sxs-lookup"><span data-stu-id="3bd6c-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="3bd6c-106">呼叫方 (通常称为 CNAM) ，最大长度为 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="3bd6c-107">进行呼叫时，CLID (电话号码) 路由到目的地的运营商 (也称为终止运营商) 。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="3bd6c-108">呼叫的 CNAM 信息可能会路由，也可能不能与调用一起路由，因为这取决于国家/地区实现 CNAM (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="3bd6c-109">通过呼叫进行 CNAM 传送的可靠性因作为中介和/或终止运营商处理呼叫的国家/地区或运营商而异。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="3bd6c-110">CLID & CNAM 传输是终止运营商的责任，因为终止运营商必须支持 CLID & CNAM 功能，并为这两个值提供最新记录。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="3bd6c-111">Microsoft 在发起调用时可靠地提供 CLID 值，但这些值在通过中间运营商或终止运营商后可能不会保持不变。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="3bd6c-112">遗憾的是，如果 CLID 值被中介或终止运营商更改、省略或截断，Microsoft 几乎无法纠正公共电话网络中此类问题。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="3bd6c-113">CNAM 中的不一致可能是由于中间或终止性运营商在权威数据库中刷新 CNAM 信息（如美国的情况）出现延迟。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="3bd6c-114">在没有 CNAM 权威数据库的国家/地区，各个运营商的做法也可能导致 CNAM 信息在呼叫中保持不变。</span><span class="sxs-lookup"><span data-stu-id="3bd6c-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="3bd6c-115">Microsoft 当前不支持美国外的国家/地区中的原始 CNAM 信息。"</span><span class="sxs-lookup"><span data-stu-id="3bd6c-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="3bd6c-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="3bd6c-116">Related topics</span></span>


