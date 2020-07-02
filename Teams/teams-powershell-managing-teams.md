---
title: 通过 Microsoft 团队 PowerShell 管理团队
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
description: 了解如何使用团队 PowerShell 管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944086"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="6d98a-103">通过 Microsoft 团队 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="6d98a-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="6d98a-104">本文介绍如何使用 Microsoft 团队 PowerShell 管理团队和 Skype for business。</span><span class="sxs-lookup"><span data-stu-id="6d98a-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="6d98a-105">将本指南与[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)和[Skype for business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)结合使用。</span><span class="sxs-lookup"><span data-stu-id="6d98a-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="6d98a-106">使用 PowerShell 创建和管理团队</span><span class="sxs-lookup"><span data-stu-id="6d98a-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="6d98a-107">用于创建和管理团队的 cmdlet 位于[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。</span><span class="sxs-lookup"><span data-stu-id="6d98a-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="6d98a-108">团队受 Office 365 组支持，因此当您创建团队时，将创建一个组。</span><span class="sxs-lookup"><span data-stu-id="6d98a-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="6d98a-109">提供了一组 cmdlet，用于在核心团队及其设置（ ``new-team`` 、 ``get-team`` 、 ``set-team`` ）、管理团队用户（、）以及 ``add-teamuser`` ``remove-teamuser`` 用于管理团队频道（ ``new-teamchannel`` 、）的 cmdlet ``remove-teamchannel`` 之间进行操作。</span><span class="sxs-lookup"><span data-stu-id="6d98a-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="6d98a-110">所有这些 cmdlet 都可以作为最终用户运行，但它们仅适用于您拥有或属于其成员的团队。</span><span class="sxs-lookup"><span data-stu-id="6d98a-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="6d98a-111">如果你是全局管理员或团队服务管理员，你将能够针对组织中的所有团队执行操作。</span><span class="sxs-lookup"><span data-stu-id="6d98a-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> <span data-ttu-id="6d98a-112">Microsoft 团队 PowerShell 模块 cmdlet 中使用的**GroupId**与 Exchange PowerShell 模块中返回的**Identity**属性相同 ``Get-UnifiedGroup`` 。</span><span class="sxs-lookup"><span data-stu-id="6d98a-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="6d98a-113">通过 PowerShell 管理策略</span><span class="sxs-lookup"><span data-stu-id="6d98a-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="6d98a-114">Skype for Business Online 连接器将合并到团队 PowerShell 中。</span><span class="sxs-lookup"><span data-stu-id="6d98a-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="6d98a-115">它目前在公共预览版中可用。</span><span class="sxs-lookup"><span data-stu-id="6d98a-115">It is currently available in public preview.</span></span> <span data-ttu-id="6d98a-116">在此期间，适用于团队的 Skype for Business Online cmdlet 将在团队 PowerShell 模块中本身提供。</span><span class="sxs-lookup"><span data-stu-id="6d98a-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="6d98a-117">安装步骤可在[安装团队 PowerShell](teams-powershell-install.md)文章中使用。</span><span class="sxs-lookup"><span data-stu-id="6d98a-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="6d98a-118">一旦连接到 Skype for Business Online，cmdlet 将在你的 PowerShell 会话中可用。</span><span class="sxs-lookup"><span data-stu-id="6d98a-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="6d98a-119">有关详细信息，请参阅[管理 Office 365 PowerShell 的 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6d98a-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="6d98a-120">在[Skype For business cmdlet 模块](https://www.microsoft.com/download/details.aspx?id=39366)中查找用于管理策略的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d98a-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="6d98a-121">策略是一组可对单个用户进行精确应用的设置。</span><span class="sxs-lookup"><span data-stu-id="6d98a-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="6d98a-122">每个策略类型都有自己的一组用于创建、查看、删除和更新策略的 cmdlet，然后将这些策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="6d98a-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="6d98a-123">常规结构是：</span><span class="sxs-lookup"><span data-stu-id="6d98a-123">The general structure is:</span></span>

- <span data-ttu-id="6d98a-124">**GET**命令（例如 ``Get-CsTeamsMeetingPolicy`` ）：返回可供您在组织中分配的策略文档，包括 Microsoft 为您创建的策略以及您创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="6d98a-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="6d98a-125">若要仅查找您在组织中创建的自定义策略，请使用 ``-Filter "tag:*"`` 。</span><span class="sxs-lookup"><span data-stu-id="6d98a-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="6d98a-126">**新**命令（例如 ``New-CsTeamsMeetingPolicy`` ）：为您的组织创建用于分配给组织中的用户的新策略。</span><span class="sxs-lookup"><span data-stu-id="6d98a-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="6d98a-127">并非所有策略都支持创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="6d98a-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="6d98a-128">通常，这是为了确保您在组织中使用的策略具有受支持的设置组合。</span><span class="sxs-lookup"><span data-stu-id="6d98a-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="6d98a-129">**SET**命令（例如 ``Set-CsTeamsMeetingPolicy`` ）：在给定策略上设置特定值。</span><span class="sxs-lookup"><span data-stu-id="6d98a-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="6d98a-130">某些策略没有可用的 SET 命令，或者它们包含无法在策略中自定义的参数。</span><span class="sxs-lookup"><span data-stu-id="6d98a-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="6d98a-131">PowerShell 说明告诉你无法自定义哪些参数。</span><span class="sxs-lookup"><span data-stu-id="6d98a-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="6d98a-132">若要编辑默认情况下将分配给您的组织中未分配自定义策略的用户的策略，请运行 ``Set-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="6d98a-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="6d98a-133">**删除**命令（例如 ``Remove-CsTeamsMeetingPolicy`` ）：删除在你的租户中创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="6d98a-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="6d98a-134">如果您删除的自定义策略已分配给您的组织中的至少一个用户，该用户将回退到全局策略。</span><span class="sxs-lookup"><span data-stu-id="6d98a-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="6d98a-135">你无法真正删除组织中的全局策略，但是如果你想要将组织中的全局策略重置为 Microsoft 提供的默认设置，请运行 ``Remove-Cs<PolicyName> -Identity Global`` 。</span><span class="sxs-lookup"><span data-stu-id="6d98a-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="6d98a-136">"**授予**" 命令（例如 ``Grant-CsTeamsMeetingPolicy`` ）：为特定用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="6d98a-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="6d98a-137">若要删除自定义策略分配并使用户回退到组织中的默认策略，请运行 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 。</span><span class="sxs-lookup"><span data-stu-id="6d98a-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="6d98a-138">并非所有策略都允许创建自定义策略，某些策略具有你无法自定义的设置（因此你可以查看设置，但不能在和期间设置自定义值 ``set-`` ``new-`` ）。</span><span class="sxs-lookup"><span data-stu-id="6d98a-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="6d98a-139">每个 cmdlet 的文档都将调用用户是否可以使用参数。</span><span class="sxs-lookup"><span data-stu-id="6d98a-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="6d98a-140">常用参数：</span><span class="sxs-lookup"><span data-stu-id="6d98a-140">Common parameters:</span></span>

- <span data-ttu-id="6d98a-141">**标识**：对于 ``Get-`` 、 ``Set-`` 、 ``New-`` 和， ``Remove-`` **identity**参数将始终引用特定策略实例。</span><span class="sxs-lookup"><span data-stu-id="6d98a-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="6d98a-142">对于 ``Grant`` ， **Identity**参数引用要对其应用策略的特定用户对象。</span><span class="sxs-lookup"><span data-stu-id="6d98a-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="6d98a-143">通过 PowerShell 管理配置</span><span class="sxs-lookup"><span data-stu-id="6d98a-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="6d98a-144">在[Skype For business cmdlet 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中查找用于管理配置的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6d98a-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="6d98a-145">配置是在服务中维护的不能在用户级别指定的设置的存储桶。</span><span class="sxs-lookup"><span data-stu-id="6d98a-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="6d98a-146">设置始终在整个组织中应用。</span><span class="sxs-lookup"><span data-stu-id="6d98a-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="6d98a-147">您的全局配置是您的组织中唯一有效的配置。</span><span class="sxs-lookup"><span data-stu-id="6d98a-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="6d98a-148">每种配置类型均带有两个主要 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="6d98a-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="6d98a-149">``Get-Cs<ConfigurationName>``（例如 ``Get-CsTeamsClientConfiguration`` ）：</span><span class="sxs-lookup"><span data-stu-id="6d98a-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="6d98a-150">SET 命令（例如 ``Set-CsTeamsClientConfiguration`` ）：在该类型的配置中设置属性。</span><span class="sxs-lookup"><span data-stu-id="6d98a-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="6d98a-151">指定要修改的参数。</span><span class="sxs-lookup"><span data-stu-id="6d98a-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="6d98a-152">你可以通过以下两种方式之一引用你正在修改的配置：通过指定**全局标识**或通过运行进行修改 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 。</span><span class="sxs-lookup"><span data-stu-id="6d98a-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="6d98a-153">每个管理员角色可以执行哪些操作？</span><span class="sxs-lookup"><span data-stu-id="6d98a-153">What can each admin role do?</span></span>

<span data-ttu-id="6d98a-154">已阅读[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)，了解可以运行每个 PowerShell cmdlet 的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="6d98a-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d98a-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="6d98a-155">Related topics</span></span>

[<span data-ttu-id="6d98a-156">安装团队 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d98a-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="6d98a-157">团队 PowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="6d98a-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="6d98a-158">团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="6d98a-158">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="6d98a-159">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="6d98a-159">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="6d98a-160">使用 Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="6d98a-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)