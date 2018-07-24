---
title: 设置 Skype 会议室系统 Exchange 和 Skype 帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fa71a2da-2cc9-4ad1-8ec9-08d1c9c5247a
description: 阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。
ms.openlocfilehash: 584b4582f68510302af81afa32b47672220304f2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988428"
---
# <a name="provisioning-of-skype-room-system-exchange-and-skype-accounts"></a><span data-ttu-id="c3c76-103">设置 Skype 会议室系统 Exchange 和 Skype 帐户</span><span class="sxs-lookup"><span data-stu-id="c3c76-103">Provisioning of Skype Room System Exchange and Skype Accounts</span></span>
 
<span data-ttu-id="c3c76-104">阅读这些主题，了解如何为 Skype 会议室系统设置 Exchange 和 Skype 帐户。</span><span class="sxs-lookup"><span data-stu-id="c3c76-104">Read these topics to learn how to provision Exchange and Skype accounts for Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="c3c76-105">Skype 会议室系统 v2 是具有不同的依赖关系和部署过程的不同产品。</span><span class="sxs-lookup"><span data-stu-id="c3c76-105">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="c3c76-106">Skype 会议室系统 v2 的信息，请参阅 Skype 会议室系统 v2[部署概述](room-systems-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c76-106">For information on Skype Room Systems v2, see the Skype Room Systems v2 [deployment overview](room-systems-v2.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3c76-107">Skype 会议室系统帐户设置取决于您的组织的拓扑的类型。</span><span class="sxs-lookup"><span data-stu-id="c3c76-107">Skype Room System account provisioning depends on the type of topology your organization has.</span></span> <span data-ttu-id="c3c76-108">若要了解有关 Active Directory 拓扑的详细信息，请参阅[环境要求 Skype 的业务服务器 2015年](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3c76-108">To know more about Active Directory topologies, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span> 
  
## <a name="provisioning-of-skype-room-system-exchange-amp-skype-for-business-accounts"></a><span data-ttu-id="c3c76-109">Skype 会议室系统 Exchange 设置&amp;Skype 业务帐户</span><span class="sxs-lookup"><span data-stu-id="c3c76-109">Provisioning of Skype Room System Exchange &amp; Skype for Business Accounts</span></span>

<span data-ttu-id="c3c76-110">以下主题介绍如何设置和管理用于以下各项的 Skype 会议室系统 Exchange 和 Skype for Business 帐户：</span><span class="sxs-lookup"><span data-stu-id="c3c76-110">The following topics describe how to provision and manage Skype Room System Exchange and Skype for Business accounts for:</span></span>
  
- <span data-ttu-id="c3c76-111">单林本地部署</span><span class="sxs-lookup"><span data-stu-id="c3c76-111">Single forest on-premises deployments</span></span>
    
- <span data-ttu-id="c3c76-112">多林本地部署</span><span class="sxs-lookup"><span data-stu-id="c3c76-112">Multiple forest on-premises deployments</span></span>
    
- <span data-ttu-id="c3c76-113">Office 365</span><span class="sxs-lookup"><span data-stu-id="c3c76-113">Office 365</span></span>
    
- <span data-ttu-id="c3c76-114">混合部署</span><span class="sxs-lookup"><span data-stu-id="c3c76-114">Hybrid deployments</span></span>
    
- <span data-ttu-id="c3c76-115">Skype 会议室系统和 Skype for Business 联盟伙伴</span><span class="sxs-lookup"><span data-stu-id="c3c76-115">Skype Room System and Skype for Business federated partners</span></span>
    
- <span data-ttu-id="c3c76-116">管理 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="c3c76-116">Manage Skype Room System accounts</span></span>
    

