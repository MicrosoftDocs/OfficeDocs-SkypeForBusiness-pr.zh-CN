---
title: 创建并管理拨号计划
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: '了解如何在 Office 365 中创建呼叫拨号计划（PSTN 呼叫拨号计划）以及如何管理它们。 '
ms.openlocfilehash: 3b96c2f504096b3f77c7080feda1dac982f46e9c
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516668"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="a6920-103">创建并管理拨号计划</span><span class="sxs-lookup"><span data-stu-id="a6920-103">Create and manage dial plans</span></span>

<span data-ttu-id="a6920-104">在为组织计划了拨号计划并确定了需要为呼叫路由创建的所有规范化规则后，您需要使用 Windows PowerShell 创建拨号计划并进行任何设置更改。</span><span class="sxs-lookup"><span data-stu-id="a6920-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6920-105">[!注释] Skype for Business 管理中心不能用于创建和管理拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a6920-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="a6920-106">验证并启动远程 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6920-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="a6920-107">**检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**</span><span class="sxs-lookup"><span data-stu-id="a6920-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="a6920-108">若要验证正在运行的版本是 3.0 或更高：**开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="a6920-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a6920-109">通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。</span><span class="sxs-lookup"><span data-stu-id="a6920-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="a6920-p101">如果你没有版本3.0 或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。出现提示时，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="a6920-p101">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="a6920-p102">还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。</span><span class="sxs-lookup"><span data-stu-id="a6920-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="a6920-116">如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="a6920-117">**启动 Windows PowerShell 会话**</span><span class="sxs-lookup"><span data-stu-id="a6920-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="a6920-118">从 **开始菜单** > **Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="a6920-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="a6920-119">在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a6920-120">[!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。</span><span class="sxs-lookup"><span data-stu-id="a6920-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="a6920-121">如果需要有关启动 Windows PowerShell 的详细信息，请参阅使用 Windows PowerShell[连接到单个 Windows powershell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[连接到 Skype for business Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="a6920-122">创建并管理你的拨号计划</span><span class="sxs-lookup"><span data-stu-id="a6920-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="a6920-123">你可以使用单个 cmdlet 或 PowerShell 脚本创建和管理租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a6920-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="a6920-124">使用单个 cmdlet</span><span class="sxs-lookup"><span data-stu-id="a6920-124">Using single cmdlets</span></span>

- <span data-ttu-id="a6920-125">要创建新的拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="a6920-126">有关其他示例和参数，请参阅 [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="a6920-127">要对现有拨号计划进行设置更改，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="a6920-128">有关其他示例和参数，请参阅 [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="a6920-129">要向拨号计划中添加用户，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="a6920-130">有关其他示例和参数，请参阅 [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="a6920-131">要查看拨号计划中的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="a6920-132">有关其他示例和参数，请参阅 [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="a6920-133">要删除拨号计划，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="a6920-134">有关其他示例和参数，请参阅 [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="a6920-135">要查看有效拨号计划的设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="a6920-136">有关其他示例和参数，请参阅 [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="a6920-137">要测试拨号计划的有效设置，请运行：</span><span class="sxs-lookup"><span data-stu-id="a6920-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="a6920-138">有关其他示例和参数，请参阅 [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a6920-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="a6920-139">使用 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="a6920-139">Using a PowerShell script</span></span>

<span data-ttu-id="a6920-140">运行此脚本即可删除与租户拨号计划关联的规范化规则，而不需要先删除租户拨号计划：</span><span class="sxs-lookup"><span data-stu-id="a6920-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="a6920-141">运行此脚本即可将下列规范化规则添加到名为 RedmondDialPlan 的现有租户拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="a6920-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="a6920-142">运行此脚本即可将下列规范化规则从名为 RedmondDialPlan 的现有租户拨号计划中删除。</span><span class="sxs-lookup"><span data-stu-id="a6920-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="a6920-p103">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span><span class="sxs-lookup"><span data-stu-id="a6920-p103">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it. The array of normalization rules starts with index 0. We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="a6920-146">运行此脚本即可找出所有已取得 RedmondDialPlan 租户拨号计划授权的用户。</span><span class="sxs-lookup"><span data-stu-id="a6920-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="a6920-147">运行此操作以删除具有 HostingProvider sipfed.online.lync.com 的所有用户的 policyname。</span><span class="sxs-lookup"><span data-stu-id="a6920-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="a6920-148">运行这些脚本可为你的组织将名为 OPDP1 的本地拨号计划添加为租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a6920-148">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="a6920-149">您需要先将本地拨号计划保存到 .xml 文件，然后使用它创建新的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a6920-149">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="a6920-150">运行此操作以将本地拨号计划保存到 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="a6920-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="a6920-151">运行此脚本创建新的租户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a6920-151">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a6920-152">想要了解有关 Windows Powershell 的详细信息？</span><span class="sxs-lookup"><span data-stu-id="a6920-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="a6920-153">Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="a6920-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a6920-154">当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="a6920-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="a6920-155">若要开始使用 Windows PowerShell，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="a6920-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a6920-156">Windows PowerShell 和 Skype for Business Online 简介</span><span class="sxs-lookup"><span data-stu-id="a6920-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a6920-157">为什么要使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6920-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="a6920-158">Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。</span><span class="sxs-lookup"><span data-stu-id="a6920-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a6920-159">通过以下主题了解这些优势：</span><span class="sxs-lookup"><span data-stu-id="a6920-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="a6920-160">使用 Windows PowerShell 管理 Office 365 的最佳方式</span><span class="sxs-lookup"><span data-stu-id="a6920-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="a6920-161">使用 Windows PowerShell 管理 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a6920-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a6920-162">使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="a6920-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="a6920-163">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6920-163">Related topics</span></span>
[<span data-ttu-id="a6920-164">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="a6920-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="a6920-165">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="a6920-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="a6920-166">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="a6920-166">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="a6920-167">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="a6920-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="a6920-168">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a6920-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
