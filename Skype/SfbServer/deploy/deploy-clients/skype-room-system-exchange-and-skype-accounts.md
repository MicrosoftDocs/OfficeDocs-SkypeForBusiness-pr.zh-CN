---
title: 设置 Skype 会议室系统 Exchange 和 Skype 帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。
ms.openlocfilehash: 2da978d84ac763a27bba135e1899e83955b4fb53
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207893"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="a71f0-103">设置 Skype 会议室系统 Exchange 和 Skype 帐户</span><span class="sxs-lookup"><span data-stu-id="a71f0-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="a71f0-104">阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="a71f0-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="a71f0-105">Microsoft 团队聊天室是一种不同的产品具有不同的依赖项以及部署过程。</span><span class="sxs-lookup"><span data-stu-id="a71f0-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="a71f0-106">有关 Microsoft 团队聊天室的信息，请参阅 Microsoft 团队聊天室[部署概述](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="a71f0-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a71f0-107">Skype 会议室系统帐户设置取决于您的组织的拓扑的类型。</span><span class="sxs-lookup"><span data-stu-id="a71f0-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="a71f0-108">要了解有关 Active Directory 拓扑的更多信息，请参阅 [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a71f0-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="a71f0-109">Skype 会议室系统 Exchange 设置&amp;Skype 业务帐户</span><span class="sxs-lookup"><span data-stu-id="a71f0-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="a71f0-110">以下主题介绍如何设置和管理用于以下各项的 Skype 会议室系统 Exchange 和 Skype for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="a71f0-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="a71f0-111">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="a71f0-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="a71f0-112">多林本地部署</span><span class="sxs-lookup"><span data-stu-id="a71f0-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="a71f0-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="a71f0-113">Office 365</span></span>
    
- <span data-ttu-id="a71f0-114">混合部署</span><span class="sxs-lookup"><span data-stu-id="a71f0-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="a71f0-115">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="a71f0-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="a71f0-116">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="a71f0-116">Manage Skype Room System accounts</span></span>
    

