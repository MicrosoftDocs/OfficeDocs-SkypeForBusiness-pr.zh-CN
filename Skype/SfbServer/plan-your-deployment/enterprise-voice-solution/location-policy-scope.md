---
title: 在 Skype for Business Server 2015 中分配位置策略作用域
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: 规划业务服务器企业语音在 Skype E9-1-1 部署的位置策略。
ms.openlocfilehash: 472ca2e6382a92005476eb7ed7c6bcfb22e71f85
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="assign-location-policy-scope-in-skype-for-business-server-2015"></a><span data-ttu-id="a413a-103">在 Skype for Business Server 2015 中分配位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="a413a-103">Assign location policy scope in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a413a-104">规划业务服务器企业语音在 Skype E9-1-1 部署的位置策略。</span><span class="sxs-lookup"><span data-stu-id="a413a-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="a413a-105">如与其他 Skype 业务服务器策略，位置可以将策略分配多个作用域级别： 全局站点和用户。</span><span class="sxs-lookup"><span data-stu-id="a413a-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="a413a-106">然而，用户级别的位置策略的作用域行为与其他 Skype 业务服务器策略不同于一点。</span><span class="sxs-lookup"><span data-stu-id="a413a-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="a413a-107">不只可以基于用户位置的策略应用到终结点对象 （如用户和公共区域电话联系对象），它们也可以应用到 Skype 的业务服务器网络站点。</span><span class="sxs-lookup"><span data-stu-id="a413a-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="a413a-108">网络站点是地理位置关联的客户端子网的分组（但可能不需要所有子网位于一个中央站点或分支站点）。</span><span class="sxs-lookup"><span data-stu-id="a413a-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="a413a-109">连接到一个网络站点的子网的所有客户端将自动挑选分配给该网络站点的位置策略。</span><span class="sxs-lookup"><span data-stu-id="a413a-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="a413a-110">在将用户级别的位置策略分配给一个用户和一个网络站点的情况下，基于网络站点的位置策略将覆盖每用户策略设置。</span><span class="sxs-lookup"><span data-stu-id="a413a-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="a413a-111">每个网络站点均分配有一个位置策略，并且每个策略均分配有不同的 PSTN 用法、通知 URI 和会议 URI 值。</span><span class="sxs-lookup"><span data-stu-id="a413a-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a413a-112">此特定策略作用域行为的原因是当驻留在 office 网站的池中的用户访问另一个站点并发出紧急呼叫时，无论该用户分配到的池或站点如何，都将应用与该网络站点对应的 E9-1-1 呼叫路由设置。</span><span class="sxs-lookup"><span data-stu-id="a413a-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

