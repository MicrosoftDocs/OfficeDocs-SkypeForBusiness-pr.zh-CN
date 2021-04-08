---
title: 使用 Microsoft Teams PowerShell 管理 Teams
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams PowerShell 管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8494f7951a051f95f9b934d04f274a020446b6cd
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "51617744"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="a47f3-103">使用 Microsoft Teams PowerShell 管理 Teams</span><span class="sxs-lookup"><span data-stu-id="a47f3-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="a47f3-104">本文演示如何使用 Microsoft Teams PowerShell 管理 Teams 和 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="a47f3-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="a47f3-105">将本指南与 [Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps) 和 Skype for Business [cmdlet 参考结合使用](/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a47f3-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="a47f3-106">使用 PowerShell 创建和管理团队</span><span class="sxs-lookup"><span data-stu-id="a47f3-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="a47f3-107">用于创建和管理团队的 cmdlet 在 Microsoft [Teams PowerShell 模块 中](https://www.powershellgallery.com/packages/MicrosoftTeams/)。</span><span class="sxs-lookup"><span data-stu-id="a47f3-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="a47f3-108">Teams 由 Office 365 组支持，因此创建团队时，会创建一个组。</span><span class="sxs-lookup"><span data-stu-id="a47f3-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="a47f3-109">提供了一组 cmdlet 用于核心团队及其设置 （ (、、) 、管理团队用户 (、) ）以及用于管理团队 (、) 的频道的 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` ``new-teamchannel`` ``remove-teamchannel`` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a47f3-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="a47f3-110">所有这些 cmdlet 都可以作为最终用户运行，但它们只能在你拥有或成员的团队中运行。</span><span class="sxs-lookup"><span data-stu-id="a47f3-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="a47f3-111">如果你是全局管理员或 Teams 服务管理员，你将能够对组织的所有团队采取行动。</span><span class="sxs-lookup"><span data-stu-id="a47f3-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -DisplayName "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> <span data-ttu-id="a47f3-112">Microsoft Teams PowerShell 模块 cmdlet 中使用的 **GroupId** 与Exchange PowerShell 模块中返回的 ``Get-UnifiedGroup`` Identity 属性相同。</span><span class="sxs-lookup"><span data-stu-id="a47f3-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="a47f3-113">通过 PowerShell 管理策略</span><span class="sxs-lookup"><span data-stu-id="a47f3-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="a47f3-114">Skype for Business Online 连接器正在整合到 Teams PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="a47f3-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="a47f3-115">它目前以公共预览版提供。</span><span class="sxs-lookup"><span data-stu-id="a47f3-115">It is currently available in public preview.</span></span> <span data-ttu-id="a47f3-116">随后，适用于 Teams 的 Skype for Business Online cmdlet 将在 Teams PowerShell 模块中本机提供。</span><span class="sxs-lookup"><span data-stu-id="a47f3-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="a47f3-117">安装步骤可在安装 [Teams PowerShell](teams-powershell-install.md) 一文获得。</span><span class="sxs-lookup"><span data-stu-id="a47f3-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="a47f3-118">连接到 Skype for Business Online 后，这些 cmdlet 将在 PowerShell 会话中可用。</span><span class="sxs-lookup"><span data-stu-id="a47f3-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="a47f3-119">有关详细信息，请参阅使用 [Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)管理 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="a47f3-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="a47f3-120">在 Skype for Business cmdlet 模块 中查找用于管理策略[的 cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="a47f3-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="a47f3-121">策略是一组设置，可以精细地应用于单个用户。</span><span class="sxs-lookup"><span data-stu-id="a47f3-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="a47f3-122">每个策略类型都有其自己的一组 cmdlet，用于创建、查看、删除和更新策略本身，然后将这些策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a47f3-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="a47f3-123">一般结构为：</span><span class="sxs-lookup"><span data-stu-id="a47f3-123">The general structure is:</span></span>

- <span data-ttu-id="a47f3-124">**GET** (例如，) ：返回可供你在组织中分配的策略文档，包括 Microsoft 创建供你使用的策略以及你创建的自定义策略。 ``Get-CsTeamsMeetingPolicy``</span><span class="sxs-lookup"><span data-stu-id="a47f3-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="a47f3-125">若要仅查找在组织中创建的自定义策略，请使用 ``-Filter "tag:*"`` 。</span><span class="sxs-lookup"><span data-stu-id="a47f3-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="a47f3-126">**新** (例如，) ：为组织创建新策略 ``New-CsTeamsMeetingPolicy`` 以分配给组织的用户。</span><span class="sxs-lookup"><span data-stu-id="a47f3-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="a47f3-127">并非所有策略都支持创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a47f3-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="a47f3-128">通常，这是为了确保在组织中使用的策略具有受支持的设置组合。</span><span class="sxs-lookup"><span data-stu-id="a47f3-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="a47f3-129">**SET** 命令 (例如 ``Set-CsTeamsMeetingPolicy`` ，) ：在给定策略上设置特定值。</span><span class="sxs-lookup"><span data-stu-id="a47f3-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="a47f3-130">某些策略没有可用的 SET 命令，或者包含在策略中无法自定义的参数。</span><span class="sxs-lookup"><span data-stu-id="a47f3-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="a47f3-131">PowerShell 说明告知无法自定义哪些参数。</span><span class="sxs-lookup"><span data-stu-id="a47f3-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="a47f3-132">若要编辑默认情况下将分配给组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="a47f3-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="a47f3-133">**删除** (，例如) ：删除已在租户 ``Remove-CsTeamsMeetingPolicy`` 中创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="a47f3-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="a47f3-134">如果删除已分配给组织中至少一个用户的自定义策略，该用户将回退到全局策略。</span><span class="sxs-lookup"><span data-stu-id="a47f3-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="a47f3-135">实际上无法删除组织的全局策略，但如果要将组织中全局策略重置为 Microsoft 提供的默认设置，请运行 ``Remove-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="a47f3-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="a47f3-136">**GRANT** 命令 (例如 ``Grant-CsTeamsMeetingPolicy`` ，) ：向特定用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="a47f3-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="a47f3-137">若要删除自定义策略分配，并让用户回退到组织的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。</span><span class="sxs-lookup"><span data-stu-id="a47f3-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="a47f3-138">并非所有策略都允许创建自定义策略，并且某些策略具有无法自定义 (因此可以查看设置，但无法设置自定义值期间和 ``set-`` ``new-``) 。</span><span class="sxs-lookup"><span data-stu-id="a47f3-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="a47f3-139">每个 cmdlet 的文档会指出参数是否可供客户使用。</span><span class="sxs-lookup"><span data-stu-id="a47f3-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="a47f3-140">常见参数：</span><span class="sxs-lookup"><span data-stu-id="a47f3-140">Common parameters:</span></span>

- <span data-ttu-id="a47f3-141">**标识**： ``Get-`` 对于 ``Set-`` 、、 ``New-`` 和 ``Remove-`` **，Identity** 参数将始终引用特定的策略实例。</span><span class="sxs-lookup"><span data-stu-id="a47f3-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="a47f3-142">对于 ``Grant`` **，Identity** 参数是指要应用策略的特定用户对象。</span><span class="sxs-lookup"><span data-stu-id="a47f3-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="a47f3-143">通过 PowerShell 管理配置</span><span class="sxs-lookup"><span data-stu-id="a47f3-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="a47f3-144">在 Skype for Business cmdlet 模块 中查找用于管理配置的[cmdlet。](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="a47f3-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="a47f3-145">配置是服务中维护的设置存储桶，无法以用户级别指定。</span><span class="sxs-lookup"><span data-stu-id="a47f3-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="a47f3-146">设置始终应用于整个组织。</span><span class="sxs-lookup"><span data-stu-id="a47f3-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="a47f3-147">全局配置是组织中唯一有效的配置。</span><span class="sxs-lookup"><span data-stu-id="a47f3-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="a47f3-148">每个配置类型附带两个主要 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a47f3-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="a47f3-149">``Get-Cs<ConfigurationName>`` (例如 ``Get-CsTeamsClientConfiguration`` ，) ：</span><span class="sxs-lookup"><span data-stu-id="a47f3-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="a47f3-150">SET (例如 ``Set-CsTeamsClientConfiguration`` ，) ：设置该类型的配置中的属性。</span><span class="sxs-lookup"><span data-stu-id="a47f3-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="a47f3-151">指定要修改的参数。</span><span class="sxs-lookup"><span data-stu-id="a47f3-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="a47f3-152">可以通过以下两种方式之一引用要修改的配置：通过指定 -**Identity Global** 或运行 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。</span><span class="sxs-lookup"><span data-stu-id="a47f3-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="a47f3-153">每个管理员角色可以执行哪些功能？</span><span class="sxs-lookup"><span data-stu-id="a47f3-153">What can each admin role do?</span></span>

<span data-ttu-id="a47f3-154">请阅读 [使用 Microsoft Teams 管理员角色管理 Teams，](using-admin-roles.md) 了解哪些管理员角色可以运行每个 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a47f3-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a47f3-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="a47f3-155">Related topics</span></span>

[<span data-ttu-id="a47f3-156">安装 Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="a47f3-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="a47f3-157">Teams PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="a47f3-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="a47f3-158">Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="a47f3-158">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="a47f3-159">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="a47f3-159">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="a47f3-160">使用 Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="a47f3-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)