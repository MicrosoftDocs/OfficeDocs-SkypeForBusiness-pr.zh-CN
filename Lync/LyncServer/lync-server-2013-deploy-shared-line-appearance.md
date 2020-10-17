---
title: Lync Server 2013：部署共享线路外观
description: Lync Server 2013：部署共享线路外观。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c83c06bbc9b91e11cabc0abee20de28fc7281205
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558618"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="96890-103">在 Lync Server 2013 中部署共享线路外观</span><span class="sxs-lookup"><span data-stu-id="96890-103">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96890-104">_**上次修改的主题：** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="96890-104">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="96890-105">阅读本主题，了解如何在 Lync Server 2013 中部署共享线路外观 (SLA) ，累积更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="96890-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="96890-106">SLA 是一项用于处理对特定号码（称为共享号码）的多个呼叫的功能。</span><span class="sxs-lookup"><span data-stu-id="96890-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="96890-107">有关此功能的详细信息，请参阅 [在 Lync Server 2013 中规划共享线路外观](lync-server-2013-plan-for-shared-line-appearance.md)。</span><span class="sxs-lookup"><span data-stu-id="96890-107">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="96890-108">共享线路外观 (SLA) 是 Lync Server 2013 中的一项新功能，累积更新4月2016。</span><span class="sxs-lookup"><span data-stu-id="96890-108">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="96890-109">若要启用此功能，必须先部署此累积更新。</span><span class="sxs-lookup"><span data-stu-id="96890-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="96890-110">安装共享线路外观</span><span class="sxs-lookup"><span data-stu-id="96890-110">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="96890-111">在 Lync Server 2013 中，部署了累积更新4月2016，默认情况下不启用 SLA 应用程序。</span><span class="sxs-lookup"><span data-stu-id="96890-111">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="96890-112">若要启用应用程序，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="96890-112">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="96890-113">通过对每个池运行以下命令，将 SLA 注册为服务器应用程序：</span><span class="sxs-lookup"><span data-stu-id="96890-113">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="96890-114">其中，% FQDN% 是池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="96890-114">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="96890-115">运行以下命令以更新 SLA cmdlet 的 RBAC 角色：</span><span class="sxs-lookup"><span data-stu-id="96890-115">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="96890-116">在安装并启用了 SLA 的所有池中，重新启动所有前端服务器 (RTCSRV 服务) ：</span><span class="sxs-lookup"><span data-stu-id="96890-116">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="96890-117">创建 SLA 组并向其添加用户</span><span class="sxs-lookup"><span data-stu-id="96890-117">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="96890-118">使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 创建 SLA 组：</span><span class="sxs-lookup"><span data-stu-id="96890-118">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="96890-119">Set-CsSlaConfiguration cmdlet 将企业语音帐户 SLAGroup1 标记为 SLA 实体，SLAGroup1 的数量将成为 SLA 组的编号。</span><span class="sxs-lookup"><span data-stu-id="96890-119">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="96890-120">对 SLAGroup1 的所有呼叫都将拨打整个 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="96890-120">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="96890-121">下面的示例为现有企业语音用户 SLAGroup1 创建 SLA 组，并使用分配给 SLAGroup1 的号码作为 SLA 主线编号。</span><span class="sxs-lookup"><span data-stu-id="96890-121">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="96890-122">该命令将新 SLA 组的最大并发呼叫数设置为3，而超出该限制的呼叫数会听到占线信号：</span><span class="sxs-lookup"><span data-stu-id="96890-122">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="96890-123">您可以使用 Set-CsSlaConfiguration 创建新的 SLA 组或修改现有 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="96890-123">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96890-124">请注意，指定的 <CODE>-Identity</CODE> 必须是有效的现有企业语音的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="96890-124">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="96890-125">使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet 向组添加委派：</span><span class="sxs-lookup"><span data-stu-id="96890-125">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="96890-126">下面的示例将用户添加到 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="96890-126">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="96890-127">添加到该组的每个用户都必须是有效的企业语音启用的用户：</span><span class="sxs-lookup"><span data-stu-id="96890-127">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="96890-128">为要添加到组中的每个用户重复此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96890-128">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="96890-129">用户只能属于一个 SLA 组。</span><span class="sxs-lookup"><span data-stu-id="96890-129">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="96890-130">配置 SLA 组忙碌选项</span><span class="sxs-lookup"><span data-stu-id="96890-130">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="96890-131">使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 配置 SLA 组忙碌选项：</span><span class="sxs-lookup"><span data-stu-id="96890-131">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="96890-132">以下示例将超过要转接到电话号码202-555-1234 的最大并发呼叫数设置为呼叫。</span><span class="sxs-lookup"><span data-stu-id="96890-132">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="96890-133">目标可以是组织中的用户，而不是电话号码;在这种情况下，接收转发呼叫的人的语法与您指定代理时的语法相同： `sip:<NameofDelegate@domain>` 。</span><span class="sxs-lookup"><span data-stu-id="96890-133">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="96890-134">的其他可能的参数 `BusyOption` 为 `Voicemail` ：</span><span class="sxs-lookup"><span data-stu-id="96890-134">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="96890-135">配置 SLA 组未接来电选项</span><span class="sxs-lookup"><span data-stu-id="96890-135">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="96890-136">使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 配置 SLA 组未接来电选项：</span><span class="sxs-lookup"><span data-stu-id="96890-136">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="96890-137">下面的示例指定将未接来电转发给名为的用户 `sla_forward_number` 。</span><span class="sxs-lookup"><span data-stu-id="96890-137">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="96890-138">参数的有效选项为 `-MissedCallOption` `Forward` 、 `BusySignal` 或 `Disconnect` 。</span><span class="sxs-lookup"><span data-stu-id="96890-138">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="96890-139">如果选择 `Forward` 此选项，则还必须包括 `-MissedCallForwardTarget` 参数，以用户或电话号码作为目标：</span><span class="sxs-lookup"><span data-stu-id="96890-139">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="96890-140">从组中删除委派</span><span class="sxs-lookup"><span data-stu-id="96890-140">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="96890-141">使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet 从组中删除委派：</span><span class="sxs-lookup"><span data-stu-id="96890-141">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="96890-142">例如：</span><span class="sxs-lookup"><span data-stu-id="96890-142">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="96890-143">删除 SLA 组</span><span class="sxs-lookup"><span data-stu-id="96890-143">Delete an SLA group</span></span>

1.  <span data-ttu-id="96890-144">使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 删除 SLA 组：</span><span class="sxs-lookup"><span data-stu-id="96890-144">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="96890-145">例如：</span><span class="sxs-lookup"><span data-stu-id="96890-145">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

