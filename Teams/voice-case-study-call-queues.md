---
title: 团队语音 Contoso 个案研究
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
description: 多国公司的团队语音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785957"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="19660-103">Contoso 个案研究：自动助理和呼叫队列</span><span class="sxs-lookup"><span data-stu-id="19660-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="19660-104">Contoso 通过其本地 Skype for Business 部署熟悉自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="19660-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="19660-105">若要了解如何设置云自动助理，他们审阅[了什么是云自动助理？](what-are-phone-system-auto-attendants.md)和[小型企业版示例-设置自动助理教程](tutorial-org-aa.yml)。</span><span class="sxs-lookup"><span data-stu-id="19660-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="19660-106">若要了解可用于设置呼叫队列的选项，Contoso 已审阅 "[创建云呼叫队列](create-a-phone-system-call-queue.md)"。</span><span class="sxs-lookup"><span data-stu-id="19660-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="19660-107">根据网站类型的要求</span><span class="sxs-lookup"><span data-stu-id="19660-107">Requirements depending on site type</span></span>

<span data-ttu-id="19660-108">根据网站类型，Contoso 有以下需要：</span><span class="sxs-lookup"><span data-stu-id="19660-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="19660-109">网站类型 A：传统旧电话系统</span><span class="sxs-lookup"><span data-stu-id="19660-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="19660-110">网站类型将与接待员相关联的电话号码保留为其自动助理的编号。</span><span class="sxs-lookup"><span data-stu-id="19660-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="19660-111">其中每个站点的关键部门都有自己的通话队列，它们将路由到团队成员。</span><span class="sxs-lookup"><span data-stu-id="19660-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="19660-112">有一种网站混合使用手机系统和通话计划的直接路由和电话系统。</span><span class="sxs-lookup"><span data-stu-id="19660-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="19660-113">网站类型 B： Skype for Business 企业语音</span><span class="sxs-lookup"><span data-stu-id="19660-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="19660-114">网站类型 B 拥有迁移到团队所需的自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="19660-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="19660-115">Contoso 需要保留与自动助理相关联的电话号码。</span><span class="sxs-lookup"><span data-stu-id="19660-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="19660-116">Contoso 通过通话计划将大部分这些站点移动到电话系统。</span><span class="sxs-lookup"><span data-stu-id="19660-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="19660-117">但是，在通话计划不可用的几个位置中，Contoso 将这些网站移动到直接路由配置。</span><span class="sxs-lookup"><span data-stu-id="19660-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="19660-118">网站类型 C： Skype for Business 企业语音 & 传统旧式电话系统</span><span class="sxs-lookup"><span data-stu-id="19660-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="19660-119">网站类型 C 具有驻留在传统旧式电话系统中的现有自动助理。</span><span class="sxs-lookup"><span data-stu-id="19660-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="19660-120">此网站的决策和配置与网站类型 A 相同。</span><span class="sxs-lookup"><span data-stu-id="19660-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="19660-121">对于所有网站类型，Contoso 询问以下问题：</span><span class="sxs-lookup"><span data-stu-id="19660-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="19660-122">问：我们将使用新号码还是现有号码？</span><span class="sxs-lookup"><span data-stu-id="19660-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="19660-123">A： Contoso 决定使用现有电话号码分配给自动助理的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="19660-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="19660-124">问：自动助理是否可以用来接受拨入电话？</span><span class="sxs-lookup"><span data-stu-id="19660-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="19660-125">A： Contoso 决定设置营业时间，并在营业时间已重定向到 "时间超过" 自动助理后收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="19660-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="19660-126">问：如何将呼叫路由到呼叫队列中的成员：助理、串行或循环路由？</span><span class="sxs-lookup"><span data-stu-id="19660-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="19660-127">A： Contoso 决定使用助理路由，</span><span class="sxs-lookup"><span data-stu-id="19660-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="19660-128">问：如何确定用户何时应该或不应该进行呼叫？</span><span class="sxs-lookup"><span data-stu-id="19660-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="19660-129">A： Contoso 决定使用呼叫处理选项确定代理是否可用：基于状态的路由。</span><span class="sxs-lookup"><span data-stu-id="19660-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="19660-130">配置</span><span class="sxs-lookup"><span data-stu-id="19660-130">Configuration</span></span>

<span data-ttu-id="19660-131">设置自动助理和呼叫队列的步骤包括 "[管理资源帐户](manage-resource-accounts.md)" 中列出的以下内容：</span><span class="sxs-lookup"><span data-stu-id="19660-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="19660-132">获取服务号码。</span><span class="sxs-lookup"><span data-stu-id="19660-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="19660-133">获取免费电话系统-虚拟用户许可证或付费电话系统许可证，以便与资源帐户或电话系统许可证配合使用。</span><span class="sxs-lookup"><span data-stu-id="19660-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="19660-134">创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="19660-134">Create the resource account.</span></span> <span data-ttu-id="19660-135">需要使用自动助理或呼叫队列才能拥有关联的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="19660-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="19660-136">为资源帐户分配电话系统或电话系统-虚拟用户许可证。</span><span class="sxs-lookup"><span data-stu-id="19660-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="19660-137">有关详细信息，请参阅[Microsoft 365 Phone 系统-虚拟用户许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)。</span><span class="sxs-lookup"><span data-stu-id="19660-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="19660-138">将服务电话号码分配给您为其分配了许可证的资源帐户。</span><span class="sxs-lookup"><span data-stu-id="19660-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="19660-139">创建电话系统呼叫队列或自动助理</span><span class="sxs-lookup"><span data-stu-id="19660-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="19660-140">将资源帐户与呼叫队列或自动助理链接。</span><span class="sxs-lookup"><span data-stu-id="19660-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="19660-141">带有直接路由的手机系统的站点</span><span class="sxs-lookup"><span data-stu-id="19660-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="19660-142">Contoso 必须将本地运营商提供的电话号码设置为 Office 365 中的服务号码。</span><span class="sxs-lookup"><span data-stu-id="19660-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="19660-143">若要通过直接路由设置可用的电话号码，Contoso 按照 "[管理资源帐户](manage-resource-accounts.md)" 中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="19660-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="19660-144">由于 Office 365 不知道本地电话号码，Contoso 使用 PowerShell 完成设置。</span><span class="sxs-lookup"><span data-stu-id="19660-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="19660-145">若要配置云自动助理，Contoso 按照[设置云自动助理](create-a-phone-system-auto-attendant.md)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="19660-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="19660-146">若要设置云呼叫队列，Contoso 按照[创建云呼叫队列](create-a-phone-system-call-queue.md)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="19660-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="19660-147">带有呼叫计划的带有电话系统的站点</span><span class="sxs-lookup"><span data-stu-id="19660-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="19660-148">Contoso 必须将用于 Skype for Business 企业语音自动助理的电话号码移植到 Office 365 电话系统。</span><span class="sxs-lookup"><span data-stu-id="19660-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="19660-149">这允许将同一号码分配为作为自动助理使用的服务号码。</span><span class="sxs-lookup"><span data-stu-id="19660-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="19660-150">若要移植电话号码，Contoso 按照[向团队转移电话号码](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)的说明进行操作，并在[管理您的组织的电话号码](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)时获得其他指导。</span><span class="sxs-lookup"><span data-stu-id="19660-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="19660-151">若要配置云自动助理，Contoso 按照[设置云自动助理](create-a-phone-system-auto-attendant.md)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="19660-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="19660-152">若要设置云呼叫队列，Contoso 按照[创建云呼叫队列](create-a-phone-system-call-queue.md)中概述的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="19660-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 