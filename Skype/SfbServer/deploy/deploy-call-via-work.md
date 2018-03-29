---
title: 在 Skype for Business Server 2015 中部署单位电话呼叫
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要： 了解如何部署调用通过工作在 Skype 业务服务器 2015年的某些或所有用户。
ms.openlocfilehash: 325134bd4e24621bbb223ccc47180274256eaca2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a><span data-ttu-id="527fc-103">在 Skype for Business Server 2015 中部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="527fc-103">Deploy Call Via Work in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="527fc-104">**摘要：**了解如何部署调用通过工作在 Skype 业务服务器 2015年的某些或所有用户。</span><span class="sxs-lookup"><span data-stu-id="527fc-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server 2015 for some or all of your users.</span></span>
  
<span data-ttu-id="527fc-105">使用下列步骤为您的用户部署调用通过工作。</span><span class="sxs-lookup"><span data-stu-id="527fc-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="527fc-106">[用于调用通过工作在 Skype 的业务服务器 2015年计划](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)中讨论规划的考虑因素。</span><span class="sxs-lookup"><span data-stu-id="527fc-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="527fc-107">在以前版本的 Lync 服务器远程调用控制是一种功能，使用户能够控制手机 PBX Lync Server。</span><span class="sxs-lookup"><span data-stu-id="527fc-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="527fc-108">在 Skype 业务服务器，此功能已被调用通过工作。</span><span class="sxs-lookup"><span data-stu-id="527fc-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="527fc-109">通过工作的呼叫的先决条件</span><span class="sxs-lookup"><span data-stu-id="527fc-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="527fc-110">通过工作中调用使用统一通信 Web API (UCWA)，它的业务服务器前端服务器会自动在所有 Skype 上安装。</span><span class="sxs-lookup"><span data-stu-id="527fc-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="527fc-111">若要使用户调用通过工作，还必须满足以下先决条件到位：</span><span class="sxs-lookup"><span data-stu-id="527fc-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="527fc-112">您必须部署，中介服务器作为前端服务器的一部分或作为一个独立的角色。</span><span class="sxs-lookup"><span data-stu-id="527fc-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="527fc-113">您还必须部署 IP-PBX 网关。</span><span class="sxs-lookup"><span data-stu-id="527fc-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="527fc-114">所有的用户都将启用调用通过工作必须直接向内拨号 (DID) 的 PBX 电话系统。</span><span class="sxs-lookup"><span data-stu-id="527fc-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="527fc-115">您必须启用企业语音调用通过工作的所有用户。</span><span class="sxs-lookup"><span data-stu-id="527fc-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="527fc-116">当您执行此操作时，您必须配置为每个用户使用相应的 PBX 电话系统的相应 DID 号码业务未编号 Skype。</span><span class="sxs-lookup"><span data-stu-id="527fc-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="527fc-117">所有的用户都将使用调用通过工作必须具有**自动配置**其 Skype 业务客户端在其**高级连接**选项中选择。</span><span class="sxs-lookup"><span data-stu-id="527fc-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="527fc-118">这使客户端能够发现 UCWA Url。</span><span class="sxs-lookup"><span data-stu-id="527fc-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="527fc-119">**自动配置**为默认选择。</span><span class="sxs-lookup"><span data-stu-id="527fc-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="527fc-120">对于每个调用通过工作的用户，启用呼叫转移和并发响铃。</span><span class="sxs-lookup"><span data-stu-id="527fc-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="527fc-121">对于每个呼叫通过单位用户，请确保启用了拨入会议和会议拨出。</span><span class="sxs-lookup"><span data-stu-id="527fc-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="527fc-122">这使这些用户可以获得 Skype 进出业务会议。</span><span class="sxs-lookup"><span data-stu-id="527fc-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="527fc-123">确保每个呼叫通过单位用户禁用委派、 团队联络和响应组。</span><span class="sxs-lookup"><span data-stu-id="527fc-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="527fc-124">部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="527fc-124">Deploy Call Via Work</span></span>

<span data-ttu-id="527fc-125">先决条件就绪后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="527fc-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="527fc-126">创建部署 Skype 业务显示在 PBX 呼叫方 ID 的用户要调用调用通过工作全局的电话号码。</span><span class="sxs-lookup"><span data-stu-id="527fc-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="527fc-127">创建一个或多个调用通过工作策略</span><span class="sxs-lookup"><span data-stu-id="527fc-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="527fc-128">为每个用户都将启用调用通过工作分配调用通过工作策略</span><span class="sxs-lookup"><span data-stu-id="527fc-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="527fc-129">创建通过工号拨号全局电话号码</span><span class="sxs-lookup"><span data-stu-id="527fc-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="527fc-130">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="527fc-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="527fc-131">例如，以下 cmdlet 将全局电话号码设为 1-555-123-4567。</span><span class="sxs-lookup"><span data-stu-id="527fc-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="527fc-132">创建通过工号拨号策略</span><span class="sxs-lookup"><span data-stu-id="527fc-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="527fc-133">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="527fc-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    <span data-ttu-id="527fc-134">例如，以下 cmdlet 创建称为 ContosoUser1CvWP 的调用通过的工作策略，要求用户使用管理员回拨号码，并将该回叫号码设置为 1-555-789-1234。</span><span class="sxs-lookup"><span data-stu-id="527fc-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="527fc-135">向用户分配调用通过工作策略</span><span class="sxs-lookup"><span data-stu-id="527fc-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="527fc-136">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="527fc-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="527fc-137">例如，以下 cmdlet 将分配给名为**ContosoUser1**的用户的调用通过工作策略"ContosoUser1CvWP"。</span><span class="sxs-lookup"><span data-stu-id="527fc-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="527fc-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="527fc-138">See also</span></span>

#### 

[<span data-ttu-id="527fc-139">规划工作在 Skype 业务服务器 2015年通过调用</span><span class="sxs-lookup"><span data-stu-id="527fc-139">Plan for Call Via Work in Skype for Business Server 2015</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

