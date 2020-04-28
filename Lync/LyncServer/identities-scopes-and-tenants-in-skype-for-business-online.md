---
title: Skype for Business Online 中的标识、范围和租户
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 598f1cb760a6b4ca969c1e8df25f9735fd0df7c1
ms.sourcegitcommit: 0835f4335ebc8ca53b8348e0b1b906828eb4e13e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "43918560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="30c77-102">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="30c77-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30c77-103">_**上次修改的主题：** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="30c77-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="30c77-104">许多用于管理 Skype for Business Online 的 Windows PowerShell cmdlet 都要求您特别注意您尝试管理的项目。</span><span class="sxs-lookup"><span data-stu-id="30c77-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="30c77-105">例如，当您运行[CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet 时，您必须指明要尝试管理的用户。</span><span class="sxs-lookup"><span data-stu-id="30c77-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="30c77-106">这很合理。</span><span class="sxs-lookup"><span data-stu-id="30c77-106">This makes sense.</span></span> <span data-ttu-id="30c77-107">除非您明确告知 cmdlet 要管理哪个用户帐户，否则**CsUserAcp** cmdlet 将不知道应修改哪个用户的音频会议信息。</span><span class="sxs-lookup"><span data-stu-id="30c77-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="30c77-108">因此，每次运行**CsUserAcp** cmdlet 时，都需要包含 identity 参数，后跟要修改的用户帐户的标识：</span><span class="sxs-lookup"><span data-stu-id="30c77-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="30c77-109">如果术语 "*标识*" 总是指用户帐户的标识，则很少导致混淆。</span><span class="sxs-lookup"><span data-stu-id="30c77-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="30c77-110">当您处理人员（用户、联系人等）时，标识将分别引用各个用户。</span><span class="sxs-lookup"><span data-stu-id="30c77-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="30c77-111">但是，除用户帐户之外的其他项目也具有标识。</span><span class="sxs-lookup"><span data-stu-id="30c77-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="30c77-112">当您处理 Skype for Business Online 服务的组件（策略、配置设置等）时，术语标识意味着有些不同。</span><span class="sxs-lookup"><span data-stu-id="30c77-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="30c77-113">例如，请考虑以下命令：</span><span class="sxs-lookup"><span data-stu-id="30c77-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="30c77-114">在这种情况下，标识 "global" 表示会议配置设置的范围。</span><span class="sxs-lookup"><span data-stu-id="30c77-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="30c77-115">*Scope*是 Skype For business Online 中使用的术语（在 Lync Server 中），用于指定用于管理的球体。</span><span class="sxs-lookup"><span data-stu-id="30c77-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="30c77-116">默认情况下，策略和设置始终具有全局作用域。</span><span class="sxs-lookup"><span data-stu-id="30c77-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="30c77-117">在您首次设置 Skype for Business Online 帐户时，默认情况下，将拥有全局策略和设置（全局会议配置设置、全局外部访问策略、全局拨号计划等）的集合。</span><span class="sxs-lookup"><span data-stu-id="30c77-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="30c77-118">这些全局策略和设置在 Microsoft Lync Server 2010 中引入，以帮助确保所有用户和所有组件都始终以某种方式进行管理。</span><span class="sxs-lookup"><span data-stu-id="30c77-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="30c77-119">在 Microsoft Office Communicator 2007 R2 中不一定如此。</span><span class="sxs-lookup"><span data-stu-id="30c77-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="30c77-120">根据您访问系统的方式，可能会最终导致不受管理的状态（通常是因为组策略不能应用于您的用户帐户）。</span><span class="sxs-lookup"><span data-stu-id="30c77-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="30c77-121">与此相反，在 Lync Server 和 Skype for Business Online 中，决不会留下任何非托管。</span><span class="sxs-lookup"><span data-stu-id="30c77-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="30c77-122">这是因为，而不是其他任何内容，则始终强制实施全局策略和设置。</span><span class="sxs-lookup"><span data-stu-id="30c77-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="30c77-123">我们的意思是 "代替其他任何程序"？</span><span class="sxs-lookup"><span data-stu-id="30c77-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="30c77-124">嗯，在 Skype for business Online 的情况下，可以在*标记范围*或管理层创建策略。</span><span class="sxs-lookup"><span data-stu-id="30c77-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="30c77-125">在标记作用域（也称为 *"每用户范围"*）中创建的策略优先于在全局范围内创建的策略。</span><span class="sxs-lookup"><span data-stu-id="30c77-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="30c77-126">换言之，每用户策略将始终优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="30c77-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="30c77-127">例如，您可能有两个外部用户访问策略。</span><span class="sxs-lookup"><span data-stu-id="30c77-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="30c77-128">全局策略禁止用户与在公共即时消息（IM）提供程序（如 Windows Live）上具有帐户的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="30c77-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="30c77-129">每用户策略 AllowPublicIMCommunication 允许与公共 IM 提供商进行通信。</span><span class="sxs-lookup"><span data-stu-id="30c77-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="30c77-130">您可能还有两个用户： Ken Myer 和 Pilar Ackerman。</span><span class="sxs-lookup"><span data-stu-id="30c77-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="30c77-131">已为 Ken Myer 分配每用户策略。</span><span class="sxs-lookup"><span data-stu-id="30c77-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="30c77-132">尚未为 Pilar Ackerman 分配每用户策略;即，由全局外部访问策略管理她。</span><span class="sxs-lookup"><span data-stu-id="30c77-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="30c77-133">下表显示了可以与公共 IM 提供商通信的用户（如果有）：</span><span class="sxs-lookup"><span data-stu-id="30c77-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30c77-134">策略设置</span><span class="sxs-lookup"><span data-stu-id="30c77-134">Policy Settings</span></span></th>
<th><span data-ttu-id="30c77-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="30c77-135">Ken Myer</span></span></th>
<th><span data-ttu-id="30c77-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="30c77-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30c77-137">公用 IM 提供商的全局策略设置</span><span class="sxs-lookup"><span data-stu-id="30c77-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="30c77-138">否</span><span class="sxs-lookup"><span data-stu-id="30c77-138">No</span></span></p></td>
<td><p><span data-ttu-id="30c77-139">否</span><span class="sxs-lookup"><span data-stu-id="30c77-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30c77-140">公用 IM 提供商的每用户策略设置</span><span class="sxs-lookup"><span data-stu-id="30c77-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="30c77-141">是</span><span class="sxs-lookup"><span data-stu-id="30c77-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="30c77-142">否</span><span class="sxs-lookup"><span data-stu-id="30c77-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30c77-143">用户可以与公共 IM 提供商通信</span><span class="sxs-lookup"><span data-stu-id="30c77-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="30c77-144">是</span><span class="sxs-lookup"><span data-stu-id="30c77-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="30c77-145">否</span><span class="sxs-lookup"><span data-stu-id="30c77-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30c77-146">正如您所看到的，允许 Ken Myer 与公共 IM 提供商通信。</span><span class="sxs-lookup"><span data-stu-id="30c77-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="30c77-147">这是因为分配给他的每用户策略中的设置将覆盖全局策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="30c77-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="30c77-148">Pilar Ackerman 无法与公共 IM 提供商通信。</span><span class="sxs-lookup"><span data-stu-id="30c77-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="30c77-149">这是因为她由全局策略进行管理，而全局策略将禁止此类通信。</span><span class="sxs-lookup"><span data-stu-id="30c77-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="30c77-150">必须由 Microsoft 支持为您创建每个用户的策略。</span><span class="sxs-lookup"><span data-stu-id="30c77-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="30c77-151">创建策略后，可以使用相应的**Grant-Cs** cmdlet 将它们分配给用户（例如， [set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)）。</span><span class="sxs-lookup"><span data-stu-id="30c77-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="30c77-152">由于策略标识总是以标记**前缀**开头，因此每个用户的策略易于识别。</span><span class="sxs-lookup"><span data-stu-id="30c77-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="30c77-153">例如：</span><span class="sxs-lookup"><span data-stu-id="30c77-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="30c77-154">标记<STRONG>前缀</STRONG>日期返回到 Lync Server 2010 的早期开发日。</span><span class="sxs-lookup"><span data-stu-id="30c77-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="30c77-155">在这些天中，每个用户的策略称为<EM>标记策略</EM>，并由标记<STRONG>前缀</STRONG>标识。</span><span class="sxs-lookup"><span data-stu-id="30c77-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="30c77-156">现在，这些策略更准确地称为 "<EM>每用户策略</EM>"，标记作用域更准确地称为 "<EM>每用户" 作用域</EM>。</span><span class="sxs-lookup"><span data-stu-id="30c77-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="30c77-157">但是，由于技术原因，标记<STRONG>前缀</STRONG>永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="30c77-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="30c77-158">使用 Skype for Business Online 和 Windows PowerShell 时使用的另一个关键术语是*租户*。</span><span class="sxs-lookup"><span data-stu-id="30c77-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="30c77-159">当你设置 Skype for Business Online 帐户时，将为你的新部署分配租户 ID 号，该号码是与以下内容类似的全局唯一标识符（GUID）：</span><span class="sxs-lookup"><span data-stu-id="30c77-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="30c77-160">几个 Skype for Business Online cmdlet 要求您在每次运行 cmdlet 时输入租户 ID。</span><span class="sxs-lookup"><span data-stu-id="30c77-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="30c77-161">您必须输入租户 ID，即使您已登录到且只有一个租户。</span><span class="sxs-lookup"><span data-stu-id="30c77-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="30c77-162">幸运的是，您不必记住租户 ID。</span><span class="sxs-lookup"><span data-stu-id="30c77-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="30c77-163">您可以通过运行以下 Windows PowerShell 命令随时检索租户 ID：</span><span class="sxs-lookup"><span data-stu-id="30c77-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="30c77-164">当然，了解全局范围和每用户范围之间的差异（或标记范围）只是一件工作的一半。</span><span class="sxs-lookup"><span data-stu-id="30c77-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="30c77-165">此外，了解何时（或即使）可以使用这些范围也很重要。</span><span class="sxs-lookup"><span data-stu-id="30c77-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="30c77-166">对于标识和租户参数，情况也是如此。</span><span class="sxs-lookup"><span data-stu-id="30c77-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="30c77-167">以下主题介绍不同的 Skype for Business Online cmdlet 如何使用标识、作用域和租户参数：</span><span class="sxs-lookup"><span data-stu-id="30c77-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="30c77-168">仅使用全局范围的 Skype for business Online 中的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="30c77-169">Skype for Business Online 中使用全局作用域和标记作用域的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="30c77-170">Skype for Business Online 中使用用户标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="30c77-171">Skype for Business Online 中使用用户标识和标记作用域的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="30c77-172">使用租户参数的 Skype for Business Online 中的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="30c77-173">Skype for Business Online 中使用会议提供商标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="30c77-174">Skype for Business Online 中不使用作用域或标识的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="30c77-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

