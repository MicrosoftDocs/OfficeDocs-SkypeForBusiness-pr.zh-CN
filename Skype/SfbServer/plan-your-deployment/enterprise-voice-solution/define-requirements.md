---
title: 在 Skype for Business Server 中定义紧急呼叫要求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: d891a212-8ad9-4bfa-9ca7-04921c46fb45
description: 总结了在 Skype for Business Server 企业语音 中启用 E9-1-1 所需的步骤，具体取决于您是否具有 SIP 中继 E9-1-1 服务提供商或 ELIN 网关。
ms.openlocfilehash: 8efd38657a80bee1ecd979e8730feacfb980053e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825812"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="9c027-103">在 Skype for Business Server 中定义紧急呼叫要求</span><span class="sxs-lookup"><span data-stu-id="9c027-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="9c027-104">总结了在 Skype for Business Server 企业语音 中启用 E9-1-1 所需的步骤，具体取决于您是否具有 SIP 中继 E9-1-1 服务提供商或 ELIN 网关。</span><span class="sxs-lookup"><span data-stu-id="9c027-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="9c027-105">在开始 Skype for Business Server E9-1-1 部署之前，应首先能够回答以下部分中详述的问题。</span><span class="sxs-lookup"><span data-stu-id="9c027-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="9c027-106">您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="9c027-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="9c027-107">下表标识了此规划工作簿中需要针对其中每个解决方案查看的部分。</span><span class="sxs-lookup"><span data-stu-id="9c027-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="9c027-108">**按 E9-1-1 解决方案的类型显示的规划步骤**</span><span class="sxs-lookup"><span data-stu-id="9c027-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="9c027-109">**SIP 中继服务提供商**</span><span class="sxs-lookup"><span data-stu-id="9c027-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="9c027-110">**ELIN 网关**</span><span class="sxs-lookup"><span data-stu-id="9c027-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="9c027-111">在 Skype for Business Server 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="9c027-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="9c027-112">在 Skype for Business Server 中定义 E9-1-1 部署的范围</span><span class="sxs-lookup"><span data-stu-id="9c027-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="9c027-113">定义用于确定 Skype for Business Server 中位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="9c027-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="9c027-114">定义用于确定 Skype for Business Server 中位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="9c027-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="9c027-115">在 Skype for Business Server 中为用户启用 E9-1-1</span><span class="sxs-lookup"><span data-stu-id="9c027-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="9c027-116">在 Skype for Business Server 中为用户启用 E9-1-1</span><span class="sxs-lookup"><span data-stu-id="9c027-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="9c027-117">在 Skype for Business Server 中管理 SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="9c027-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="9c027-118">在 Skype for Business Server 中管理 ELIN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="9c027-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="9c027-119">定义在 Skype for Business Server 中手动获取位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="9c027-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="9c027-120">定义在 Skype for Business Server 中手动获取位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="9c027-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="9c027-121">在 Skype for Business Server 中为 E9-1-1 设计 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="9c027-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="9c027-122">在 Skype for Business Server 中包括安全服务台</span><span class="sxs-lookup"><span data-stu-id="9c027-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="9c027-123">在 Skype for Business Server 中包括安全服务台</span><span class="sxs-lookup"><span data-stu-id="9c027-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="9c027-124">规划 Skype for Business Server 的位置策略</span><span class="sxs-lookup"><span data-stu-id="9c027-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="9c027-125">为 Skype for Business Server 选择 E9-1-1 服务提供商</span><span class="sxs-lookup"><span data-stu-id="9c027-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="9c027-126">在 Skype for Business Server 中分配位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="9c027-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="9c027-127">规划 Skype for Business Server 的位置策略</span><span class="sxs-lookup"><span data-stu-id="9c027-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="9c027-128">在 Skype for Business Server 中分配位置策略作用域</span><span class="sxs-lookup"><span data-stu-id="9c027-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

