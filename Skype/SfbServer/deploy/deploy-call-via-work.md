---
title: 在 Skype for Business Server 中部署通过工位呼叫
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 摘要：了解如何在 Skype for Business Server 中为部分或所有用户部署通过工位呼叫。
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825002"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="01b7b-103">在 Skype for Business Server 中部署通过工位呼叫</span><span class="sxs-lookup"><span data-stu-id="01b7b-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="01b7b-104">**摘要：** 了解如何在 Skype for Business Server 中为部分或所有用户部署通过工位呼叫。</span><span class="sxs-lookup"><span data-stu-id="01b7b-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="01b7b-105">使用以下步骤为用户部署通过工位呼叫。</span><span class="sxs-lookup"><span data-stu-id="01b7b-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="01b7b-106">规划注意事项在 Plan [for Call Via Work in Skype for Business Server 中进行讨论](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)。</span><span class="sxs-lookup"><span data-stu-id="01b7b-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="01b7b-107">在早期版本的 Lync Server 远程呼叫控制中，该功能使用户能够使用 Lync Server 控制 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="01b7b-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="01b7b-108">在 Skype for Business Server 中，此功能已替换为通过工位电话呼叫功能。</span><span class="sxs-lookup"><span data-stu-id="01b7b-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="01b7b-109">通过工次电话呼叫的先决条件</span><span class="sxs-lookup"><span data-stu-id="01b7b-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="01b7b-110">通过工次电话呼叫使用 UCWA (统一通信 Web API) ，它会自动安装在所有 Skype for Business Server 前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="01b7b-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="01b7b-111">若要为用户启用通过工位电话呼叫，还必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="01b7b-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="01b7b-112">必须部署中介服务器（作为前端服务器的一部分或作为独立角色）。</span><span class="sxs-lookup"><span data-stu-id="01b7b-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="01b7b-113">还必须部署 IP-PBX 网关。</span><span class="sxs-lookup"><span data-stu-id="01b7b-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="01b7b-114">将启用通过工号拨号的所有用户都必须在 PBX 电话系统 (DID) 直拨拨号码。</span><span class="sxs-lookup"><span data-stu-id="01b7b-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="01b7b-115">必须为所有通过工位呼叫的用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="01b7b-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="01b7b-116">这样做时，必须将每个用户的 Skype for Business DID 号码配置为相应的 PBX 电话系统的对应 DID 号码。</span><span class="sxs-lookup"><span data-stu-id="01b7b-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="01b7b-117">将使用单位电话呼叫的所有用户都必须在 **Skype** for Business客户端的高级连接选项中选中自动配置。</span><span class="sxs-lookup"><span data-stu-id="01b7b-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="01b7b-118">这使客户端能够发现 UCWA URL。</span><span class="sxs-lookup"><span data-stu-id="01b7b-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="01b7b-119">**自动配置** 是默认选择。</span><span class="sxs-lookup"><span data-stu-id="01b7b-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="01b7b-120">对于每个通过工位呼叫的用户，启用呼叫转发和同时响铃。</span><span class="sxs-lookup"><span data-stu-id="01b7b-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="01b7b-121">对于每个通过工号拨号的用户，确保启用了电话拨入式会议和会议拨出。</span><span class="sxs-lookup"><span data-stu-id="01b7b-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="01b7b-122">这使这些用户可以进入和退出 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="01b7b-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="01b7b-123">确保已针对每个通过工位呼叫的用户禁用委派、团队呼叫和响应组。</span><span class="sxs-lookup"><span data-stu-id="01b7b-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="01b7b-124">部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="01b7b-124">Deploy Call Via Work</span></span>

<span data-ttu-id="01b7b-125">在先决条件就位后，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="01b7b-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="01b7b-126">为部署创建全局电话号码，Skype for Business 将在进行通过工号呼叫的用户的 PBX 呼叫者 ID 上显示该号码。</span><span class="sxs-lookup"><span data-stu-id="01b7b-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="01b7b-127">创建一个或多个通过工位呼叫策略</span><span class="sxs-lookup"><span data-stu-id="01b7b-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="01b7b-128">为将启用通过工位电话呼叫的每个用户分配"通过工位呼叫"策略</span><span class="sxs-lookup"><span data-stu-id="01b7b-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="01b7b-129">创建通过工号呼叫全局电话号码</span><span class="sxs-lookup"><span data-stu-id="01b7b-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="01b7b-130">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01b7b-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="01b7b-131">例如，以下 cmdlet 将全局电话号码设置为 1-555-123-4567。</span><span class="sxs-lookup"><span data-stu-id="01b7b-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="01b7b-132">创建通过工位呼叫策略</span><span class="sxs-lookup"><span data-stu-id="01b7b-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="01b7b-133">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01b7b-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="01b7b-134">例如，以下 cmdlet 创建名为 ContosoUser1CvWP 的"通过工号呼叫"策略，要求用户使用管理员回拨号码，并设置该回拨号码为 1-555-789-1234。</span><span class="sxs-lookup"><span data-stu-id="01b7b-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="01b7b-135">向用户分配通过工位呼叫策略</span><span class="sxs-lookup"><span data-stu-id="01b7b-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="01b7b-136">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="01b7b-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="01b7b-137">例如，以下 cmdlet 将"通过工号呼叫"策略"ContosoUser1CvWP"分配给名为 **ContosoUser1 的用户**。</span><span class="sxs-lookup"><span data-stu-id="01b7b-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="01b7b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01b7b-138">See also</span></span>

[<span data-ttu-id="01b7b-139">在 Skype for Business Server 中规划通过工位呼叫</span><span class="sxs-lookup"><span data-stu-id="01b7b-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

