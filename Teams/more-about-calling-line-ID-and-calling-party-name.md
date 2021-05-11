---
title: 更多关于呼叫线路 ID 和主叫方名称的信息
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 了解呼叫线路 ID 和呼叫方名称。
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308311"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="79555-103">更多关于呼叫线路 ID 和主叫方名称的信息</span><span class="sxs-lookup"><span data-stu-id="79555-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="79555-104">CallerID 包含两条面向用户的信息：</span><span class="sxs-lookup"><span data-stu-id="79555-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="79555-105">电话号码 (称为 CLID 或呼叫线路 ID) 。</span><span class="sxs-lookup"><span data-stu-id="79555-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="79555-106">调用方 (通常称为 CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="79555-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="79555-107">进行呼叫时，CLID (电话号码) 路由到目的地的运营商 (也称为终止运营商) 。</span><span class="sxs-lookup"><span data-stu-id="79555-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="79555-108">调用的 CNAM 信息可能会路由，也可能不能与调用一起路由，因为此信息取决于国家/地区实现 CNAM (（如果) ）。</span><span class="sxs-lookup"><span data-stu-id="79555-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="79555-109">通过呼叫进行 CNAM 传送的可靠性因处理呼叫的国家/地区或运营商（作为中介或终止性运营商）而异。</span><span class="sxs-lookup"><span data-stu-id="79555-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="79555-110">CLID & CNAM 传输是终止运营商的责任。</span><span class="sxs-lookup"><span data-stu-id="79555-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="79555-111">终止运营商必须支持 CLID & CNAM 功能，并为这两个值提供最新记录。</span><span class="sxs-lookup"><span data-stu-id="79555-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="79555-112">Microsoft 在发起调用时可靠地提供 CLID 值，但这些值在通过中间运营商或终止运营商后可能不会保持不变。</span><span class="sxs-lookup"><span data-stu-id="79555-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="79555-113">如果 CLID 值被中介或终止运营商更改、省略或截断，Microsoft 几乎无法解决公共电话网络中此类问题。</span><span class="sxs-lookup"><span data-stu-id="79555-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="79555-114">当中间或终止性运营商延迟刷新权威数据库中的 CNAM 信息时（如美国的情况）时，CNAM 中的不一致可能引起。</span><span class="sxs-lookup"><span data-stu-id="79555-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="79555-115">在没有 CNAM 权威数据库的国家/地区，各个运营商的做法也可能导致 CNAM 信息在呼叫中保持不变。</span><span class="sxs-lookup"><span data-stu-id="79555-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="79555-116">Microsoft 目前不支持美国外的国家/地区提供原始 CNAM 信息。</span><span class="sxs-lookup"><span data-stu-id="79555-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="79555-117">相关主题</span><span class="sxs-lookup"><span data-stu-id="79555-117">Related topics</span></span>


