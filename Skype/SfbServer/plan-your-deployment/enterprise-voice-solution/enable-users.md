---
title: 在 Skype for business 服务器中启用 E9-1-1 的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: 适用于 Skype for Business Server Enterprise Voice 中的 E9 部署的位置策略所需的决策，包括要启用哪些用户以及如何支持漫游用户。
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802952"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="1038b-103">在 Skype for business 服务器中启用 E9-1-1 的用户</span><span class="sxs-lookup"><span data-stu-id="1038b-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="1038b-104">适用于 Skype for Business Server Enterprise Voice 中的 E9 部署的位置策略所需的决策，包括要启用哪些用户以及如何支持漫游用户。</span><span class="sxs-lookup"><span data-stu-id="1038b-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="1038b-105">在客户端注册期间，Skype for Business 服务器使用一个位置策略来配置支持企业语音的用户的 E9 属性。</span><span class="sxs-lookup"><span data-stu-id="1038b-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="1038b-106">此策略包含定义 E9-1-1 实现方式的设置。</span><span class="sxs-lookup"><span data-stu-id="1038b-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="1038b-107">例如，位置策略包含 "紧急拨号" 字符串之类的信息，以及是否需要用户手动输入一个位置（如果位置信息服务不会自动提供）。</span><span class="sxs-lookup"><span data-stu-id="1038b-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="1038b-108">有关位置策略的完整定义，请参阅为[Skype For Business 服务器计划位置策略](location-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1038b-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="1038b-109">Skype for Business 服务器可以基于子网将位置策略分配给客户，也可以基于全局、每个站点或每用户策略为用户分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="1038b-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="1038b-110">为帮助确定启用用户的方式，应首先回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="1038b-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="1038b-111">**你计划启用所有用户还是限制为对企业的特定地理区域的支持？**</span><span class="sxs-lookup"><span data-stu-id="1038b-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="1038b-112">可以使用全局位置策略为企业中的所有用户分配位置。</span><span class="sxs-lookup"><span data-stu-id="1038b-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="1038b-113">但是，通过将位置策略分配给 Skype for business 服务器网络网站，然后将子网添加到该网站，你可以将 E9 支持限制到企业内选定的位置，并以每个站点为基础指定 E9 路由行为。</span><span class="sxs-lookup"><span data-stu-id="1038b-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="1038b-114">**你是否计划通过用户策略启用单个用户？**</span><span class="sxs-lookup"><span data-stu-id="1038b-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="1038b-115">如果要自定义 E9-1-1 支持，您可以直接向特定用户或公共区域电话联系人对象分配位置策略。</span><span class="sxs-lookup"><span data-stu-id="1038b-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="1038b-116">**当客户端在网络外漫游或从未定义的子网连接时，是否仍然应该为客户端启用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="1038b-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="1038b-117">如果为用户分配了全局、网站或每用户位置策略，则可以在客户端不在定义的子网中或未找到位置信息服务的位置时，将其手动输入到客户端的位置。</span><span class="sxs-lookup"><span data-stu-id="1038b-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="1038b-118">有关详细信息，请参阅[定义在 Skype For Business 服务器中手动获取位置的用户体验](manually-acquiring-a-location.md)。</span><span class="sxs-lookup"><span data-stu-id="1038b-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

