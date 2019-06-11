---
title: Skype for Business Online 中的身份、范围和租户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="187dc-102">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="187dc-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="187dc-103">_**主题上次修改时间:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="187dc-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="187dc-104">许多用于管理 Skype for Business Online 的 Windows PowerShell cmdlet 要求你特别了解你尝试管理的项目。</span><span class="sxs-lookup"><span data-stu-id="187dc-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="187dc-105">例如, 当你运行[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet 时, 你必须指明要尝试管理的用户。</span><span class="sxs-lookup"><span data-stu-id="187dc-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="187dc-106">这样做有意义。</span><span class="sxs-lookup"><span data-stu-id="187dc-106">This makes sense.</span></span> <span data-ttu-id="187dc-107">除非你明确告诉 cmdlet 要管理的用户帐户, 否则**CsUserAcp** cmdlet 将不知道应修改哪些用户的音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="187dc-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="187dc-108">因此, 每次运行**CsUserAcp** cmdlet 时, 你都需要包含 identity 参数, 后跟要修改的用户帐户的标识:</span><span class="sxs-lookup"><span data-stu-id="187dc-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="187dc-109">如果术语 "*标识*" 始终引用用户帐户的标识, 则不会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="187dc-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="187dc-110">当您处理人员 (用户、联系人等) 时, 标识会引用单个用户。</span><span class="sxs-lookup"><span data-stu-id="187dc-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="187dc-111">但是, 除用户帐户以外的其他项目也有标识。</span><span class="sxs-lookup"><span data-stu-id="187dc-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="187dc-112">当您处理 Skype for Business Online 服务 (策略、配置设置等) 的组件时, 术语标识意味着略有不同。</span><span class="sxs-lookup"><span data-stu-id="187dc-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="187dc-113">例如, 请考虑以下命令:</span><span class="sxs-lookup"><span data-stu-id="187dc-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="187dc-114">在这种情况下, 标识 "global" 指会议配置设置的范围。</span><span class="sxs-lookup"><span data-stu-id="187dc-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="187dc-115">*范围*是 Skype For business Online (在 Lync Server 中) 使用的术语, 用于指定球体的管理。</span><span class="sxs-lookup"><span data-stu-id="187dc-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="187dc-116">默认情况下, 策略和设置始终具有全局范围。</span><span class="sxs-lookup"><span data-stu-id="187dc-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="187dc-117">当你首次设置 Skype for Business Online 帐户时, 默认情况下, 你将拥有全局策略和设置的集合-全局会议配置设置、全局外部访问策略、全局拨号计划等。</span><span class="sxs-lookup"><span data-stu-id="187dc-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="187dc-118">Microsoft Lync Server 2010 中引入了这些全局策略和设置, 以帮助确保所有用户和所有组件始终以某种方式管理。</span><span class="sxs-lookup"><span data-stu-id="187dc-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="187dc-119">这在 Microsoft Office Communicator 2007 R2 中不一定是这样。</span><span class="sxs-lookup"><span data-stu-id="187dc-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="187dc-120">根据你的访问系统的方式, 你可能最终处于不太基本的非托管状态 (通常, 因为组策略不能应用于你的用户帐户)。</span><span class="sxs-lookup"><span data-stu-id="187dc-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="187dc-121">相比之下, 在 Lync Server 和 Skype for business Online 中, 不会永远不会留下任何非托管。</span><span class="sxs-lookup"><span data-stu-id="187dc-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="187dc-122">这是因为在任何其他情况下, 将始终强制执行全局策略和设置。</span><span class="sxs-lookup"><span data-stu-id="187dc-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="187dc-123">我们的意思是 "代替其他任何人"？</span><span class="sxs-lookup"><span data-stu-id="187dc-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="187dc-124">嗯, 在 Skype for business Online 的情况下, 可以在*标记范围*(或管理的球体) 创建策略。</span><span class="sxs-lookup"><span data-stu-id="187dc-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="187dc-125">在标记作用域 (也称为*每用户范围*) 创建的策略优先于在全局范围内创建的策略。</span><span class="sxs-lookup"><span data-stu-id="187dc-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="187dc-126">换句话说, 每用户策略将始终优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="187dc-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="187dc-127">例如, 你可能有两个外部用户访问策略。</span><span class="sxs-lookup"><span data-stu-id="187dc-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="187dc-128">全局策略禁止用户与在公共即时消息 (IM) 提供程序 (如 Windows Live) 上具有帐户的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="187dc-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="187dc-129">每用户策略 AllowPublicIMCommunication 允许与公共 IM 提供商进行通信。</span><span class="sxs-lookup"><span data-stu-id="187dc-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="187dc-130">您还可能有两个用户: Ken Myer 和 Pilar Ackerman。</span><span class="sxs-lookup"><span data-stu-id="187dc-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="187dc-131">已将 Ken Myer 分配给每用户策略。</span><span class="sxs-lookup"><span data-stu-id="187dc-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="187dc-132">Pilar Ackerman 尚未分配给每用户策略;即, 她由全局外部访问策略管理。</span><span class="sxs-lookup"><span data-stu-id="187dc-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="187dc-133">下表显示了可以与公共 IM 提供商通信的用户 (如果有):</span><span class="sxs-lookup"><span data-stu-id="187dc-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="187dc-134">策略设置</span><span class="sxs-lookup"><span data-stu-id="187dc-134">Policy Settings</span></span></th>
<th><span data-ttu-id="187dc-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="187dc-135">Ken Myer</span></span></th>
<th><span data-ttu-id="187dc-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="187dc-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="187dc-137">公用 IM 提供商的全局策略设置</span><span class="sxs-lookup"><span data-stu-id="187dc-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="187dc-138">否</span><span class="sxs-lookup"><span data-stu-id="187dc-138">No</span></span></p></td>
<td><p><span data-ttu-id="187dc-139">否</span><span class="sxs-lookup"><span data-stu-id="187dc-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="187dc-140">公用 IM 提供商的每用户策略设置</span><span class="sxs-lookup"><span data-stu-id="187dc-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="187dc-141">是</span><span class="sxs-lookup"><span data-stu-id="187dc-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="187dc-142">否</span><span class="sxs-lookup"><span data-stu-id="187dc-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="187dc-143">用户可以与公共 IM 提供商通信</span><span class="sxs-lookup"><span data-stu-id="187dc-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="187dc-144">是</span><span class="sxs-lookup"><span data-stu-id="187dc-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="187dc-145">否</span><span class="sxs-lookup"><span data-stu-id="187dc-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="187dc-146">正如你所看到的, 允许 Ken Myer 与公共 IM 提供商通信。</span><span class="sxs-lookup"><span data-stu-id="187dc-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="187dc-147">这是因为分配给他的每个用户策略中的设置替代了全局策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="187dc-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="187dc-148">Pilar Ackerman 无法与公共 IM 提供商通信。</span><span class="sxs-lookup"><span data-stu-id="187dc-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="187dc-149">这是因为她由全局策略管理, 而全局策略禁止此类通信。</span><span class="sxs-lookup"><span data-stu-id="187dc-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="187dc-150">每个用户的策略必须由 Office 365 支持人员创建。</span><span class="sxs-lookup"><span data-stu-id="187dc-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="187dc-151">创建策略后, 您可以使用相应的**授权-Cs** cmdlet 将它们分配给用户 (例如,[授予 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy))。</span><span class="sxs-lookup"><span data-stu-id="187dc-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="187dc-152">每用户策略易于识别, 因为策略标识始终以标记**前缀**开头。</span><span class="sxs-lookup"><span data-stu-id="187dc-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="187dc-153">例如：</span><span class="sxs-lookup"><span data-stu-id="187dc-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="187dc-154">标记<STRONG>前缀</STRONG>日期返回 Lync Server 2010 的早期开发日。</span><span class="sxs-lookup"><span data-stu-id="187dc-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="187dc-155">在这些天内, 每个用户的策略称为<EM>标记策略</EM>, 并由标记<STRONG>前缀</STRONG>标识。</span><span class="sxs-lookup"><span data-stu-id="187dc-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="187dc-156">这些策略现在更准确地称为 "<EM>每用户策略</EM>", 标记范围更准确地称为 "<EM>每用户" 范围</EM>。</span><span class="sxs-lookup"><span data-stu-id="187dc-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="187dc-157">但是, 由于技术原因, 标记<STRONG>前缀</STRONG>永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="187dc-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="187dc-158">使用 Skype for Business Online 和 Windows PowerShell 时使用的另一个关键术语是*租户*。</span><span class="sxs-lookup"><span data-stu-id="187dc-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="187dc-159">设置 Skype for Business Online 帐户时, 将为你的新部署分配租户 ID 号, 它是类似于以下内容的全局唯一标识符 (GUID):</span><span class="sxs-lookup"><span data-stu-id="187dc-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="187dc-160">一些 Skype for Business Online cmdlet 要求你在运行 cmdlet 时输入租户 ID。</span><span class="sxs-lookup"><span data-stu-id="187dc-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="187dc-161">你必须输入租户 ID, 即使你已登录到且仅有一个租户。</span><span class="sxs-lookup"><span data-stu-id="187dc-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="187dc-162">幸运的是, 您不必记住租户 ID。</span><span class="sxs-lookup"><span data-stu-id="187dc-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="187dc-163">你可以随时通过运行以下 Windows PowerShell 命令来检索租户 ID:</span><span class="sxs-lookup"><span data-stu-id="187dc-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="187dc-164">当然, 知道全局范围和每用户作用域 (或标签范围) 之间的区别, 只有一半的工作。</span><span class="sxs-lookup"><span data-stu-id="187dc-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="187dc-165">了解何时 (或即使) 你可以使用这些范围也很重要。</span><span class="sxs-lookup"><span data-stu-id="187dc-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="187dc-166">对于标识和租户参数, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="187dc-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="187dc-167">以下主题介绍不同的 Skype for Business Online cmdlet 如何使用标识、作用域和租户参数:</span><span class="sxs-lookup"><span data-stu-id="187dc-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="187dc-168">Skype for Business Online 中仅使用全局范围的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="187dc-169">Skype for Business Online 中使用全局范围和标记范围的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="187dc-170">Skype for Business Online 中使用用户标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="187dc-171">Skype for Business Online 中使用用户标识和标记作用域的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="187dc-172">Skype for Business Online 中使用租户参数的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="187dc-173">Skype for Business Online 中使用会议提供商标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="187dc-174">Skype for Business Online 中不使用作用域或标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="187dc-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

