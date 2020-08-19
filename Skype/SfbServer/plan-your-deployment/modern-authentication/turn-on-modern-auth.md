---
title: 规划在内部和外部在网络中关闭旧版身份验证方法
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
ms.assetid: ''
description: 本文概述了可让管理员更好地控制企业内部和外部使用的身份验证方法的 cmdlet。 管理员可以在内部或外部在其网络中打开或关闭身份验证方法。
ms.openlocfilehash: e2f9a8c9c8576c07de3158fb2446cb3cb89bac72
ms.sourcegitcommit: aae3eeb4dedd825ab176abe7e1aff9463c88799b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797450"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a><span data-ttu-id="ae220-104">规划在内部和外部将旧版身份验证方法关闭到网络中。</span><span class="sxs-lookup"><span data-stu-id="ae220-104">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>

> [!NOTE]
> <span data-ttu-id="ae220-105">如果要阅读本文，您应该已经知道受支持的新式身份验证拓扑、ADAL 和关于新式身份验证配置的信息，但如果你不知道，以下是你需要启动的文章：</span><span class="sxs-lookup"><span data-stu-id="ae220-105">If you're about to read this article, you should already know about supported Modern Authentication topologies, ADAL, and about Modern Authentication config, but, in case you don't, here are the articles you need to start out:</span></span> 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
<span data-ttu-id="ae220-106">新式验证不只是启用更安全的身份验证方法（如双重身份验证或基于证书的身份验证），它可以在不需要用户名或密码的情况下执行用户授权。</span><span class="sxs-lookup"><span data-stu-id="ae220-106">Modern Authentication doesn't just enable more secure methods of authentication, like Two-Factor Auth, or Certificate-based Auth, it can carry out authorization of your user without needing a username or password too.</span></span> <span data-ttu-id="ae220-107">这非常方便。</span><span class="sxs-lookup"><span data-stu-id="ae220-107">It's pretty handy.</span></span>

<span data-ttu-id="ae220-108">本文将帮助您插入已在 Skype for business 服务器上利用的拒绝服务 (DOS) 攻击的漏洞，方法是将用于身份验证的较旧方法（外部、内部或同时）关闭到网络。</span><span class="sxs-lookup"><span data-stu-id="ae220-108">This article will help you plug holes that have been exploited for Denial Of Service (DOS) attacks on Skype for Business Servers, by turning off older methods used for authentication, externally, internally, or both, to your network.</span></span> <span data-ttu-id="ae220-109">例如，一种帮助阻止 DOS 攻击的有用方法是关闭 Windows 集成身份验证 (，其中包括 NTLM 和 Kerberos) 。</span><span class="sxs-lookup"><span data-stu-id="ae220-109">For example, one good method to help stop DOS attacks would be to turn off Windows Integrated Authentication (which includes NTLM and Kerberos).</span></span> <span data-ttu-id="ae220-110">在外部关闭 NTLM 并依赖基于证书的身份验证有助于防止密码泄露。</span><span class="sxs-lookup"><span data-stu-id="ae220-110">Turning off NTLM externally and relying on certificate-based authentication helps to protect passwords from exposure.</span></span> <span data-ttu-id="ae220-111">这是因为 NTLM 使用密码凭据对用户进行身份验证，但基于证书的身份验证--由新式 Auth 启用--不会。</span><span class="sxs-lookup"><span data-stu-id="ae220-111">This is because NTLM uses password credentials to authenticate users, but certificate-based authentication -- enabled by Modern Auth -- doesn't.</span></span> <span data-ttu-id="ae220-112">这意味着降低 DOS 攻击的理想选择是在外部阻止 NTLM，而在那里仅使用基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ae220-112">That means one ideal option to reduce DOS attacks is to block NTLM externally, and use only certificate-based authentication there, instead.</span></span>

<span data-ttu-id="ae220-113">完全正确，让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="ae220-113">All right, let's get started.</span></span>

## <a name="what-would-you-be-changing"></a><span data-ttu-id="ae220-114">您要更改什么？</span><span class="sxs-lookup"><span data-stu-id="ae220-114">What would you be changing?</span></span> 

<span data-ttu-id="ae220-115">这些 cmdlet 适用于访问的 SIP 和 Web 服务点。</span><span class="sxs-lookup"><span data-stu-id="ae220-115">These cmdlets work for both SIP and Web Services points of access.</span></span> <span data-ttu-id="ae220-116">虽然这两个通道使用不同的访问方法，从 NTLM 和 Kerberos 到匿名访问运行，但所有 Skype for Business 使用的标准方法都已考虑在内。</span><span class="sxs-lookup"><span data-stu-id="ae220-116">Though these two channels use different access methods, running the gamut from NTLM and Kerberos to Anonymous access, all standard methods used by Skype for Business have been taken into consideration.</span></span>

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a><span data-ttu-id="ae220-117">如何获取 Get 和 CsAuthConfig cmdlet</span><span class="sxs-lookup"><span data-stu-id="ae220-117">How to get the Get- and Set-CsAuthConfig cmdlets</span></span>

<span data-ttu-id="ae220-118">这些 cmdlet 将仅安装在 Microsoft Skype for Business Server 2015 的2018累积更新 (6.0.9319.534) 中，然后您可以为您的 Skype for business server 推出多种拓扑。</span><span class="sxs-lookup"><span data-stu-id="ae220-118">These cmdlets will only be installed post July 2018 cumulative update (6.0.9319.534) for Microsoft Skype for Business Server 2015, and then you have a variety of topologies that can be rolled out for your Skype for Business server.</span></span>

## <a name="topologies"></a><span data-ttu-id="ae220-119">拓扑</span><span class="sxs-lookup"><span data-stu-id="ae220-119">Topologies</span></span>

<span data-ttu-id="ae220-120">请务必记住，这是此方案中涉及的受支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="ae220-120">It's important to keep in mind that these are the Supported Topologies involved in this scenario!</span></span> <span data-ttu-id="ae220-121">例如，如果您需要转到支持有关阻止方法的帮助，您需要在下面的类型之间配置配置。</span><span class="sxs-lookup"><span data-stu-id="ae220-121">If you need to go to Support for help with blocking a method, for example, you will need to have a configuration among the types below.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ae220-122">在下面的表和说明中， *新式身份验证* 以 __MA__ 为缩写， *Windows 集成身份验证* 以 __Win__形式进行缩写。</span><span class="sxs-lookup"><span data-stu-id="ae220-122">In the table and descriptions below, *Modern Authentication* is abbreviated as __MA__ and *Windows Integrated Authentication* is abbreviated as __Win__.</span></span> <span data-ttu-id="ae220-123">作为提醒，Windows 集成身份验证由两种方法组成： NTLM 和 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ae220-123">As a reminder, Windows Integrated Authentication is made up of two methods: NTLM and Kerberos authentication.</span></span> <span data-ttu-id="ae220-124">您需要知道这一点才能正确阅读表格！</span><span class="sxs-lookup"><span data-stu-id="ae220-124">You'll need to know this to read the table properly!</span></span>


|       |<span data-ttu-id="ae220-125">看</span><span class="sxs-lookup"><span data-stu-id="ae220-125">Externally</span></span>  |<span data-ttu-id="ae220-126">从</span><span class="sxs-lookup"><span data-stu-id="ae220-126">Internally</span></span>  |<span data-ttu-id="ae220-127">参数</span><span class="sxs-lookup"><span data-stu-id="ae220-127">Parameter</span></span>  |
|---------|:---------|:---------|---------|
|<span data-ttu-id="ae220-128">__键入1__</span><span class="sxs-lookup"><span data-stu-id="ae220-128">__Type 1__</span></span>   |  <span data-ttu-id="ae220-129">MA + Win</span><span class="sxs-lookup"><span data-stu-id="ae220-129">MA + Win</span></span>       | <span data-ttu-id="ae220-130">MA + Win</span><span class="sxs-lookup"><span data-stu-id="ae220-130">MA + Win</span></span>         |  <span data-ttu-id="ae220-131">AllowAllExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="ae220-131">AllowAllExternallyAndInternally</span></span>       |
|<span data-ttu-id="ae220-132">__类型2__</span><span class="sxs-lookup"><span data-stu-id="ae220-132">__Type 2__</span></span>   |  <span data-ttu-id="ae220-133">MA</span><span class="sxs-lookup"><span data-stu-id="ae220-133">MA</span></span>       | <span data-ttu-id="ae220-134">MA + Win</span><span class="sxs-lookup"><span data-stu-id="ae220-134">MA + Win</span></span>         | <span data-ttu-id="ae220-135">BlockWindowsAuthExternally</span><span class="sxs-lookup"><span data-stu-id="ae220-135">BlockWindowsAuthExternally</span></span>        |
|<span data-ttu-id="ae220-136">__类型3__</span><span class="sxs-lookup"><span data-stu-id="ae220-136">__Type 3__</span></span>   |  <span data-ttu-id="ae220-137">MA</span><span class="sxs-lookup"><span data-stu-id="ae220-137">MA</span></span>       | <span data-ttu-id="ae220-138">MA</span><span class="sxs-lookup"><span data-stu-id="ae220-138">MA</span></span>        | <span data-ttu-id="ae220-139">BlockWindowsAuthExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="ae220-139">BlockWindowsAuthExternallyAndInternally</span></span>        |
|<span data-ttu-id="ae220-140">__类型4__</span><span class="sxs-lookup"><span data-stu-id="ae220-140">__Type 4__</span></span>   |  <span data-ttu-id="ae220-141">MA</span><span class="sxs-lookup"><span data-stu-id="ae220-141">MA</span></span>       | <span data-ttu-id="ae220-142">赢</span><span class="sxs-lookup"><span data-stu-id="ae220-142">Win</span></span>        | <span data-ttu-id="ae220-143">BlockWindowsAuthExternallyAndModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="ae220-143">BlockWindowsAuthExternallyAndModernAuthInternally</span></span>    |
|<span data-ttu-id="ae220-144">__类型5__</span><span class="sxs-lookup"><span data-stu-id="ae220-144">__Type 5__</span></span>   |  <span data-ttu-id="ae220-145">MA + Win</span><span class="sxs-lookup"><span data-stu-id="ae220-145">MA + Win</span></span>       | <span data-ttu-id="ae220-146">赢</span><span class="sxs-lookup"><span data-stu-id="ae220-146">Win</span></span>        | <span data-ttu-id="ae220-147">BlockModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="ae220-147">BlockModernAuthInternally</span></span>         |

<span data-ttu-id="ae220-148">__类型1说明：__ 这是 Skype for business __Server 的 MA 打开时__ 的默认情况。</span><span class="sxs-lookup"><span data-stu-id="ae220-148">__Type 1 Description:__ This is the default scenario when MA is turned __on__ for Skype for Business Server.</span></span> <span data-ttu-id="ae220-149">换句话说，这是配置 MA 时的 *起始点* 。</span><span class="sxs-lookup"><span data-stu-id="ae220-149">In other words, this is the *starting point* when MA is configured.</span></span>

<span data-ttu-id="ae220-150">__键入2说明：__ 此拓扑将在 *外部*阻止 ntlm，但允许 Ntlm 或 Kerberos (不支持 ADAL) 的客户端 *在内部*工作。</span><span class="sxs-lookup"><span data-stu-id="ae220-150">__Type 2 Description:__ This topology blocks NTLM *externally*, but allows NTLM or Kerberos (for clients that don't support ADAL) to work *internally*.</span></span> <span data-ttu-id="ae220-151">如果你的客户端支持 ADAL，它们将在内部使用 MA。</span><span class="sxs-lookup"><span data-stu-id="ae220-151">If your clients  do support ADAL they will use MA internally.</span></span>

<span data-ttu-id="ae220-152">__类型3说明：__ 此拓扑要求对所有用户进行 MA。</span><span class="sxs-lookup"><span data-stu-id="ae220-152">__Type 3 Description:__ This topology requires MA for all users.</span></span> <span data-ttu-id="ae220-153">你的所有支持 ADAL 的客户端将在此拓扑中运行，例如，如果你关闭了使用基于证书的身份验证的密码，则不会利用密码。</span><span class="sxs-lookup"><span data-stu-id="ae220-153">All your ADAL-capable clients will work in this topology, and passwords will not be leveraged if, for example, you turn off the use of passwords with Certificate-based Auth.</span></span>

<span data-ttu-id="ae220-154">__类型4说明：__ 此拓扑在内部阻止 *了 NTLM，* 并在内部阻止了 MA。</span><span class="sxs-lookup"><span data-stu-id="ae220-154">__Type 4 Description:__ This topology blocks NTLM *externally* and MA internally.</span></span> <span data-ttu-id="ae220-155">它允许*所有客户端\*\*在内部*使用旧版身份验证方法， (甚至支持 ADAL 的客户端) 。</span><span class="sxs-lookup"><span data-stu-id="ae220-155">It allows *all clients* to use legacy authentication methods *internally* (even ADAL-capable clients).</span></span>

<span data-ttu-id="ae220-156">__类型5说明：__ *外部*，您的新式 ADAL 客户端将使用 MA，任何不支持 ADAL 的客户端都将使用旧版身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="ae220-156">__Type 5 Description:__ *Externally*, your modern ADAL clients will use MA and any clients that don't support ADAL will use legacy authentication methods.</span></span> <span data-ttu-id="ae220-157">但是， *在内部*， *所有客户端* 都将使用旧版身份验证 (包括所有支持 ADAL 的客户端) 。</span><span class="sxs-lookup"><span data-stu-id="ae220-157">But, *internally* *all clients* will use legacy authentication (including all ADAL-capable clients).</span></span>

<span data-ttu-id="ae220-158">在可用选项中跟踪保护密码的目的相当容易。</span><span class="sxs-lookup"><span data-stu-id="ae220-158">It's pretty easy to lose track of the goal of protecting your passwords in the options available.</span></span> <span data-ttu-id="ae220-159">请注意，理想的情况是使用 MA 外部 (例如，通过配置基于证书的身份验证) 来避免 DOS 攻击。</span><span class="sxs-lookup"><span data-stu-id="ae220-159">Keep in mind the ideal situation is to use MA externally (for example, by configuring certificate-based auth), to avoid DOS attacks.</span></span> <span data-ttu-id="ae220-160">如果您在内部将其用于新式客户端，则还将为您的网络提供有关 Skype for Business Server DOS 攻击的经得起未来考验。</span><span class="sxs-lookup"><span data-stu-id="ae220-160">If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.</span></span>

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a><span data-ttu-id="ae220-161">为什么要在全局级别使用 CsAuthConfig 设置</span><span class="sxs-lookup"><span data-stu-id="ae220-161">Why to use Set-CsAuthConfig at the Global level</span></span>

<span data-ttu-id="ae220-162">`Set-CsAuthConfig`注册器和 Web 服务角色上的 cmdlet 效果配置。</span><span class="sxs-lookup"><span data-stu-id="ae220-162">The `Set-CsAuthConfig` cmdlet effects configuration on both the Registrar and the Web Services roles.</span></span>

<span data-ttu-id="ae220-163">此 cmdlet 应在 Skype for business server 的全局级别运行。</span><span class="sxs-lookup"><span data-stu-id="ae220-163">This cmdlet is meant to be run at the Global level of your Skype for Business server.</span></span> <span data-ttu-id="ae220-164">它 *可以* 在池级别运行，但 *不建议这样做* ，因为这会增加安装的复杂性。</span><span class="sxs-lookup"><span data-stu-id="ae220-164">It *can* be run at the Pool level but that is *not recommended* because it will add complexity to your installation.</span></span> <span data-ttu-id="ae220-165">通过在池级别运行这些命令，如果您的池不包含 (的所有角色（例如，它不具有 Web 服务) ，则将仅为注册器角色设置这些设置。</span><span class="sxs-lookup"><span data-stu-id="ae220-165">By running these commands at the Pool level, if your Pool doesn't have all of the roles included (for example, it doesn't have Web Services), the settings will only be set for the Registrar role.</span></span> <span data-ttu-id="ae220-166">在这种情况下，Web 服务将使用来自全局级别的设置，这可能会造成混淆行为 (尤其是在无意中) 的情况下执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ae220-166">In that case, Web Services will carry on with settings from the Global level, which can be confusing behaviour (particularly when this is done unintentionally).</span></span>

<span data-ttu-id="ae220-167">如果客户端使用来自一个池的注册器设置和另一个池的 Web 服务设置，并且身份验证设置处于不一致状态，则 yous 客户端可能无法登录。</span><span class="sxs-lookup"><span data-stu-id="ae220-167">If a client uses the Registrar settings from one pool and the Web Services settings from another pool and the authentication settings are in an inconsistent state, yous clients may be unable to log on.</span></span>

<span data-ttu-id="ae220-168">此外，如果有一个池角色存在：</span><span class="sxs-lookup"><span data-stu-id="ae220-168">Also, if there's only one role present for a pool:</span></span> 
* <span data-ttu-id="ae220-169">Set-将仅设置与存在的角色对应的设置。</span><span class="sxs-lookup"><span data-stu-id="ae220-169">Set- will only set the settings that correspond to the role that exists.</span></span> <span data-ttu-id="ae220-170">由于 *未* 设置某些设置，因此不会提供特殊警告。</span><span class="sxs-lookup"><span data-stu-id="ae220-170">No special warning will be given because some settings were *not* set.</span></span> 
* <span data-ttu-id="ae220-171">Get-将返回与存在的角色对应的设置，以及不存在的角色的全局设置。</span><span class="sxs-lookup"><span data-stu-id="ae220-171">Get- will return the setting that corresponds to the role that exists, and the Global settings for the role that doesn't exist.</span></span>
* <span data-ttu-id="ae220-172">如果池的两个角色都不存在，则 Set-和 Get 将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="ae220-172">If neither role is present for a pool, both Set- and Get- will return an error message.</span></span>
* <span data-ttu-id="ae220-173">如果池的两个角色都存在，但未在池级别定义策略，则 Get 将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="ae220-173">If both roles are present for a pool but policies aren't defined at the pool level, Get- will return an error message.</span></span>

<span data-ttu-id="ae220-174">Wisest 可能是为了获取这些值，并在进行任何更改之前对其开始状态进行屏幕截图或记录。</span><span class="sxs-lookup"><span data-stu-id="ae220-174">It may be wisest to do a Get- for these values, and to screenshot or record their starting state before making any changes.</span></span> <span data-ttu-id="ae220-175">您还可以考虑保留 OneNote 中的更改日志。</span><span class="sxs-lookup"><span data-stu-id="ae220-175">You might also consider keeping a log of changes in a OneNote.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="ae220-176">注意：配置 CsAuthConfig 后，必须在每台计算机上运行 CsComputer，以便使设置生效。</span><span class="sxs-lookup"><span data-stu-id="ae220-176">Note: After configuring the CsAuthConfig, you must run Enable-CsComputer on each computer in order for the settings to take effect.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae220-177">如果您使用的是 Lync Web Access (LWA) ，并且必须使用基于表单的 Access (FBA) 进行外部访问，请重新配置 LWA，以便客户端可以通过匿名访问访问它以支持这些方案。</span><span class="sxs-lookup"><span data-stu-id="ae220-177">If you're using Lync Web Access (LWA) and must use Forms-based Access (FBA) for external access, reconfigure LWA so that clients can access it with Anonymous Access to support these scenarios.</span></span> <span data-ttu-id="ae220-178">同样，如果使用电话拨入 Pin，则将仅对外部用户阻止 FBA。</span><span class="sxs-lookup"><span data-stu-id="ae220-178">Likewise, if you use Dial-in Pin, FBA will be blocked for external users only.</span></span> <span data-ttu-id="ae220-179">如果他们需要更改 pin，则需要在内部登录他们的公司来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ae220-179">If they need to change their pin, they will need to login to their corporation to do so, internally.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="ae220-180">如果您使用 BlockWindowsAuthExternally 参数对外阻止 NTLM，请注意，这也会在内部为 SIP 通道阻止 NTLM。</span><span class="sxs-lookup"><span data-stu-id="ae220-180">If you use the BlockWindowsAuthExternally parameter to externally block NTLM, be aware this also blocks NTLM internally for the SIP channel.</span></span> <span data-ttu-id="ae220-181">但是，如果 Skype for Business 和 Lync 客户端的版本高于2010，将仍可登录，因为他们将使用 HTTP 上的 NTLM 进行登录，并在内部获取证书以通过 SIP 登录。</span><span class="sxs-lookup"><span data-stu-id="ae220-181">However, Skype for Business and Lync clients newer than 2010 will still be able to login because they will use NTLM over HTTP for signin, internally, and then fetch a certificate to login over SIP.</span></span> <span data-ttu-id="ae220-182">但是，如果超过2010的客户端在这种情况下无法在内部登录，则可能需要考虑升级这些应用程序，以便用户可以恢复安全功能。</span><span class="sxs-lookup"><span data-stu-id="ae220-182">However, clients older than 2010 will not be able to login internally in this circumstance, and you may want to consider upgrading these applications so that your users can resume secure functionality.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="ae220-183">某些 Skype for Business web 应用程序不支持 MA。</span><span class="sxs-lookup"><span data-stu-id="ae220-183">Some of the Skype for Business web applications don't support MA.</span></span> <span data-ttu-id="ae220-184">因此，通过使用 BlockWindowsAuthExternallyAndInternally 方案，你将无法访问这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae220-184">So by using the BlockWindowsAuthExternallyAndInternally scenario, you won't be able to access these applications.</span></span> <span data-ttu-id="ae220-185">没有 MA 支持的应用程序包括 Web 计划程序、电话拨入页、Skype for Business 控制面板 (CSCP) 和响应组设置页。</span><span class="sxs-lookup"><span data-stu-id="ae220-185">Applications without MA support are Web Scheduler, Dial-In Page, Skype for Business Control Panel (CSCP), and Response Group Settings Page.</span></span> 

## <a name="links"></a><span data-ttu-id="ae220-186">链接</span><span class="sxs-lookup"><span data-stu-id="ae220-186">Links</span></span> 
- <span data-ttu-id="ae220-187">有关 PowerShell 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="ae220-187">For more PowerShell information:</span></span>
    -  [<span data-ttu-id="ae220-188">CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="ae220-188">Get-CsAuthConfig</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [<span data-ttu-id="ae220-189">CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="ae220-189">Set-CsAuthConfig</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- <span data-ttu-id="ae220-190">有关如何使用命令或安装这些命令所需的 CU 的更多指导：</span><span class="sxs-lookup"><span data-stu-id="ae220-190">For more direction on how to use the commands or on the CU needed to install them:</span></span>
    - [<span data-ttu-id="ae220-191">Cmdlet 简介</span><span class="sxs-lookup"><span data-stu-id="ae220-191">Cmdlets briefing</span></span>](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - <span data-ttu-id="ae220-192">[Skype for Business Server 2015 的更新](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (常规) </span><span class="sxs-lookup"><span data-stu-id="ae220-192">[Updates for Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (General)</span></span>
    - <span data-ttu-id="ae220-193">[2018 年7月 Skype for Business Server 2015 核心组件 CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534) </span><span class="sxs-lookup"><span data-stu-id="ae220-193">The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span></span>


 
