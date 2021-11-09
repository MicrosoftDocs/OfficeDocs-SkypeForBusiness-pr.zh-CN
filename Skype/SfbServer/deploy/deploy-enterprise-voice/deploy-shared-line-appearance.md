---
title: Deploy Shared Line Appearance in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: 阅读本主题，了解如何在 2015 年 11 月累积更新的 Skype for Business Server 2015 (SLA) 部署共享线路外观。 SLA 是一项功能，用于处理对名为共享号码的特定号码的多个呼叫。
ms.openlocfilehash: e79bb427c28f2c0e8dcc3ff7b5e0d1f6319ac7d8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835940"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Deploy Shared Line Appearance in Skype for Business Server 2015

阅读本主题，了解如何在 2015 年 11 月累积更新的 Skype for Business Server 2015 (SLA) 部署共享线路外观。 SLA 是一项功能，用于处理对名为共享号码的特定号码的多个呼叫。

有关此功能详细信息，请参阅 Plan [for Shared Line Appearance in Skype for Business Server 2015。](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)

共享线路 (SLA) 是 2015 年 11 月累积Skype for Business Server中的一项新功能。 若要启用此功能，必须先部署此累积更新。

### <a name="install-shared-line-appearance"></a>安装共享线路外观

1. 部署Skype for Business Server 2015 年 11 月累积更新后，在池中的每台前端 `SkypeServerUpdateInstaller.exe` 服务器上运行修补程序。

2. 安装程序将部署最新版本的 SLA 应用程序，但默认情况下不启用该应用程序。 它通过按照下面列出的步骤启用：

    a. 通过针对每个池运行以下命令，将 SLA 注册为服务器应用程序：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   其中 %FQDN% 是池的完全限定域名。

    b. 运行以下命令以更新 SLA cmdlet 的 RBAC 角色：

   ```powershell
   Update-CsAdminRole
   ```

    c. 在安装和启用 SLA 的所有池中 (RTCSRV) 所有前端服务器：

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>创建 SLA 组并添加用户

1. 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 创建 SLA 组：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    此Set-CsSlaConfiguration cmdlet 将企业语音 SLAGroup1 帐户标记为 SLA 实体，并且 SLAGroup1 的数量将成为 SLA 组的数量。 对 SLAGroup1 的所有调用都将拨打整个 SLA 组。

    以下示例为现有用户 SLAGroup1 企业语音 SLAGroup1，并使用为 SLAGroup1 分配的号码作为 SLA 主线号码。

    此命令将新 SLA 组的最大并发呼叫数设置为 3，超过此数目的呼叫将听到繁忙信号：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    可以使用新Set-CsSlaConfiguration SLA 组或修改现有 SLA 组。

    > [!NOTE]
    > 请注意，您为 指定的 `-Identity` 必须是启用企业语音用户帐户的有效现有帐户。

2. 使用 [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet 将委派添加到组：

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    以下示例将用户添加到 SLA 组。 添加到该组的每个用户必须是已启用企业语音用户：

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    对要添加到组的每个用户重复此 cmdlet。 用户只能属于单个 SLA 组。

### <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

- 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组忙碌选项：

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    以下示例设置超过要转发到电话号码 202-555-1234 的最大并发呼叫数的呼叫。 目标可以是您组织的用户，而不是电话号码;在这种情况下，接收被转发呼叫的人的语法与指定代理人时相同  `sip:<NameofDelegate@domain>` ：。 另一个可能的参数  `BusyOption` 是 `Voicemail` ：

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组未接来电选项

1. 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet 配置 SLA 组未接来电选项：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 以下示例指定将未接来电转发到名为 的用户  `sla_forward_number` 。 参数的有效选项是  `-MissedCallOption` 、 `Forward`  `BusySignal` 或  `Disconnect` 。 如果选择 ，  `Forward` 则还必须包含 参数，以  `-MissedCallForwardTarget` 用户或电话号码作为目标：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>从组中删除代理

- 使用 [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet 从组中删除委派：

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>删除 SLA 组

- 使用 [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet 删除 SLA 组：

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如：

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```