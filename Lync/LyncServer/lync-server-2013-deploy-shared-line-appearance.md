---
title: Lync Server 2013：部署共享行外观
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da81073fc239822a682f926e1b782c8555153bf6
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>在 Lync Server 2013 中部署共享行外观

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-06-13_

阅读本主题，了解如何在 Lync Server 2013 中部署共享线路外观（SLA），累积更新4月2016。 SLA 是用于处理对特定号码（称为“共享号码”）的多个呼叫的功能。

有关此功能的详细信息，请参阅[Lync Server 2013 中的共享行外观计划](lync-server-2013-plan-for-shared-line-appearance.md)。

共享线路外观（SLA）是 Lync Server 2013 中的一项新功能，累积更新4月2016。 要启用此功能，必须首先部署此累积更新。

<div>

## <a name="install-shared-line-appearance"></a>安装共享线路外观

1.  在 Lync Server 2013 之后，将部署 "累积更新4月 2016"，默认情况下不启用 SLA 应用程序。 若要启用该应用程序，请按照下列步骤操作：
    
    1.  为每个池运行以下命令，以便将 SLA 注册为服务器应用程序：
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        其中，%FQDN% 是池的完全限定的域名。
    
    2.  运行以下命令来更新 SLA cmdlet 的 RBAC 角色：
        ```powershell
        Update-CsAdminRole 
        ```
    3.  重新启动所有池中已安装并启用 SLA 的所有前端服务器（RTCSRV 服务）：
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>创建一个 SLA 组并向该组添加用户

1.  使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet 创建 SLA 组：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Set-CsSlaConfiguration cmdlet 会将企业语音帐户 SLAGroup1 标记为 SLA 实体，并且 SLAGroup1 的号码将变为 SLA 组的号码。对 SLAGroup1 的所有呼叫将拨打整个 SLA 组。
    
    以下示例将为现有企业语音用户创建 SLA 组 SLAGroup1，并使用为 SLAGroup1 分配的号码作为 SLA 主线路号码。
    
    命令会将新 SLA 组的最大并发呼叫数设置为 3，超过该数目的呼叫将听到忙音信号：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    您可以使用 Set-CsSlaConfiguration 创建新的 SLA 组或修改现有 SLA 组。
    
    <div>
    

    > [!NOTE]  
    > 请注意，为指定的<CODE>-Identity</CODE>内容必须是有效的现有企业语音的用户帐户。

    
    </div>

2.  使用 [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet 向组添加代理人：
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    以下示例将向 SLA 组添加一个用户。 添加到该组的每个用户都必须是有效的企业语音支持的用户：
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    对要添加到组的每个用户重复该 cmdlet。用户只能属于单个 SLA 组。

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

1.  使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet 配置 SLA 组忙碌选项：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    以下示例会将超过最大并发呼叫数的呼叫设置为转接到电话号码 202-555-1234。 目标可以是组织中的用户，而不是电话号码;在这种情况下，接收转接呼叫的用户的语法与您指定代理人时的语法相同： `sip:<NameofDelegate@domain>`。 的另一个可能的`BusyOption`参数`Voicemail`是：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组未接来电选项

1.  使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet 配置 SLA 组未接来电选项：
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    以下示例指定将未接来电转发到名为`sla_forward_number`的用户。 `-MissedCallOption`参数的有效选项为`Forward`、 `BusySignal`或`Disconnect`。 如果选择`Forward`""，则还必须包括`-MissedCallForwardTarget`参数，将用户或电话号码用作目标：
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>从组中删除代理人

1.  使用 [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet 从组中删除代理人：
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

1.  使用 [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet 删除 SLA 组：
    
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

