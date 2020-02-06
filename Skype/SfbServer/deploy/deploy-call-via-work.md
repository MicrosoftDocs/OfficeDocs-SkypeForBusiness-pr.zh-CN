---
title: 通过 Skype for Business 服务器中的工作部署呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何在某些或所有用户的 Skype for Business 服务器中通过工作部署呼叫。
ms.openlocfilehash: 9b77207d6618e4a869ae369697bc8395aba81673
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791080"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a><span data-ttu-id="58c52-103">通过 Skype for Business 服务器中的工作部署呼叫</span><span class="sxs-lookup"><span data-stu-id="58c52-103">Deploy Call Via Work in Skype for Business Server</span></span>
 
<span data-ttu-id="58c52-104">**摘要：** 了解如何通过适用于部分或全部用户的 Skype for Business 服务器中的工作部署呼叫。</span><span class="sxs-lookup"><span data-stu-id="58c52-104">**Summary:** Learn how to deploy Call Via Work in Skype for Business Server for some or all of your users.</span></span>
  
<span data-ttu-id="58c52-105">使用这些步骤通过适用于您的用户的工作来部署呼叫。</span><span class="sxs-lookup"><span data-stu-id="58c52-105">Use these steps to deploy Call Via Work for your users.</span></span> <span data-ttu-id="58c52-106">[通过 Skype For Business Server 中的工作计划呼叫计划](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)中讨论了规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="58c52-106">Planning considerations are discussed in [Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md).</span></span> <span data-ttu-id="58c52-107">在早期版本的 Lync Server 远程呼叫控制中，支持用户使用 Lync Server 控制其 PBX 手机的功能。</span><span class="sxs-lookup"><span data-stu-id="58c52-107">In previous versions of Lync Server remote call control was a feature which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="58c52-108">在 Skype for Business 服务器中，此功能已替换为 "通过工作通话"。</span><span class="sxs-lookup"><span data-stu-id="58c52-108">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span> 
  
## <a name="prerequisites-for-call-via-work"></a><span data-ttu-id="58c52-109">通过工作进行通话的先决条件</span><span class="sxs-lookup"><span data-stu-id="58c52-109">Prerequisites for Call Via Work</span></span>

<span data-ttu-id="58c52-110">通过工作进行呼叫使用统一通信 Web API （UCWA），该 API 自动安装在所有 Skype for business 服务器前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="58c52-110">Call Via Work uses Unified Communications Web API (UCWA), which is automatically installed on all Skype for Business Server Front End Servers.</span></span> <span data-ttu-id="58c52-111">若要允许用户通过工作进行呼叫，还必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="58c52-111">To enable users for Call Via Work, you must also have the following prerequisites in place:</span></span> 
  
- <span data-ttu-id="58c52-112">你必须已部署中介服务器，或者作为前端服务器的一部分，或者作为独立角色进行部署。</span><span class="sxs-lookup"><span data-stu-id="58c52-112">You must have a Mediation Server deployed, either as part of a Front End Server or as a standalone role.</span></span> <span data-ttu-id="58c52-113">您还必须部署 IP-PBX 网关。</span><span class="sxs-lookup"><span data-stu-id="58c52-113">You must also deploy an IP-PBX gateway.</span></span>
    
- <span data-ttu-id="58c52-114">通过工作启用呼叫的所有用户必须在 PBX 电话系统上进行直接向内拨号（已执行）。</span><span class="sxs-lookup"><span data-stu-id="58c52-114">All users who will be enabled for Call Via Work must have a Direct Inward Dialing (DID) on the PBX phone system.</span></span> 
    
- <span data-ttu-id="58c52-115">您必须通过适用于企业语音的工作用户启用所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="58c52-115">You must enable all Call Via Work users for Enterprise Voice.</span></span> <span data-ttu-id="58c52-116">执行此操作时，必须为每位用户将 Skype for Business 的号码配置为相应的 PBX 电话系统对应的 "号码"。</span><span class="sxs-lookup"><span data-stu-id="58c52-116">When you do this, you must configure the Skype for Business DID number for each user to the corresponding DID number for the corresponding PBX phone system.</span></span> 
    
- <span data-ttu-id="58c52-117">通过工作进行呼叫的所有用户都必须在其 Skype for Business 客户端的 "**高级连接**" 选项中选中 "**自动配置**"。</span><span class="sxs-lookup"><span data-stu-id="58c52-117">All users who will be using Call Via Work must have **Automatic Configuration** selected in their **Advanced Connections** option in their Skype for Business client.</span></span> <span data-ttu-id="58c52-118">这使客户能够发现 UCWA Url。</span><span class="sxs-lookup"><span data-stu-id="58c52-118">This enables the client to discover the UCWA URLs.</span></span> <span data-ttu-id="58c52-119">**自动配置**为默认选择。</span><span class="sxs-lookup"><span data-stu-id="58c52-119">**Automatic Configuration** is the default selection.</span></span>
    
- <span data-ttu-id="58c52-120">对于每个通过工作用户拨打的电话，启用呼叫转接和同时拨打。</span><span class="sxs-lookup"><span data-stu-id="58c52-120">For each Call Via Work user, enable call forwarding and simultaneous ringing.</span></span> 
    
- <span data-ttu-id="58c52-121">对于每个通过工作用户进行的呼叫，请确保已启用电话拨入式会议和会议拨出。</span><span class="sxs-lookup"><span data-stu-id="58c52-121">For each Call Via Work user, ensure that dial-in conferencing and conferencing dial-out are enabled.</span></span> <span data-ttu-id="58c52-122">这使这些用户能够进入和注销 Skype for Business 会议。</span><span class="sxs-lookup"><span data-stu-id="58c52-122">This enables these users to get into and out of Skype for Business conferences.</span></span>
    
- <span data-ttu-id="58c52-123">确保通过工作用户对每个呼叫禁用委派、团队呼叫和响应组。</span><span class="sxs-lookup"><span data-stu-id="58c52-123">Ensure that delegation, team call, and response group are disabled for every Call Via Work user.</span></span>
    
## <a name="deploy-call-via-work"></a><span data-ttu-id="58c52-124">部署单位电话呼叫</span><span class="sxs-lookup"><span data-stu-id="58c52-124">Deploy Call Via Work</span></span>

<span data-ttu-id="58c52-125">先决条件就绪后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="58c52-125">After the prerequisites are in place, do the following:</span></span>
  
- <span data-ttu-id="58c52-126">为你的部署创建全球电话号码 Skype for Business 显示在通过工作电话进行呼叫的用户的 PBX 呼叫方 ID 上。</span><span class="sxs-lookup"><span data-stu-id="58c52-126">Create a global phone number for your deployment which Skype for Business displays on the PBX caller ID of users who are making Call Via Work calls.</span></span> 
    
- <span data-ttu-id="58c52-127">通过工作策略创建一个或多个通话</span><span class="sxs-lookup"><span data-stu-id="58c52-127">Create one or more Call Via Work policies</span></span>
    
- <span data-ttu-id="58c52-128">通过工作策略将呼叫分配给每个用户，这些用户将通过工作进行呼叫</span><span class="sxs-lookup"><span data-stu-id="58c52-128">Assign a Call Via Work policy to each user who will be enabled for Call Via Work</span></span>
    
### <a name="create-the-call-via-work-global-phone-number"></a><span data-ttu-id="58c52-129">创建通过工号拨号全局电话号码</span><span class="sxs-lookup"><span data-stu-id="58c52-129">Create the Call Via Work global phone number</span></span>

- <span data-ttu-id="58c52-130">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="58c52-130">Type the following cmdlet</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    <span data-ttu-id="58c52-131">例如，以下 cmdlet 将全局电话号码设为 1-555-123-4567。</span><span class="sxs-lookup"><span data-stu-id="58c52-131">For example, the following cmdlet sets the global phone number to 1-555-123-4567.</span></span>
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a><span data-ttu-id="58c52-132">创建通过工号拨号策略</span><span class="sxs-lookup"><span data-stu-id="58c52-132">Create a Call Via Work policy</span></span>

- <span data-ttu-id="58c52-133">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="58c52-133">Type the following cmdlet</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    <span data-ttu-id="58c52-134">例如，以下 cmdlet 通过名为 ContosoUser1CvWP 的工作策略创建呼叫，要求用户使用管理员回拨号码，并将该回拨号码设置为1-555-789-1234。</span><span class="sxs-lookup"><span data-stu-id="58c52-134">For example, the following cmdlet creates a Call Via Work policy called ContosoUser1CvWP, requires the user to use an admin callback number, and sets that callback number to 1-555-789-1234.</span></span>
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a><span data-ttu-id="58c52-135">通过工作策略向用户分配呼叫</span><span class="sxs-lookup"><span data-stu-id="58c52-135">Assign a Call Via Work policy to a user</span></span>

- <span data-ttu-id="58c52-136">键入以下 cmdlet</span><span class="sxs-lookup"><span data-stu-id="58c52-136">Type the following cmdlet</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    <span data-ttu-id="58c52-137">例如，以下 cmdlet 通过工作策略 "ContosoUser1CvWP" 将调用分配给名为**ContosoUser1**的用户。</span><span class="sxs-lookup"><span data-stu-id="58c52-137">For example, the following cmdlet assigns the Call Via Work policy "ContosoUser1CvWP" to the user named **ContosoUser1**.</span></span>
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a><span data-ttu-id="58c52-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58c52-138">See also</span></span>

[<span data-ttu-id="58c52-139">通过 Skype for Business Server 中的工作计划呼叫计划</span><span class="sxs-lookup"><span data-stu-id="58c52-139">Plan for Call Via Work in Skype for Business Server</span></span>](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

