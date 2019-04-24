---
title: 为业务服务器中 Skype 定义紧急呼叫要求
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: 总结了根据是否必须 SIP 中继 E9-1-1 服务提供商或 ELIN 网关启用业务 Server 企业语音，E9-1-1 Skype 中所需的步骤。
ms.openlocfilehash: 3ddcb25b86689f29831872f24a1893d5ff2f1f4c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206976"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="2953a-103">为业务服务器中 Skype 定义紧急呼叫要求</span><span class="sxs-lookup"><span data-stu-id="2953a-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="2953a-104">总结了根据是否必须 SIP 中继 E9-1-1 服务提供商或 ELIN 网关启用业务 Server 企业语音，E9-1-1 Skype 中所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="2953a-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="2953a-105">Skype 业务服务器 E9-1-1 部署之前，首先应该能够回答以下各节详细的问题。</span><span class="sxs-lookup"><span data-stu-id="2953a-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="2953a-106">您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="2953a-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="2953a-107">下表标识需要这些解决方案的每个查看此规划工作簿中的部分。</span><span class="sxs-lookup"><span data-stu-id="2953a-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="2953a-108">**按 E9-1-1 解决方案的类型显示的规划步骤**</span><span class="sxs-lookup"><span data-stu-id="2953a-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="2953a-109">**SIP 中继服务提供商**</span><span class="sxs-lookup"><span data-stu-id="2953a-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="2953a-110">**ELIN 网关**</span><span class="sxs-lookup"><span data-stu-id="2953a-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2953a-111">定义业务 Server 中 Skype E9-1-1 部署范围</span><span class="sxs-lookup"><span data-stu-id="2953a-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="2953a-112">定义业务 Server 中 Skype E9-1-1 部署范围</span><span class="sxs-lookup"><span data-stu-id="2953a-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="2953a-113">定义用于确定业务服务器中 Skype 位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="2953a-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="2953a-114">定义用于确定业务服务器中 Skype 位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="2953a-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="2953a-115">为用户启用 E9-1-1 在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="2953a-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="2953a-116">为用户启用 E9-1-1 在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="2953a-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="2953a-117">管理 Business Server Skype SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="2953a-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="2953a-118">管理 ELIN 网关 Skype 中的业务服务器的位置</span><span class="sxs-lookup"><span data-stu-id="2953a-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="2953a-119">定义手动获取业务服务器的 Skype 中的位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="2953a-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="2953a-120">定义手动获取业务服务器的 Skype 中的位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="2953a-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="2953a-121">SIP 中继的设计 E9-1-1 在 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="2953a-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="2953a-122">为业务服务器中 Skype 包括安全服务台</span><span class="sxs-lookup"><span data-stu-id="2953a-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="2953a-123">为业务服务器中 Skype 包括安全服务台</span><span class="sxs-lookup"><span data-stu-id="2953a-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="2953a-124">规划业务 Server Skype 的位置策略</span><span class="sxs-lookup"><span data-stu-id="2953a-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="2953a-125">选择 Skype for Business Server 的 E9-1-1 服务提供商</span><span class="sxs-lookup"><span data-stu-id="2953a-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="2953a-126">为业务服务器分配位置策略作用域中 Skype</span><span class="sxs-lookup"><span data-stu-id="2953a-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="2953a-127">规划业务 Server Skype 的位置策略</span><span class="sxs-lookup"><span data-stu-id="2953a-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="2953a-128">为业务服务器分配位置策略作用域中 Skype</span><span class="sxs-lookup"><span data-stu-id="2953a-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

