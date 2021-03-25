---
title: 新式验证支持的 Skype for Business 拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 本文列出了 Skype for Business 中的新式验证支持哪些联机和本地拓扑，以及适用于每个拓扑的安全功能。
ms.openlocfilehash: 759ee11a4cd6828d65b45a713f50bb8b32856a4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116060"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="5f430-103">新式验证支持的 Skype for Business 拓扑</span><span class="sxs-lookup"><span data-stu-id="5f430-103">Skype for Business topologies supported with Modern Authentication</span></span>

<span data-ttu-id="5f430-104">本文列出了 Skype for Business 中的新式验证支持哪些联机和本地拓扑，以及适用于每个拓扑的安全功能。</span><span class="sxs-lookup"><span data-stu-id="5f430-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>

## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="5f430-105">Skype for Business 中的新式验证</span><span class="sxs-lookup"><span data-stu-id="5f430-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="5f430-106">Skype for Business 可以利用新式验证的安全优势。</span><span class="sxs-lookup"><span data-stu-id="5f430-106">Skype for Business can leverage security advantages of Modern Authentication.</span></span> <span data-ttu-id="5f430-107">由于 Skype for Business 与 Exchange 紧密配合，Skype for Business 客户端用户将看到的登录行为也将受 Exchange 的 MA 状态影响。</span><span class="sxs-lookup"><span data-stu-id="5f430-107">Because Skype for Business works closely with Exchange, the login behavior Skype for Business client users will see will also be affected by the MA status of Exchange.</span></span> <span data-ttu-id="5f430-108">如果你拥有 Skype for Business 拆分域混合，这同样适用。</span><span class="sxs-lookup"><span data-stu-id="5f430-108">This will also apply if you have a Skype for Business split-domain hybrid.</span></span> <span data-ttu-id="5f430-109">这有许多移动部件，但此处的目标是轻松直观地显示支持的拓扑列表。</span><span class="sxs-lookup"><span data-stu-id="5f430-109">That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>

<span data-ttu-id="5f430-110">鉴于 Skype for Business、Skype for Business online、Exchange Server 和 Exchange Online，MA 支持哪些拓扑？</span><span class="sxs-lookup"><span data-stu-id="5f430-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="5f430-111">Skype for Business 中支持的 MA 拓扑</span><span class="sxs-lookup"><span data-stu-id="5f430-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="5f430-112">MA 使用的 Skype for Business 拓扑可能涉及两个服务器应用程序，以及两个 Microsoft 365 或 Office 365 工作负载。</span><span class="sxs-lookup"><span data-stu-id="5f430-112">There are potentially two server applications, and two Microsoft 365 or Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>

- <span data-ttu-id="5f430-113">Skype for Business server (CU 5) 本地部署</span><span class="sxs-lookup"><span data-stu-id="5f430-113">Skype for Business server (CU 5) on-premises</span></span>

- <span data-ttu-id="5f430-114">Skype for Business online (SFBO) </span><span class="sxs-lookup"><span data-stu-id="5f430-114">Skype for Business online (SFBO)</span></span>

- <span data-ttu-id="5f430-115">内部部署 Exchange 服务器</span><span class="sxs-lookup"><span data-stu-id="5f430-115">Exchange server on-premises</span></span>

- <span data-ttu-id="5f430-116">EXCHANGE server online (EXO) </span><span class="sxs-lookup"><span data-stu-id="5f430-116">Exchange server online (EXO)</span></span>

<span data-ttu-id="5f430-117">MA 的另一个重要部分是了解身份验证 (身份验证) 身份验证 (身份验证) 身份验证将在何处进行。</span><span class="sxs-lookup"><span data-stu-id="5f430-117">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place.</span></span> <span data-ttu-id="5f430-118">两个选项是：</span><span class="sxs-lookup"><span data-stu-id="5f430-118">The two options are:</span></span>

- <span data-ttu-id="5f430-119">Microsoft 云中的联机 Azure AD</span><span class="sxs-lookup"><span data-stu-id="5f430-119">Azure AD, online in the Microsoft Cloud</span></span>

- <span data-ttu-id="5f430-120">Active Directory 联合服务器 (本地) ADFS</span><span class="sxs-lookup"><span data-stu-id="5f430-120">Active Directory Federation Server (ADFS) on-premises</span></span>

<span data-ttu-id="5f430-121">因此，它看起来有点类似，在云中使用 Azure AD 的 EXO 和 SFBO，以及 Exchange Server (EXCH) 和 Skype for Business (SFB) SFB。</span><span class="sxs-lookup"><span data-stu-id="5f430-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>

![启用 MA 时可能涉及的所有 (Exchange 和 Skype for Business) 和工作负载 (EXO 和 SFBO) 以及两个授权服务器 (ADFS 和 evoSTS) 的示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

<span data-ttu-id="5f430-123">以下是受支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="5f430-123">Here are the supported topologies.</span></span> <span data-ttu-id="5f430-124">请注意图形的键：</span><span class="sxs-lookup"><span data-stu-id="5f430-124">Please note the key for the graphics:</span></span>

- <span data-ttu-id="5f430-125">如果图标灰显或灰显，则不用于此方案。</span><span class="sxs-lookup"><span data-stu-id="5f430-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>

- <span data-ttu-id="5f430-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5f430-126">EXO is Exchange Online.</span></span>

- <span data-ttu-id="5f430-127">SFBO 是 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="5f430-127">SFBO is Skype for Business Online.</span></span>

- <span data-ttu-id="5f430-128">EXCH 是 Exchange 本地部署。</span><span class="sxs-lookup"><span data-stu-id="5f430-128">EXCH is Exchange on-premises.</span></span>

- <span data-ttu-id="5f430-129">SFB 是本地 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="5f430-129">SFB is Skype for Business on-premises.</span></span>

- <span data-ttu-id="5f430-130">授权服务器由三角形表示，例如，Azure AD 是一个三角形，后面有云。</span><span class="sxs-lookup"><span data-stu-id="5f430-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>

- <span data-ttu-id="5f430-131">箭头指向授权服务器，客户端尝试访问指定的服务器资源时将使用该服务器。</span><span class="sxs-lookup"><span data-stu-id="5f430-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>

<span data-ttu-id="5f430-132">首先，让我们在仅本地拓扑或仅云拓扑中介绍 Skype for Business 的 MA。</span><span class="sxs-lookup"><span data-stu-id="5f430-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f430-133">准备好在 Skype for Business Online 中设置新式验证了吗？</span><span class="sxs-lookup"><span data-stu-id="5f430-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="5f430-134">启用此功能[的步骤在此处。](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f430-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>

|<span data-ttu-id="5f430-135">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="5f430-135">Topology name</span></span>  <br/> |<span data-ttu-id="5f430-136">示例</span><span class="sxs-lookup"><span data-stu-id="5f430-136">Example</span></span>  <br/> |<span data-ttu-id="5f430-137">说明</span><span class="sxs-lookup"><span data-stu-id="5f430-137">Description</span></span>  <br/> |<span data-ttu-id="5f430-138">支持</span><span class="sxs-lookup"><span data-stu-id="5f430-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f430-139">仅云</span><span class="sxs-lookup"><span data-stu-id="5f430-139">Cloud only</span></span>  <br/> |![支持 SFB 和 MA 拓扑，仅云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="5f430-141">用户所定位/邮箱：联机</span><span class="sxs-lookup"><span data-stu-id="5f430-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="5f430-142">MA 对 EXO 和 SFBO 均打开。</span><span class="sxs-lookup"><span data-stu-id="5f430-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="5f430-143">因此，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5f430-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="5f430-144">多重身份验证 (MFA) 、基于客户端证书的身份验证 (CBA) 、条件访问 (CA) /移动应用程序管理 (MAM) 和 Intune。</span><span class="sxs-lookup"><span data-stu-id="5f430-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="5f430-145">\*</span><span class="sxs-lookup"><span data-stu-id="5f430-145">\*</span></span>  <br/> |
|<span data-ttu-id="5f430-146">仅 On-prem</span><span class="sxs-lookup"><span data-stu-id="5f430-146">On-prem only</span></span>  <br/> |![支持 SFB 和 MA 拓扑，仅本地。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="5f430-148">用户所管理/邮箱位于：本地</span><span class="sxs-lookup"><span data-stu-id="5f430-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="5f430-149">MA 为本地 SFB 打开。</span><span class="sxs-lookup"><span data-stu-id="5f430-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="5f430-150">因此，授权服务器为 ADFS。</span><span class="sxs-lookup"><span data-stu-id="5f430-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="5f430-151">有关配置的详细信息，请参阅 [本文。](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="5f430-151">For configuration details, please see [this article.](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span></span> <br/> |<span data-ttu-id="5f430-152">仅 (Windows 桌面版 MFA - 不支持移动) 。</span><span class="sxs-lookup"><span data-stu-id="5f430-152">MFA (Windows Desktop only - mobile clients are not supported).</span></span> <span data-ttu-id="5f430-153">没有 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="5f430-153">No Exchange integration features.</span></span>  <br/><p> <span data-ttu-id="5f430-154">**建议不要采用这种方法。请参阅此处：**[https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="5f430-154">**We do not recommend this approach. Please see here:** [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span></span><p/> |

> [!IMPORTANT]
> <span data-ttu-id="5f430-155">建议 Skype for Business 和 Exchange (的 MA 状态相同，) 减少提示次数。</span><span class="sxs-lookup"><span data-stu-id="5f430-155">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span>

<span data-ttu-id="5f430-156">混合拓扑涉及 SFB 拆分域混合的组合。</span><span class="sxs-lookup"><span data-stu-id="5f430-156">Mixed topologies involve combinations of SFB split-domain hybrids.</span></span> <span data-ttu-id="5f430-157">目前支持以下混合拓扑：</span><span class="sxs-lookup"><span data-stu-id="5f430-157">These are the Mixed topologies currently supported:</span></span>

|<span data-ttu-id="5f430-158">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="5f430-158">Topology name</span></span>  <br/> |<span data-ttu-id="5f430-159">示例</span><span class="sxs-lookup"><span data-stu-id="5f430-159">Example</span></span>  <br/> |<span data-ttu-id="5f430-160">说明</span><span class="sxs-lookup"><span data-stu-id="5f430-160">Description</span></span>  <br/> |<span data-ttu-id="5f430-161">支持</span><span class="sxs-lookup"><span data-stu-id="5f430-161">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f430-162">混合 1</span><span class="sxs-lookup"><span data-stu-id="5f430-162">Mixed 1</span></span>  <br/> |![支持 SFB 与 MA 拓扑，混合 1 (EXO + SFB) 。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="5f430-164">用户所管理/邮箱位于：EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="5f430-164">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="5f430-165">未为 SFB 启用 MA;此拓扑中没有任何 SFB MA 功能可用。</span><span class="sxs-lookup"><span data-stu-id="5f430-165">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="5f430-166">SFB 没有 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="5f430-166">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="5f430-167">混合 2</span><span class="sxs-lookup"><span data-stu-id="5f430-167">Mixed 2</span></span>  <br/> |![S4B 混合拓扑 2 支持 MA，SFBO 加上 MA 与 EXCH on-prem 一起运行。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="5f430-169">用户所管理/邮箱位于：EXCH 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="5f430-169">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="5f430-170">MA 仅适用于 SFBO。</span><span class="sxs-lookup"><span data-stu-id="5f430-170">MA is on for SFBO only.</span></span> <span data-ttu-id="5f430-171">对于 SFBO 中托管的用户，授权服务器是 Azure AD，而 AD 适用于本地 EXCH。</span><span class="sxs-lookup"><span data-stu-id="5f430-171">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="5f430-172">使用 Intune 的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="5f430-172">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="5f430-173">混合 3</span><span class="sxs-lookup"><span data-stu-id="5f430-173">Mixed 3</span></span>  <br/> |![支持 MA 与 SFB、使用 MA 的 EXO 以及本地 EXCH 和 SFB。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="5f430-175">用户所在的用户/邮箱：EXO + SFB 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="5f430-175">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="5f430-176">此拓扑中没有任何 SFB MA 功能可用</span><span class="sxs-lookup"><span data-stu-id="5f430-176">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="5f430-177">SFB 没有 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="5f430-177">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="5f430-178">混合 4</span><span class="sxs-lookup"><span data-stu-id="5f430-178">Mixed 4</span></span>  <br/> |![支持 MA 与 SFB、SFBO（MA 打开）以及 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="5f430-180">用户所在的用户/邮箱：EXCH +SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="5f430-180">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="5f430-181">MA 为 SFBO 打开，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5f430-181">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="5f430-182">SFB 和 EXO 中的 On-prem 用户使用 AD。</span><span class="sxs-lookup"><span data-stu-id="5f430-182">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="5f430-183">MFA、CBA、CA/MAM with Intune 仅适用于联机用户。\*</span><span class="sxs-lookup"><span data-stu-id="5f430-183">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="5f430-184">混合 5</span><span class="sxs-lookup"><span data-stu-id="5f430-184">Mixed 5</span></span>  <br/> |![SFB 中支持的 MA、带 MA 的 EXO 和带 MA 的 SFBO，以及本地 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="5f430-186">用户所在的用户/邮箱：EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="5f430-186">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="5f430-187">MA 在 EXO 和 SFBO 中均打开，因此对于 SFBO 中托管的用户，授权服务器是 Azure AD;EXCH 和 SFB 中的用户使用 AD。</span><span class="sxs-lookup"><span data-stu-id="5f430-187">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="5f430-188">MFA、CBA、CA/MAM with Intune 仅适用于联机用户。\*</span><span class="sxs-lookup"><span data-stu-id="5f430-188">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="5f430-189">混合 6</span><span class="sxs-lookup"><span data-stu-id="5f430-189">Mixed 6</span></span>  <br/> |![在混合 6 拓扑中，所有四个假设位置都启用新式验证- 对于新式身份验证，这是理想选择。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="5f430-191">用户所在的用户/邮箱：EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="5f430-191">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="5f430-192">MA 位于任何地方，因此授权服务器是适用于所有用户的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="5f430-192">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="5f430-193"> (联机和本地部署) </span><span class="sxs-lookup"><span data-stu-id="5f430-193">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="5f430-194">请参阅 [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) 了解部署步骤。</span><span class="sxs-lookup"><span data-stu-id="5f430-194">Please see [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) for deployment steps.</span></span> <br/> |<span data-ttu-id="5f430-195">MFA、CBA 和 CA/MAM (Intune) 适用于所有用户。</span><span class="sxs-lookup"><span data-stu-id="5f430-195">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |

<span data-ttu-id="5f430-196">\* - MFA 包括 Windows 桌面、MAC、iOS、Android 设备和 Windows 手机;CBA 包括 Windows 桌面、iOS 和 Android 设备;使用 Intune 的 CA/MAM 包括 Android 和 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="5f430-196">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f430-197">值得注意的是，在某些情况下，用户可能会看到多个提示，尤其是当客户端可能需要和请求的所有服务器资源中的 MA 状态不同时，与混合拓扑的所有版本一样。</span><span class="sxs-lookup"><span data-stu-id="5f430-197">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f430-198">另请注意，在某些情况下， (混合 1、3 和 5) [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) 注册表项必须设置为正确配置 Windows 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="5f430-198">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>