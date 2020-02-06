---
title: 在 Skype for Business 服务器中定义紧急呼叫的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 总结了在 Skype for Business 服务器企业语音中启用 E9 所需的步骤，具体取决于你是否拥有 SIP 中继 E9 服务提供商或 ELIN 网关。
ms.openlocfilehash: ffda7796390fea6c44d943770c9b4af6d299549a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803082"
---
# <a name="define-your-requirements-for-emergency-calls-in-skype-for-business-server"></a><span data-ttu-id="1309c-103">在 Skype for Business 服务器中定义紧急呼叫的要求</span><span class="sxs-lookup"><span data-stu-id="1309c-103">Define your requirements for emergency calls in Skype for Business Server</span></span>
 
<span data-ttu-id="1309c-104">总结了在 Skype for Business 服务器企业语音中启用 E9 所需的步骤，具体取决于你是否拥有 SIP 中继 E9 服务提供商或 ELIN 网关。</span><span class="sxs-lookup"><span data-stu-id="1309c-104">Summarizes the steps necessary for enabling E9-1-1 in Skype for Business Server Enterprise Voice, depending on whether you have a SIP trunk E9-1-1 service provider or an ELIN gateway.</span></span>
  
<span data-ttu-id="1309c-105">开始使用 Skype for Business Server E9 部署之前，应首先能够回答以下部分中详细介绍的问题。</span><span class="sxs-lookup"><span data-stu-id="1309c-105">Before you begin a Skype for Business Server E9-1-1 deployment, you should first be able to answer the questions detailed in the following sections.</span></span> <span data-ttu-id="1309c-106">您需要执行的规划取决于选择部署的 E9-1-1 解决方案的类型 - SIP 中继 E9-1-1 服务提供商或紧急位置标识符号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="1309c-106">The planning you need to do depends on the type of E9-1-1 solution that you choose to deploy—a SIP trunk E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway.</span></span> <span data-ttu-id="1309c-107">下表标识了此规划工作簿中每个解决方案需要检查的部分。</span><span class="sxs-lookup"><span data-stu-id="1309c-107">The following table identifies the sections in this planning workbook that you'll need to review for each of those solutions.</span></span>
  
<span data-ttu-id="1309c-108">**按 E9-1-1 解决方案的类型显示的规划步骤**</span><span class="sxs-lookup"><span data-stu-id="1309c-108">**Planning Steps by Type of E9-1-1 Solution**</span></span>

|<span data-ttu-id="1309c-109">**SIP 中继服务提供商**</span><span class="sxs-lookup"><span data-stu-id="1309c-109">**SIP trunk service provider**</span></span>|<span data-ttu-id="1309c-110">**ELIN 网关**</span><span class="sxs-lookup"><span data-stu-id="1309c-110">**ELIN gateway**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="1309c-111">在 Skype for Business 服务器中定义 E9 部署的范围</span><span class="sxs-lookup"><span data-stu-id="1309c-111">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |[<span data-ttu-id="1309c-112">在 Skype for Business 服务器中定义 E9 部署的范围</span><span class="sxs-lookup"><span data-stu-id="1309c-112">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>](scope.md) <br/> |
|[<span data-ttu-id="1309c-113">定义用于确定 Skype for Business 服务器中的位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="1309c-113">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |[<span data-ttu-id="1309c-114">定义用于确定 Skype for Business 服务器中的位置的网络元素</span><span class="sxs-lookup"><span data-stu-id="1309c-114">Define the network elements used to determine location in Skype for Business Server</span></span>](network-location.md) <br/> |
|[<span data-ttu-id="1309c-115">在 Skype for business 服务器中启用 E9-1-1 的用户</span><span class="sxs-lookup"><span data-stu-id="1309c-115">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |[<span data-ttu-id="1309c-116">在 Skype for business 服务器中启用 E9-1-1 的用户</span><span class="sxs-lookup"><span data-stu-id="1309c-116">Enable users for E9-1-1 in Skype for Business Server</span></span>](enable-users.md) <br/> |
|[<span data-ttu-id="1309c-117">在 Skype for Business Server 中管理 SIP 中继服务提供商的位置</span><span class="sxs-lookup"><span data-stu-id="1309c-117">Manage locations for SIP trunk service providers in Skype for Business Server</span></span>](manage-locations.md) <br/> |[<span data-ttu-id="1309c-118">管理 Skype for Business Server 中的 ELIN 网关的位置</span><span class="sxs-lookup"><span data-stu-id="1309c-118">Manage locations for ELIN gateways in Skype for Business Server</span></span>](elin-gateways.md) <br/> |
|[<span data-ttu-id="1309c-119">定义在 Skype for Business 服务器中手动获取位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="1309c-119">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |[<span data-ttu-id="1309c-120">定义在 Skype for Business 服务器中手动获取位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="1309c-120">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>](manually-acquiring-a-location.md) <br/> |
|[<span data-ttu-id="1309c-121">在 Skype for Business 服务器中设计 E9 的 SIP 主干-1-1</span><span class="sxs-lookup"><span data-stu-id="1309c-121">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>](design-the-sip-trunk.md) <br/> |[<span data-ttu-id="1309c-122">在 Skype for Business 服务器中包括安全桌面</span><span class="sxs-lookup"><span data-stu-id="1309c-122">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |
|[<span data-ttu-id="1309c-123">在 Skype for Business 服务器中包括安全桌面</span><span class="sxs-lookup"><span data-stu-id="1309c-123">Include the security desk in Skype for Business Server</span></span>](security-desk.md) <br/> |[<span data-ttu-id="1309c-124">为 Skype for Business Server 规划位置策略</span><span class="sxs-lookup"><span data-stu-id="1309c-124">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> |
|[<span data-ttu-id="1309c-125">选择 Skype for Business Server 的 E9-1-1 服务提供商</span><span class="sxs-lookup"><span data-stu-id="1309c-125">Choose an E9-1-1 service provider for Skype for Business Server</span></span>](choose-a-service-provider.md) <br/> |[<span data-ttu-id="1309c-126">在 Skype for Business 服务器中分配位置策略范围</span><span class="sxs-lookup"><span data-stu-id="1309c-126">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> |
|[<span data-ttu-id="1309c-127">为 Skype for Business Server 规划位置策略</span><span class="sxs-lookup"><span data-stu-id="1309c-127">Plan location policies for Skype for Business Server</span></span>](location-policies.md) <br/> ||
|[<span data-ttu-id="1309c-128">在 Skype for Business 服务器中分配位置策略范围</span><span class="sxs-lookup"><span data-stu-id="1309c-128">Assign location policy scope in Skype for Business Server</span></span>](location-policy-scope.md) <br/> ||
   

