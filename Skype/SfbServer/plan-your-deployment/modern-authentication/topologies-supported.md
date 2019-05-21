---
title: 支持新式验证的 Skype for Business 拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: 04dc6933fb63db7ebaec4f2c346e3cfbc60f9e24
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297335"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="6fd69-103">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="6fd69-103">Skype for Business topologies supported with Modern Authentication</span></span>
 
<span data-ttu-id="6fd69-104">本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。</span><span class="sxs-lookup"><span data-stu-id="6fd69-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>
  
## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="6fd69-105">Skype for Business 中的新式验证</span><span class="sxs-lookup"><span data-stu-id="6fd69-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="6fd69-p101">Skype for Business 可以利用新式验证的安全优势。因为 Skype for Business 与 Exchange 密切协作，Skype for Business 客户端用户的登录行为也将受 Exchange 的 MA 状态影响。如果你具有混合 Skype for Business 拆分域，这一点也适用。这其中有很多活动部分，但其目的是为了轻松地将支持的拓扑列表可视化。</span><span class="sxs-lookup"><span data-stu-id="6fd69-p101">Skype for Business can leverage security advantages of Modern Authentication. Because Skype for Business works closely with Exchange, the login behaviour Skype for Business client users will see will also be effected by the MA status of Exchange. This will also apply if you have a Skype for Business split-domain hybrid. That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>
  
<span data-ttu-id="6fd69-110">对于 Skype for Business、Skype for Business Online、Exchange Server 和 Exchange Onlin，MA 支持哪些拓扑？</span><span class="sxs-lookup"><span data-stu-id="6fd69-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="6fd69-111">Skype for Business 中支持的 MA 拓扑</span><span class="sxs-lookup"><span data-stu-id="6fd69-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="6fd69-112">MA 使用的 Skype for Business 拓扑可能涉及两个服务器应用程序和两个 Office 365 工作负载。</span><span class="sxs-lookup"><span data-stu-id="6fd69-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>
  
- <span data-ttu-id="6fd69-113">Skype for business 服务器 (CU 5) 内部部署</span><span class="sxs-lookup"><span data-stu-id="6fd69-113">Skype for Business server (CU 5) on-premises</span></span>
    
- <span data-ttu-id="6fd69-114">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="6fd69-114">Skype for Business online (SFBO)</span></span>
    
- <span data-ttu-id="6fd69-115">Exchange Server 本地</span><span class="sxs-lookup"><span data-stu-id="6fd69-115">Exchange server on-premises</span></span>
    
- <span data-ttu-id="6fd69-116">Exchange Server Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="6fd69-116">Exchange server online (EXO)</span></span>
    
<span data-ttu-id="6fd69-p102">MA 的另一个重要部分是了解在何处执行用户身份验证 (authN) 和授权 (authZ)。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="6fd69-p102">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place. The two options are:</span></span>
  
- <span data-ttu-id="6fd69-119">Azure AD，在 Microsoft Cloud 中在线进行</span><span class="sxs-lookup"><span data-stu-id="6fd69-119">Azure AD, online in the Microsoft Cloud</span></span>
    
- <span data-ttu-id="6fd69-120">Active Directory Federation Server (ADFS) 本地</span><span class="sxs-lookup"><span data-stu-id="6fd69-120">Active Directory Federation Server (ADFS) on-premises</span></span>
    
<span data-ttu-id="6fd69-121">因此, 它看起来有点类似, 在云中使用 EXO 和 SFBO, 使用 Azure AD 以及 Exchange Server (EXCH) 和 Skype for business Server (SFB) on-本地。</span><span class="sxs-lookup"><span data-stu-id="6fd69-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>
  
![所有应用程序（Exchange 和 Skype for Business）和工作负载（EXO 和 SFBO）以及开启 MA 时会涉及的两种授权服务器（ADFS 和 evoSTS）示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
<span data-ttu-id="6fd69-p103">支持的拓扑如下：请注意图形的图例：</span><span class="sxs-lookup"><span data-stu-id="6fd69-p103">Here are the supported topologies. Please note the key for the graphics:</span></span>
  
- <span data-ttu-id="6fd69-125">如果图标变暗或灰显，则表明在此情况下无法使用。</span><span class="sxs-lookup"><span data-stu-id="6fd69-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>
    
- <span data-ttu-id="6fd69-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="6fd69-126">EXO is Exchange Online.</span></span>
    
- <span data-ttu-id="6fd69-127">SFBO 是 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="6fd69-127">SFBO is Skype for Business Online.</span></span>
    
- <span data-ttu-id="6fd69-128">EXCH 是 Exchange 本地。</span><span class="sxs-lookup"><span data-stu-id="6fd69-128">EXCH is Exchange on-premises.</span></span>
    
- <span data-ttu-id="6fd69-129">SFB 是 Skype for Business 本地。</span><span class="sxs-lookup"><span data-stu-id="6fd69-129">SFB is Skype for Business on-premises.</span></span>
    
- <span data-ttu-id="6fd69-130">授权服务器用三角形表示，例如，Azure AD 是后面有一朵云的三角形。</span><span class="sxs-lookup"><span data-stu-id="6fd69-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>
    
- <span data-ttu-id="6fd69-131">箭头指向当客户尝试访问指定的服务器资源时将使用的授权服务器。</span><span class="sxs-lookup"><span data-stu-id="6fd69-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>
    
<span data-ttu-id="6fd69-132">首先，我们来看看仅本地或仅云拓扑中的 Skype for Business 的 MA。</span><span class="sxs-lookup"><span data-stu-id="6fd69-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6fd69-133">是否已准备好在 Skype for Business Online 中设置新式验证？</span><span class="sxs-lookup"><span data-stu-id="6fd69-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="6fd69-134">启用此功能的步骤在[这里](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6fd69-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span> 
  
|<span data-ttu-id="6fd69-135">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="6fd69-135">Topology name</span></span>  <br/> |<span data-ttu-id="6fd69-136">示例</span><span class="sxs-lookup"><span data-stu-id="6fd69-136">Example</span></span>  <br/> |<span data-ttu-id="6fd69-137">说明</span><span class="sxs-lookup"><span data-stu-id="6fd69-137">Description</span></span>  <br/> |<span data-ttu-id="6fd69-138">支持</span><span class="sxs-lookup"><span data-stu-id="6fd69-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6fd69-139">仅云</span><span class="sxs-lookup"><span data-stu-id="6fd69-139">Cloud only</span></span>  <br/> |![支持 SFB 与 MA 拓扑，仅限云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="6fd69-141">用户托管/邮箱位置：在线 </span><span class="sxs-lookup"><span data-stu-id="6fd69-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="6fd69-142">MA 对于 EXO 和 SFBO 为启用状态。</span><span class="sxs-lookup"><span data-stu-id="6fd69-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="6fd69-143">因此，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6fd69-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="6fd69-144">多重身份验证 (MFA)、基于客户端证书的身份验证 (CBA)、Intune 有条件访问 (CA)/移动应用管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="6fd69-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="6fd69-145">\*</span><span class="sxs-lookup"><span data-stu-id="6fd69-145"></span></span>  <br/> |
|<span data-ttu-id="6fd69-146">仅本地</span><span class="sxs-lookup"><span data-stu-id="6fd69-146">On-prem only</span></span>  <br/> |![支持 SFB 与 MA 拓扑，仅限本地部署。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="6fd69-148">用户托管/邮箱位置：本地</span><span class="sxs-lookup"><span data-stu-id="6fd69-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="6fd69-149">MA 对于 SFB 本地为启用状态。</span><span class="sxs-lookup"><span data-stu-id="6fd69-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="6fd69-150">因此，授权服务器是 ADFS。</span><span class="sxs-lookup"><span data-stu-id="6fd69-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="6fd69-151">有关配置的详细信息, 请参阅[本文。](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="6fd69-151">For configuration details, please see [this article.](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="6fd69-p106">MFA（仅限 Windows 桌面 - 不支持移动客户端）。不提供 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="6fd69-p106">MFA (Windows Desktop only - mobile clients are not supported). No Exchange integration features.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="6fd69-154">建议 Skype for Business 和 Exchange（及其在线对应项）的 MA 状态应相同，以减少提示数量。</span><span class="sxs-lookup"><span data-stu-id="6fd69-154">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span> 
  
<span data-ttu-id="6fd69-p107">混合拓扑涉及 SFB 拆分域混合组合。当前支持下列混合拓扑：</span><span class="sxs-lookup"><span data-stu-id="6fd69-p107">Mixed topologies involve combinations of SFB split-domain hybrids. These are the Mixed topologies currently supported:</span></span>
  
|<span data-ttu-id="6fd69-157">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="6fd69-157">Topology name</span></span>  <br/> |<span data-ttu-id="6fd69-158">示例</span><span class="sxs-lookup"><span data-stu-id="6fd69-158">Example</span></span>  <br/> |<span data-ttu-id="6fd69-159">说明</span><span class="sxs-lookup"><span data-stu-id="6fd69-159">Description</span></span>  <br/> |<span data-ttu-id="6fd69-160">支持</span><span class="sxs-lookup"><span data-stu-id="6fd69-160">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6fd69-161">混合 1</span><span class="sxs-lookup"><span data-stu-id="6fd69-161">Mixed 1</span></span>  <br/> |![支持 SFB 与 MA 拓扑，混合 1 (EXO + SFB)。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="6fd69-163">用户托管/邮箱位置：EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="6fd69-163">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="6fd69-164">MA 对 SFB 未启用，此拓扑中不提供 SFB MA 功能。</span><span class="sxs-lookup"><span data-stu-id="6fd69-164">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="6fd69-165">SFB 无 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="6fd69-165">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="6fd69-166">混合 2</span><span class="sxs-lookup"><span data-stu-id="6fd69-166">Mixed 2</span></span>  <br/> |![支持 MA 与 S4B 混合拓扑 2，使用本地 EXCH 的 SFBO 加 MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="6fd69-168">用户托管/邮箱位置：EXCH 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="6fd69-168">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="6fd69-169">MA 对于仅 SFBO 为启用状态。</span><span class="sxs-lookup"><span data-stu-id="6fd69-169">MA is on for SFBO only.</span></span> <span data-ttu-id="6fd69-170">授权服务器是托管在 SFBO 中的用户的 Azure AD, 但 EXCH 本地的广告。</span><span class="sxs-lookup"><span data-stu-id="6fd69-170">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="6fd69-171">具有 Intune 的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="6fd69-171">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="6fd69-172">混合 3</span><span class="sxs-lookup"><span data-stu-id="6fd69-172">Mixed 3</span></span>  <br/> |![支持 MA 与 SFB，启用了 MA 的 EXO，加本地 EXCH 和 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="6fd69-174">用户托管/邮箱位置：EXO + SFB 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="6fd69-174">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="6fd69-175">此拓扑中不提供 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="6fd69-175">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="6fd69-176">SFB 无 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="6fd69-176">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="6fd69-177">混合 4</span><span class="sxs-lookup"><span data-stu-id="6fd69-177">Mixed 4</span></span>  <br/> |![支持 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="6fd69-179">用户托管/邮箱位置：EXCH +SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="6fd69-179">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="6fd69-180">MA 对于 SFBO 为启用状态，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6fd69-180">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="6fd69-181">本地 SFB 和 EXO 中的用户使用广告。</span><span class="sxs-lookup"><span data-stu-id="6fd69-181">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="6fd69-182">仅限适用于联机用户的适用于 MFA、CBA、CA/MAM 的 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="6fd69-182">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="6fd69-183">混合 5</span><span class="sxs-lookup"><span data-stu-id="6fd69-183">Mixed 5</span></span>  <br/> |![支持 SFB 中的 MA、具有 MA 的 EXO、具有 MA 的 SFBO 以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="6fd69-185">用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="6fd69-185">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="6fd69-186">MA 同时在 EXO 和 SFBO 中, 因此授权服务器是托管在 SFBO 中的用户的 Azure AD;本地 EXCH 和 SFB 中的用户使用广告。</span><span class="sxs-lookup"><span data-stu-id="6fd69-186">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="6fd69-187">仅限适用于联机用户的适用于 MFA、CBA、CA/MAM 的 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="6fd69-187">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="6fd69-188">混合6</span><span class="sxs-lookup"><span data-stu-id="6fd69-188">Mixed 6</span></span>  <br/> |![在混合 6 拓扑中，所有 4 个可能位置都启用新式验证 - 采用新式验证时的理想情况。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="6fd69-190">用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="6fd69-190">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="6fd69-191">MA 位于任意位置, 因此授权服务器是适用于所有用户的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6fd69-191">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="6fd69-192">(联机和本地)</span><span class="sxs-lookup"><span data-stu-id="6fd69-192">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="6fd69-193">请参阅[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)了解部署步骤。</span><span class="sxs-lookup"><span data-stu-id="6fd69-193">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="6fd69-194">对所有用户的 MFA、CBA 和 CA/MAM (通过 Intune)。</span><span class="sxs-lookup"><span data-stu-id="6fd69-194">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |
   
<span data-ttu-id="6fd69-195">\*-MFA 包括 Windows 桌面版、MAC 版、iOS 版、Android 设备和 Windows phone;CBA 包括 Windows 桌面版、iOS 版和 Android 设备;带有 Intune 的 CA/MAM 包括 Android 和 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="6fd69-195">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6fd69-196">必须注意的是，在某些情况下，用户可能会看到**多个提示**，尤其是当客户可能需要和请求的服务器资源的 MA 状态不同时，因为这种情况下包含所有版本的混合拓扑。 </span><span class="sxs-lookup"><span data-stu-id="6fd69-196">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fd69-197">另请注意, 在某些情况下 (特别是1、3和 5), 必须为 Windows 桌面客户端设置正确配置的[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项。</span><span class="sxs-lookup"><span data-stu-id="6fd69-197">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>
  

