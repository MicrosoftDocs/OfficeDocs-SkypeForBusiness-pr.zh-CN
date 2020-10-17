---
title: Lync Server 2013：部署共享线路外观
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
ms.openlocfilehash: 15d0bffd92c4c2e2448938c467eec73c9bab1a94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531409"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中部署共享线路外观

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-06-13_

阅读本主题，了解如何在 Lync Server 2013 中部署共享线路外观 (SLA) ，累积更新4月2016。 SLA 是一项用于处理对特定号码（称为共享号码）的多个呼叫的功能。

有关此功能的详细信息，请参阅 [在 Lync Server 2013 中规划共享线路外观](lync-server-2013-plan-for-shared-line-appearance.md)。

共享线路外观 (SLA) 是 Lync Server 2013 中的一项新功能，累积更新4月2016。 若要启用此功能，必须先部署此累积更新。

<div>

## <a name="install-shared-line-appearance"></a>安装共享线路外观

1.  在 Lync Server 2013 中，部署了累积更新4月2016，默认情况下不启用 SLA 应用程序。 若要启用应用程序，请执行以下步骤：
    
    1.  通过对每个池运行以下命令，将 SLA 注册为服务器应用程序：
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        其中，% FQDN% 是池的完全限定的域名。
    
    2.  运行以下命令以更新 SLA cmdlet 的 RBAC 角色：
        ```powershell
        Update-CsAdminRole 
        ```
    3.  在安装并启用了 SLA 的所有池中，重新启动所有前端服务器 (RTCSRV 服务) ：
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>创建 SLA 组并向其添加用户

1.  使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 创建 SLA 组：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Set-CsSlaConfiguration cmdlet 将企业语音帐户 SLAGroup1 标记为 SLA 实体，SLAGroup1 的数量将成为 SLA 组的编号。 对 SLAGroup1 的所有呼叫都将拨打整个 SLA 组。
    
    下面的示例为现有企业语音用户 SLAGroup1 创建 SLA 组，并使用分配给 SLAGroup1 的号码作为 SLA 主线编号。
    
    该命令将新 SLA 组的最大并发呼叫数设置为3，而超出该限制的呼叫数会听到占线信号：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    您可以使用 Set-CsSlaConfiguration 创建新的 SLA 组或修改现有 SLA 组。
    
    <div>
    

    > [!NOTE]  
    > 请注意，指定的 <CODE>-Identity</CODE> 必须是有效的现有企业语音的用户帐户。

    
    </div>

2.  使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet 向组添加委派：
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    下面的示例将用户添加到 SLA 组。 添加到该组的每个用户都必须是有效的企业语音启用的用户：
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    为要添加到组中的每个用户重复此 cmdlet。 用户只能属于一个 SLA 组。

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

1.  使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 配置 SLA 组忙碌选项：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    以下示例将超过要转接到电话号码202-555-1234 的最大并发呼叫数设置为呼叫。 目标可以是组织中的用户，而不是电话号码;在这种情况下，接收转发呼叫的人的语法与您指定代理时的语法相同： `sip:<NameofDelegate@domain>` 。 的其他可能的参数 `BusyOption` 为 `Voicemail` ：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组未接来电选项

1.  使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) CMDLET 配置 SLA 组未接来电选项：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    下面的示例指定将未接来电转发给名为的用户 `sla_forward_number` 。 参数的有效选项为 `-MissedCallOption` `Forward` 、 `BusySignal` 或 `Disconnect` 。 如果选择 `Forward` 此选项，则还必须包括 `-MissedCallForwardTarget` 参数，以用户或电话号码作为目标：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>从组中删除委派

1.  使用 [CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet 从组中删除委派：
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    例如：
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>删除 SLA 组

1.  使用 [set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 删除 SLA 组：
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    例如：
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

