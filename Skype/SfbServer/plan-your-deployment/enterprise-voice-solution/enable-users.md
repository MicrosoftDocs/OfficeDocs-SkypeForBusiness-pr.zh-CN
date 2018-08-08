---
title: 为用户启用 E9-1-1 在 Skype 业务服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 业务 Server 企业语音，包括启用的用户以及如何支持漫游用户的位置策略中 Skype E9-1-1 部署所需的决策。
ms.openlocfilehash: c5dbbc7904313ffc1706615f2aec506032e20074
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997192"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="6d326-103">为用户启用 E9-1-1 在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="6d326-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="6d326-104">业务 Server 企业语音，包括启用的用户以及如何支持漫游用户的位置策略中 Skype E9-1-1 部署所需的决策。</span><span class="sxs-lookup"><span data-stu-id="6d326-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="6d326-105">在客户端注册过程 Skype 业务服务器使用位置策略配置 E9-1-1 属性已启用企业语音的用户。</span><span class="sxs-lookup"><span data-stu-id="6d326-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="6d326-106">此策略包含定义 E9-1-1 实现方式的设置。</span><span class="sxs-lookup"><span data-stu-id="6d326-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="6d326-107">例如，位置策略包含信息，如，紧急拨号字符串，以及要求用户手动输入位置，如果位置信息服务不会自动提供一个。</span><span class="sxs-lookup"><span data-stu-id="6d326-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="6d326-108">位置策略的完整定义，请参阅[Plan for Business Server Skype 的位置策略](location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6d326-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="6d326-109">Skype 业务服务器到客户端的子网，或根据全局，用户可以分配位置策略的站点或每用户策略。</span><span class="sxs-lookup"><span data-stu-id="6d326-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="6d326-110">为帮助确定启用用户的方式，应首先回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="6d326-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="6d326-111">**你计划启用所有用户还是限制为对企业的特定地理区域的支持？**</span><span class="sxs-lookup"><span data-stu-id="6d326-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="6d326-112">可以使用全局位置策略为企业中的所有用户分配位置。</span><span class="sxs-lookup"><span data-stu-id="6d326-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="6d326-113">但是，通过向 Skype Business Server 网络站点分配位置策略，然后将子网添加到网站，您可以限制对所选位置将在企业内部的 E9-1-1 支持和单独对每个网站指定 E9-1-1 路由行为。</span><span class="sxs-lookup"><span data-stu-id="6d326-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="6d326-114">**你是否计划通过用户策略启用单个用户？**</span><span class="sxs-lookup"><span data-stu-id="6d326-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="6d326-115">如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="6d326-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="6d326-116">**当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="6d326-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="6d326-117">如果用户分配全局，网站，每用户位置策略，也可以是管理需要手动到客户端输入的位置，如果客户端不是位于定义的子网，或者没有位置已找到由位置信息服务。</span><span class="sxs-lookup"><span data-stu-id="6d326-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="6d326-118">有关详细信息，请参阅[定义手动获取 Skype 业务服务器中的位置的用户体验](manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="6d326-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

