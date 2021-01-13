---
title: 在 Skype for Business Server 中分配位置策略作用域
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 规划 Skype for Business Server 企业语音 中的 E9-1-1 部署的位置企业语音。
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825522"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="a41fe-103">在 Skype for Business Server 中分配位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="a41fe-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="a41fe-104">规划 Skype for Business Server 企业语音 中的 E9-1-1 部署的位置企业语音。</span><span class="sxs-lookup"><span data-stu-id="a41fe-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a41fe-105">与其他 Skype for Business Server 策略一样，可在多个范围级别分配位置策略：全局、站点和用户。</span><span class="sxs-lookup"><span data-stu-id="a41fe-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="a41fe-106">但是，用户级别位置策略的范围与其他 Skype for Business Server 策略的行为有点不同。</span><span class="sxs-lookup"><span data-stu-id="a41fe-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="a41fe-107">不仅可以将每用户位置策略应用于终结点对象 (例如用户和公用区域电话联系对象) ，还可以应用于 Skype for Business Server 网络站点。</span><span class="sxs-lookup"><span data-stu-id="a41fe-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="a41fe-108">网络站点是与地理位置关联的客户端子网的分组（但是不一定全部都为整个中央站点或分支站点中的子网）。</span><span class="sxs-lookup"><span data-stu-id="a41fe-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="a41fe-109">任何连接到网络站点子网的客户端都自动拾取分配给该网络站点的位置策略。</span><span class="sxs-lookup"><span data-stu-id="a41fe-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="a41fe-110">如果用户级别的位置策略同时分配给用户和网络站点，则基于网络站点的位置策略将覆盖任何每用户策略设置。</span><span class="sxs-lookup"><span data-stu-id="a41fe-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="a41fe-111">每个网络站点都有为其分配的位置策略，而且每个策略都有为其分配的不同 PSTN 用途、通知 URI 和会议 URI 值。</span><span class="sxs-lookup"><span data-stu-id="a41fe-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a41fe-112">此特殊策略作用域行为的原因是，当一个位于一个办公室站点的池中的用户访问另一个站点并必须进行紧急呼叫时，无论用户分配到了哪一个池或站点，适用于该网络站点的 E9-1-1 呼叫路由设置都将适用。</span><span class="sxs-lookup"><span data-stu-id="a41fe-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

