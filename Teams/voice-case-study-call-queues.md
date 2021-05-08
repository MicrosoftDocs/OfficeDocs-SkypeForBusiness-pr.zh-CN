---
title: Teams Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams多语言公司语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0cb8029a8f4e979a76afe069ee9b22e7be897913
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121290"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="8c684-103">Contoso 案例研究：自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="8c684-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="8c684-104">Contoso 熟悉自动助理和从本地部署呼叫Skype for Business队列。</span><span class="sxs-lookup"><span data-stu-id="8c684-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8c684-105">为了了解如何设置云自动助理和呼叫队列，他们查看了规划Teams自动助理[和呼叫队列。](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="8c684-105">To understand how to set up Cloud auto attendants and call queues, they reviewed [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md).</span></span>

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="8c684-106">要求，具体取决于网站类型</span><span class="sxs-lookup"><span data-stu-id="8c684-106">Requirements depending on site type</span></span>

<span data-ttu-id="8c684-107">根据站点类型，Contoso 具有以下需求：</span><span class="sxs-lookup"><span data-stu-id="8c684-107">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="8c684-108">站点类型 A：传统传统电话系统</span><span class="sxs-lookup"><span data-stu-id="8c684-108">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="8c684-109">网站类型 A 需要保留与其自动助理号码相同的与接待员相关联的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8c684-109">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="8c684-110">每个网站的关键部门都有自己的呼叫队列，这些队列将路由到团队成员。</span><span class="sxs-lookup"><span data-stu-id="8c684-110">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="8c684-111">网站混合使用直接路由和电话系统路由电话系统呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="8c684-111">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="8c684-112">站点类型 B：Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="8c684-112">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="8c684-113">站点类型 B 有现有的自动助理和呼叫队列，这些队列需要迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="8c684-113">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="8c684-114">Contoso 需要保留与自动助理关联的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8c684-114">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="8c684-115">Contoso 移动了这些网站中的大多数电话系统套餐。</span><span class="sxs-lookup"><span data-stu-id="8c684-115">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="8c684-116">但是，在呼叫计划不可用的少数位置，Contoso 将这些站点移到了直接路由配置。</span><span class="sxs-lookup"><span data-stu-id="8c684-116">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="8c684-117">站点类型 C：Skype for Business 企业语音 &传统旧电话系统</span><span class="sxs-lookup"><span data-stu-id="8c684-117">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="8c684-118">站点类型 C 具有驻留在传统旧电话系统中的现有自动助理。</span><span class="sxs-lookup"><span data-stu-id="8c684-118">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="8c684-119">此站点的决策和配置与站点类型 A 相同。</span><span class="sxs-lookup"><span data-stu-id="8c684-119">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="8c684-120">对于所有网站类型，Contoso 询问了以下问题：</span><span class="sxs-lookup"><span data-stu-id="8c684-120">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="8c684-121">问：我们将使用新号码还是现有号码？</span><span class="sxs-lookup"><span data-stu-id="8c684-121">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="8c684-122">答：Contoso 决定使用现有电话号码分配给自动助理的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="8c684-122">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="8c684-123">问：何时可以使用自动助理接受传入呼叫？</span><span class="sxs-lookup"><span data-stu-id="8c684-123">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="8c684-124">答：Contoso 决定设置营业时间，将营业时间后收到的呼叫重定向到"非工作时间"自动助理。</span><span class="sxs-lookup"><span data-stu-id="8c684-124">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="8c684-125">问：如何将呼叫路由到呼叫队列中的成员：attendant、serial 或轮循机制路由？</span><span class="sxs-lookup"><span data-stu-id="8c684-125">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="8c684-126">答：Contoso 决定使用 Attendant 路由，</span><span class="sxs-lookup"><span data-stu-id="8c684-126">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="8c684-127">问：如何确定用户何时应或不应进行呼叫？</span><span class="sxs-lookup"><span data-stu-id="8c684-127">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="8c684-128">答：Contoso 决定使用呼叫处理选项来确定代理是否可用：基于状态的路由。</span><span class="sxs-lookup"><span data-stu-id="8c684-128">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="8c684-129">配置</span><span class="sxs-lookup"><span data-stu-id="8c684-129">Configuration</span></span>

<span data-ttu-id="8c684-130">设置自动助理和呼叫队列的步骤包括管理资源帐户 [中概述的以下内容](manage-resource-accounts.md)：</span><span class="sxs-lookup"><span data-stu-id="8c684-130">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="8c684-131">获取服务编号。</span><span class="sxs-lookup"><span data-stu-id="8c684-131">Obtain a service number.</span></span> 

2. <span data-ttu-id="8c684-132">获取免费电话系统 - 虚拟用户许可证或付费电话系统许可证，以用于资源帐户或电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="8c684-132">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="8c684-133">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c684-133">Create the resource account.</span></span> <span data-ttu-id="8c684-134">需要自动助理或呼叫队列才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c684-134">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="8c684-135">将电话系统或电话系统 - 虚拟用户许可证分配给资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8c684-135">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="8c684-136">有关详细信息，请参阅 Microsoft 365 电话系统[– 虚拟用户许可证](./teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-136">For more information, see [Microsoft 365 Phone System – Virtual User license](./teams-add-on-licensing/virtual-user.md).</span></span>

5. <span data-ttu-id="8c684-137">将服务电话号码分配给分配给资源帐户的许可证。</span><span class="sxs-lookup"><span data-stu-id="8c684-137">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="8c684-138">创建电话系统呼叫队列或自动助理</span><span class="sxs-lookup"><span data-stu-id="8c684-138">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="8c684-139">将资源帐户与呼叫队列或自动助理关联。</span><span class="sxs-lookup"><span data-stu-id="8c684-139">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="8c684-140">使用直接电话系统路由的站点</span><span class="sxs-lookup"><span data-stu-id="8c684-140">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="8c684-141">Contoso 必须设置本地运营商提供的电话号码作为 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8c684-141">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="8c684-142">为了设置通过直接路由提供的电话号码，Contoso 按照管理资源帐户 [中的说明进行操作](manage-resource-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-142">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="8c684-143">由于Office 365不知道本地电话号码，Contoso 使用 PowerShell 完成设置。</span><span class="sxs-lookup"><span data-stu-id="8c684-143">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="8c684-144">为了配置云自动助理，Contoso 遵循了设置云自动助理 [中概述的步骤](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-144">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="8c684-145">为了设置云呼叫队列，Contoso 遵循创建云呼叫队列 [中概述的步骤](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-145">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="8c684-146">具有通话电话系统套餐的网站</span><span class="sxs-lookup"><span data-stu-id="8c684-146">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="8c684-147">Contoso 必须将用于自动助理的电话号码Skype for Business 企业语音自动助理Office 365 电话系统。</span><span class="sxs-lookup"><span data-stu-id="8c684-147">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="8c684-148">这允许将同一号码分配为用作自动助理的服务号码。</span><span class="sxs-lookup"><span data-stu-id="8c684-148">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="8c684-149">为了转转电话号码，Contoso 按照将电话号码转接[](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md)到Teams在管理组织的电话号码中获得了[其他指导](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-149">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) and obtained additional guidance at [Manage phone numbers for your organization](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="8c684-150">为了配置云自动助理，Contoso 遵循了设置云自动助理 [中概述的步骤](create-a-phone-system-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-150">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="8c684-151">为了设置云呼叫队列，Contoso 遵循创建云呼叫队列 [中概述的步骤](create-a-phone-system-call-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="8c684-151">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

