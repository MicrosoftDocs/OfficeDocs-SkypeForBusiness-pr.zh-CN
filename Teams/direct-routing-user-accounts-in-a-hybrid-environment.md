---
title: 混合环境中的用户帐户与 PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解用户创建的不同组合以及支持或不支持的组合。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bdab33d6f1f009ce51afe999923f4f6f5d1905a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141075"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a><span data-ttu-id="f919d-103">采用 PSTN 连接的混合环境中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="f919d-103">User accounts in a hybrid environment with PSTN connectivity</span></span>

## <a name="about-the-environment"></a><span data-ttu-id="f919d-104">关于环境</span><span class="sxs-lookup"><span data-stu-id="f919d-104">About the environment</span></span>

<span data-ttu-id="f919d-105">本文适用于您拥有以下所有内容的环境：</span><span class="sxs-lookup"><span data-stu-id="f919d-105">This article applies to environments in which you have all of the following:</span></span> 
 
- <span data-ttu-id="f919d-106">Skype for Business 服务器或 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f919d-106">Skype for Business Server or Lync Server 2013</span></span> 
- <span data-ttu-id="f919d-107">Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="f919d-107">An Office 365 tenant</span></span> 
- <span data-ttu-id="f919d-108">在 Skype for Business 服务器与 Skype for business Online 或 Microsoft 团队租户之间配置的混合连接</span><span class="sxs-lookup"><span data-stu-id="f919d-108">Hybrid connectivity configured between the Skype for Business Server and Skype for Business Online or Microsoft Teams tenant</span></span> 
- <span data-ttu-id="f919d-109">在客户端上启用和接收公共交换电话网络（PSTN）呼叫的用户</span><span class="sxs-lookup"><span data-stu-id="f919d-109">Users who are enabled to make and receive Public Switched Telephone Network (PSTN) calls to and from the client</span></span>

 
<span data-ttu-id="f919d-110">如果你有其他环境（如 Skype for business 云连接器版）、混合未配置或你的用户未启用 PSTN 呼叫，则 "可支持性" 矩阵将有所不同。</span><span class="sxs-lookup"><span data-stu-id="f919d-110">If you have a different environment (such as Skype for Business Cloud Connector Edition), hybrid is not configured, or your users are not enabled for PSTN calls, the supportability matrix will be different.</span></span>  

## <a name="about-the-combinations-and-the-supportability-statement"></a><span data-ttu-id="f919d-111">关于组合和可支持性语句</span><span class="sxs-lookup"><span data-stu-id="f919d-111">About the combinations and the supportability statement</span></span>  

<span data-ttu-id="f919d-112">具有 PSTN 连接的 Skype for business 混合环境提供了有关提供用户服务的位置以及如何设置和管理用户帐户的灵活性。</span><span class="sxs-lookup"><span data-stu-id="f919d-112">A Skype for Business hybrid environment with PSTN connectivity provides flexibility regarding where user services are provided and how user accounts are provisioned and managed.</span></span> <span data-ttu-id="f919d-113">但是，丰富的选项可能会创建一些不受支持的组合。</span><span class="sxs-lookup"><span data-stu-id="f919d-113">But the abundance of options might create some unsupported combinations.</span></span> <span data-ttu-id="f919d-114">本部分介绍用户创建的不同组合，后跟一个可支持性语句。</span><span class="sxs-lookup"><span data-stu-id="f919d-114">This section explains different combinations of user creation, followed by a supportability statement.</span></span>


<span data-ttu-id="f919d-115">**码**</span><span class="sxs-lookup"><span data-stu-id="f919d-115">**Definitions:**</span></span>   
- <span data-ttu-id="f919d-116">**企业语音：** 用于向使用本地 Skype for business 用户帐户的用户提供对 PSTN 的访问的选项。</span><span class="sxs-lookup"><span data-stu-id="f919d-116">**Enterprise Voice:** Option to provide access to PSTN for users with on-premises Skype for Business user account.</span></span> <span data-ttu-id="f919d-117">本地 Skype for Business 中介服务器向 PSTN 提供 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="f919d-117">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span>  
- <span data-ttu-id="f919d-118">**混合语音连接：** 用于为使用 Skype for business Online 帐户的用户提供对 PSTN 的访问的选项。</span><span class="sxs-lookup"><span data-stu-id="f919d-118">**Hybrid Voice Connectivity:** Option to provide access to PSTN for users with Skype for Business Online account.</span></span> <span data-ttu-id="f919d-119">本地 Skype for Business 中介服务器向 PSTN 提供 interconnectivity。</span><span class="sxs-lookup"><span data-stu-id="f919d-119">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span> 
- <span data-ttu-id="f919d-120">**直接路由：** 选项，为使用 Microsoft 团队客户端的联机 Skype for Business 帐户、Microsoft 团队许可证的用户提供对 PSTN 的访问。</span><span class="sxs-lookup"><span data-stu-id="f919d-120">**Direct routing:** Option to provide access to PSTN for users with online Skype for Business account, Microsoft Teams license, using Microsoft Teams client.</span></span> <span data-ttu-id="f919d-121">SBC 已连接到 Office 365 中的 SIP 代理，无需任何本地的 Microsoft 软件。</span><span class="sxs-lookup"><span data-stu-id="f919d-121">The SBC is connected to the SIP Proxy in Office 365 without need for any on-premises software from Microsoft.</span></span>

  
<span data-ttu-id="f919d-122">**环境支持以下组合：**</span><span class="sxs-lookup"><span data-stu-id="f919d-122">**The environment supports the following combinations:**</span></span>
- <span data-ttu-id="f919d-123">**情形1：** 本地 Skype for Business 中的用户帐户，并且将使用具有企业语音的 Skype for Business 客户端</span><span class="sxs-lookup"><span data-stu-id="f919d-123">**Scenario 1:** User account in Skype for Business on-premises and will use the Skype for Business client with Enterprise Voice</span></span>
- <span data-ttu-id="f919d-124">**方案2：** Skype for business online 中的用户帐户，并将使用具有混合语音连接的 Skype for Business 客户端</span><span class="sxs-lookup"><span data-stu-id="f919d-124">**Scenario 2:** User account in Skype for business online and will use the Skype for Business client with Hybrid Voice Connectivity</span></span>
- <span data-ttu-id="f919d-125">**情形3：** Skype for business online 中使用 Microsoft 团队许可证的用户帐户，并将使用团队客户端</span><span class="sxs-lookup"><span data-stu-id="f919d-125">**Scenario 3:** User account in Skype for Business online with Microsoft Teams license and will use Teams client</span></span>
 
### <a name="supportability-matrix"></a><span data-ttu-id="f919d-126">支持列表</span><span class="sxs-lookup"><span data-stu-id="f919d-126">Supportability matrix</span></span>


|<span data-ttu-id="f919d-127">**在中创建的用户对象**</span><span class="sxs-lookup"><span data-stu-id="f919d-127">**User object created in**</span></span>  |<span data-ttu-id="f919d-128">**用户的 Skype for Business 服务提供商**</span><span class="sxs-lookup"><span data-stu-id="f919d-128">**User's Skype for Business service provider**</span></span>|<span data-ttu-id="f919d-129">**用户的客户端**</span><span class="sxs-lookup"><span data-stu-id="f919d-129">**User's Client**</span></span>|<span data-ttu-id="f919d-130">**语音选项**</span><span class="sxs-lookup"><span data-stu-id="f919d-130">**Voice option**</span></span>|<span data-ttu-id="f919d-131">**支持**</span><span class="sxs-lookup"><span data-stu-id="f919d-131">**Supported**</span></span>|
| ------------ | --------- | --------- | --------- | -------- |
|<span data-ttu-id="f919d-132">本地广告</span><span class="sxs-lookup"><span data-stu-id="f919d-132">On premises AD</span></span>| <span data-ttu-id="f919d-133">内部部署</span><span class="sxs-lookup"><span data-stu-id="f919d-133">On premises</span></span> |<span data-ttu-id="f919d-134">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f919d-134">Skype for Business</span></span>   | <span data-ttu-id="f919d-135">企业语音</span><span class="sxs-lookup"><span data-stu-id="f919d-135">Enterprise Voice</span></span>   |<span data-ttu-id="f919d-136">是</span><span class="sxs-lookup"><span data-stu-id="f919d-136">Yes</span></span>|
|<span data-ttu-id="f919d-137">本地广告</span><span class="sxs-lookup"><span data-stu-id="f919d-137">On premises AD</span></span>|<span data-ttu-id="f919d-138">Online</span><span class="sxs-lookup"><span data-stu-id="f919d-138">Online</span></span>| <span data-ttu-id="f919d-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f919d-139">Skype for Business</span></span>  | <span data-ttu-id="f919d-140">混合语音连接</span><span class="sxs-lookup"><span data-stu-id="f919d-140">Hybrid Voice Connectivity</span></span>   |<span data-ttu-id="f919d-141">是</span><span class="sxs-lookup"><span data-stu-id="f919d-141">Yes</span></span> |
|<span data-ttu-id="f919d-142">本地广告</span><span class="sxs-lookup"><span data-stu-id="f919d-142">On premises AD</span></span>|<span data-ttu-id="f919d-143">Online</span><span class="sxs-lookup"><span data-stu-id="f919d-143">Online</span></span> |<span data-ttu-id="f919d-144">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f919d-144">Microsoft Teams</span></span> |<span data-ttu-id="f919d-145">直接路由</span><span class="sxs-lookup"><span data-stu-id="f919d-145">Direct Routing</span></span>  |<span data-ttu-id="f919d-146">是</span><span class="sxs-lookup"><span data-stu-id="f919d-146">Yes</span></span> |
|<span data-ttu-id="f919d-147">**不支持的组合**</span><span class="sxs-lookup"><span data-stu-id="f919d-147">**Unsupported combinations**</span></span>    | |         |         |      |
|<span data-ttu-id="f919d-148">Azure AD</span><span class="sxs-lookup"><span data-stu-id="f919d-148">Azure AD</span></span>| <span data-ttu-id="f919d-149">本地/联机</span><span class="sxs-lookup"><span data-stu-id="f919d-149">On premises/online</span></span> | <span data-ttu-id="f919d-150">Skype for Business/Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f919d-150">Skype for Business/Microsoft Teams</span></span>|<span data-ttu-id="f919d-151">企业语音/混合语音连接/直接路由</span><span class="sxs-lookup"><span data-stu-id="f919d-151">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>  |<span data-ttu-id="f919d-152">否，必须先在本地广告中创建用户对象</span><span class="sxs-lookup"><span data-stu-id="f919d-152">No, user object MUST be created in on-premises AD first</span></span> |
|<span data-ttu-id="f919d-153">本地广告</span><span class="sxs-lookup"><span data-stu-id="f919d-153">On premises AD</span></span>  |<span data-ttu-id="f919d-154">内部部署</span><span class="sxs-lookup"><span data-stu-id="f919d-154">On premises</span></span>| <span data-ttu-id="f919d-155">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f919d-155">Microsoft Teams</span></span>| <span data-ttu-id="f919d-156">企业语音/混合语音连接/直接路由</span><span class="sxs-lookup"><span data-stu-id="f919d-156">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>   |<span data-ttu-id="f919d-157">否，本地 Skype for business 不支持 Microsoft 团队客户端</span><span class="sxs-lookup"><span data-stu-id="f919d-157">No, Microsoft Teams client is not supported with on-premises Skype for Business</span></span> |     
|<span data-ttu-id="f919d-158">本地广告</span><span class="sxs-lookup"><span data-stu-id="f919d-158">On premises AD</span></span>  |<span data-ttu-id="f919d-159">Online</span><span class="sxs-lookup"><span data-stu-id="f919d-159">Online</span></span> |<span data-ttu-id="f919d-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f919d-160">Skype for Business</span></span>  | <span data-ttu-id="f919d-161">直接路由</span><span class="sxs-lookup"><span data-stu-id="f919d-161">Direct Routing</span></span>  |<span data-ttu-id="f919d-162">否，Skype for Business 客户端不支持直接路由，用户必须在 Skype for business 中首先启用企业语音</span><span class="sxs-lookup"><span data-stu-id="f919d-162">No, Direct Routing is not supported with Skype for Business client, and user must be enabled for Enterprise Voice in Skype for Business first</span></span>  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a><span data-ttu-id="f919d-163">适用于具有 PSTN 的混合环境的可支持性声明</span><span class="sxs-lookup"><span data-stu-id="f919d-163">Supportability statement for the hybrid environment with PSTN</span></span>

<span data-ttu-id="f919d-164">对于所有用户，**必须**在本地广告中创建用户对象，并使用 Azure ad Connect 工具将该对象同步到 Azure ad。</span><span class="sxs-lookup"><span data-stu-id="f919d-164">For all users, the user object **must** be created in the on-premises AD and synchronized to the Azure AD using the Azure AD Connect tool.</span></span> <span data-ttu-id="f919d-165">如果在混合配置中直接在 Azure AD 中创建用户对象，则**不支持**为团队/Skype for business 启用用户。</span><span class="sxs-lookup"><span data-stu-id="f919d-165">Enabling users for Teams/Skype for Business **is not supported** if the user object is created directly in the Azure AD in a hybrid configuration.</span></span> <span data-ttu-id="f919d-166">对于要直接为团队启用的新用户（如新员工），用户必须使用本地 Skype for business 管理工具启用 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="f919d-166">For new users, such as a new hire, who will be enabled directly for Teams, the user must be enabled for Skype for Business using on premises Skype for Business management tools.</span></span> <span data-ttu-id="f919d-167">在**不支持**企业语音的本地池中的情况下，在联机 Skype for Business 或团队中创建用户。</span><span class="sxs-lookup"><span data-stu-id="f919d-167">Creating users in online Skype for Business or Teams without first enabling them in on-premises pool with Enterprise Voice **is not supported**.</span></span> <span data-ttu-id="f919d-168">有关此操作的详细信息，请在[Skype for Business 服务器中通过本地 PSTN 连接在 Office 365 中查找计划电话系统](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="f919d-168">For more information on this, look into [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).</span></span>
