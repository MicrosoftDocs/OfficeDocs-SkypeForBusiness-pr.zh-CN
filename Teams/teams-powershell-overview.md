---
title: 团队 PowerShell 概述 （英文)
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: 了解如何使用 PowerShell 控件来管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e85261b133d8f1562bcca7d79f83eb21e345be2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204466"
---
# <a name="teams-powershell-overview"></a><span data-ttu-id="c3d3a-103">团队 PowerShell 概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="c3d3a-103">Teams PowerShell Overview</span></span>

<span data-ttu-id="c3d3a-104">Microsoft 团队具有一组丰富的 IT 管理员可以管理通过 Microsoft 团队管理中心、 PowerShell 控件和图形 Api 产品的工具。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-104">Microsoft Teams has a rich set of tools for IT admins to manage the product through the Microsoft Teams admin center, PowerShell controls, and Graph APIs.</span></span> <span data-ttu-id="c3d3a-105">本指南介绍了我们如何构建 IT 管理员可以使用，我们 PowerShell cmdlet，并提供指向更多文档。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-105">This guide explains how we structure our PowerShell cmdlets for IT admins to use, and provides pointers to further documentation.</span></span> <span data-ttu-id="c3d3a-106">请注意不同工作组管理员角色有权访问不同的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-106">Note that different Teams admin roles have access to different cmdlets.</span></span> <span data-ttu-id="c3d3a-107">有关详细信息，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-107">For more information, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>

## <a name="which-modules-do-you-need-to-use"></a><span data-ttu-id="c3d3a-108">您需要使用哪些模块？</span><span class="sxs-lookup"><span data-stu-id="c3d3a-108">Which modules do you need to use?</span></span>

<span data-ttu-id="c3d3a-109">管理团队的 PowerShell 控件是两个不同的 PowerShell 模块中：</span><span class="sxs-lookup"><span data-stu-id="c3d3a-109">The PowerShell controls for managing Teams are in two different PowerShell modules:</span></span> 
- <span data-ttu-id="c3d3a-110">[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)： 团队 PowerShell 模块包含您需要创建和管理团队的所有 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-110">[Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/) : The Teams PowerShell module contains all the cmdlets you need to create and manage teams.</span></span>  
- <span data-ttu-id="c3d3a-111">[业务 PowerShell 模块的 Skype](https://www.microsoft.com/en-us/download/details.aspx?id=39366): Skype for Business PowerShell 模块包含 cmdlet 来管理策略、 配置和其他团队工具。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-111">[Skype for Business PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366): The Skype for Business PowerShell module contains the cmdlets to manage policies, configurations, and other Teams tools.</span></span> 

<span data-ttu-id="c3d3a-112">PowerShell 控件的参考文档会告诉您哪些模块包含正在研究 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-112">The reference documentation for the PowerShell controls will tell you which module contains the cmdlet you're investigating.</span></span> <span data-ttu-id="c3d3a-113">（最终，两个模块将合并。）</span><span class="sxs-lookup"><span data-stu-id="c3d3a-113">(Eventually, the two modules will be combined.)</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="c3d3a-114">每个管理员角色可以做什么？</span><span class="sxs-lookup"><span data-stu-id="c3d3a-114">What can each admin role do?</span></span>

<span data-ttu-id="c3d3a-115">阅读[使用的 Microsoft 团队管理角色，来管理工作组](using-admin-roles.md)了解哪些 PowerShell cmdlet 管理不同角色都将能够利用。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-115">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which PowerShell cmdlets different admin roles will be able to leverage.</span></span>

## <a name="creating-and-managing-teams-via-powershell"></a><span data-ttu-id="c3d3a-116">创建和管理团队通过 PowerShell 自定义</span><span class="sxs-lookup"><span data-stu-id="c3d3a-116">Creating and managing teams via PowerShell</span></span>

<span data-ttu-id="c3d3a-117">用于创建和管理团队的 cmdlet 是在[Microsoft 团队 PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftTeams/)中。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-117">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span> 

<span data-ttu-id="c3d3a-118">团队有后盾 O365 组，因此何时创建工作组，创建一个组。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-118">Teams are backed by O365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="c3d3a-119">有一组的操作系统上核心团队和其设置为提供的 cmdlet (``new-team``， ``get-team``， ``set-team``)，管理团队用户 (``add-teamuser``， ``remove-teamuser``)，以及用于管理团队的通道 cmdlet (``new-teamchannel``， ``remove-teamchannel``)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-119">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="c3d3a-120">所有这些 cmdlet 可以为最终用户运行，但其将仅参与团队拥有或的成员。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-120">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="c3d3a-121">如果您是全局管理员或团队服务管理员，您将能够在组织中的所有团队。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-121">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

> <span data-ttu-id="c3d3a-122">使用中的 Microsoft 团队 PowerShell 模块 cmdlet **GroupId**是返回的**Identity**属性相同``Get-UnifiedGroup``Exchange PowerShell 模块中。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-122">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="managing-policies-via-powershell"></a><span data-ttu-id="c3d3a-123">管理通过 PowerShell 自定义策略</span><span class="sxs-lookup"><span data-stu-id="c3d3a-123">Managing policies via PowerShell</span></span>

<span data-ttu-id="c3d3a-124">用于管理策略的 cmdlet 是[Skype for Business cmdlet 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-124">The cmdlets for managing policies are in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="c3d3a-125">策略是可以应用于单个用户的粒度设置一组。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-125">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="c3d3a-126">每个策略类型都有其自己的创建、 查看、 删除和更新策略本身，然后将这些策略分配给用户用于 cmdlet 集。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-126">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="c3d3a-127">一般结构是：</span><span class="sxs-lookup"><span data-stu-id="c3d3a-127">The general structure is:</span></span>

- <span data-ttu-id="c3d3a-128">GET 命令 (例如， ``Get-CsTeamsMeetingPolicy``): 返回供您在您的组织，供您使用 Microsoft 创建的策略和已创建的自定义策略分配的策略文档。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-128">GET commands (for example, ``Get-CsTeamsMeetingPolicy``):  return the policy documents that are available for you to assign in your organization, both the policies created by Microsoft for you to use and the custom policies you’ve created.</span></span>
   > <span data-ttu-id="c3d3a-129">如果您想要查找只有您已在组织中创建自定义策略，则可以使用``-Filter "tag:*"``。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-129">If you want to find only the custom policies you’ve created in your organization, you can use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="c3d3a-130">新命令 (例如， ``New-CsTeamsMeetingPolicy``): 允许您创建了然后可分配给您的组织中的用户的组织的新策略。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-130">NEW commands (for example, ``New-CsTeamsMeetingPolicy``): let you create new policies for your organization that are then available to be assigned to users in your organization.</span></span> <span data-ttu-id="c3d3a-131">并非所有策略都支持创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-131">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="c3d3a-132">通常，这是为了确保在组织中使用的策略设置的支持的组合。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-132">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="c3d3a-133">设置命令 (例如， ``Set-CsTeamsMeetingPolicy``): 允许您在给定的策略设置特定的值。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-133">SET commands (for example, ``Set-CsTeamsMeetingPolicy``): lets you set particular values on a given policy.</span></span> <span data-ttu-id="c3d3a-134">一些策略没有设置命令可用，或包含不能自定义策略中的参数。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-134">Some policies do not have set commands available, or contain parameters that cannot be customized in the policy.</span></span> <span data-ttu-id="c3d3a-135">每个 PowerShell 说明将调用出哪些参数不能自定义。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-135">Each PowerShell description will call out which parameters cannot be customized.</span></span> 
   > <span data-ttu-id="c3d3a-136">若要编辑的策略，将默认情况下分配给组织中没有自定义策略分配的用户，请运行``Set-Cs<PolicyName> -Identity Global``。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-136">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="c3d3a-137">删除命令 (例如， ``Remove-CsTeamsMeetingPolicy``): 您可以使用此 cmdlet 删除您的租户中已创建的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-137">REMOVE commands (for example, ``Remove-CsTeamsMeetingPolicy``): you can use this cmdlet to delete a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="c3d3a-138">如果您删除已分配给您的组织中的至少一个用户的自定义策略，该用户将回退到全局策略。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-138">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   > <span data-ttu-id="c3d3a-139">您无法实际删除全局策略，在您的组织，但如果您想要将您的组织中的全局策略重置为 Microsoft 提供的默认设置，则可以运行``Remove-Cs<PolicyName> -Identity Global``。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-139">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, you can run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="c3d3a-140">授予命令 (例如， ``Grant-CsTeamsMeetingPolicy``): 允许您将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-140">GRANT command (for example, ``Grant-CsTeamsMeetingPolicy``): lets you assign a policy to a particular user.</span></span>
   > <span data-ttu-id="c3d3a-141">若要删除一个自定义策略分配并使用户回退到您的组织中的默认策略，请运行``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-141">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="c3d3a-142">并非所有策略都允许要创建的自定义策略和一些策略具有不能自定义的设置 (使您可以查看的设置，但无法设置过程中的自定义值``set-``和``new-``)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-142">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="c3d3a-143">如果参数不是可供客户使用将调用的特定 cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-143">The documentation of the specific cmdlet will call out if parameters are not available for use by customers.</span></span>

<span data-ttu-id="c3d3a-144">常见的参数：</span><span class="sxs-lookup"><span data-stu-id="c3d3a-144">Common parameters:</span></span>

- <span data-ttu-id="c3d3a-145">**标识**： 为``Get-``， ``Set-``， ``New-``，和``Remove-``， **Identity**参数将始终引用一个特定的策略实例。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-145">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="c3d3a-146">为``Grant``， **Identity**参数指的是应用策略的特定用户对象。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-146">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a><span data-ttu-id="c3d3a-147">管理通过 PowerShell 自定义配置</span><span class="sxs-lookup"><span data-stu-id="c3d3a-147">Managing configurations via PowerShell</span></span>

<span data-ttu-id="c3d3a-148">用于管理您的配置的 cmdlet 是[Skype for Business cmdlet 模块](https://www.microsoft.com/en-us/download/details.aspx?id=39366)中。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-148">The cmdlets for managing your configuration are in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="c3d3a-149">配置是存储桶的维护中不能在用户级别指定的服务的设置。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-149">Configurations are buckets of settings maintained in the service that cannot be specified at a user level.</span></span> <span data-ttu-id="c3d3a-150">在整个组织始终应用设置。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-150">Settings always apply across the whole organization.</span></span> <span data-ttu-id="c3d3a-151">全局配置是在组织中的唯一有效的配置。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-151">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="c3d3a-152">每种配置类型附带的两个主要 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3d3a-152">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="c3d3a-153">``Get-Cs<ConfigurationName>``(例如， ``Get-CsTeamsClientConfiguration``):</span><span class="sxs-lookup"><span data-stu-id="c3d3a-153">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span> 

- <span data-ttu-id="c3d3a-154">设置命令 (例如， ``Set-CsTeamsClientConfiguration``): 该类型的配置中设置属性。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-154">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="c3d3a-155">指定要修改的参数。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-155">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="c3d3a-156">您可以引用正在修改以下两种方式中的配置： 通过指定-**Identity 全局**，或通过运行``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-156">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="other-powershell-tools"></a><span data-ttu-id="c3d3a-157">其他 PowerShell 工具</span><span class="sxs-lookup"><span data-stu-id="c3d3a-157">Other PowerShell tools</span></span>

<span data-ttu-id="c3d3a-158">您可以找到详细的说明如何管理 Microsoft 团队和 Skype 的业务需要，包括详细的说明中的[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)和[Skype 的每个策略中的设置为使用所有 PowerShell 控件业务 cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3d3a-158">You can find detailed instructions on how to use all PowerShell controls for managing Microsoft Teams and Skype for Business, including detailed descriptions of the settings in each policy, in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="learn-more"></a><span data-ttu-id="c3d3a-159">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="c3d3a-159">Learn more</span></span>

- [<span data-ttu-id="c3d3a-160">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="c3d3a-160">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [<span data-ttu-id="c3d3a-161">Skype 的业务 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="c3d3a-161">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [<span data-ttu-id="c3d3a-162">使用 Microsoft Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="c3d3a-162">Use Microsoft Teams admin roles to manage Teams</span></span>](using-admin-roles.md)
