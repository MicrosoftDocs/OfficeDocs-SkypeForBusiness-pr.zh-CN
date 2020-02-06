---
title: 支持新式验证的 Skype for Business 拓扑
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
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: 2eb043768c46406696b32da5dfb84e2358a30749
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815820"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="988c0-103">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="988c0-103">Skype for Business topologies supported with Modern Authentication</span></span>
 
<span data-ttu-id="988c0-104">本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。</span><span class="sxs-lookup"><span data-stu-id="988c0-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>
  
## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="988c0-105">Skype for Business 中的新式验证</span><span class="sxs-lookup"><span data-stu-id="988c0-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="988c0-p101">Skype for Business 可以利用新式验证的安全优势。因为 Skype for Business 与 Exchange 密切协作，Skype for Business 客户端用户的登录行为也将受 Exchange 的 MA 状态影响。如果你具有混合 Skype for Business 拆分域，这一点也适用。这其中有很多活动部分，但其目的是为了轻松地将支持的拓扑列表可视化。</span><span class="sxs-lookup"><span data-stu-id="988c0-p101">Skype for Business can leverage security advantages of Modern Authentication. Because Skype for Business works closely with Exchange, the login behaviour Skype for Business client users will see will also be effected by the MA status of Exchange. This will also apply if you have a Skype for Business split-domain hybrid. That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>
  
<span data-ttu-id="988c0-110">对于 Skype for Business、Skype for Business Online、Exchange Server 和 Exchange Onlin，MA 支持哪些拓扑？</span><span class="sxs-lookup"><span data-stu-id="988c0-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="988c0-111">Skype for Business 中支持的 MA 拓扑</span><span class="sxs-lookup"><span data-stu-id="988c0-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="988c0-112">MA 使用的 Skype for Business 拓扑可能涉及两个服务器应用程序和两个 Office 365 工作负载。</span><span class="sxs-lookup"><span data-stu-id="988c0-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>
  
- <span data-ttu-id="988c0-113">Skype for business 服务器（CU 5）内部部署</span><span class="sxs-lookup"><span data-stu-id="988c0-113">Skype for Business server (CU 5) on-premises</span></span>
    
- <span data-ttu-id="988c0-114">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="988c0-114">Skype for Business online (SFBO)</span></span>
    
- <span data-ttu-id="988c0-115">Exchange Server 本地</span><span class="sxs-lookup"><span data-stu-id="988c0-115">Exchange server on-premises</span></span>
    
- <span data-ttu-id="988c0-116">Exchange Server Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="988c0-116">Exchange server online (EXO)</span></span>
    
<span data-ttu-id="988c0-p102">MA 的另一个重要部分是了解在何处执行用户身份验证 (authN) 和授权 (authZ)。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="988c0-p102">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place. The two options are:</span></span>
  
- <span data-ttu-id="988c0-119">Azure AD，在 Microsoft Cloud 中在线进行</span><span class="sxs-lookup"><span data-stu-id="988c0-119">Azure AD, online in the Microsoft Cloud</span></span>
    
- <span data-ttu-id="988c0-120">Active Directory Federation Server (ADFS) 本地</span><span class="sxs-lookup"><span data-stu-id="988c0-120">Active Directory Federation Server (ADFS) on-premises</span></span>
    
<span data-ttu-id="988c0-121">因此，它看起来有点类似，在云中使用 EXO 和 SFBO，使用 Azure AD 以及 Exchange Server （EXCH）和 Skype for business Server （SFB） on-本地。</span><span class="sxs-lookup"><span data-stu-id="988c0-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>
  
![所有应用程序（Exchange 和 Skype for Business）和工作负载（EXO 和 SFBO）以及开启 MA 时会涉及的两种授权服务器（ADFS 和 evoSTS）示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
<span data-ttu-id="988c0-p103">支持的拓扑如下：请注意图形的图例：</span><span class="sxs-lookup"><span data-stu-id="988c0-p103">Here are the supported topologies. Please note the key for the graphics:</span></span>
  
- <span data-ttu-id="988c0-125">如果图标变暗或灰显，则表明在此情况下无法使用。</span><span class="sxs-lookup"><span data-stu-id="988c0-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>
    
- <span data-ttu-id="988c0-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="988c0-126">EXO is Exchange Online.</span></span>
    
- <span data-ttu-id="988c0-127">SFBO 是 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="988c0-127">SFBO is Skype for Business Online.</span></span>
    
- <span data-ttu-id="988c0-128">EXCH 是 Exchange 本地。</span><span class="sxs-lookup"><span data-stu-id="988c0-128">EXCH is Exchange on-premises.</span></span>
    
- <span data-ttu-id="988c0-129">SFB 是 Skype for Business 本地。</span><span class="sxs-lookup"><span data-stu-id="988c0-129">SFB is Skype for Business on-premises.</span></span>
    
- <span data-ttu-id="988c0-130">授权服务器用三角形表示，例如，Azure AD 是后面有一朵云的三角形。</span><span class="sxs-lookup"><span data-stu-id="988c0-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>
    
- <span data-ttu-id="988c0-131">箭头指向当客户尝试访问指定的服务器资源时将使用的授权服务器。</span><span class="sxs-lookup"><span data-stu-id="988c0-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>
    
<span data-ttu-id="988c0-132">首先，我们来看看仅本地或仅云拓扑中的 Skype for Business 的 MA。</span><span class="sxs-lookup"><span data-stu-id="988c0-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="988c0-133">是否已准备好在 Skype for Business Online 中设置新式验证？</span><span class="sxs-lookup"><span data-stu-id="988c0-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="988c0-134">启用此功能的步骤在[这里](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="988c0-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span> 
  
|<span data-ttu-id="988c0-135">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="988c0-135">Topology name</span></span>  <br/> |<span data-ttu-id="988c0-136">示例</span><span class="sxs-lookup"><span data-stu-id="988c0-136">Example</span></span>  <br/> |<span data-ttu-id="988c0-137">说明</span><span class="sxs-lookup"><span data-stu-id="988c0-137">Description</span></span>  <br/> |<span data-ttu-id="988c0-138">支持</span><span class="sxs-lookup"><span data-stu-id="988c0-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="988c0-139">仅云</span><span class="sxs-lookup"><span data-stu-id="988c0-139">Cloud only</span></span>  <br/> |![支持 SFB 与 MA 拓扑，仅限云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="988c0-141">用户托管/邮箱位置：在线 </span><span class="sxs-lookup"><span data-stu-id="988c0-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="988c0-142">MA 对于 EXO 和 SFBO 为启用状态。</span><span class="sxs-lookup"><span data-stu-id="988c0-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="988c0-143">因此，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="988c0-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="988c0-144">多重身份验证 (MFA)、基于客户端证书的身份验证 (CBA)、Intune 有条件访问 (CA)/移动应用管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="988c0-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="988c0-145">\*</span><span class="sxs-lookup"><span data-stu-id="988c0-145">\*</span></span>  <br/> |
|<span data-ttu-id="988c0-146">仅本地</span><span class="sxs-lookup"><span data-stu-id="988c0-146">On-prem only</span></span>  <br/> |![支持 SFB 与 MA 拓扑，仅限本地部署。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="988c0-148">用户托管/邮箱位置：本地</span><span class="sxs-lookup"><span data-stu-id="988c0-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="988c0-149">MA 对于 SFB 本地为启用状态。</span><span class="sxs-lookup"><span data-stu-id="988c0-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="988c0-150">因此，授权服务器是 ADFS。</span><span class="sxs-lookup"><span data-stu-id="988c0-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="988c0-151">有关配置的详细信息，请参阅[本文。](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="988c0-151">For configuration details, please see [this article.](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="988c0-152">MFA（仅限 Windows 桌面 - 不支持移动客户端）。</span><span class="sxs-lookup"><span data-stu-id="988c0-152">MFA (Windows Desktop only - mobile clients are not supported).</span></span> <span data-ttu-id="988c0-153">不提供 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="988c0-153">No Exchange integration features.</span></span>  <br/><p> <span data-ttu-id="988c0-154">**我们不建议采用这种方法。请参阅此处：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span><span class="sxs-lookup"><span data-stu-id="988c0-154">**We do not recommend this approach. Please see here:** [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span></span><p/> |
   
> [!IMPORTANT]
> <span data-ttu-id="988c0-155">建议 Skype for Business 和 Exchange（及其在线对应项）的 MA 状态应相同，以减少提示数量。</span><span class="sxs-lookup"><span data-stu-id="988c0-155">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span> 
  
<span data-ttu-id="988c0-p107">混合拓扑涉及 SFB 拆分域混合组合。当前支持下列混合拓扑：</span><span class="sxs-lookup"><span data-stu-id="988c0-p107">Mixed topologies involve combinations of SFB split-domain hybrids. These are the Mixed topologies currently supported:</span></span>
  
|<span data-ttu-id="988c0-158">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="988c0-158">Topology name</span></span>  <br/> |<span data-ttu-id="988c0-159">示例</span><span class="sxs-lookup"><span data-stu-id="988c0-159">Example</span></span>  <br/> |<span data-ttu-id="988c0-160">说明</span><span class="sxs-lookup"><span data-stu-id="988c0-160">Description</span></span>  <br/> |<span data-ttu-id="988c0-161">支持</span><span class="sxs-lookup"><span data-stu-id="988c0-161">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="988c0-162">混合 1</span><span class="sxs-lookup"><span data-stu-id="988c0-162">Mixed 1</span></span>  <br/> |![支持 SFB 与 MA 拓扑，混合 1 (EXO + SFB)。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="988c0-164">用户托管/邮箱位置：EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="988c0-164">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="988c0-165">MA 对 SFB 未启用，此拓扑中不提供 SFB MA 功能。</span><span class="sxs-lookup"><span data-stu-id="988c0-165">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="988c0-166">SFB 无 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="988c0-166">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="988c0-167">混合 2</span><span class="sxs-lookup"><span data-stu-id="988c0-167">Mixed 2</span></span>  <br/> |![支持 MA 与 S4B 混合拓扑 2，使用本地 EXCH 的 SFBO 加 MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="988c0-169">用户托管/邮箱位置：EXCH 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="988c0-169">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="988c0-170">MA 对于仅 SFBO 为启用状态。</span><span class="sxs-lookup"><span data-stu-id="988c0-170">MA is on for SFBO only.</span></span> <span data-ttu-id="988c0-171">授权服务器是托管在 SFBO 中的用户的 Azure AD，但 EXCH 本地的广告。</span><span class="sxs-lookup"><span data-stu-id="988c0-171">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="988c0-172">具有 Intune 的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="988c0-172">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="988c0-173">混合 3</span><span class="sxs-lookup"><span data-stu-id="988c0-173">Mixed 3</span></span>  <br/> |![支持 MA 与 SFB，启用了 MA 的 EXO，加本地 EXCH 和 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="988c0-175">用户托管/邮箱位置：EXO + SFB 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="988c0-175">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="988c0-176">此拓扑中不提供 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="988c0-176">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="988c0-177">SFB 无 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="988c0-177">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="988c0-178">混合 4</span><span class="sxs-lookup"><span data-stu-id="988c0-178">Mixed 4</span></span>  <br/> |![支持 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="988c0-180">用户托管/邮箱位置：EXCH +SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="988c0-180">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="988c0-181">MA 对于 SFBO 为启用状态，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="988c0-181">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="988c0-182">本地 SFB 和 EXO 中的用户使用广告。</span><span class="sxs-lookup"><span data-stu-id="988c0-182">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="988c0-183">仅限适用于联机用户的适用于 MFA、CBA、CA/MAM 的 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="988c0-183">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="988c0-184">混合 5</span><span class="sxs-lookup"><span data-stu-id="988c0-184">Mixed 5</span></span>  <br/> |![支持 SFB 中的 MA、具有 MA 的 EXO、具有 MA 的 SFBO 以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="988c0-186">用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="988c0-186">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="988c0-187">MA 同时在 EXO 和 SFBO 中，因此授权服务器是托管在 SFBO 中的用户的 Azure AD;本地 EXCH 和 SFB 中的用户使用广告。</span><span class="sxs-lookup"><span data-stu-id="988c0-187">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="988c0-188">仅限适用于联机用户的适用于 MFA、CBA、CA/MAM 的 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="988c0-188">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="988c0-189">混合6</span><span class="sxs-lookup"><span data-stu-id="988c0-189">Mixed 6</span></span>  <br/> |![在混合 6 拓扑中，所有 4 个可能位置都启用新式验证 - 采用新式验证时的理想情况。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="988c0-191">用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="988c0-191">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="988c0-192">MA 位于任意位置，因此授权服务器是适用于所有用户的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="988c0-192">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="988c0-193">（联机和本地）</span><span class="sxs-lookup"><span data-stu-id="988c0-193">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="988c0-194">请参阅[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)了解部署步骤。</span><span class="sxs-lookup"><span data-stu-id="988c0-194">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="988c0-195">对所有用户的 MFA、CBA 和 CA/MAM （通过 Intune）。</span><span class="sxs-lookup"><span data-stu-id="988c0-195">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |
   
<span data-ttu-id="988c0-196">\*-MFA 包括 Windows 桌面版、MAC 版、iOS 版、Android 设备和 Windows phone;CBA 包括 Windows 桌面版、iOS 版和 Android 设备;带有 Intune 的 CA/MAM 包括 Android 和 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="988c0-196">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="988c0-197">必须注意的是，在某些情况下，用户可能会看到**多个提示**，尤其是当客户可能需要和请求的服务器资源的 MA 状态不同时，因为这种情况下包含所有版本的混合拓扑。 </span><span class="sxs-lookup"><span data-stu-id="988c0-197">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="988c0-198">另请注意，在某些情况下（特别是1、3和5），必须为 Windows 桌面客户端设置正确配置的[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项。</span><span class="sxs-lookup"><span data-stu-id="988c0-198">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>
  

