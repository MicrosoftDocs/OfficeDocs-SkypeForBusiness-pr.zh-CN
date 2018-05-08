---
title: 在 Skype for Business Server 2015 中定义紧急呼叫要求
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: 总结了根据是否必须 SIP 中继 E9-1-1 服务提供商或 ELIN 网关启用业务 Server 企业语音，E9-1-1 Skype 中所需的步骤。
ms.openlocfilehash: 20e741c9bdffb51b2e210c506dfd3ad2dc52d792
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server-2015"></a><span data-ttu-id="9a900-103">在 Skype for Business Server 2015 中定义紧急呼叫要求</span><span class="sxs-lookup"><span data-stu-id="9a900-103">Define your requirements for emergency calls in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9a900-104">总结了根据是否必须 SIP 中继 E9-1-1 服务提供商或 ELIN 网关启用业务 Server 企业语音，E9-1-1 Skype 中所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="9a900-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="9a900-105">Skype 业务服务器 E9-1-1 部署之前，首先应该能够回答以下各节详细的问题。</span><span class="sxs-lookup"><span data-stu-id="9a900-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="9a900-106">您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="9a900-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="9a900-107">下表标识需要这些解决方案的每个查看此规划工作簿中的部分。</span><span class="sxs-lookup"><span data-stu-id="9a900-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="9a900-108">**按类型 E9-1-1 解决方案的规划步骤**</span><span class="sxs-lookup"><span data-stu-id="9a900-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="9a900-109">**SIP 中继服务提供商**</span><span class="sxs-lookup"><span data-stu-id="9a900-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="9a900-110">**ELIN 网关**</span><span class="sxs-lookup"><span data-stu-id="9a900-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9a900-111">为业务服务器 2015 Skype 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="9a900-111">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>](scope.md) <br/> |[<span data-ttu-id="9a900-112">为业务服务器 2015 Skype 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="9a900-112">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>](scope.md) <br/> |
|[<span data-ttu-id="9a900-113">定义用于确定业务服务器 2015 Skype 中的位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="9a900-113">Define the network elements used to determine location in Skype for Business Server 2015</span></span>](network-location.md) <br/> |[<span data-ttu-id="9a900-114">定义用于确定业务服务器 2015 Skype 中的位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="9a900-114">Define the network elements used to determine location in Skype for Business Server 2015</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="9a900-115">为用户启用 E9-1-1 Skype 中的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="9a900-115">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>](enable-users.md) <br/> |[<span data-ttu-id="9a900-116">为用户启用 E9-1-1 Skype 中的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="9a900-116">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="9a900-117">管理业务服务器 2015 Skype SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="9a900-117">Manage locations for SIP trunk service providers in Skype for Business Server 2015</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="9a900-118">管理业务服务器 2015年中 Skype ELIN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="9a900-118">Manage locations for ELIN gateways in Skype for Business Server 2015</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="9a900-119">定义手动获取的业务服务器 2015年的 Skype 中的位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="9a900-119">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="9a900-120">定义手动获取的业务服务器 2015年的 Skype 中的位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="9a900-120">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="9a900-121">SIP 中继的设计 E9-1-1 Skype 中的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="9a900-121">Design the SIP trunk for E9-1-1 in Skype for Business Server 2015</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="9a900-122">为业务服务器 2015 Skype 中包括安全服务台</span><span class="sxs-lookup"><span data-stu-id="9a900-122">Include the security desk in Skype for Business Server 2015</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="9a900-123">为业务服务器 2015 Skype 中包括安全服务台</span><span class="sxs-lookup"><span data-stu-id="9a900-123">Include the security desk in Skype for Business Server 2015</span></span>](security-desk.md) <br/> |[<span data-ttu-id="9a900-124">规划业务服务器 2015 Skype 的位置策略</span><span class="sxs-lookup"><span data-stu-id="9a900-124">Plan location policies for Skype for Business Server 2015</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="9a900-125">为业务服务器 2015年选择 Skype E9-1-1 服务提供的商</span><span class="sxs-lookup"><span data-stu-id="9a900-125">Choose an E9-1-1 service provider for Skype for Business Server 2015</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="9a900-126">为业务服务器 2015年分配位置策略作用域中 Skype</span><span class="sxs-lookup"><span data-stu-id="9a900-126">Assign location policy scope in Skype for Business Server 2015</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="9a900-127">规划业务服务器 2015 Skype 的位置策略</span><span class="sxs-lookup"><span data-stu-id="9a900-127">Plan location policies for Skype for Business Server 2015</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="9a900-128">为业务服务器 2015年分配位置策略作用域中 Skype</span><span class="sxs-lookup"><span data-stu-id="9a900-128">Assign location policy scope in Skype for Business Server 2015</span></span>](location-policy-scope.md) <br/> ||
   

