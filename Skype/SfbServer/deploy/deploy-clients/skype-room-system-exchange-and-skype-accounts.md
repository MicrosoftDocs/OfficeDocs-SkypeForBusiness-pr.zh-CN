---
title: 设置 Skype 会议室系统 Exchange 和 Skype 帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。
ms.openlocfilehash: 504c1551cdda30bef46ba30584de8a557c5a4941
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287676"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="cfb45-103">设置 Skype 会议室系统 Exchange 和 Skype 帐户</span><span class="sxs-lookup"><span data-stu-id="cfb45-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="cfb45-104">阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="cfb45-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="cfb45-105">Microsoft 团队聊天室是具有不同的依赖项和部署过程的其他产品。</span><span class="sxs-lookup"><span data-stu-id="cfb45-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="cfb45-106">有关 Microsoft 团队聊天室的信息, 请参阅 Microsoft 团队会议室[部署概述](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="cfb45-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="cfb45-107">Skype 会议室系统帐户预配取决于您的组织拥有的拓扑类型。</span><span class="sxs-lookup"><span data-stu-id="cfb45-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="cfb45-108">要了解有关 Active Directory 拓扑的更多信息，请参阅 [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfb45-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="cfb45-109">预配 Skype 会议室系统 Exchange &amp; skype For business 帐户</span><span class="sxs-lookup"><span data-stu-id="cfb45-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="cfb45-110">以下主题介绍如何设置和管理用于以下各项的 Skype 会议室系统 Exchange 和 Skype for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="cfb45-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="cfb45-111">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="cfb45-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="cfb45-112">多林本地部署</span><span class="sxs-lookup"><span data-stu-id="cfb45-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="cfb45-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="cfb45-113">Office 365</span></span>
    
- <span data-ttu-id="cfb45-114">混合部署</span><span class="sxs-lookup"><span data-stu-id="cfb45-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="cfb45-115">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="cfb45-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="cfb45-116">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="cfb45-116">Manage Skype Room System accounts</span></span>
    

