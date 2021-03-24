---
title: Deploy Shared Line Appearance in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新 (SLA) 部署共享线路外观。 SLA 是一项功能，用于处理对称为共享号码的特定号码的多个呼叫。
ms.openlocfilehash: 7758354b7c4be123cb9b5a482af3304b069931a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104908"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="4c7ea-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4c7ea-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="4c7ea-105">阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新 (SLA) 部署共享线路外观。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="4c7ea-106">SLA 是一项功能，用于处理对称为共享号码的特定号码的多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="4c7ea-107">有关此功能详细信息，请参阅 Plan [for Shared Line Appearance in Skype for Business Server 2015。](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)</span><span class="sxs-lookup"><span data-stu-id="4c7ea-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="4c7ea-108">Skype for Business Server 的 (SLA) 是 Skype for Business Server 2015 年 11 月累积更新中的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="4c7ea-109">若要启用此功能，必须先部署此累积更新。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="4c7ea-110">安装共享线路外观</span><span class="sxs-lookup"><span data-stu-id="4c7ea-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="4c7ea-111">部署 Skype for Business Server 2015 年 11 月累积更新后，在池中的每台前端  `SkypeServerUpdateInstaller.exe` 服务器上运行修补程序。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="4c7ea-112">安装程序将部署最新版本的 SLA 应用程序，但默认情况下不启用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="4c7ea-113">它通过按照下面列出的步骤启用：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="4c7ea-114">a.</span><span class="sxs-lookup"><span data-stu-id="4c7ea-114">a.</span></span> <span data-ttu-id="4c7ea-115">通过针对每个池运行以下命令，将 SLA 注册为服务器应用程序：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="4c7ea-116">其中 %FQDN% 是池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="4c7ea-117">b.</span><span class="sxs-lookup"><span data-stu-id="4c7ea-117">b.</span></span> <span data-ttu-id="4c7ea-118">运行以下命令以更新 SLA cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="4c7ea-119">c.</span><span class="sxs-lookup"><span data-stu-id="4c7ea-119">c.</span></span> <span data-ttu-id="4c7ea-120">在安装和启用 SLA 的所有池中 (RTCSRV) 所有前端服务器：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="4c7ea-121">创建 SLA 组并添加用户</span><span class="sxs-lookup"><span data-stu-id="4c7ea-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="4c7ea-122">使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 创建 SLA 组：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-122">Create the SLA group by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="4c7ea-123">此Set-CsSlaConfiguration cmdlet 将企业语音 SLAGroup1 帐户标记为 SLA 实体，并且 SLAGroup1 的数量将成为 SLA 组的数量。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="4c7ea-124">对 SLAGroup1 的所有调用都将拨打整个 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="4c7ea-125">以下示例为现有用户 SLAGroup1 企业语音 SLAGroup1，并使用为 SLAGroup1 分配的号码作为 SLA 主线号码。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="4c7ea-126">此命令将新 SLA 组的最大并发呼叫数设置为 3，超过此数目的呼叫将听到繁忙信号：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="4c7ea-127">可以使用新Set-CsSlaConfiguration SLA 组或修改现有 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c7ea-128">请注意，您为 指定的  `-Identity` 必须是启用企业语音用户帐户的有效现有帐户。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="4c7ea-129">使用 [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet 将委派添加到组：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-129">Add delegates to the group by using the [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="4c7ea-130">以下示例将用户添加到 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="4c7ea-131">添加到该组的每个用户必须是已启用企业语音用户：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="4c7ea-132">对要添加到组的每个用户重复此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="4c7ea-133">用户只能属于单个 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="4c7ea-134">配置 SLA 组忙碌选项</span><span class="sxs-lookup"><span data-stu-id="4c7ea-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="4c7ea-135">使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组忙碌选项：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="4c7ea-136">以下示例设置超过要转发到电话号码 202-555-1234 的最大并发呼叫数的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="4c7ea-137">目标可以是您组织的用户，而不是电话号码;在这种情况下，接收被转发呼叫的人的语法与指定代理人时相同  `sip:<NameofDelegate@domain>` ：。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="4c7ea-138">另一个可能的参数  `BusyOption` 是 `Voicemail` ：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="4c7ea-139">配置 SLA 组未接来电选项</span><span class="sxs-lookup"><span data-stu-id="4c7ea-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="4c7ea-140">使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组未接来电选项：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="4c7ea-141">以下示例指定将未接来电转发到名为 的用户  `sla_forward_number` 。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="4c7ea-142">参数的有效选项是  `-MissedCallOption` 、 `Forward`  `BusySignal` 或  `Disconnect` 。</span><span class="sxs-lookup"><span data-stu-id="4c7ea-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="4c7ea-143">如果选择 ，  `Forward` 则还必须包含 参数，以  `-MissedCallForwardTarget` 用户或电话号码作为目标：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="4c7ea-144">从组中删除代理</span><span class="sxs-lookup"><span data-stu-id="4c7ea-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="4c7ea-145">使用 [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet 从组中删除委派：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="4c7ea-146">例如：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="4c7ea-147">删除 SLA 组</span><span class="sxs-lookup"><span data-stu-id="4c7ea-147">Delete an SLA group</span></span>

- <span data-ttu-id="4c7ea-148">使用 [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet 删除 SLA 组：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="4c7ea-149">例如：</span><span class="sxs-lookup"><span data-stu-id="4c7ea-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```