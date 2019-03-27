---
title: 部署呼叫通过业务服务器 Skype 中工作
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要： 了解如何部署为部分或全部用户呼叫通过单位电话的 Skype 业务服务器。
ms.openlocfilehash: d0cee2cbf3a88514983efd77e2b1728b2df1e792
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879432"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="01687-103">部署呼叫通过业务服务器 Skype 中工作</span><span class="sxs-lookup"><span data-stu-id="01687-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="01687-104">**摘要：** 了解如何部署为部分或全部用户呼叫通过单位电话的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="01687-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="01687-105">使用以下步骤为用户部署通过单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="01687-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="01687-106">[规划呼叫通过中工作的企业服务器的 Skype](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)中讨论了规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="01687-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="01687-107">在早期版本的 Lync Server 远程呼叫控制是一种功能，允许用户控制其 PBX 电话与 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="01687-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="01687-108">在业务服务器 Skype，此功能已取代与通过单位电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="01687-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="01687-109">用单位电话呼叫的先决条件</span><span class="sxs-lookup"><span data-stu-id="01687-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="01687-110">通过单位电话呼叫使用统一通信 Web API (UCWA)，其上自动安装所有 Skype 的业务 Server 前端服务器。</span><span class="sxs-lookup"><span data-stu-id="01687-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="01687-111">若要为用户启用呼叫通过单位电话，您必须具有就地以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="01687-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="01687-112">您必须具有中介服务器部署，前端服务器的一部分或作为独立角色。</span><span class="sxs-lookup"><span data-stu-id="01687-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="01687-113">您还必须部署 IP-PBX 网关。</span><span class="sxs-lookup"><span data-stu-id="01687-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="01687-114">将启用呼叫通过单位电话的所有用户必须在 PBX 电话系统上都具有外线直拨分机 (DID)。</span><span class="sxs-lookup"><span data-stu-id="01687-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="01687-115">您必须启用企业语音呼叫通过单位电话的所有用户。</span><span class="sxs-lookup"><span data-stu-id="01687-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="01687-116">时执行此操作时，您必须配置为每个用户使用的相应的 PBX 电话系统的相应 DID 号码业务 DID 号码 Skype。</span><span class="sxs-lookup"><span data-stu-id="01687-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="01687-117">将使用呼叫通过单位电话的所有用户必须都具有**自动配置**其 Skype 业务客户端中其**高级连接**选项中选择。</span><span class="sxs-lookup"><span data-stu-id="01687-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="01687-118">这样，客户端可以发现 UCWA Url。</span><span class="sxs-lookup"><span data-stu-id="01687-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="01687-119">**自动配置**为默认选择。</span><span class="sxs-lookup"><span data-stu-id="01687-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="01687-120">对于每个呼叫通过单位电话用户，启用呼叫转接和同时响铃。</span><span class="sxs-lookup"><span data-stu-id="01687-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="01687-121">为每个呼叫通过单位电话用户，确保启用了电话拨入式会议和拨出式会议。</span><span class="sxs-lookup"><span data-stu-id="01687-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="01687-122">这样，这些用户获得业务会议和 Skype 注销。</span><span class="sxs-lookup"><span data-stu-id="01687-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="01687-123">确保通过单位电话呼叫中的每个用户禁用委派、 团队呼叫和响应组。</span><span class="sxs-lookup"><span data-stu-id="01687-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="01687-124">部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="01687-124">Deploy Call Via Work</span></span>

<span data-ttu-id="01687-125">先决条件就绪后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01687-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="01687-126">创建部署上正在呼叫通过单位电话的呼叫的用户的 PBX 呼叫者 ID 显示 for Business 的 Skype 全局电话号码。</span><span class="sxs-lookup"><span data-stu-id="01687-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="01687-127">创建一个或多个呼叫通过单位电话的策略</span><span class="sxs-lookup"><span data-stu-id="01687-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="01687-128">通过单位电话呼叫策略分配给每个用户都将启用通过单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="01687-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="01687-129">创建通过工号拨号全局电话号码</span><span class="sxs-lookup"><span data-stu-id="01687-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="01687-130">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01687-130">Type the following cmdlet</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="01687-131">例如，以下 cmdlet 将全局电话号码设为 1-555-123-4567。</span><span class="sxs-lookup"><span data-stu-id="01687-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="01687-132">创建通过工号拨号策略</span><span class="sxs-lookup"><span data-stu-id="01687-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="01687-133">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01687-133">Type the following cmdlet</span></span>
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="01687-134">例如，以下 cmdlet 创建名为 ContosoUser1CvWP 呼叫通过单位电话策略、 要求用户使用管理员回拨号码，并将该回拨号码设置为 1-555-789-1234。</span><span class="sxs-lookup"><span data-stu-id="01687-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="01687-135">为用户分配呼叫通过工作策略</span><span class="sxs-lookup"><span data-stu-id="01687-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="01687-136">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01687-136">Type the following cmdlet</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="01687-137">例如，以下 cmdlet 将"ContosoUser1CvWP"的通过单位电话呼叫策略分配给名为**ContosoUser1**的用户。</span><span class="sxs-lookup"><span data-stu-id="01687-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="01687-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01687-138">See also</span></span>

[<span data-ttu-id="01687-139">规划用单位电话的 Skype 业务服务器的呼叫</span><span class="sxs-lookup"><span data-stu-id="01687-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

