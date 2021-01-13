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
ms.openlocfilehash: fb0b511d8a99d6aa9901459e1ea06d2f05ae4a42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833912"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="7a866-103">预配 Skype 会议室系统 Exchange 和 Skype 帐户</span><span class="sxs-lookup"><span data-stu-id="7a866-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="7a866-104">阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="7a866-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="7a866-105">Microsoft Teams 会议室是具有不同的依赖项和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="7a866-105">Microsoft Teams Rooms is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="7a866-106">有关 Microsoft Teams 会议室的信息，请参阅 Microsoft Teams 会议室 [部署概述](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="7a866-106">For information on Microsoft Teams Rooms, see the Microsoft Teams Rooms [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7a866-107">Skype 会议室系统帐户设置取决于组织具有的拓扑类型。</span><span class="sxs-lookup"><span data-stu-id="7a866-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="7a866-108">若要详细了解 Active Directory 拓扑，请参阅 [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)的环境要求。</span><span class="sxs-lookup"><span data-stu-id="7a866-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="7a866-109">预配 Skype 会议室系统 Exchange &amp; Skype for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="7a866-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="7a866-110">以下主题介绍如何为以下帐户设置和管理 Skype 会议室系统 Exchange 和 Skype for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="7a866-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="7a866-111">单个林本地部署</span><span class="sxs-lookup"><span data-stu-id="7a866-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="7a866-112">多个林本地部署</span><span class="sxs-lookup"><span data-stu-id="7a866-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="7a866-113">Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="7a866-113">Microsoft 365 or Office 365</span></span>
    
- <span data-ttu-id="7a866-114">混合部署</span><span class="sxs-lookup"><span data-stu-id="7a866-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="7a866-115">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="7a866-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="7a866-116">管理 Skype 会议室系统账户</span><span class="sxs-lookup"><span data-stu-id="7a866-116">Manage Skype Room System accounts</span></span>
    

