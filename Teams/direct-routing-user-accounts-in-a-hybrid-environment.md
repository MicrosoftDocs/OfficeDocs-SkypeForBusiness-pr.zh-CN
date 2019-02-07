---
title: 采用 PSTN 连接的混合环境中的用户帐户
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: 了解不同的用户创建和组合的受支持或不受支持的组合。
ms.openlocfilehash: 6f1cdbfc012026d7a41f5ca96e730aeb861eeb40
ms.sourcegitcommit: d400c8f83a2325c4a8bbb963ddad685a346bc4d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "29760556"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a><span data-ttu-id="f5f66-103">采用 PSTN 连接的混合环境中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="f5f66-103">User accounts in a hybrid environment with PSTN connectivity</span></span>

## <a name="about-the-environment"></a><span data-ttu-id="f5f66-104">有关环境</span><span class="sxs-lookup"><span data-stu-id="f5f66-104">About the environment</span></span>

<span data-ttu-id="f5f66-105">本文适用于具有以下所有的环境：</span><span class="sxs-lookup"><span data-stu-id="f5f66-105">This article applies to environments in which you have all of the following:</span></span> 
 
- <span data-ttu-id="f5f66-106">Skype 业务服务器或 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5f66-106">Skype for Business Server or Lync Server 2013</span></span> 
- <span data-ttu-id="f5f66-107">Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="f5f66-107">An Office 365 tenant</span></span> 
- <span data-ttu-id="f5f66-108">Skype 业务服务器和 Skype 业务联机或 Microsoft 团队租户之间配置混合连接性</span><span class="sxs-lookup"><span data-stu-id="f5f66-108">Hybrid connectivity configured between the Skype for Business Server and Skype for Business Online or Microsoft Teams tenant</span></span> 
- <span data-ttu-id="f5f66-109">启用发起和接收和来自客户端的公共公用电话交换网 (PSTN) 呼叫的用户</span><span class="sxs-lookup"><span data-stu-id="f5f66-109">Users who are enabled to make and receive Public Switched Telephone Network (PSTN) calls to and from the client</span></span>

 
<span data-ttu-id="f5f66-110">如果您具有不同的环境 （如业务云连接器 edition Skype)、 混合未配置，或您的用户未启用 PSTN 呼叫，可支持性矩阵将不同。</span><span class="sxs-lookup"><span data-stu-id="f5f66-110">If you have a different environment (such as Skype for Business Cloud Connector Edition), hybrid is not configured, or your users are not enabled for PSTN calls, the supportability matrix will be different.</span></span>  

## <a name="about-the-combinations-and-the-supportability-statement"></a><span data-ttu-id="f5f66-111">组合以及可支持性语句</span><span class="sxs-lookup"><span data-stu-id="f5f66-111">About the combinations and the supportability statement</span></span>  

<span data-ttu-id="f5f66-112">通过 PSTN 连接的业务混合环境 Skype 提供了有关用户服务提供的位置和设置和管理用户帐户的方式的灵活性。</span><span class="sxs-lookup"><span data-stu-id="f5f66-112">A Skype for Business hybrid environment with PSTN connectivity provides flexibility regarding where user services are provided and how user accounts are provisioned and managed.</span></span> <span data-ttu-id="f5f66-113">但选项大量可能创建某些不受支持的组合。</span><span class="sxs-lookup"><span data-stu-id="f5f66-113">But the abundance of options might create some unsupported combinations.</span></span> <span data-ttu-id="f5f66-114">本节介绍不同的用户创建，可支持性语句后跟组合。</span><span class="sxs-lookup"><span data-stu-id="f5f66-114">This section explains different combinations of user creation, followed by a supportability statement.</span></span>


<span data-ttu-id="f5f66-115">**定义：**</span><span class="sxs-lookup"><span data-stu-id="f5f66-115">**Definitions:**</span></span>   
- <span data-ttu-id="f5f66-116">**企业语音：** 提供具有内部部署 Skype 业务用户帐户的用户访问 PSTN 的选项。</span><span class="sxs-lookup"><span data-stu-id="f5f66-116">**Enterprise Voice:** Option to provide access to PSTN for users with on-premises Skype for Business user account.</span></span> <span data-ttu-id="f5f66-117">业务中介服务器的内部部署 Skype pstn 提供互联性。</span><span class="sxs-lookup"><span data-stu-id="f5f66-117">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span>  
- <span data-ttu-id="f5f66-118">**混合语音连接性：** 提供的用户与 Skype 业务 Online 帐户访问 PSTN 的选项。</span><span class="sxs-lookup"><span data-stu-id="f5f66-118">**Hybrid Voice Connectivity:** Option to provide access to PSTN for users with Skype for Business Online account.</span></span> <span data-ttu-id="f5f66-119">业务中介服务器的内部部署 Skype pstn 提供互联性。</span><span class="sxs-lookup"><span data-stu-id="f5f66-119">On-premises Skype for Business Mediation server provides interconnectivity to PSTN.</span></span> 
- <span data-ttu-id="f5f66-120">**直接路由：** 具有联机 Skype 业务帐户，Microsoft 团队许可证，使用的 Microsoft 团队客户端的用户提供 PSTN 访问的选项。</span><span class="sxs-lookup"><span data-stu-id="f5f66-120">**Direct routing:** Option to provide access to PSTN for users with online Skype for Business account, Microsoft Teams license, using Microsoft Teams client.</span></span> <span data-ttu-id="f5f66-121">SBC 从 Microsoft 连接到 Office 365 中 SIP 代理服务器不需要任何本地软件。</span><span class="sxs-lookup"><span data-stu-id="f5f66-121">The SBC is connected to the SIP Proxy in Office 365 without need for any on-premises software from Microsoft.</span></span>

  
<span data-ttu-id="f5f66-122">**环境支持下列组合：**</span><span class="sxs-lookup"><span data-stu-id="f5f66-122">**The environment supports the following combinations:**</span></span>
- <span data-ttu-id="f5f66-123">**方案 1:** 用户帐户中 Skype 业务本地和将 Skype 用于业务客户端与企业语音</span><span class="sxs-lookup"><span data-stu-id="f5f66-123">**Scenario 1:** User account in Skype for Business on-premises and will use the Skype for Business client with Enterprise Voice</span></span>
- <span data-ttu-id="f5f66-124">**方案 2:** 用户帐户中 Skype 在线业务和将 Skype 用于业务混合语音连接的客户端</span><span class="sxs-lookup"><span data-stu-id="f5f66-124">**Scenario 2:** User account in Skype for business online and will use the Skype for Business client with Hybrid Voice Connectivity</span></span>
- <span data-ttu-id="f5f66-125">**方案 3:** 用户帐户中的业务联机 Skype 与 Microsoft 团队许可证，并将使用团队客户端</span><span class="sxs-lookup"><span data-stu-id="f5f66-125">**Scenario 3:** User account in Skype for Business online with Microsoft Teams license and will use Teams client</span></span>
 
### <a name="supportability-matrix"></a><span data-ttu-id="f5f66-126">可支持性矩阵</span><span class="sxs-lookup"><span data-stu-id="f5f66-126">Supportability matrix</span></span>


|<span data-ttu-id="f5f66-127">**中创建的用户对象**</span><span class="sxs-lookup"><span data-stu-id="f5f66-127">**User object created in**</span></span>  |<span data-ttu-id="f5f66-128">**业务服务提供商的用户的 Skype**</span><span class="sxs-lookup"><span data-stu-id="f5f66-128">**User’s Skype for Business service provider**</span></span>|<span data-ttu-id="f5f66-129">**用户的客户端**</span><span class="sxs-lookup"><span data-stu-id="f5f66-129">**User’s Client**</span></span>|<span data-ttu-id="f5f66-130">**语音选项**</span><span class="sxs-lookup"><span data-stu-id="f5f66-130">**Voice option**</span></span>|<span data-ttu-id="f5f66-131">**支持**</span><span class="sxs-lookup"><span data-stu-id="f5f66-131">**Supported**</span></span>|
| ------------ | --------- | --------- | --------- | -------- |
|<span data-ttu-id="f5f66-132">本地 AD</span><span class="sxs-lookup"><span data-stu-id="f5f66-132">On premises AD</span></span>| <span data-ttu-id="f5f66-133">内部部署</span><span class="sxs-lookup"><span data-stu-id="f5f66-133">On premises</span></span> |<span data-ttu-id="f5f66-134">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5f66-134">Skype for Business</span></span>   | <span data-ttu-id="f5f66-135">企业语音</span><span class="sxs-lookup"><span data-stu-id="f5f66-135">Enterprise Voice</span></span>   |<span data-ttu-id="f5f66-136">是</span><span class="sxs-lookup"><span data-stu-id="f5f66-136">Yes</span></span>|
|<span data-ttu-id="f5f66-137">本地 AD</span><span class="sxs-lookup"><span data-stu-id="f5f66-137">On premises AD</span></span>|<span data-ttu-id="f5f66-138">Online</span><span class="sxs-lookup"><span data-stu-id="f5f66-138">Online</span></span>| <span data-ttu-id="f5f66-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5f66-139">Skype for Business</span></span>  | <span data-ttu-id="f5f66-140">混合语音连接</span><span class="sxs-lookup"><span data-stu-id="f5f66-140">Hybrid Voice Connectivity</span></span>   |<span data-ttu-id="f5f66-141">是</span><span class="sxs-lookup"><span data-stu-id="f5f66-141">Yes</span></span> |
|<span data-ttu-id="f5f66-142">本地 AD</span><span class="sxs-lookup"><span data-stu-id="f5f66-142">On premises AD</span></span>|<span data-ttu-id="f5f66-143">Online</span><span class="sxs-lookup"><span data-stu-id="f5f66-143">Online</span></span> |<span data-ttu-id="f5f66-144">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5f66-144">Microsoft Teams</span></span> |<span data-ttu-id="f5f66-145">直接路由</span><span class="sxs-lookup"><span data-stu-id="f5f66-145">Direct Routing</span></span>  |<span data-ttu-id="f5f66-146">是</span><span class="sxs-lookup"><span data-stu-id="f5f66-146">Yes</span></span> |
|<span data-ttu-id="f5f66-147">**不受支持的组合**</span><span class="sxs-lookup"><span data-stu-id="f5f66-147">**Unsupported combinations**</span></span>    | |         |         |      |
|<span data-ttu-id="f5f66-148">Azure AD</span><span class="sxs-lookup"><span data-stu-id="f5f66-148">Azure AD</span></span>| <span data-ttu-id="f5f66-149">部署/online 上</span><span class="sxs-lookup"><span data-stu-id="f5f66-149">On premises/online</span></span> | <span data-ttu-id="f5f66-150">Skype 业务/Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="f5f66-150">Skype for Business/Microsoft Teams</span></span>|<span data-ttu-id="f5f66-151">企业语音/混合语音连接/直接路由</span><span class="sxs-lookup"><span data-stu-id="f5f66-151">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>  |<span data-ttu-id="f5f66-152">否，必须在用户对象中创建的本地 AD 首先</span><span class="sxs-lookup"><span data-stu-id="f5f66-152">No, user object MUST be created in on-premises AD first</span></span> |
|<span data-ttu-id="f5f66-153">本地 AD</span><span class="sxs-lookup"><span data-stu-id="f5f66-153">On premises AD</span></span>  |<span data-ttu-id="f5f66-154">内部部署</span><span class="sxs-lookup"><span data-stu-id="f5f66-154">On premises</span></span>| <span data-ttu-id="f5f66-155">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5f66-155">Microsoft Teams</span></span>| <span data-ttu-id="f5f66-156">企业语音/混合语音连接/直接路由</span><span class="sxs-lookup"><span data-stu-id="f5f66-156">Enterprise Voice/Hybrid Voice Connectivity/Direct Routing</span></span>   |<span data-ttu-id="f5f66-157">否，Microsoft 团队客户端不支持的本地 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5f66-157">No, Microsoft Teams client is not supported with on-premises Skype for Business</span></span> |     
|<span data-ttu-id="f5f66-158">本地 AD</span><span class="sxs-lookup"><span data-stu-id="f5f66-158">On premises AD</span></span>  |<span data-ttu-id="f5f66-159">Online</span><span class="sxs-lookup"><span data-stu-id="f5f66-159">Online</span></span> |<span data-ttu-id="f5f66-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f5f66-160">Skype for Business</span></span>  | <span data-ttu-id="f5f66-161">直接路由</span><span class="sxs-lookup"><span data-stu-id="f5f66-161">Direct Routing</span></span>  |<span data-ttu-id="f5f66-162">否，直接路由中不支持与 Skype for Business 客户端，用户必须先为 Skype for Business 中的企业语音启用</span><span class="sxs-lookup"><span data-stu-id="f5f66-162">No, Direct Routing is not supported with Skype for Business client, and user must be enabled for Enterprise Voice in Skype for Business first</span></span>  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a><span data-ttu-id="f5f66-163">与 PSTN 的混合环境的可支持性语句</span><span class="sxs-lookup"><span data-stu-id="f5f66-163">Supportability statement for the hybrid environment with PSTN</span></span>

<span data-ttu-id="f5f66-164">所有用户的用户对象**必须**在内部部署中创建 AD 和同步到 Azure AD 使用 Azure AD 连接工具。</span><span class="sxs-lookup"><span data-stu-id="f5f66-164">For all users, the user object **must** be created in the on-premises AD and synchronized to the Azure AD using the Azure AD Connect tool.</span></span> <span data-ttu-id="f5f66-165">为用户启用团队/Skype 的业务**不支持**如果直接在 Azure AD 混合配置中创建的用户对象。</span><span class="sxs-lookup"><span data-stu-id="f5f66-165">Enabling users for Teams/Skype for Business **is not supported** if the user object is created directly in the Azure AD in a hybrid configuration.</span></span> <span data-ttu-id="f5f66-166">为新用户，如新员工，用户将直接为团队启用，用户必须的 Skype 启用业务在本地 Skype 使用的业务管理工具。</span><span class="sxs-lookup"><span data-stu-id="f5f66-166">For new users, such as a new hire, who will be enabled directly for Teams, the user must be enabled for Skype for Business using on premises Skype for Business management tools.</span></span> <span data-ttu-id="f5f66-167">在中创建用户联机 Skype 适用于商务或团队没有首先启用它们与企业语音**不支持**的本地池中。</span><span class="sxs-lookup"><span data-stu-id="f5f66-167">Creating users in online Skype for Business or Teams without first enabling them in on-premises pool with Enterprise Voice **is not supported**.</span></span> <span data-ttu-id="f5f66-168">请有关如何为用户启用 for Business 的 Skype 混合配置，参阅[本文](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f5f66-168">Please see [this article](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises) for more details on how to enable users for Skype for Business in hybrid configuration.</span></span>
