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
description: 阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。
ms.openlocfilehash: ec812f569e096d31fb1085d196037677edf5da37
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699272"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="1a2d0-103">设置 Skype 会议室系统 Exchange 和 Skype 帐户</span><span class="sxs-lookup"><span data-stu-id="1a2d0-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="1a2d0-104">阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="1a2d0-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="1a2d0-105">Skype 会议室系统 v2 是具有不同的依赖关系和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="1a2d0-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="1a2d0-106">Skype 会议室系统 v2 的信息，请参阅 Skype 会议室系统 v2[部署概述](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2d0-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1a2d0-107">Skype 会议室系统帐户设置取决于您的组织的拓扑的类型。</span><span class="sxs-lookup"><span data-stu-id="1a2d0-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="1a2d0-108">要了解有关 Active Directory 拓扑的更多信息，请参阅 [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1a2d0-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="1a2d0-109">Skype 会议室系统 Exchange 设置&amp;Skype 业务帐户</span><span class="sxs-lookup"><span data-stu-id="1a2d0-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="1a2d0-110">以下主题介绍如何设置和管理用于以下各项的 Skype 会议室系统 Exchange 和 Skype for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="1a2d0-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="1a2d0-111">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="1a2d0-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="1a2d0-112">多林本地部署</span><span class="sxs-lookup"><span data-stu-id="1a2d0-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="1a2d0-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="1a2d0-113">Office 365</span></span>
    
- <span data-ttu-id="1a2d0-114">混合部署</span><span class="sxs-lookup"><span data-stu-id="1a2d0-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="1a2d0-115">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="1a2d0-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="1a2d0-116">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="1a2d0-116">Manage Skype Room System accounts</span></span>
    

