---
title: 在 Skype for Business Server 2015 中部署共享线路外观
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 阅读本主题，了解如何在 Skype for Business Server 2015 的 2015 年 11 月累积更新中部署共享线路外观 (SLA)。SLA 是用于处理对特定号码（称为“共享号码”）的多个呼叫的功能。
ms.openlocfilehash: 45d4d78b157f5fb987de2345cf2b7d5c5867edab
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "21145300"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署共享线路外观
 
阅读本主题，了解如何在 Skype for Business Server 2015 的 2015 年 11 月累积更新中部署共享线路外观 (SLA)。SLA 是用于处理对特定号码（称为“共享号码”）的多个呼叫的功能。 
  
有关此功能的详细信息，请参阅[规划中的业务服务器 2015 Skype 共享行外观](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。
  
共享行外观 (SLA) 是 Skype 业务服务器中的新功能年 11 月 2015年累积更新。 要启用此功能，必须首先部署此累积更新。
  
### <a name="install-shared-line-appearance"></a>安装共享线路外观

1. 对于业务服务器，年 11 月 2015年部署累积更新，Skype 后运行`SkypeServerUpdateInstaller.exe`池中每个前端服务器上的修补程序。
    
2. 安装程序将部署最新的 SLA 应用程序，然而，该应用程序默认情况下不启用。可按照下面所述的步骤启用它：
    
    a. 为每个池运行以下命令，以便将 SLA 注册为服务器应用程序：
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   其中，%FQDN% 是池的完全限定的域名。 
    
    b. 运行以下命令来更新 SLA cmdlet 的 RBAC 角色： 
    
   ```
   Update-CsAdminRole 
   ```

    c. 重新启动所有池中已安装并启用 SLA 的所有前端服务器（RTCSRV 服务）：
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV   
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>创建一个 SLA 组并向该组添加用户

1. 使用[组 CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 创建的 SLA 组：
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
  ```

    Set-CsSlaConfiguration cmdlet 会将企业语音帐户 SLAGroup1 标记为 SLA 实体，并且 SLAGroup1 的号码将变为 SLA 组的号码。对 SLAGroup1 的所有呼叫将拨打整个 SLA 组。
    
    以下示例将为现有企业语音用户创建 SLA 组 SLAGroup1，并使用为 SLAGroup1 分配的号码作为 SLA 主线路号码。 
    
    命令会将新 SLA 组的最大并发呼叫数设置为 3，超过该数目的呼叫将听到忙音信号：
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
  ```

    您可以使用 Set-CsSlaConfiguration 创建新的 SLA 组或修改现有 SLA 组。
    
    > [!NOTE]
    > 请注意，您所指定的`-Identity`必须为有效的现有已启用企业语音的用户帐户。
  
2. 通过使用[添加 CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet 添加到组的代理人：
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    以下示例将向 SLA 组添加一个用户。 添加到组中每个用户必须是有效的启用了企业语音的用户：
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
  ```

    对要添加到组的每个用户重复该 cmdlet。用户只能属于单个 SLA 组。
    
### <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

- 配置 SLA 忙选项组使用[集 CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    以下示例会将超过最大并发呼叫数的呼叫设置为转接到电话号码 202-555-1234。 目标可能而不是一个电话号码; 您组织内的用户在这种情况下，接收呼叫转移的人员的语法是相同时指定代理人： `sip:<NameofDelegate@domain>`。 其他可能的参数的`BusyOption`是`Voicemail`:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组未接来电选项

1. 使用[组 CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组错过呼叫选项：
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. 下面的示例指定错过的呼叫转接至指定的用户`sla_forward_number`。 有效选项`-MissedCallOption`参数`Forward`， `BusySignal`，或`Disconnect`。 如果您选择`Forward`，还必须包括`-MissedCallForwardTarget`参数，作为目标用户或电话号码：
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a>从组中删除代理人

- 使用[删除 CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet 从组中删除代理人：
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>删除 SLA 组

- 使用[删除 CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet 删除 SLA 组：
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如： 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


