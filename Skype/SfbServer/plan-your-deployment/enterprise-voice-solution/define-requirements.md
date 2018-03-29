---
title: 在 Skype for Business Server 2015 中定义紧急呼叫要求
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: 总结了业务服务器企业语音，具体取决于您是否有一个 SIP 中继 E9-1-1 服务提供商或 ELIN 网关启用 E9-1-1 在 Skype 所需要的步骤。
ms.openlocfilehash: 69f6f9189db9293e0c171072db4a6a6fcf7a935c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server-2015"></a><span data-ttu-id="649c5-103">在 Skype for Business Server 2015 中定义紧急呼叫要求</span><span class="sxs-lookup"><span data-stu-id="649c5-103">Define your requirements for emergency calls in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="649c5-104">总结了业务服务器企业语音，具体取决于您是否有一个 SIP 中继 E9-1-1 服务提供商或 ELIN 网关启用 E9-1-1 在 Skype 所需要的步骤。</span><span class="sxs-lookup"><span data-stu-id="649c5-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="649c5-105">Skype 业务服务器 E9-1-1 部署之前，应首先能够回答以下各节中详细介绍的问题。</span><span class="sxs-lookup"><span data-stu-id="649c5-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="649c5-106">您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="649c5-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="649c5-107">下表列出了您将需要查看这些解决方案中的每个该规划工作簿中的部分。</span><span class="sxs-lookup"><span data-stu-id="649c5-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="649c5-108">**规划步骤中，通过种 E9-1-1 的解决方案**</span><span class="sxs-lookup"><span data-stu-id="649c5-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="649c5-109">**SIP 中继服务提供商**</span><span class="sxs-lookup"><span data-stu-id="649c5-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="649c5-110">**ELIN 网关**</span><span class="sxs-lookup"><span data-stu-id="649c5-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="649c5-111">定义部署范围的 E9-1-1 在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-111">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>](scope.md) <br/> |[<span data-ttu-id="649c5-112">定义部署范围的 E9-1-1 在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-112">Define the scope of the E9-1-1 deployment in Skype for Business Server 2015</span></span>](scope.md) <br/> |
|[<span data-ttu-id="649c5-113">定义用于确定业务服务器 2015年位置在 Skype 的网络元素</span><span class="sxs-lookup"><span data-stu-id="649c5-113">Define the network elements used to determine location in Skype for Business Server 2015</span></span>](network-location.md) <br/> |[<span data-ttu-id="649c5-114">定义用于确定业务服务器 2015年位置在 Skype 的网络元素</span><span class="sxs-lookup"><span data-stu-id="649c5-114">Define the network elements used to determine location in Skype for Business Server 2015</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="649c5-115">允许用户使用的 E9-1-1 在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-115">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>](enable-users.md) <br/> |[<span data-ttu-id="649c5-116">允许用户使用的 E9-1-1 在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-116">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="649c5-117">管理业务服务器 2015 SIP 中继服务提供商 Skype 在位置</span><span class="sxs-lookup"><span data-stu-id="649c5-117">Manage locations for SIP trunk service providers in Skype for Business Server 2015</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="649c5-118">管理业务服务器 2015 ELIN 在 Skype 的网关的位置</span><span class="sxs-lookup"><span data-stu-id="649c5-118">Manage locations for ELIN gateways in Skype for Business Server 2015</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="649c5-119">定义用户体验手动为业务服务器 2015年收购 Skype 的位置</span><span class="sxs-lookup"><span data-stu-id="649c5-119">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="649c5-120">定义用户体验手动为业务服务器 2015年收购 Skype 的位置</span><span class="sxs-lookup"><span data-stu-id="649c5-120">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="649c5-121">设计 SIP 中继 E9-1-1 在 Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-121">Design the SIP trunk for E9-1-1 in Skype for Business Server 2015</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="649c5-122">包括的保安在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-122">Include the security desk in Skype for Business Server 2015</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="649c5-123">包括的保安在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-123">Include the security desk in Skype for Business Server 2015</span></span>](security-desk.md) <br/> |[<span data-ttu-id="649c5-124">Skype 的位置策略规划业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-124">Plan location policies for Skype for Business Server 2015</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="649c5-125">选择业务服务器 2015年 E9-1-1 服务提供商 Skype</span><span class="sxs-lookup"><span data-stu-id="649c5-125">Choose an E9-1-1 service provider for Skype for Business Server 2015</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="649c5-126">为业务服务器 2015年分配在 Skype 的位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="649c5-126">Assign location policy scope in Skype for Business Server 2015</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="649c5-127">Skype 的位置策略规划业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="649c5-127">Plan location policies for Skype for Business Server 2015</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="649c5-128">为业务服务器 2015年分配在 Skype 的位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="649c5-128">Assign location policy scope in Skype for Business Server 2015</span></span>](location-policy-scope.md) <br/> ||
   

