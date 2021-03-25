---
title: 预配 Skype 会议室系统 Exchange 和 Skype 帐户
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
ms.collection: M365-voice
description: 阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。
ms.openlocfilehash: 0e8c73bc83a62465dc711b4a6f2725f1d9c576f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113058"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="c3d7b-103">预配 Skype 会议室系统 Exchange 和 Skype 帐户</span><span class="sxs-lookup"><span data-stu-id="c3d7b-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="c3d7b-104">阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="c3d7b-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="c3d7b-105">Microsoft Teams 会议室是具有不同的依赖项和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="c3d7b-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="c3d7b-106">有关 Microsoft Teams 会议室的信息，请参阅 Microsoft Teams 会议室 [部署概述](/MicrosoftTeams/rooms/rooms-deploy)。</span><span class="sxs-lookup"><span data-stu-id="c3d7b-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](/MicrosoftTeams/rooms/rooms-deploy).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3d7b-107">Skype 会议室系统帐户设置取决于你的组织具有的拓扑类型。</span><span class="sxs-lookup"><span data-stu-id="c3d7b-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="c3d7b-108">若要详细了解 Active Directory 拓扑，请参阅[Environmental requirements for Skype for Business Server 2015。](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="c3d7b-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="c3d7b-109">设置 Skype 会议室系统 Exchange &amp; Skype for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="c3d7b-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="c3d7b-110">以下主题介绍如何为以下帐户设置和管理 Skype 会议室系统 Exchange 和 Skype for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="c3d7b-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="c3d7b-111">单个林本地部署</span><span class="sxs-lookup"><span data-stu-id="c3d7b-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="c3d7b-112">多个林本地部署</span><span class="sxs-lookup"><span data-stu-id="c3d7b-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="c3d7b-113">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="c3d7b-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="c3d7b-114">混合部署</span><span class="sxs-lookup"><span data-stu-id="c3d7b-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="c3d7b-115">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="c3d7b-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="c3d7b-116">管理 Skype 会议室系统账户</span><span class="sxs-lookup"><span data-stu-id="c3d7b-116">Manage Skype Room System accounts</span></span>
