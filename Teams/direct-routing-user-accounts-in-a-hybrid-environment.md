---
title: 使用 PSTN 的混合环境中用户帐户
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
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096322"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a><span data-ttu-id="45e72-103">采用 PSTN 连接的混合环境中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="45e72-103">User accounts in a hybrid environment with PSTN connectivity</span></span>

## <a name="about-the-environment"></a><span data-ttu-id="45e72-104">关于环境</span><span class="sxs-lookup"><span data-stu-id="45e72-104">About the environment</span></span>

<span data-ttu-id="45e72-105">本文适用于具有以下所有功能的环境：</span><span class="sxs-lookup"><span data-stu-id="45e72-105">This article applies to environments in which you have all of the following:</span></span> 
 
- <span data-ttu-id="45e72-106">Skype for Business Server 或 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45e72-106">Skype for Business Server or Lync Server 2013</span></span> 
- <span data-ttu-id="45e72-107">Microsoft 365 或 Office 365 组织</span><span class="sxs-lookup"><span data-stu-id="45e72-107">An Microsoft 365 or Office 365 organization</span></span> 
- <span data-ttu-id="45e72-108">在 Skype for Business Server 和 Skype for Business Online 或 Microsoft Teams 租户之间配置的混合连接</span><span class="sxs-lookup"><span data-stu-id="45e72-108">Hybrid connectivity configured between the Skype for Business Server and Skype for Business Online or Microsoft Teams tenant</span></span> 
- <span data-ttu-id="45e72-109">已启用与客户端建立和接收公用电话交换网 (PSTN) 呼叫的用户</span><span class="sxs-lookup"><span data-stu-id="45e72-109">Users who are enabled to make and receive Public Switched Telephone Network (PSTN) calls to and from the client</span></span>

 
<span data-ttu-id="45e72-110">如果你有不同的环境 (如 Skype for Business Cloud Connector Edition) 、未配置混合，或者未为用户启用 PSTN 呼叫，则可支持性矩阵会有所不同。</span><span class="sxs-lookup"><span data-stu-id="45e72-110">If you have a different environment (such as Skype for Business Cloud Connector Edition), hybrid is not configured, or your users are not enabled for PSTN calls, the supportability matrix will be different.</span></span>  

## <a name="about-the-combinations-and-the-supportability-statement"></a><span data-ttu-id="45e72-111">关于组合和可支持性声明</span><span class="sxs-lookup"><span data-stu-id="45e72-111">About the combinations and the supportability statement</span></span>  

<span data-ttu-id="45e72-112">具有 PSTN 连接的 Skype for Business 混合环境在提供用户服务以及如何预配和管理用户帐户方面提供了灵活性。</span><span class="sxs-lookup"><span data-stu-id="45e72-112">A Skype for Business hybrid environment with PSTN connectivity provides flexibility regarding where user services are provided and how user accounts are provisioned and managed.</span></span> <span data-ttu-id="45e72-113">但是，选项的丰富可能会创建一些不受支持的组合。</span><span class="sxs-lookup"><span data-stu-id="45e72-113">But the abundance of options might create some unsupported combinations.</span></span> <span data-ttu-id="45e72-114">本部分介绍用户创建的不同组合，后跟可支持性声明。</span><span class="sxs-lookup"><span data-stu-id="45e72-114">This section explains different combinations of user creation, followed by a supportability statement.</span></span>


<span data-ttu-id="45e72-115">**定义：**</span><span class="sxs-lookup"><span data-stu-id="45e72-115">**Definitions:**</span></span>   
- <span data-ttu-id="45e72-116">**企业语音：** 为具有本地 Skype for Business 用户帐户的用户提供 PSTN 访问权限的选项。</span><span class="sxs-lookup"><span data-stu-id="45e72-116">**Enterprise Voice:** Option to provide access to PSTN for users with on-premises Skype for Business user account.</span></span> <span data-ttu-id="45e72-117">本地 Skype for Business 中介服务器提供与 PSTN 的互连。</span><span class="sxs-lookup"><span data-stu-id="45e72-117">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span>  
- <span data-ttu-id="45e72-118">**混合语音连接：** 为使用 Skype for Business Online 帐户的用户提供 PSTN 访问权限的选项。</span><span class="sxs-lookup"><span data-stu-id="45e72-118">**Hybrid Voice Connectivity:** Option to provide access to PSTN for users with Skype for Business Online account.</span></span> <span data-ttu-id="45e72-119">本地 Skype for Business 中介服务器提供与 PSTN 的互连。</span><span class="sxs-lookup"><span data-stu-id="45e72-119">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span> 
- <span data-ttu-id="45e72-120">**直接路由：** 为具有在线 Skype for Business 帐户、Microsoft Teams 许可证、使用 Microsoft Teams 客户端的用户提供 PSTN 访问权限的选项。</span><span class="sxs-lookup"><span data-stu-id="45e72-120">**Direct routing:** Option to provide access to PSTN for users with online Skype for Business account, Microsoft Teams license, using Microsoft Teams client.</span></span> <span data-ttu-id="45e72-121">SBC 连接到 Microsoft 365 或 Office 365 中的 SIP 代理，无需 Microsoft 提供的任何本地软件。</span><span class="sxs-lookup"><span data-stu-id="45e72-121">The SBC is connected to the SIP Proxy in Microsoft 365 or Office 365 without need for any on-premises software from Microsoft.</span></span>

  
<span data-ttu-id="45e72-122">**环境支持以下组合：**</span><span class="sxs-lookup"><span data-stu-id="45e72-122">**The environment supports the following combinations:**</span></span>
- <span data-ttu-id="45e72-123">**方案 1：** 本地 Skype for Business 中的用户帐户，将 Skype for Business 客户端与 企业语音</span><span class="sxs-lookup"><span data-stu-id="45e72-123">**Scenario 1:** User account in Skype for Business on-premises and will use the Skype for Business client with Enterprise Voice</span></span>
- <span data-ttu-id="45e72-124">**方案 2：** Skype for business Online 中的用户帐户，将 Skype for Business 客户端与混合语音连接一起使用</span><span class="sxs-lookup"><span data-stu-id="45e72-124">**Scenario 2:** User account in Skype for business online and will use the Skype for Business client with Hybrid Voice Connectivity</span></span>
- <span data-ttu-id="45e72-125">**方案 3：** 具有 Microsoft Teams 许可证的 Skype for Business Online 用户帐户，将使用 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="45e72-125">**Scenario 3:** User account in Skype for Business online with Microsoft Teams license and will use Teams client</span></span>
 
### <a name="supportability-matrix"></a><span data-ttu-id="45e72-126">可支持性矩阵</span><span class="sxs-lookup"><span data-stu-id="45e72-126">Supportability matrix</span></span>


|<span data-ttu-id="45e72-127">**在 中创建的用户对象**</span><span class="sxs-lookup"><span data-stu-id="45e72-127">**User object created in**</span></span>  |<span data-ttu-id="45e72-128">**用户的 Skype for Business 服务提供商**</span><span class="sxs-lookup"><span data-stu-id="45e72-128">**User's Skype for Business service provider**</span></span>|<span data-ttu-id="45e72-129">**用户的客户端**</span><span class="sxs-lookup"><span data-stu-id="45e72-129">**User's Client**</span></span>|<span data-ttu-id="45e72-130">**语音选项**</span><span class="sxs-lookup"><span data-stu-id="45e72-130">**Voice option**</span></span>|<span data-ttu-id="45e72-131">**支持**</span><span class="sxs-lookup"><span data-stu-id="45e72-131">**Supported**</span></span>|
| ------------ | --------- | --------- | --------- | -------- |
|<span data-ttu-id="45e72-132">本地 AD</span><span class="sxs-lookup"><span data-stu-id="45e72-132">On premises AD</span></span>| <span data-ttu-id="45e72-133">内部部署</span><span class="sxs-lookup"><span data-stu-id="45e72-133">On premises</span></span> |<span data-ttu-id="45e72-134">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45e72-134">Skype for Business</span></span>   | <span data-ttu-id="45e72-135">企业语音</span><span class="sxs-lookup"><span data-stu-id="45e72-135">Enterprise Voice</span></span>   |<span data-ttu-id="45e72-136">是</span><span class="sxs-lookup"><span data-stu-id="45e72-136">Yes</span></span>|
|<span data-ttu-id="45e72-137">本地 AD</span><span class="sxs-lookup"><span data-stu-id="45e72-137">On premises AD</span></span>|<span data-ttu-id="45e72-138">Online</span><span class="sxs-lookup"><span data-stu-id="45e72-138">Online</span></span>| <span data-ttu-id="45e72-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45e72-139">Skype for Business</span></span>  | <span data-ttu-id="45e72-140">混合语音连接</span><span class="sxs-lookup"><span data-stu-id="45e72-140">Hybrid Voice Connectivity</span></span>   |<span data-ttu-id="45e72-141">是</span><span class="sxs-lookup"><span data-stu-id="45e72-141">Yes</span></span> |
|<span data-ttu-id="45e72-142">本地 AD</span><span class="sxs-lookup"><span data-stu-id="45e72-142">On premises AD</span></span>|<span data-ttu-id="45e72-143">Online</span><span class="sxs-lookup"><span data-stu-id="45e72-143">Online</span></span> |<span data-ttu-id="45e72-144">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45e72-144">Microsoft Teams</span></span> |<span data-ttu-id="45e72-145">直接路由</span><span class="sxs-lookup"><span data-stu-id="45e72-145">Direct Routing</span></span>  |<span data-ttu-id="45e72-146">是</span><span class="sxs-lookup"><span data-stu-id="45e72-146">Yes</span></span> |
|<span data-ttu-id="45e72-147">**不支持的组合**</span><span class="sxs-lookup"><span data-stu-id="45e72-147">**Unsupported combinations**</span></span>    | |         |         |      |
|<span data-ttu-id="45e72-148">Azure AD</span><span class="sxs-lookup"><span data-stu-id="45e72-148">Azure AD</span></span>| <span data-ttu-id="45e72-149">本地/联机</span><span class="sxs-lookup"><span data-stu-id="45e72-149">On premises/online</span></span> | <span data-ttu-id="45e72-150">Skype for Business/Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45e72-150">Skype for Business/Microsoft Teams</span></span>|<span data-ttu-id="45e72-151">企业语音/混合语音连接/直接路由</span><span class="sxs-lookup"><span data-stu-id="45e72-151">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>  |<span data-ttu-id="45e72-152">否，必须先在本地 AD 中创建用户对象</span><span class="sxs-lookup"><span data-stu-id="45e72-152">No, user object MUST be created in on-premises AD first</span></span> |
|<span data-ttu-id="45e72-153">本地 AD</span><span class="sxs-lookup"><span data-stu-id="45e72-153">On premises AD</span></span>  |<span data-ttu-id="45e72-154">内部部署</span><span class="sxs-lookup"><span data-stu-id="45e72-154">On premises</span></span>| <span data-ttu-id="45e72-155">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45e72-155">Microsoft Teams</span></span>| <span data-ttu-id="45e72-156">企业语音/混合语音连接/直接路由</span><span class="sxs-lookup"><span data-stu-id="45e72-156">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>   |<span data-ttu-id="45e72-157">否，本地 Skype for Business 不支持 Microsoft Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="45e72-157">No, Microsoft Teams client is not supported with on-premises Skype for Business</span></span> |     
|<span data-ttu-id="45e72-158">本地 AD</span><span class="sxs-lookup"><span data-stu-id="45e72-158">On premises AD</span></span>  |<span data-ttu-id="45e72-159">Online</span><span class="sxs-lookup"><span data-stu-id="45e72-159">Online</span></span> |<span data-ttu-id="45e72-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45e72-160">Skype for Business</span></span>  | <span data-ttu-id="45e72-161">直接路由</span><span class="sxs-lookup"><span data-stu-id="45e72-161">Direct Routing</span></span>  |<span data-ttu-id="45e72-162">否，Skype for Business 客户端不支持直接路由</span><span class="sxs-lookup"><span data-stu-id="45e72-162">No, Direct Routing is not supported with Skype for Business client</span></span>  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a><span data-ttu-id="45e72-163">使用 PSTN 的混合环境的可支持性声明</span><span class="sxs-lookup"><span data-stu-id="45e72-163">Supportability statement for the hybrid environment with PSTN</span></span>

<span data-ttu-id="45e72-164">对于所有用户，必须在本地 AD 中创建用户对象，然后使用 Azure AD Connect 工具同步到 Azure AD。 </span><span class="sxs-lookup"><span data-stu-id="45e72-164">For all users, the user object **must** be created in the on-premises AD and synchronized to the Azure AD using the Azure AD Connect tool.</span></span> <span data-ttu-id="45e72-165">如果用户对象是在混合配置中直接在 Azure AD 中创建的，则不支持为用户启用 Teams/Skype for **Business。**</span><span class="sxs-lookup"><span data-stu-id="45e72-165">Enabling users for Teams/Skype for Business **is not supported** if the user object is created directly in the Azure AD in a hybrid configuration.</span></span> <span data-ttu-id="45e72-166">对于新用户（例如将直接为 Teams 启用的新员工）来说，必须使用本地 Skype for Business 管理工具为该用户启用 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="45e72-166">For new users, such as a new hire, who will be enabled directly for Teams, the user must be enabled for Skype for Business using on premises Skype for Business management tools.</span></span> <span data-ttu-id="45e72-167">不支持在联机 Skype for Business 或 Teams 中创建用户，而不首先在本地池中使用 企业语音 **用户**。</span><span class="sxs-lookup"><span data-stu-id="45e72-167">Creating users in online Skype for Business or Teams without first enabling them in on-premises pool with Enterprise Voice **is not supported**.</span></span> <span data-ttu-id="45e72-168">有关详细信息，请参阅在 Skype for Business Server 中使用本地 [PSTN 连接规划电话系统](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="45e72-168">For more information on this, look into [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).</span></span>