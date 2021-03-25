---
title: 规划在网络内部和外部关闭旧式身份验证方法
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
ms.assetid: ''
description: 本文概述了 cmdlet，这些 cmdlet 使管理员可以更加控制在企业内外使用的身份验证方法。 管理员可以在内部或外部打开或关闭身份验证方法。
ms.openlocfilehash: 3d7217167f7e72c4db0ec438fb20d746cd612cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116050"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a><span data-ttu-id="a8ea5-104">计划在网络内部和外部关闭旧式身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-104">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>

> [!NOTE]
> <span data-ttu-id="a8ea5-105">如果你要阅读本文，你应该已经了解支持的新式验证拓扑、ADAL 以及新式验证配置，但是，如果你不了解，以下是需要开始的文章：</span><span class="sxs-lookup"><span data-stu-id="a8ea5-105">If you're about to read this article, you should already know about supported Modern Authentication topologies, ADAL, and about Modern Authentication config, but, in case you don't, here are the articles you need to start out:</span></span> 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
<span data-ttu-id="a8ea5-106">新式验证并不仅仅是启用更安全的身份验证方法（Two-Factor身份验证或基于证书的身份验证方法，它还无需用户名和密码即可执行用户授权。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-106">Modern Authentication doesn't just enable more secure methods of authentication, like Two-Factor Auth, or Certificate-based Auth, it can carry out authorization of your user without needing a username or password too.</span></span> <span data-ttu-id="a8ea5-107">它相当方便。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-107">It's pretty handy.</span></span>

<span data-ttu-id="a8ea5-108">本文将帮助你将已利用的拒绝服务 (DOS) 攻击的漏洞插入 Skype for Business 服务器，方法是关闭用于对网络进行外部、内部或两者身份验证的较旧方法。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-108">This article will help you plug holes that have been exploited for Denial Of Service (DOS) attacks on Skype for Business Servers, by turning off older methods used for authentication, externally, internally, or both, to your network.</span></span> <span data-ttu-id="a8ea5-109">例如，帮助停止 DOS 攻击的一个好方法是关闭 Windows 集成身份验证 (包括 NTLM 和 Kerberos) 。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-109">For example, one good method to help stop DOS attacks would be to turn off Windows Integrated Authentication (which includes NTLM and Kerberos).</span></span> <span data-ttu-id="a8ea5-110">在外部关闭 NTLM 并依赖基于证书的身份验证有助于保护密码免遭泄露。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-110">Turning off NTLM externally and relying on certificate-based authentication helps to protect passwords from exposure.</span></span> <span data-ttu-id="a8ea5-111">这是因为 NTLM 使用密码凭据对用户进行身份验证，但基于证书的身份验证（由新式身份验证启用）不会。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-111">This is because NTLM uses password credentials to authenticate users, but certificate-based authentication -- enabled by Modern Auth -- doesn't.</span></span> <span data-ttu-id="a8ea5-112">这意味着减少 DOS 攻击的一个理想选项是，在外部阻止 NTLM，并仅在该位置使用基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-112">That means one ideal option to reduce DOS attacks is to block NTLM externally, and use only certificate-based authentication there, instead.</span></span>

<span data-ttu-id="a8ea5-113">好了，让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-113">All right, let's get started.</span></span>

## <a name="what-would-you-be-changing"></a><span data-ttu-id="a8ea5-114">要更改什么？</span><span class="sxs-lookup"><span data-stu-id="a8ea5-114">What would you be changing?</span></span> 

<span data-ttu-id="a8ea5-115">这些 cmdlet 适用于 SIP 和 Web 服务访问点。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-115">These cmdlets work for both SIP and Web Services points of access.</span></span> <span data-ttu-id="a8ea5-116">尽管这两个通道使用不同的访问方法（从 NTLM 和 Kerberos 到匿名访问）运行游戏，但 Skype for Business 使用的所有标准方法都已被考虑在内。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-116">Though these two channels use different access methods, running the gamut from NTLM and Kerberos to Anonymous access, all standard methods used by Skype for Business have been taken into consideration.</span></span>

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a><span data-ttu-id="a8ea5-117">如何获取 Get- 和 Set-CsAuthConfig cmdlet</span><span class="sxs-lookup"><span data-stu-id="a8ea5-117">How to get the Get- and Set-CsAuthConfig cmdlets</span></span>

<span data-ttu-id="a8ea5-118">这些 cmdlet 仅在 Microsoft Skype for Business Server 2015 的 2018 年 7 月累积更新 (6.0.9319.534) 后安装，然后你便拥有各种可用于 Skype for Business 服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-118">These cmdlets will only be installed post July 2018 cumulative update (6.0.9319.534) for Microsoft Skype for Business Server 2015, and then you have a variety of topologies that can be rolled out for your Skype for Business server.</span></span>

## <a name="topologies"></a><span data-ttu-id="a8ea5-119">拓扑</span><span class="sxs-lookup"><span data-stu-id="a8ea5-119">Topologies</span></span>

<span data-ttu-id="a8ea5-120">必须记住，这些是此方案中涉及的受支持拓扑！</span><span class="sxs-lookup"><span data-stu-id="a8ea5-120">It's important to keep in mind that these are the Supported Topologies involved in this scenario!</span></span> <span data-ttu-id="a8ea5-121">例如，如果需要转到"支持"，获得阻止方法的帮助，则需要在下面的类型中配置。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-121">If you need to go to Support for help with blocking a method, for example, you will need to have a configuration among the types below.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a8ea5-122">在下表和说明中，新式验证缩写为 __MA，Windows__ *集成* 身份验证缩写为 __Win。__</span><span class="sxs-lookup"><span data-stu-id="a8ea5-122">In the table and descriptions below, *Modern Authentication* is abbreviated as __MA__ and *Windows Integrated Authentication* is abbreviated as __Win__.</span></span> <span data-ttu-id="a8ea5-123">提醒一下，Windows 集成身份验证由两种方法决定：NTLM 和 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-123">As a reminder, Windows Integrated Authentication is made up of two methods: NTLM and Kerberos authentication.</span></span> <span data-ttu-id="a8ea5-124">你需要知道这一点，以正确读取表！</span><span class="sxs-lookup"><span data-stu-id="a8ea5-124">You'll need to know this to read the table properly!</span></span>


|       |<span data-ttu-id="a8ea5-125">外部</span><span class="sxs-lookup"><span data-stu-id="a8ea5-125">Externally</span></span>  |<span data-ttu-id="a8ea5-126">内部</span><span class="sxs-lookup"><span data-stu-id="a8ea5-126">Internally</span></span>  |<span data-ttu-id="a8ea5-127">参数</span><span class="sxs-lookup"><span data-stu-id="a8ea5-127">Parameter</span></span>  |
|---------|:---------|:---------|---------|
|<span data-ttu-id="a8ea5-128">__类型 1__</span><span class="sxs-lookup"><span data-stu-id="a8ea5-128">__Type 1__</span></span>   |  <span data-ttu-id="a8ea5-129">MA + Win</span><span class="sxs-lookup"><span data-stu-id="a8ea5-129">MA + Win</span></span>       | <span data-ttu-id="a8ea5-130">MA + Win</span><span class="sxs-lookup"><span data-stu-id="a8ea5-130">MA + Win</span></span>         |  <span data-ttu-id="a8ea5-131">AllowAllExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="a8ea5-131">AllowAllExternallyAndInternally</span></span>       |
|<span data-ttu-id="a8ea5-132">__类型 2__</span><span class="sxs-lookup"><span data-stu-id="a8ea5-132">__Type 2__</span></span>   |  <span data-ttu-id="a8ea5-133">MA</span><span class="sxs-lookup"><span data-stu-id="a8ea5-133">MA</span></span>       | <span data-ttu-id="a8ea5-134">MA + Win</span><span class="sxs-lookup"><span data-stu-id="a8ea5-134">MA + Win</span></span>         | <span data-ttu-id="a8ea5-135">BlockWindowsAuthExternally</span><span class="sxs-lookup"><span data-stu-id="a8ea5-135">BlockWindowsAuthExternally</span></span>        |
|<span data-ttu-id="a8ea5-136">__类型 3__</span><span class="sxs-lookup"><span data-stu-id="a8ea5-136">__Type 3__</span></span>   |  <span data-ttu-id="a8ea5-137">MA</span><span class="sxs-lookup"><span data-stu-id="a8ea5-137">MA</span></span>       | <span data-ttu-id="a8ea5-138">MA</span><span class="sxs-lookup"><span data-stu-id="a8ea5-138">MA</span></span>        | <span data-ttu-id="a8ea5-139">BlockWindowsAuthExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="a8ea5-139">BlockWindowsAuthExternallyAndInternally</span></span>        |
|<span data-ttu-id="a8ea5-140">__类型 4__</span><span class="sxs-lookup"><span data-stu-id="a8ea5-140">__Type 4__</span></span>   |  <span data-ttu-id="a8ea5-141">MA</span><span class="sxs-lookup"><span data-stu-id="a8ea5-141">MA</span></span>       | <span data-ttu-id="a8ea5-142">Win</span><span class="sxs-lookup"><span data-stu-id="a8ea5-142">Win</span></span>        | <span data-ttu-id="a8ea5-143">BlockWindowsAuthExternallyAndModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="a8ea5-143">BlockWindowsAuthExternallyAndModernAuthInternally</span></span>    |
|<span data-ttu-id="a8ea5-144">__类型 5__</span><span class="sxs-lookup"><span data-stu-id="a8ea5-144">__Type 5__</span></span>   |  <span data-ttu-id="a8ea5-145">MA + Win</span><span class="sxs-lookup"><span data-stu-id="a8ea5-145">MA + Win</span></span>       | <span data-ttu-id="a8ea5-146">Win</span><span class="sxs-lookup"><span data-stu-id="a8ea5-146">Win</span></span>        | <span data-ttu-id="a8ea5-147">BlockModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="a8ea5-147">BlockModernAuthInternally</span></span>         |

<span data-ttu-id="a8ea5-148">__类型 1 说明：__ 这是为 Skype for Business Server 打开 MA __时的默认__ 方案。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-148">__Type 1 Description:__ This is the default scenario when MA is turned __on__ for Skype for Business Server.</span></span> <span data-ttu-id="a8ea5-149">换句话说，这是 *配置* MA 时的起点。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-149">In other words, this is the *starting point* when MA is configured.</span></span>

<span data-ttu-id="a8ea5-150">__类型 2 说明：__ 此拓扑在外部阻止 *NTLM，* 但允许 NTLM 或 Kerberos (不支持 ADAL) 在内部 *工作*。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-150">__Type 2 Description:__ This topology blocks NTLM *externally*, but allows NTLM or Kerberos (for clients that don't support ADAL) to work *internally*.</span></span> <span data-ttu-id="a8ea5-151">如果你的客户端支持 ADAL，他们将在内部使用 MA。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-151">If your clients  do support ADAL they will use MA internally.</span></span>

<span data-ttu-id="a8ea5-152">__类型 3 说明：__ 此拓扑要求所有用户使用 MA。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-152">__Type 3 Description:__ This topology requires MA for all users.</span></span> <span data-ttu-id="a8ea5-153">所有支持 ADAL 的客户端都将在此拓扑中工作，例如，如果关闭对基于证书的身份验证的密码的使用，将不会利用密码。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-153">All your ADAL-capable clients will work in this topology, and passwords will not be leveraged if, for example, you turn off the use of passwords with Certificate-based Auth.</span></span>

<span data-ttu-id="a8ea5-154">__类型 4 说明：__ 此拓扑在外部阻止 *NTLM，* 在内部阻止 MA。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-154">__Type 4 Description:__ This topology blocks NTLM *externally* and MA internally.</span></span> <span data-ttu-id="a8ea5-155">它允许 *所有客户端在* 内部使用旧身份验证 (支持 ADAL 的客户端) 。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-155">It allows *all clients* to use legacy authentication methods *internally* (even ADAL-capable clients).</span></span>

<span data-ttu-id="a8ea5-156">__类型 5 描述：__*从* 外部来说，新式 ADAL 客户端将使用 MA，任何不支持 ADAL 的客户端都将使用旧版身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-156">__Type 5 Description:__ *Externally*, your modern ADAL clients will use MA and any clients that don't support ADAL will use legacy authentication methods.</span></span> <span data-ttu-id="a8ea5-157">但是 *，在内部\*\*，所有客户端* 将使用旧版 (包括所有支持 ADAL 的客户端) 。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-157">But, *internally* *all clients* will use legacy authentication (including all ADAL-capable clients).</span></span>

<span data-ttu-id="a8ea5-158">很容易会失去对可用选项中保护密码的目标的跟踪。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-158">It's pretty easy to lose track of the goal of protecting your passwords in the options available.</span></span> <span data-ttu-id="a8ea5-159">请记住，理想情况是在外部使用 MA (例如，通过配置基于证书的身份验证) 以避免 DOS 攻击。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-159">Keep in mind the ideal situation is to use MA externally (for example, by configuring certificate-based auth), to avoid DOS attacks.</span></span> <span data-ttu-id="a8ea5-160">如果你在内部为新式客户端利用它，你还将针对 Skype for Business Server DOS 攻击对网络进行未来证明。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-160">If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.</span></span>

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a><span data-ttu-id="a8ea5-161">为什么要在Set-CsAuthConfig级别使用全局</span><span class="sxs-lookup"><span data-stu-id="a8ea5-161">Why to use Set-CsAuthConfig at the Global level</span></span>

<span data-ttu-id="a8ea5-162">`Set-CsAuthConfig`此 cmdlet 将影响注册器角色和 Web 服务角色上的配置。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-162">The `Set-CsAuthConfig` cmdlet effects configuration on both the Registrar and the Web Services roles.</span></span>

<span data-ttu-id="a8ea5-163">此 cmdlet 旨在运行在 Skype for Business 服务器的全局级别。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-163">This cmdlet is meant to be run at the Global level of your Skype for Business server.</span></span> <span data-ttu-id="a8ea5-164">*它可以* 在池级别运行，但不建议这样做，因为这会增加安装的复杂性。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-164">It *can* be run at the Pool level but that is *not recommended* because it will add complexity to your installation.</span></span> <span data-ttu-id="a8ea5-165">在池级别运行这些命令，如果您的池不包含 (例如，它没有 Web 服务) ，则只会为注册器角色设置。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-165">By running these commands at the Pool level, if your Pool doesn't have all of the roles included (for example, it doesn't have Web Services), the settings will only be set for the Registrar role.</span></span> <span data-ttu-id="a8ea5-166">在这种情况下，Web 服务将继续使用全局级别的设置，这可能会令人混淆的行为 (尤其是在无意中完成此操作) 。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-166">In that case, Web Services will carry on with settings from the Global level, which can be confusing behaviour (particularly when this is done unintentionally).</span></span>

<span data-ttu-id="a8ea5-167">如果客户端使用一个池中的注册器设置和另一个池中的 Web 服务设置，并且身份验证设置的状态不一致，则客户端可能无法登录。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-167">If a client uses the Registrar settings from one pool and the Web Services settings from another pool and the authentication settings are in an inconsistent state, yous clients may be unable to log on.</span></span>

<span data-ttu-id="a8ea5-168">此外，如果池只有一个角色：</span><span class="sxs-lookup"><span data-stu-id="a8ea5-168">Also, if there's only one role present for a pool:</span></span> 
* <span data-ttu-id="a8ea5-169">Set- 将仅设置与存在的角色对应的设置。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-169">Set- will only set the settings that correspond to the role that exists.</span></span> <span data-ttu-id="a8ea5-170">由于未设置某些设置，因此不会提供 *特殊* 警告。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-170">No special warning will be given because some settings were *not* set.</span></span> 
* <span data-ttu-id="a8ea5-171">Get- 将返回对应于已存在的角色的设置，以及不存在的角色的全局设置。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-171">Get- will return the setting that corresponds to the role that exists, and the Global settings for the role that doesn't exist.</span></span>
* <span data-ttu-id="a8ea5-172">如果池不存在任何角色，Set- 和 Get- 都将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-172">If neither role is present for a pool, both Set- and Get- will return an error message.</span></span>
* <span data-ttu-id="a8ea5-173">如果池存在这两个角色，但没有在池级别定义策略，则 Get- 将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-173">If both roles are present for a pool but policies aren't defined at the pool level, Get- will return an error message.</span></span>

<span data-ttu-id="a8ea5-174">对这些值执行 Get-，以及进行任何更改之前屏幕截图或记录其开始状态可能最明智。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-174">It may be wisest to do a Get- for these values, and to screenshot or record their starting state before making any changes.</span></span> <span data-ttu-id="a8ea5-175">还可以考虑在 OneNote 中保留更改日志。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-175">You might also consider keeping a log of changes in a OneNote.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="a8ea5-176">注意：配置 CsAuthConfig 后，必须在Enable-CsComputer运行此配置，设置才能生效。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-176">Note: After configuring the CsAuthConfig, you must run Enable-CsComputer on each computer in order for the settings to take effect.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8ea5-177">如果您使用的是 Lync Web Access (LWA) 并且必须使用基于表单的 Access (FBA) 进行外部访问，请重新配置 LWA，以便客户端可以使用匿名访问访问它以支持这些方案。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-177">If you're using Lync Web Access (LWA) and must use Forms-based Access (FBA) for external access, reconfigure LWA so that clients can access it with Anonymous Access to support these scenarios.</span></span> <span data-ttu-id="a8ea5-178">同样，如果使用拨入 Pin，则 FBA 将仅针对外部用户进行阻止。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-178">Likewise, if you use Dial-in Pin, FBA will be blocked for external users only.</span></span> <span data-ttu-id="a8ea5-179">如果他们需要更改其 PIN，则需要在内部登录到其公司。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-179">If they need to change their pin, they will need to login to their corporation to do so, internally.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="a8ea5-180">如果使用 BlockWindowsAuthExternally 参数在外部阻止 NTLM，请注意这还会在内部阻止 SIP 通道的 NTLM。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-180">If you use the BlockWindowsAuthExternally parameter to externally block NTLM, be aware this also blocks NTLM internally for the SIP channel.</span></span> <span data-ttu-id="a8ea5-181">但是，2010 版本的 Skype for Business 和 Lync 客户端仍可登录，因为它们将在内部使用 NTLM over HTTP 登录，然后获取证书以通过 SIP 登录。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-181">However, Skype for Business and Lync clients newer than 2010 will still be able to login because they will use NTLM over HTTP for signin, internally, and then fetch a certificate to login over SIP.</span></span> <span data-ttu-id="a8ea5-182">但是，2010 之前版本低于 2010 的客户端在这种情况下将无法在内部登录，您可能需要考虑升级这些应用程序，以便您的用户可以恢复安全功能。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-182">However, clients older than 2010 will not be able to login internally in this circumstance, and you may want to consider upgrading these applications so that your users can resume secure functionality.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="a8ea5-183">某些 Skype for Business Web 应用程序不支持 MA。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-183">Some of the Skype for Business web applications don't support MA.</span></span> <span data-ttu-id="a8ea5-184">因此，通过使用 BlockWindowsAuthExternallyAndInternally 方案，你将无法访问这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-184">So by using the BlockWindowsAuthExternallyAndInternally scenario, you won't be able to access these applications.</span></span> <span data-ttu-id="a8ea5-185">没有 MA 支持的应用程序包括 Web 计划程序、拨入页面、Skype for Business 控制面板 (、) 和响应组设置页。</span><span class="sxs-lookup"><span data-stu-id="a8ea5-185">Applications without MA support are Web Scheduler, Dial-In Page, Skype for Business Control Panel (CSCP), and Response Group Settings Page.</span></span> 

## <a name="links"></a><span data-ttu-id="a8ea5-186">链接</span><span class="sxs-lookup"><span data-stu-id="a8ea5-186">Links</span></span> 
- <span data-ttu-id="a8ea5-187">有关 PowerShell 的更多信息：</span><span class="sxs-lookup"><span data-stu-id="a8ea5-187">For more PowerShell information:</span></span>
    -  [<span data-ttu-id="a8ea5-188">Get-CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="a8ea5-188">Get-CsAuthConfig</span></span>](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [<span data-ttu-id="a8ea5-189">Set-CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="a8ea5-189">Set-CsAuthConfig</span></span>](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- <span data-ttu-id="a8ea5-190">有关如何使用命令或安装命令所需的 CU 的更多方向：</span><span class="sxs-lookup"><span data-stu-id="a8ea5-190">For more direction on how to use the commands or on the CU needed to install them:</span></span>
    - [<span data-ttu-id="a8ea5-191">Cmdlet 简介</span><span class="sxs-lookup"><span data-stu-id="a8ea5-191">Cmdlets briefing</span></span>](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - <span data-ttu-id="a8ea5-192">[Skype for Business Server 2015 更新 (](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) 常规) </span><span class="sxs-lookup"><span data-stu-id="a8ea5-192">[Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (General)</span></span>
    - <span data-ttu-id="a8ea5-193">2018 年 7 月 [Skype for Business Server 2015 核心](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) 组件 CU (6.0.9319.534) </span><span class="sxs-lookup"><span data-stu-id="a8ea5-193">The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span></span>


