---
title: 在 Skype for Business Server 2015 中部署共享线路外观
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
description: 阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新 (SLA) 部署共享线路外观。 SLA 是一项功能，用于处理对名为共享号码的特定号码的多个呼叫。
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812402"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署共享线路外观

阅读本主题，了解如何在 Skype for Business Server 2015 2015 年 11 月累积更新 (SLA) 部署共享线路外观。 SLA 是一项功能，用于处理对名为共享号码的特定号码的多个呼叫。

有关此功能详细信息，请参阅 Plan [for Shared Line Appearance in Skype for Business Server 2015。](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)

SLA (共享线路外观) 是 Skype for Business Server 2015 年 11 月累积更新中的一项新功能。 若要启用此功能，必须先部署此累积更新。

### <a name="install-shared-line-appearance"></a>安装共享线路外观

1. 部署 Skype for Business Server 2015 年 11 月累积更新后，在池中的每台前端  `SkypeServerUpdateInstaller.exe` 服务器上运行修补程序。

2. 安装程序将部署最新版本的 SLA 应用程序，但默认情况下不会启用该应用程序。 它通过按照下面列出的步骤启用：

    a. 通过针对每个池运行以下命令，将 SLA 注册为服务器应用程序：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   其中 %FQDN% 是池的完全限定域名。

    b. 运行以下命令以更新 SLA cmdlet 的 RBAC 角色：

   ```powershell
   Update-CsAdminRole
   ```

    c. 在安装和启用 SLA 的所有池中 (RTCSRV) 重新启动所有前端服务器：

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>创建 SLA 组并添加用户

1. 使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 创建 SLA 组：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    此 Set-CsSlaConfiguration cmdlet 将企业语音 SLAGroup1 标记为 SLA 实体，并且 SLAGroup1 的数量将成为 SLA 组的编号。 对 SLAGroup1 的所有调用都将整个 SLA 组响铃。

    以下示例为现有用户 SLAGroup1 企业语音 SLAGroup1 创建 SLA 组，并使用为 SLAGroup1 分配的号码作为 SLA 主线号码。

    此命令将新 SLA 组的最大并发呼叫数设置为 3，对于超过此数目的呼叫，将听到繁忙信号：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    您可以使用新Set-CsSlaConfiguration SLA 组或修改现有 SLA 组。

    > [!NOTE]
    > 请注意，您指定的帐户  `-Identity` 必须是启用企业语音用户帐户的有效现有帐户。

2. 使用 [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet 将委派添加到组：

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    以下示例将用户添加到 SLA 组。 添加到该组的每个用户都必须是启用企业语音用户：

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    对要添加到组的每个用户重复此 cmdlet。 用户只能属于单个 SLA 组。

### <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

- 使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组忙碌选项：

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    以下示例设置超过要转发到电话号码 202-555-1234 的最大并发呼叫数的呼叫。 目标可以是您组织的用户，而不是电话号码;在这种情况下，接收转发呼叫的人的语法与指定代理人时  `sip:<NameofDelegate@domain>` 相同： 另一个可能的参数  `BusyOption` 是 `Voicemail` ：

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组未接来电选项

1. 使用 [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组未接来电选项：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 下面的示例指定将未接来电转发到名为的用户  `sla_forward_number` 。 参数的有效选项是  `-MissedCallOption` ， `Forward`  `BusySignal` 或  `Disconnect` 。 如果选择，  `Forward` 还必须包含参数，以用户或  `-MissedCallForwardTarget` 电话号码为目标：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>从组中删除委派

- 使用 [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet 从组中删除委派：

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>删除 SLA 组

- 使用 [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet 删除 SLA 组：

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如：

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


