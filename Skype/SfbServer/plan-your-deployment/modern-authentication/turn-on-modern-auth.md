---
title: 计划在内部和外部关闭旧版身份验证方法
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
ms.assetid: ''
description: 本文概述了可让管理员更好地控制在企业内部和外部使用的身份验证方法的 cmdlet。 管理员可以在内部或外部打开或关闭身份验证方法。
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297265"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a><span data-ttu-id="33ebd-104">计划在内部和外部关闭旧版身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="33ebd-104">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>

> [!NOTE]
> <span data-ttu-id="33ebd-105">如果你即将阅读本文, 你应该已了解支持的新式身份验证拓扑、ADAL 以及有关新式身份验证配置, 但如果不是这样, 你需要启动以下文章:</span><span class="sxs-lookup"><span data-stu-id="33ebd-105">If you're about to read this article, you should already know about supported Modern Authentication topologies, ADAL, and about Modern Authentication config, but, in case you don't, here are the articles you need to start out:</span></span> 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
<span data-ttu-id="33ebd-106">新式身份验证不仅支持更安全的身份验证方法 (如两因素身份验证或基于证书的身份验证), 还可以在不需要用户名或密码的情况下对用户进行授权。</span><span class="sxs-lookup"><span data-stu-id="33ebd-106">Modern Authentication doesn't just enable more secure methods of authentication, like Two-Factor Auth, or Certificate-based Auth, it can carry out authorization of your user without needing a username or password too.</span></span> <span data-ttu-id="33ebd-107">非常方便。</span><span class="sxs-lookup"><span data-stu-id="33ebd-107">It's pretty handy.</span></span>

<span data-ttu-id="33ebd-108">本文将帮助你在 Skype for business 服务器上插入受拒绝服务 (DOS) 攻击的漏洞, 方法是将用于身份验证的较旧方法 (外部、内部或内部) 关闭到你的网络。</span><span class="sxs-lookup"><span data-stu-id="33ebd-108">This article will help you plug holes that have been exploited for Denial Of Service (DOS) attacks on Skype for Business Servers, by turning off older methods used for authentication, externally, internally, or both, to your network.</span></span> <span data-ttu-id="33ebd-109">例如, 用于帮助阻止 DOS 攻击的一种好方法是关闭 Windows 集成身份验证 (包括 NTLM 和 Kerberos)。</span><span class="sxs-lookup"><span data-stu-id="33ebd-109">For example, one good method to help stop DOS attacks would be to turn off Windows Integrated Authentication (which includes NTLM and Kerberos).</span></span> <span data-ttu-id="33ebd-110">从外部关闭 NTLM 并依赖基于证书的身份验证有助于保护密码免遭泄密。</span><span class="sxs-lookup"><span data-stu-id="33ebd-110">Turning off NTLM externally and relying on certificate-based authentication helps to protect passwords from exposure.</span></span> <span data-ttu-id="33ebd-111">这是因为 NTLM 使用密码凭据对用户进行身份验证, 但基于证书的身份验证 (由新式身份验证启用) 不是。</span><span class="sxs-lookup"><span data-stu-id="33ebd-111">This is because NTLM uses password credentials to authenticate users, but certificate-based authentication -- enabled by Modern Auth -- doesn't.</span></span> <span data-ttu-id="33ebd-112">这意味着减少 DOS 攻击的一个理想选择是阻止来自外部的 NTLM, 并且改为在此处使用基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="33ebd-112">That means one ideal option to reduce DOS attacks is to block NTLM externally, and use only certificate-based authentication there, instead.</span></span>

<span data-ttu-id="33ebd-113">完全正确, 让我们开始吧。</span><span class="sxs-lookup"><span data-stu-id="33ebd-113">All right, let's get started.</span></span>

## <a name="what-would-you-be-changing"></a><span data-ttu-id="33ebd-114">您要更改哪些内容？</span><span class="sxs-lookup"><span data-stu-id="33ebd-114">What would you be changing?</span></span> 

<span data-ttu-id="33ebd-115">这些 cmdlet 适用于访问的 SIP 和 Web 服务点。</span><span class="sxs-lookup"><span data-stu-id="33ebd-115">These cmdlets work for both SIP and Web Services points of access.</span></span> <span data-ttu-id="33ebd-116">虽然这两个通道使用不同的访问方法 (从 NTLM 和 Kerberos 到匿名访问运行), 但已考虑 Skype for Business 使用的所有标准方法。</span><span class="sxs-lookup"><span data-stu-id="33ebd-116">Though these two channels use different access methods, running the gamut from NTLM and Kerberos to Anonymous access, all standard methods used by Skype for Business have been taken into consideration.</span></span>

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a><span data-ttu-id="33ebd-117">如何获取 CsAuthConfig cmdlet 和 Set cmdlet</span><span class="sxs-lookup"><span data-stu-id="33ebd-117">How to get the Get- and Set-CsAuthConfig cmdlets</span></span>

<span data-ttu-id="33ebd-118">这些 cmdlet 将仅安装 Microsoft Skype for Business Server 2015 的2018年7月累积更新 (6.0.9319.534), 然后你可以为 Skype for business 服务器推出各种拓扑。</span><span class="sxs-lookup"><span data-stu-id="33ebd-118">These cmdlets will only be installed post July 2018 cumulative update (6.0.9319.534) for Microsoft Skype for Business Server 2015, and then you have a variety of topologies that can be rolled out for your Skype for Business server.</span></span>

## <a name="topologies"></a><span data-ttu-id="33ebd-119">朴</span><span class="sxs-lookup"><span data-stu-id="33ebd-119">Topologies</span></span>

<span data-ttu-id="33ebd-120">请务必记住, 这是此方案中所支持的拓扑。</span><span class="sxs-lookup"><span data-stu-id="33ebd-120">It's important to keep in mind that these are the Supported Topologies involved in this scenario!</span></span> <span data-ttu-id="33ebd-121">如果需要转到支持阻止方法的帮助, 则需要在以下类型之间配置配置。</span><span class="sxs-lookup"><span data-stu-id="33ebd-121">If you need to go to Support for help with blocking a method, for example, you will need to have a configuration among the types below.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="33ebd-122">在下面的表和说明中,*新式身份验证*以__MA__为缩写, 而*Windows 集成身份验证*的缩写形式为 " __Win__"。</span><span class="sxs-lookup"><span data-stu-id="33ebd-122">In the table and descriptions below, *Modern Authentication* is abbreviated as __MA__ and *Windows Integrated Authentication* is abbreviated as __Win__.</span></span> <span data-ttu-id="33ebd-123">作为提醒, Windows 集成身份验证由两种方法组成: NTLM 和 Kerberos 身份验证。</span><span class="sxs-lookup"><span data-stu-id="33ebd-123">As a reminder, Windows Integrated Authentication is made up of two methods: NTLM and Kerberos authentication.</span></span> <span data-ttu-id="33ebd-124">您需要知道这一点才能正确阅读表格!</span><span class="sxs-lookup"><span data-stu-id="33ebd-124">You'll need to know this to read the table properly!</span></span>


|       |<span data-ttu-id="33ebd-125">外部</span><span class="sxs-lookup"><span data-stu-id="33ebd-125">Externally</span></span>  |<span data-ttu-id="33ebd-126">Alink</span><span class="sxs-lookup"><span data-stu-id="33ebd-126">Internally</span></span>  |<span data-ttu-id="33ebd-127">参数</span><span class="sxs-lookup"><span data-stu-id="33ebd-127">Parameter</span></span>  |
|---------|:---------|:---------|---------|
|<span data-ttu-id="33ebd-128">__键入1__</span><span class="sxs-lookup"><span data-stu-id="33ebd-128">__Type 1__</span></span>   |  <span data-ttu-id="33ebd-129">马萨诸塞州获胜</span><span class="sxs-lookup"><span data-stu-id="33ebd-129">MA + Win</span></span>       | <span data-ttu-id="33ebd-130">马萨诸塞州获胜</span><span class="sxs-lookup"><span data-stu-id="33ebd-130">MA + Win</span></span>         |  <span data-ttu-id="33ebd-131">AllowAllExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="33ebd-131">AllowAllExternallyAndInternally</span></span>       |
|<span data-ttu-id="33ebd-132">__键入2__</span><span class="sxs-lookup"><span data-stu-id="33ebd-132">__Type 2__</span></span>   |  <span data-ttu-id="33ebd-133">州</span><span class="sxs-lookup"><span data-stu-id="33ebd-133">MA</span></span>       | <span data-ttu-id="33ebd-134">马萨诸塞州获胜</span><span class="sxs-lookup"><span data-stu-id="33ebd-134">MA + Win</span></span>         | <span data-ttu-id="33ebd-135">BlockWindowsAuthExternally</span><span class="sxs-lookup"><span data-stu-id="33ebd-135">BlockWindowsAuthExternally</span></span>        |
|<span data-ttu-id="33ebd-136">__键入3__</span><span class="sxs-lookup"><span data-stu-id="33ebd-136">__Type 3__</span></span>   |  <span data-ttu-id="33ebd-137">州</span><span class="sxs-lookup"><span data-stu-id="33ebd-137">MA</span></span>       | <span data-ttu-id="33ebd-138">州</span><span class="sxs-lookup"><span data-stu-id="33ebd-138">MA</span></span>        | <span data-ttu-id="33ebd-139">BlockWindowsAuthExternallyAndInternally</span><span class="sxs-lookup"><span data-stu-id="33ebd-139">BlockWindowsAuthExternallyAndInternally</span></span>        |
|<span data-ttu-id="33ebd-140">__键入4__</span><span class="sxs-lookup"><span data-stu-id="33ebd-140">__Type 4__</span></span>   |  <span data-ttu-id="33ebd-141">州</span><span class="sxs-lookup"><span data-stu-id="33ebd-141">MA</span></span>       | <span data-ttu-id="33ebd-142">Win</span><span class="sxs-lookup"><span data-stu-id="33ebd-142">Win</span></span>        | <span data-ttu-id="33ebd-143">BlockWindowsAuthExternallyAndModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="33ebd-143">BlockWindowsAuthExternallyAndModernAuthInternally</span></span>    |
|<span data-ttu-id="33ebd-144">__键入5__</span><span class="sxs-lookup"><span data-stu-id="33ebd-144">__Type 5__</span></span>   |  <span data-ttu-id="33ebd-145">马萨诸塞州获胜</span><span class="sxs-lookup"><span data-stu-id="33ebd-145">MA + Win</span></span>       | <span data-ttu-id="33ebd-146">Win</span><span class="sxs-lookup"><span data-stu-id="33ebd-146">Win</span></span>        | <span data-ttu-id="33ebd-147">BlockModernAuthInternally</span><span class="sxs-lookup"><span data-stu-id="33ebd-147">BlockModernAuthInternally</span></span>         |

<span data-ttu-id="33ebd-148">__键入1说明:__ 这是 Skype for business 服务器的 MA 处于____ 打开状态时的默认方案。</span><span class="sxs-lookup"><span data-stu-id="33ebd-148">__Type 1 Description:__ This is the default scenario when MA is turned __on__ for Skype for Business Server.</span></span> <span data-ttu-id="33ebd-149">换句话说, 这是配置 MA 的*起始点*。</span><span class="sxs-lookup"><span data-stu-id="33ebd-149">In other words, this is the *starting point* when MA is configured.</span></span>

<span data-ttu-id="33ebd-150">__键入2说明:__ 此拓扑将阻止来自*外部*ntlm, 但允许 Ntlm 或 Kerberos (对于不支持 ADAL 的客户端)*在内部*工作。</span><span class="sxs-lookup"><span data-stu-id="33ebd-150">__Type 2 Description:__ This topology blocks NTLM *externally*, but allows NTLM or Kerberos (for clients that don't support ADAL) to work *internally*.</span></span> <span data-ttu-id="33ebd-151">如果您的客户支持 ADAL, 他们将在内部使用 MA。</span><span class="sxs-lookup"><span data-stu-id="33ebd-151">If your clients  do support ADAL they will use MA internally.</span></span>

<span data-ttu-id="33ebd-152">__键入3说明:__ 此拓扑要求所有用户都有 MA。</span><span class="sxs-lookup"><span data-stu-id="33ebd-152">__Type 3 Description:__ This topology requires MA for all users.</span></span> <span data-ttu-id="33ebd-153">你的所有支持 ADAL 的客户端都将在此拓扑中运行, 例如, 如果你关闭使用基于证书的身份验证的密码, 则不会利用密码。</span><span class="sxs-lookup"><span data-stu-id="33ebd-153">All your ADAL-capable clients will work in this topology, and passwords will not be leveraged if, for example, you turn off the use of passwords with Certificate-based Auth.</span></span>

<span data-ttu-id="33ebd-154">__键入4说明:__ 此拓扑在内部\*\* 阻止 NTLM 以及内部的 MA。</span><span class="sxs-lookup"><span data-stu-id="33ebd-154">__Type 4 Description:__ This topology blocks NTLM *externally* and MA internally.</span></span> <span data-ttu-id="33ebd-155">它允许*所有客户端\*\*在内部*使用旧身份验证方法 (甚至支持 ADAL 的客户端)。</span><span class="sxs-lookup"><span data-stu-id="33ebd-155">It allows *all clients* to use legacy authentication methods *internally* (even ADAL-capable clients).</span></span>

<span data-ttu-id="33ebd-156">__键入5说明:__ 在*外部*, 你的现代 ADAL 客户将使用 MA, 任何不支持 ADAL 的客户端都将使用旧身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="33ebd-156">__Type 5 Description:__ *Externally*, your modern ADAL clients will use MA and any clients that don't support ADAL will use legacy authentication methods.</span></span> <span data-ttu-id="33ebd-157">但是,*在内部*,*所有客户端*都将使用旧版身份验证 (包括所有支持 ADAL 的客户端)。</span><span class="sxs-lookup"><span data-stu-id="33ebd-157">But, *internally* *all clients* will use legacy authentication (including all ADAL-capable clients).</span></span>

<span data-ttu-id="33ebd-158">在可用选项中, 我们很容易失去保护密码的目标。</span><span class="sxs-lookup"><span data-stu-id="33ebd-158">It's pretty easy to lose track of the goal of protecting your passwords in the options available.</span></span> <span data-ttu-id="33ebd-159">请记住, 理想情况是在外部使用 MA (例如, 通过配置基于证书的身份验证) 来避免 DOS 攻击。</span><span class="sxs-lookup"><span data-stu-id="33ebd-159">Keep in mind the ideal situation is to use MA externally (for example, by configuring certificate-based auth), to avoid DOS attacks.</span></span> <span data-ttu-id="33ebd-160">如果您为您的现代客户在内部利用它, 您还将为您的网络提供有关 Skype for Business 服务器 DOS 攻击的经得起未来考验的证据。</span><span class="sxs-lookup"><span data-stu-id="33ebd-160">If you leverage it internally for your modern clients, you'll also future-proof your network regarding Skype for Business Server DOS attacks.</span></span>

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a><span data-ttu-id="33ebd-161">为什么要在全局级别使用 CsAuthConfig 设置</span><span class="sxs-lookup"><span data-stu-id="33ebd-161">Why to use Set-CsAuthConfig at the Global level</span></span>

<span data-ttu-id="33ebd-162">注册`Set-CsAuthConfig`机构和 Web 服务角色上的 cmdlet 效果配置。</span><span class="sxs-lookup"><span data-stu-id="33ebd-162">The `Set-CsAuthConfig` cmdlet effects configuration on both the Registrar and the Web Services roles.</span></span>

<span data-ttu-id="33ebd-163">此 cmdlet 应在 Skype for Business 服务器的全球级别运行。</span><span class="sxs-lookup"><span data-stu-id="33ebd-163">This cmdlet is meant to be run at the Global level of your Skype for Business server.</span></span> <span data-ttu-id="33ebd-164">它*可以*在池级别运行, 但*不建议*这样做, 因为它会增加安装的复杂性。</span><span class="sxs-lookup"><span data-stu-id="33ebd-164">It *can* be run at the Pool level but that is *not recommended* because it will add complexity to your installation.</span></span> <span data-ttu-id="33ebd-165">通过在池级别运行这些命令, 如果你的池没有包括所有角色 (例如, 它没有 Web 服务), 则仅为注册机构角色设置 "设置"。</span><span class="sxs-lookup"><span data-stu-id="33ebd-165">By running these commands at the Pool level, if your Pool doesn't have all of the roles included (for example, it doesn't have Web Services), the settings will only be set for the Registrar role.</span></span> <span data-ttu-id="33ebd-166">在这种情况下, Web 服务将通过全局级别的设置进行处理, 这可能是混乱的行为 (尤其是在无意中执行此操作时)。</span><span class="sxs-lookup"><span data-stu-id="33ebd-166">In that case, Web Services will carry on with settings from the Global level, which can be confusing behaviour (particularly when this is done unintentionally).</span></span>

<span data-ttu-id="33ebd-167">如果客户端使用来自一个池的注册器设置和另一个池中的 Web 服务设置, 并且身份验证设置处于不一致状态, 则 yous 客户端可能无法登录。</span><span class="sxs-lookup"><span data-stu-id="33ebd-167">If a client uses the Registrar settings from one pool and the Web Services settings from another pool and the authentication settings are in an inconsistent state, yous clients may be unable to log on.</span></span>

<span data-ttu-id="33ebd-168">同样, 如果一个池只有一个角色, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="33ebd-168">Also, if there's only one role present for a pool:</span></span> 
* <span data-ttu-id="33ebd-169">Set-将仅设置与存在的角色对应的设置。</span><span class="sxs-lookup"><span data-stu-id="33ebd-169">Set- will only set the settings that correspond to the role that exists.</span></span> <span data-ttu-id="33ebd-170">由于*未*设置某些设置, 因此不会提供特殊警告。</span><span class="sxs-lookup"><span data-stu-id="33ebd-170">No special warning will be given because some settings were *not* set.</span></span> 
* <span data-ttu-id="33ebd-171">Get-将返回与存在的角色对应的设置, 以及不存在的角色的全局设置。</span><span class="sxs-lookup"><span data-stu-id="33ebd-171">Get- will return the setting that corresponds to the role that exists, and the Global settings for the role that doesn't exist.</span></span>
* <span data-ttu-id="33ebd-172">如果一个池没有角色, 则 "设置" 和 "获取" 将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="33ebd-172">If neither role is present for a pool, both Set- and Get- will return an error message.</span></span>
* <span data-ttu-id="33ebd-173">如果两个角色都存在于一个池, 但未在池级别定义的策略, 则 Get-将返回错误消息。</span><span class="sxs-lookup"><span data-stu-id="33ebd-173">If both roles are present for a pool but policies aren't defined at the pool level, Get- will return an error message.</span></span>

<span data-ttu-id="33ebd-174">它可能会 wisest 来获取这些值, 并在进行任何更改之前将其从屏幕截图或记录到其开始状态。</span><span class="sxs-lookup"><span data-stu-id="33ebd-174">It may be wisest to do a Get- for these values, and to screenshot or record their starting state before making any changes.</span></span> <span data-ttu-id="33ebd-175">您还可以考虑保留 OneNote 中的更改日志。</span><span class="sxs-lookup"><span data-stu-id="33ebd-175">You might also consider keeping a log of changes in a OneNote.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="33ebd-176">注意: 配置 CsAuthConfig 后, 必须在每台计算机上运行 Enable-CsComputer, 才能使设置生效。</span><span class="sxs-lookup"><span data-stu-id="33ebd-176">Note: After configuring the CsAuthConfig, you must run Enable-CsComputer on each computer in order for the settings to take effect.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33ebd-177">如果您使用的是 Lync Web Access (LWA), 并且必须使用基于窗体的 Access (FBA) 进行外部访问, 请重新配置 LWA, 以便客户可以通过匿名访问访问它以支持这些方案。</span><span class="sxs-lookup"><span data-stu-id="33ebd-177">If you're using Lync Web Access (LWA) and must use Forms-based Access (FBA) for external access, reconfigure LWA so that clients can access it with Anonymous Access to support these scenarios.</span></span> <span data-ttu-id="33ebd-178">同样, 如果你使用拨入 Pin, 将阻止外部用户的 FBA。</span><span class="sxs-lookup"><span data-stu-id="33ebd-178">Likewise, if you use Dial-in Pin, FBA will be blocked for external users only.</span></span> <span data-ttu-id="33ebd-179">如果他们需要更改其 pin 码, 他们将需要在内部登录其公司以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="33ebd-179">If they need to change their pin, they will need to login to their corporation to do so, internally.</span></span>

## <a name="links"></a><span data-ttu-id="33ebd-180">链接</span><span class="sxs-lookup"><span data-stu-id="33ebd-180">Links</span></span> 
- <span data-ttu-id="33ebd-181">有关 PowerShell 的详细信息:</span><span class="sxs-lookup"><span data-stu-id="33ebd-181">For more PowerShell information:</span></span>
    -  [<span data-ttu-id="33ebd-182">CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="33ebd-182">Get-CsAuthConfig</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [<span data-ttu-id="33ebd-183">Set-CsAuthConfig</span><span class="sxs-lookup"><span data-stu-id="33ebd-183">Set-CsAuthConfig</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- <span data-ttu-id="33ebd-184">有关如何使用命令或对安装所需的 CU 的更多指导, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="33ebd-184">For more direction on how to use the commands or on the CU needed to install them:</span></span>
    - [<span data-ttu-id="33ebd-185">Cmdlet 简介</span><span class="sxs-lookup"><span data-stu-id="33ebd-185">Cmdlets briefing</span></span>](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - <span data-ttu-id="33ebd-186">[Skype For Business Server 2015 更新](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)总经理</span><span class="sxs-lookup"><span data-stu-id="33ebd-186">[Updates for Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) (General)</span></span>
    - <span data-ttu-id="33ebd-187">[2018 年7月 Skype for Business Server 2015, 核心组件 CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span><span class="sxs-lookup"><span data-stu-id="33ebd-187">The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)</span></span>


 
