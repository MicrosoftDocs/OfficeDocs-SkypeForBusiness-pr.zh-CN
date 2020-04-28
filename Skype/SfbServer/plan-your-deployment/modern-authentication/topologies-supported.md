---
title: 新式验证支持的 Skype for business 拓扑
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
ms.openlocfilehash: 8c580b5ddbc38073960885375b74c73222ee272d
ms.sourcegitcommit: 3ef5c913318fdeeaa8c55caab07c2f8224eae2b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43898107"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="25f99-103">新式验证支持的 Skype for business 拓扑</span><span class="sxs-lookup"><span data-stu-id="25f99-103">Skype for Business topologies supported with Modern Authentication</span></span>

<span data-ttu-id="25f99-104">本文列出了 Skype for Business 中的新式验证支持的在线和本地拓扑，以及适用于每个拓扑的安全功能。</span><span class="sxs-lookup"><span data-stu-id="25f99-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>

## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="25f99-105">Skype for Business 中的新式验证</span><span class="sxs-lookup"><span data-stu-id="25f99-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="25f99-106">Skype for Business 可以利用新式验证的安全优势。</span><span class="sxs-lookup"><span data-stu-id="25f99-106">Skype for Business can leverage security advantages of Modern Authentication.</span></span> <span data-ttu-id="25f99-107">由于 Skype for business 与 Exchange 密切合作，因此 Exchange 的 MA 状态也会影响 Skype for Business 客户端用户将看到的登录行为。</span><span class="sxs-lookup"><span data-stu-id="25f99-107">Because Skype for Business works closely with Exchange, the login behavior Skype for Business client users will see will also be affected by the MA status of Exchange.</span></span> <span data-ttu-id="25f99-108">如果你拥有 Skype for Business 拆分域混合，也会应用此项。</span><span class="sxs-lookup"><span data-stu-id="25f99-108">This will also apply if you have a Skype for Business split-domain hybrid.</span></span> <span data-ttu-id="25f99-109">这是许多移动部件，但此处的目标是可轻松可视化受支持拓扑的列表。</span><span class="sxs-lookup"><span data-stu-id="25f99-109">That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>

<span data-ttu-id="25f99-110">对于 Skype for Business、Skype for business online、Exchange Server 和 Exchange online，MA 支持哪些拓扑？</span><span class="sxs-lookup"><span data-stu-id="25f99-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="25f99-111">Skype for Business 中支持的 MA 拓扑</span><span class="sxs-lookup"><span data-stu-id="25f99-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="25f99-112">有可能有两个服务器应用程序，以及两个 Office 365 工作负载，与 MA 使用的 Skype for business 拓扑有关。</span><span class="sxs-lookup"><span data-stu-id="25f99-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>

- <span data-ttu-id="25f99-113">Skype for Business server （CU 5）本地</span><span class="sxs-lookup"><span data-stu-id="25f99-113">Skype for Business server (CU 5) on-premises</span></span>

- <span data-ttu-id="25f99-114">Skype for Business online （SFBO）</span><span class="sxs-lookup"><span data-stu-id="25f99-114">Skype for Business online (SFBO)</span></span>

- <span data-ttu-id="25f99-115">Exchange server 本地</span><span class="sxs-lookup"><span data-stu-id="25f99-115">Exchange server on-premises</span></span>

- <span data-ttu-id="25f99-116">Exchange server online （EXO）</span><span class="sxs-lookup"><span data-stu-id="25f99-116">Exchange server online (EXO)</span></span>

<span data-ttu-id="25f99-117">MA 的另一个重要部分是知道用户的身份验证（身份验证）和授权（authZ）将发生的位置。</span><span class="sxs-lookup"><span data-stu-id="25f99-117">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place.</span></span> <span data-ttu-id="25f99-118">这两个选项为：</span><span class="sxs-lookup"><span data-stu-id="25f99-118">The two options are:</span></span>

- <span data-ttu-id="25f99-119">Azure AD，在 Microsoft 云中联机</span><span class="sxs-lookup"><span data-stu-id="25f99-119">Azure AD, online in the Microsoft Cloud</span></span>

- <span data-ttu-id="25f99-120">Active Directory 联合服务器（ADFS）本地</span><span class="sxs-lookup"><span data-stu-id="25f99-120">Active Directory Federation Server (ADFS) on-premises</span></span>

<span data-ttu-id="25f99-121">因此，它看起来有点类似于在 EXO 和 SFBO 中使用 Azure AD 的云，Exchange Server （EXCH）和 Skype for Business Server （SFB）本地。</span><span class="sxs-lookup"><span data-stu-id="25f99-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>

![打开 MA 时可涉及的所有应用程序（Exchange 和 Skype for Business）和工作负荷（EXO 和 SFBO）以及这两个授权服务器（ADFS 和 evoSTS）的示例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

<span data-ttu-id="25f99-123">以下是受支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="25f99-123">Here are the supported topologies.</span></span> <span data-ttu-id="25f99-124">请记下图形的键：</span><span class="sxs-lookup"><span data-stu-id="25f99-124">Please note the key for the graphics:</span></span>

- <span data-ttu-id="25f99-125">如果图标灰显或灰色，则不在方案中使用。</span><span class="sxs-lookup"><span data-stu-id="25f99-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>

- <span data-ttu-id="25f99-126">EXO 是 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="25f99-126">EXO is Exchange Online.</span></span>

- <span data-ttu-id="25f99-127">SFBO 是 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="25f99-127">SFBO is Skype for Business Online.</span></span>

- <span data-ttu-id="25f99-128">EXCH 是 Exchange 内部部署。</span><span class="sxs-lookup"><span data-stu-id="25f99-128">EXCH is Exchange on-premises.</span></span>

- <span data-ttu-id="25f99-129">SFB 是 Skype for business 内部部署。</span><span class="sxs-lookup"><span data-stu-id="25f99-129">SFB is Skype for Business on-premises.</span></span>

- <span data-ttu-id="25f99-130">授权服务器由三角形表示，例如，Azure AD 是其背后有云的三角形。</span><span class="sxs-lookup"><span data-stu-id="25f99-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>

- <span data-ttu-id="25f99-131">箭头指向客户端尝试访问指定服务器资源时将使用的授权服务器。</span><span class="sxs-lookup"><span data-stu-id="25f99-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>

<span data-ttu-id="25f99-132">首先，让我们在仅本地或仅限云的拓扑中使用具有 Skype for Business 的 MA。</span><span class="sxs-lookup"><span data-stu-id="25f99-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25f99-133">你是否已准备好在 Skype for Business Online 中设置新式验证？</span><span class="sxs-lookup"><span data-stu-id="25f99-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="25f99-134">启用此功能的步骤在[这里](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="25f99-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>

|<span data-ttu-id="25f99-135">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="25f99-135">Topology name</span></span>  <br/> |<span data-ttu-id="25f99-136">示例</span><span class="sxs-lookup"><span data-stu-id="25f99-136">Example</span></span>  <br/> |<span data-ttu-id="25f99-137">说明</span><span class="sxs-lookup"><span data-stu-id="25f99-137">Description</span></span>  <br/> |<span data-ttu-id="25f99-138">支持</span><span class="sxs-lookup"><span data-stu-id="25f99-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="25f99-139">仅云</span><span class="sxs-lookup"><span data-stu-id="25f99-139">Cloud only</span></span>  <br/> |![受支持的 SFB 与 MA 拓扑，仅限云。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="25f99-141">用户托管/邮箱位置：联机</span><span class="sxs-lookup"><span data-stu-id="25f99-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="25f99-142">MA 对于 EXO 和 SFBO 都是打开的。</span><span class="sxs-lookup"><span data-stu-id="25f99-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="25f99-143">因此，授权服务器是 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="25f99-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="25f99-144">多因素身份验证（MFA）、基于客户端证书的身份验证（CBA）、条件访问（CA）/Mobile 应用程序管理（MAM）（Intune）。</span><span class="sxs-lookup"><span data-stu-id="25f99-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="25f99-145">\*</span><span class="sxs-lookup"><span data-stu-id="25f99-145">\*</span></span>  <br/> |
|<span data-ttu-id="25f99-146">仅限本地</span><span class="sxs-lookup"><span data-stu-id="25f99-146">On-prem only</span></span>  <br/> |![受支持的 SFB 与 MA 拓扑，仅限本地使用。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="25f99-148">用户托管/邮箱位置：内部部署</span><span class="sxs-lookup"><span data-stu-id="25f99-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="25f99-149">MA 针对内部部署的 SFB。</span><span class="sxs-lookup"><span data-stu-id="25f99-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="25f99-150">因此，授权服务器是 ADFS。</span><span class="sxs-lookup"><span data-stu-id="25f99-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="25f99-151">有关配置的详细信息，请参阅[本文。](https://technet.microsoft.com/library/mt710548.aspx)</span><span class="sxs-lookup"><span data-stu-id="25f99-151">For configuration details, please see [this article.](https://technet.microsoft.com/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="25f99-152">MFA （不支持仅限 Windows 桌面-移动客户端）。</span><span class="sxs-lookup"><span data-stu-id="25f99-152">MFA (Windows Desktop only - mobile clients are not supported).</span></span> <span data-ttu-id="25f99-153">无 Exchange 集成功能。</span><span class="sxs-lookup"><span data-stu-id="25f99-153">No Exchange integration features.</span></span>  <br/><p> <span data-ttu-id="25f99-154">**我们不建议采用这种方法。请参阅此处：**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span><span class="sxs-lookup"><span data-stu-id="25f99-154">**We do not recommend this approach. Please see here:** [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)</span></span><p/> |

> [!IMPORTANT]
> <span data-ttu-id="25f99-155">建议在 Skype for Business 和 Exchange （及其在线版）之间使用相同的 MA 状态，以减少提示次数。</span><span class="sxs-lookup"><span data-stu-id="25f99-155">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span>

<span data-ttu-id="25f99-156">混合拓扑涉及 SFB 拆分域混合的组合。</span><span class="sxs-lookup"><span data-stu-id="25f99-156">Mixed topologies involve combinations of SFB split-domain hybrids.</span></span> <span data-ttu-id="25f99-157">以下是当前支持的混合拓扑：</span><span class="sxs-lookup"><span data-stu-id="25f99-157">These are the Mixed topologies currently supported:</span></span>

|<span data-ttu-id="25f99-158">拓扑名称</span><span class="sxs-lookup"><span data-stu-id="25f99-158">Topology name</span></span>  <br/> |<span data-ttu-id="25f99-159">示例</span><span class="sxs-lookup"><span data-stu-id="25f99-159">Example</span></span>  <br/> |<span data-ttu-id="25f99-160">说明</span><span class="sxs-lookup"><span data-stu-id="25f99-160">Description</span></span>  <br/> |<span data-ttu-id="25f99-161">支持</span><span class="sxs-lookup"><span data-stu-id="25f99-161">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="25f99-162">混合1</span><span class="sxs-lookup"><span data-stu-id="25f99-162">Mixed 1</span></span>  <br/> |![支持的 SFB 与 MA 拓扑，Mixed 1 （EXO + SFB）。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="25f99-164">用户托管/邮箱位置： EXO 和 SFB</span><span class="sxs-lookup"><span data-stu-id="25f99-164">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="25f99-165">没有为 SFB 启用 MA;此拓扑中不提供 SFB MA 功能。</span><span class="sxs-lookup"><span data-stu-id="25f99-165">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="25f99-166">SFB 的 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="25f99-166">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="25f99-167">混合2</span><span class="sxs-lookup"><span data-stu-id="25f99-167">Mixed 2</span></span>  <br/> |![支持的带有 S4B 混合拓扑2、SFBO 和 MA 的 MA，使用 EXCH on 本地。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="25f99-169">用户托管/邮箱位置： EXCH 和 SFBO</span><span class="sxs-lookup"><span data-stu-id="25f99-169">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="25f99-170">MA 仅适用于 SFBO。</span><span class="sxs-lookup"><span data-stu-id="25f99-170">MA is on for SFBO only.</span></span> <span data-ttu-id="25f99-171">授权服务器是托管在 SFBO 中的用户的 Azure AD，但 EXCH 本地的 AD。</span><span class="sxs-lookup"><span data-stu-id="25f99-171">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="25f99-172">使用 Intune 的 MFA、CBA、CA/MAM。\*</span><span class="sxs-lookup"><span data-stu-id="25f99-172">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="25f99-173">混合3</span><span class="sxs-lookup"><span data-stu-id="25f99-173">Mixed 3</span></span>  <br/> |![支持的 MA 与 SFB、EXO、MA on、EXCH 和 SFB 在本地使用。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="25f99-175">用户托管/邮箱位置： EXO + SFB 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="25f99-175">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="25f99-176">此拓扑中不提供任何 SFB MA 功能</span><span class="sxs-lookup"><span data-stu-id="25f99-176">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="25f99-177">SFB 的 MA 功能。</span><span class="sxs-lookup"><span data-stu-id="25f99-177">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="25f99-178">混合4</span><span class="sxs-lookup"><span data-stu-id="25f99-178">Mixed 4</span></span>  <br/> |![支持的 MA 与 SFB、SFBO、MA 打开、加 EXCH 和 SFB。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="25f99-180">用户托管/邮箱位置： EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="25f99-180">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="25f99-181">MA 对 SFBO 是打开的，因此，授权服务器是托管在 SFBO 中的用户的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="25f99-181">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="25f99-182">SFB 和 EXO 中的本地用户使用 AD。</span><span class="sxs-lookup"><span data-stu-id="25f99-182">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="25f99-183">仅用于联机用户的仅 MFA、CBA、CA/MAM 和 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="25f99-183">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="25f99-184">混合5</span><span class="sxs-lookup"><span data-stu-id="25f99-184">Mixed 5</span></span>  <br/> |![SFB、EXO 和 MA 中支持的 MA，以及 SFBO 和，以及在本地的 EXCH 和 SFB。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="25f99-186">用户托管/邮箱位置： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="25f99-186">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="25f99-187">MA 同时在 EXO 和 SFBO 中，因此，授权服务器是托管在 SFBO 中的用户的 Azure AD;EXCH 和 SFB 中的本地用户使用 AD。</span><span class="sxs-lookup"><span data-stu-id="25f99-187">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="25f99-188">仅用于联机用户的仅 MFA、CBA、CA/MAM 和 Intune。\*</span><span class="sxs-lookup"><span data-stu-id="25f99-188">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="25f99-189">混合6</span><span class="sxs-lookup"><span data-stu-id="25f99-189">Mixed 6</span></span>  <br/> |![在混合的6拓扑中，新式验证在所有四个可能位置中，而对于新式身份验证，则是理想的理想。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="25f99-191">用户托管/邮箱位置： EXO + SFBO、EXO + SFB、EXCH + SFBO 或 EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="25f99-191">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="25f99-192">MA 在无处不在，因此授权服务器是所有用户的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="25f99-192">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="25f99-193">（联机和本地）</span><span class="sxs-lookup"><span data-stu-id="25f99-193">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="25f99-194">有关部署[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)步骤，请参阅。</span><span class="sxs-lookup"><span data-stu-id="25f99-194">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="25f99-195">对所有用户的 MFA、CBA 和 CA/MAM （通过 Intune）。</span><span class="sxs-lookup"><span data-stu-id="25f99-195">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |

<span data-ttu-id="25f99-196">\*-MFA 包括 Windows Desktop、MAC、iOS、Android 设备和 Windows phone;CBA 包括 Windows Desktop、iOS 和 Android 设备;具有 Intune 的 CA/MAM，包括 Android 和 iOS 设备。</span><span class="sxs-lookup"><span data-stu-id="25f99-196">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25f99-197">请务必注意，在某些情况下，用户可能会看到**多个提示**，特别是在客户端可能需要和请求的所有服务器资源中的 MA 状态不相同，这与所有版本的混合拓扑一样。</span><span class="sxs-lookup"><span data-stu-id="25f99-197">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25f99-198">另请注意，在某些情况下（特别是混合1、3和5），必须设置[AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)注册表项，以正确配置 Windows 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="25f99-198">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>


