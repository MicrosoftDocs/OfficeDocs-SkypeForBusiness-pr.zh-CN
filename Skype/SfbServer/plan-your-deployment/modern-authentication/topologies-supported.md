---
title: 支持新式验证的 Skype for Business 拓扑
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.date: 12/4/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: 本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: 13721b9d489b85fa6895469310240eebccc180ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="95278-103">支持新式验证的 Skype for Business 拓扑</span><span class="sxs-lookup"><span data-stu-id="95278-103">Skype for Business topologies supported with Modern Authentication</span></span>
 
<span data-ttu-id="95278-104">本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。</span><span class="sxs-lookup"><span data-stu-id="95278-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>
  
## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="95278-105">Skype for Business 中的新式验证</span><span class="sxs-lookup"><span data-stu-id="95278-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="95278-p101">Skype for Business 可以利用新式验证的安全优势。因为 Skype for Business 与 Exchange 密切协作，Skype for Business 客户端用户的登录行为也将受 Exchange 的 MA 状态影响。如果你具有混合 Skype for Business 拆分域，这一点也适用。这其中有很多活动部分，但其目的是为了轻松地将支持的拓扑列表可视化。</span><span class="sxs-lookup"><span data-stu-id="95278-p101">Skype for Business can leverage security advantages of Modern Authentication. Because Skype for Business works closely with Exchange, the login behaviour Skype for Business client users will see will also be effected by the MA status of Exchange. This will also apply if you have a Skype for Business split-domain hybrid. That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>
  
<span data-ttu-id="95278-110">对于 Skype for Business、Skype for Business Online、Exchange Server 和 Exchange Onlin，MA 支持哪些拓扑？</span><span class="sxs-lookup"><span data-stu-id="95278-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="95278-111">Skype for Business 中支持的 MA 拓扑</span><span class="sxs-lookup"><span data-stu-id="95278-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="95278-112">MA 使用的 Skype for Business 拓扑可能涉及两个服务器应用程序和两个 Office 365 工作负载。</span><span class="sxs-lookup"><span data-stu-id="95278-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>
  
- <span data-ttu-id="95278-113">Skype for Business Server 2015 (CU 5) 本地</span><span class="sxs-lookup"><span data-stu-id="95278-113">Skype for Business server 2015 (CU 5) on-premises</span></span>
    
- <span data-ttu-id="95278-114">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="95278-114">Skype for Business online (SFBO)</span></span>
    
- <span data-ttu-id="95278-115">Exchange Server 本地</span><span class="sxs-lookup"><span data-stu-id="95278-115">Exchange server on-premises</span></span>
    
- <span data-ttu-id="95278-116">Exchange Server Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="95278-116">Exchange server online (EXO)</span></span>
    
<span data-ttu-id="95278-p102">MA 的另一个重要部分是了解在何处执行用户身份验证 (authN) 和授权 (authZ)。有两个选项：</span><span class="sxs-lookup"><span data-stu-id="95278-p102">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place. The two options are:</span></span>
  
- <span data-ttu-id="95278-119">Azure AD，在 Microsoft Cloud 中在线进行</span><span class="sxs-lookup"><span data-stu-id="95278-119">Azure AD, online in the Microsoft Cloud</span></span>
    
- <span data-ttu-id="95278-120">Active Directory Federation Server (ADFS) 本地</span><span class="sxs-lookup"><span data-stu-id="95278-120">Active Directory Federation Server (ADFS) on-premises</span></span>
    
<span data-ttu-id="95278-121">因此它看上去像是这样一种情况，EXO 和 SFBO 在具有 Azure AD 的云中，Exchange Server (EXCH) 和 Skype for Business Server 2015 (SFB) 在本地。</span><span class="sxs-lookup"><span data-stu-id="95278-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server 2015 (SFB) on-prem.</span></span>
  
![所有应用程序（Exchange 和 Skype for Business）和工作负载（EXO 和 SFBO）以及开启 MA 时会涉及的两种授权服务器（ADFS 和 evoSTS）示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
<span data-ttu-id="95278-p103">支持的拓扑如下：请注意图形的图例：</span><span class="sxs-lookup"><span data-stu-id="95278-p103">Here are the supported topologies. Please note the key for the graphics:</span></span>
  
- <span data-ttu-id="95278-125">如果图标变暗或灰显，则表明在此情况下无法使用。</span><span class="sxs-lookup"><span data-stu-id="95278-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>
    
- <span data-ttu-id="95278-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="95278-126">EXO is Exchange Online.</span></span>
    
- <span data-ttu-id="95278-127">SFBO 是 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="95278-127">SFBO is Skype for Business Online.</span></span>
    
- <span data-ttu-id="95278-128">EXCH 是 Exchange 本地。</span><span class="sxs-lookup"><span data-stu-id="95278-128">EXCH is Exchange on-premises.</span></span>
    
- <span data-ttu-id="95278-129">SFB 是 Skype for Business 本地。</span><span class="sxs-lookup"><span data-stu-id="95278-129">SFB is Skype for Business on-premises.</span></span>
    
- <span data-ttu-id="95278-130">授权服务器用三角形表示，例如，Azure AD 是后面有一朵云的三角形。</span><span class="sxs-lookup"><span data-stu-id="95278-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>
    
- <span data-ttu-id="95278-131">箭头指向当客户尝试访问指定的服务器资源时将使用的授权服务器。</span><span class="sxs-lookup"><span data-stu-id="95278-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>
    
<span data-ttu-id="95278-132">首先，我们来看看仅本地或仅云拓扑中的 Skype for Business 的 MA。</span><span class="sxs-lookup"><span data-stu-id="95278-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95278-133">是否已准备好在 Skype for Business Online 中设置新式验证？</span><span class="sxs-lookup"><span data-stu-id="95278-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="95278-134">若要启用此功能的步骤是正确[这里](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="95278-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span> 
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95278-135">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="95278-135">Topology name</span></span>  <br/> |<span data-ttu-id="95278-136">示例</span><span class="sxs-lookup"><span data-stu-id="95278-136">Example</span></span>  <br/> |<span data-ttu-id="95278-137">说明</span><span class="sxs-lookup"><span data-stu-id="95278-137">Description</span></span>  <br/> |<span data-ttu-id="95278-138">支持</span><span class="sxs-lookup"><span data-stu-id="95278-138">Supported</span></span>  <br/> |
|<span data-ttu-id="95278-139">仅云</span><span class="sxs-lookup"><span data-stu-id="95278-139">Cloud only</span></span>  <br/> |![支持 SFB 与 MA 拓扑，仅限云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="95278-141">用户托管/邮箱位置：在线 </span><span class="sxs-lookup"><span data-stu-id="95278-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="95278-142">MA 对于 EXO 和 SFBO 为启用状态。</span><span class="sxs-lookup"><span data-stu-id="95278-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="95278-143">因此，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="95278-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="95278-144">多因素身份验证 (MFA)，基于客户端证书身份验证 (CBA) 条件访问 (CA) / 移动应用程序管理 (MAM) 与 Intune。</span><span class="sxs-lookup"><span data-stu-id="95278-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="95278-145">\*</span><span class="sxs-lookup"><span data-stu-id="95278-145"></span></span>  <br/> |
|<span data-ttu-id="95278-146">仅本地</span><span class="sxs-lookup"><span data-stu-id="95278-146">On-prem only</span></span>  <br/> |![支持 SFB 与 MA 拓扑，仅限本地部署。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="95278-148">用户托管/邮箱位置：本地</span><span class="sxs-lookup"><span data-stu-id="95278-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="95278-149">MA 对于 SFB 本地为启用状态。</span><span class="sxs-lookup"><span data-stu-id="95278-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="95278-150">因此，授权服务器是 ADFS。</span><span class="sxs-lookup"><span data-stu-id="95278-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="95278-151">有关配置的详细信息，请参阅[这篇文章。](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="95278-151">For configuration details, please see [this article.](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="95278-p106">MFA（仅限 Windows 桌面 - 不支持移动客户端）。不提供 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="95278-p106">MFA (Windows Desktop only - mobile clients are not supported). No Exchange integration features.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="95278-154">建议 Skype for Business 和 Exchange（及其在线对应项）的 MA 状态应相同，以减少提示数量。</span><span class="sxs-lookup"><span data-stu-id="95278-154">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span> 
  
<span data-ttu-id="95278-p107">混合拓扑涉及 SFB 拆分域混合组合。当前支持下列混合拓扑：</span><span class="sxs-lookup"><span data-stu-id="95278-p107">Mixed topologies involve combinations of SFB split-domain hybrids. These are the Mixed topologies currently supported:</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95278-157">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="95278-157">Topology name</span></span>  <br/> |<span data-ttu-id="95278-158">示例</span><span class="sxs-lookup"><span data-stu-id="95278-158">Example</span></span>  <br/> |<span data-ttu-id="95278-159">说明</span><span class="sxs-lookup"><span data-stu-id="95278-159">Description</span></span>  <br/> |<span data-ttu-id="95278-160">支持</span><span class="sxs-lookup"><span data-stu-id="95278-160">Supported</span></span>  <br/> |
|<span data-ttu-id="95278-161">混合 1</span><span class="sxs-lookup"><span data-stu-id="95278-161">Mixed 1</span></span>  <br/> |![支持 SFB 与 MA 拓扑，混合 1 (EXO + SFB)。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="95278-163">用户托管/邮箱位置：EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="95278-163">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="95278-164">MA 对 SFB 未启用，此拓扑中不提供 SFB MA 功能。</span><span class="sxs-lookup"><span data-stu-id="95278-164">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="95278-165">SFB 无 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="95278-165">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="95278-166">混合 2</span><span class="sxs-lookup"><span data-stu-id="95278-166">Mixed 2</span></span>  <br/> |![支持 MA 与 S4B 混合拓扑 2，使用本地 EXCH 的 SFBO 加 MA。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="95278-168">用户托管/邮箱位置：EXCH 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="95278-168">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="95278-169">MA 是可以 SFBO 只。</span><span class="sxs-lookup"><span data-stu-id="95278-169">MA is on for SFBO only.</span></span> <span data-ttu-id="95278-170">授权服务器是 Azure AD 用户驻留在 SFBO，但 EXCH 场所的广告。</span><span class="sxs-lookup"><span data-stu-id="95278-170">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="95278-171">MFA，CBA，CA/MAM Intune 使用。\*</span><span class="sxs-lookup"><span data-stu-id="95278-171">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="95278-172">混合 3</span><span class="sxs-lookup"><span data-stu-id="95278-172">Mixed 3</span></span>  <br/> |![支持 MA 与 SFB，启用了 MA 的 EXO，加本地 EXCH 和 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="95278-174">用户托管/邮箱位置：EXO + SFB 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="95278-174">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="95278-175">此拓扑中不提供 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="95278-175">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="95278-176">SFB 无 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="95278-176">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="95278-177">混合 4</span><span class="sxs-lookup"><span data-stu-id="95278-177">Mixed 4</span></span>  <br/> |![支持 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="95278-179">用户托管/邮箱位置：EXCH +SFBO 或 EXCH + SFB </span><span class="sxs-lookup"><span data-stu-id="95278-179">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="95278-180">马萨诸塞州的目标是 SFBO，因此授权服务器是 Azure AD 用户驻留在 SFBO。</span><span class="sxs-lookup"><span data-stu-id="95278-180">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="95278-181">在 SFB 和 EXO-prem 用户使用广告。</span><span class="sxs-lookup"><span data-stu-id="95278-181">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="95278-182">MFA，CBA，CA/MAM Intune 仅适用于在线用户使用。\*</span><span class="sxs-lookup"><span data-stu-id="95278-182">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="95278-183">混合 5</span><span class="sxs-lookup"><span data-stu-id="95278-183">Mixed 5</span></span>  <br/> |![支持 SFB 中的 MA、具有 MA 的 EXO、具有 MA 的 SFBO 以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="95278-185">用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="95278-185">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="95278-186">马萨诸塞州位于 EXO 和 SFBO，因此授权服务器是 Azure AD 用户驻留在 SFBO;在 EXCH 和 SFB prem 上用户使用广告。</span><span class="sxs-lookup"><span data-stu-id="95278-186">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="95278-187">MFA，CBA，CA/MAM Intune 仅适用于在线用户使用。\*</span><span class="sxs-lookup"><span data-stu-id="95278-187">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="95278-188">混合的 6</span><span class="sxs-lookup"><span data-stu-id="95278-188">Mixed 6</span></span>  <br/> |![在混合 6 拓扑中，所有 4 个可能位置都启用新式验证 - 采用新式验证时的理想情况。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="95278-190">用户托管/邮箱位置：XO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="95278-190">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="95278-191">马萨诸塞州上无处不在所以授权服务器是 Azure AD 中的为所有用户。</span><span class="sxs-lookup"><span data-stu-id="95278-191">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="95278-192">(联机和本地)</span><span class="sxs-lookup"><span data-stu-id="95278-192">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="95278-193">请参阅[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)的部署步骤。</span><span class="sxs-lookup"><span data-stu-id="95278-193">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="95278-194">MFA，CBA 和 CA/MAM （通过 Intune) 的所有用户。</span><span class="sxs-lookup"><span data-stu-id="95278-194">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |
   
<span data-ttu-id="95278-195">\*-MFA 包括 Windows 桌面、 MAC、 iOS、 Android 设备和 Windows 手机;CBA 包括 Windows 桌面，iOS 和 Android 设备;CA/MAM Intune，与包括 Android 和 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="95278-195">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="95278-196">必须注意的是，在某些情况下，用户可能会看到**多个提示**，尤其是当客户可能需要和请求的服务器资源的 MA 状态不同时，因为这种情况下包含所有版本的混合拓扑。</span><span class="sxs-lookup"><span data-stu-id="95278-196">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95278-197">此外请注意，在某些情况下 （混合 1、 3 和 5 专门） 必须正确配置 Windows 桌面客户端设置[AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项。</span><span class="sxs-lookup"><span data-stu-id="95278-197">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>
  

