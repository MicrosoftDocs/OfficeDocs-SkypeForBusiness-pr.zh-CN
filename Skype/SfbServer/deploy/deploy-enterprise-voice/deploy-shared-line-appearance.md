---
title: 在 Skype for Business Server 2015 中部署共享线路外观
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 阅读本主题，了解如何在 Skype for Business Server 2015 的 2015 年 11 月累积更新中部署共享线路外观 (SLA)。SLA 是用于处理对特定号码（称为“共享号码”）的多个呼叫的功能。
ms.openlocfilehash: c0da29e54f03a5c328f1b65807f438b63c14a68f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878646"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="37ee4-104">在 Skype for Business Server 2015 中部署共享线路外观</span><span class="sxs-lookup"><span data-stu-id="37ee4-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="37ee4-p102">阅读本主题，了解如何在 Skype for Business Server 2015 的 2015 年 11 月累积更新中部署共享线路外观 (SLA)。SLA 是用于处理对特定号码（称为“共享号码”）的多个呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="37ee4-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="37ee4-107">有关此功能的详细信息，请参阅[Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="37ee4-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="37ee4-108">共享行外观 (SLA) 是 Skype 业务服务器中的新功能年 11 月 2015年累积更新。</span><span class="sxs-lookup"><span data-stu-id="37ee4-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="37ee4-109">要启用此功能，必须首先部署此累积更新。</span><span class="sxs-lookup"><span data-stu-id="37ee4-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="37ee4-110">安装共享线路外观</span><span class="sxs-lookup"><span data-stu-id="37ee4-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="37ee4-111">对于业务服务器，年 11 月 2015年部署累积更新，Skype 后运行`SkypeServerUpdateInstaller.exe`池中每个前端服务器上的修补程序。</span><span class="sxs-lookup"><span data-stu-id="37ee4-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="37ee4-p104">安装程序将部署最新的 SLA 应用程序，然而，该应用程序默认情况下不启用。可按照下面所述的步骤启用它：</span><span class="sxs-lookup"><span data-stu-id="37ee4-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="37ee4-114">a.</span><span class="sxs-lookup"><span data-stu-id="37ee4-114">a.</span></span> <span data-ttu-id="37ee4-115">为每个池运行以下命令，以便将 SLA 注册为服务器应用程序：</span><span class="sxs-lookup"><span data-stu-id="37ee4-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   https://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="37ee4-116">其中，%FQDN% 是池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="37ee4-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="37ee4-117">b.</span><span class="sxs-lookup"><span data-stu-id="37ee4-117">b.</span></span> <span data-ttu-id="37ee4-118">运行以下命令来更新 SLA cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="37ee4-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```
   Update-CsAdminRole
   ```

    <span data-ttu-id="37ee4-119">c.</span><span class="sxs-lookup"><span data-stu-id="37ee4-119">c.</span></span> <span data-ttu-id="37ee4-120">重新启动所有池中已安装并启用 SLA 的所有前端服务器（RTCSRV 服务）：</span><span class="sxs-lookup"><span data-stu-id="37ee4-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="37ee4-121">创建一个 SLA 组并向该组添加用户</span><span class="sxs-lookup"><span data-stu-id="37ee4-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="37ee4-122">使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 创建 SLA 组：</span><span class="sxs-lookup"><span data-stu-id="37ee4-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="37ee4-p108">Set-CsSlaConfiguration cmdlet 会将企业语音帐户 SLAGroup1 标记为 SLA 实体，并且 SLAGroup1 的号码将变为 SLA 组的号码。对 SLAGroup1 的所有呼叫将拨打整个 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="37ee4-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="37ee4-125">以下示例将为现有企业语音用户创建 SLA 组 SLAGroup1，并使用为 SLAGroup1 分配的号码作为 SLA 主线路号码。</span><span class="sxs-lookup"><span data-stu-id="37ee4-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="37ee4-126">命令会将新 SLA 组的最大并发呼叫数设置为 3，超过该数目的呼叫将听到忙音信号：</span><span class="sxs-lookup"><span data-stu-id="37ee4-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="37ee4-127">您可以使用 Set-CsSlaConfiguration 创建新的 SLA 组或修改现有 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="37ee4-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="37ee4-128">请注意，您所指定的`-Identity`必须为有效的现有已启用企业语音的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="37ee4-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="37ee4-129">使用 [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet 向组添加代理人：</span><span class="sxs-lookup"><span data-stu-id="37ee4-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="37ee4-130">以下示例将向 SLA 组添加一个用户。</span><span class="sxs-lookup"><span data-stu-id="37ee4-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="37ee4-131">添加到组中每个用户必须是有效的启用了企业语音的用户：</span><span class="sxs-lookup"><span data-stu-id="37ee4-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="37ee4-p110">对要添加到组的每个用户重复该 cmdlet。用户只能属于单个 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="37ee4-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="37ee4-134">配置 SLA 组忙碌选项</span><span class="sxs-lookup"><span data-stu-id="37ee4-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="37ee4-135">使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组忙碌选项：</span><span class="sxs-lookup"><span data-stu-id="37ee4-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="37ee4-136">以下示例会将超过最大并发呼叫数的呼叫设置为转接到电话号码 202-555-1234。</span><span class="sxs-lookup"><span data-stu-id="37ee4-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="37ee4-137">目标可能而不是一个电话号码; 您组织内的用户在这种情况下，接收呼叫转移的人员的语法是相同时指定代理人： `sip:<NameofDelegate@domain>`。</span><span class="sxs-lookup"><span data-stu-id="37ee4-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="37ee4-138">其他可能的参数的`BusyOption`是`Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="37ee4-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="37ee4-139">配置 SLA 组未接来电选项</span><span class="sxs-lookup"><span data-stu-id="37ee4-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="37ee4-140">使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组未接来电选项：</span><span class="sxs-lookup"><span data-stu-id="37ee4-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="37ee4-141">下面的示例指定错过的呼叫转接至指定的用户`sla_forward_number`。</span><span class="sxs-lookup"><span data-stu-id="37ee4-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="37ee4-142">有效选项`-MissedCallOption`参数`Forward`， `BusySignal`，或`Disconnect`。</span><span class="sxs-lookup"><span data-stu-id="37ee4-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="37ee4-143">如果您选择`Forward`，还必须包括`-MissedCallForwardTarget`参数，作为目标用户或电话号码：</span><span class="sxs-lookup"><span data-stu-id="37ee4-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="37ee4-144">从组中删除代理人</span><span class="sxs-lookup"><span data-stu-id="37ee4-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="37ee4-145">使用 [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet 从组中删除代理人：</span><span class="sxs-lookup"><span data-stu-id="37ee4-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="37ee4-146">例如：</span><span class="sxs-lookup"><span data-stu-id="37ee4-146">For example:</span></span>

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="37ee4-147">删除 SLA 组</span><span class="sxs-lookup"><span data-stu-id="37ee4-147">Delete an SLA group</span></span>

- <span data-ttu-id="37ee4-148">使用 [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet 删除 SLA 组：</span><span class="sxs-lookup"><span data-stu-id="37ee4-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="37ee4-149">例如：</span><span class="sxs-lookup"><span data-stu-id="37ee4-149">For example:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


