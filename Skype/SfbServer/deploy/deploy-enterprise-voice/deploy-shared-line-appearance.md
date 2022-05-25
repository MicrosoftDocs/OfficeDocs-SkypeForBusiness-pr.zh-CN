---
title: 在 2015 Skype for Business Server部署共享行外观
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
description: 阅读本主题，了解如何在 2015 年 11 月Skype for Business Server累积更新中部署共享行外观 (SLA) 。 SLA 是一项功能，用于处理对称为共享号码的特定号码的多个调用。
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671588"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>在 2015 Skype for Business Server部署共享行外观

阅读本主题，了解如何在 2015 年 11 月Skype for Business Server累积更新中部署共享行外观 (SLA) 。 SLA 是一项功能，用于处理对称为共享号码的特定号码的多个调用。

有关此功能的详细信息，请参阅 [2015 Skype for Business Server中的“共享行外观计划](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)”。

共享行外观 (SLA) 是 2015 年 11 月累积更新Skype for Business Server中的一项新功能。 若要启用此功能，必须先部署此累积更新。

## <a name="install-shared-line-appearance"></a>安装共享行外观

1. Skype for Business Server部署 2015 年 11 月累积更新后，在池中的每个前端服务器上运行`SkypeServerUpdateInstaller.exe`修补程序。

2. 安装程序将部署最新版本的 SLA 应用程序，但默认情况下不会启用该应用程序。 它通过执行下面所述的步骤启用：

    a. 为每个池运行以下命令，将 SLA 注册为服务器应用程序：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   其中 %FQDN% 是池的完全限定域名。

    b. 运行以下命令以更新 SLA cmdlet 的 RBAC 角色：

   ```powershell
   Update-CsAdminRole
   ```

    c. 在安装和启用 SLA 的所有池中重启所有前端服务器 (RTCSRV 服务) ：

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>创建 SLA 组并向其添加用户

1. 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) cmdlet 创建 SLA 组：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Set-CsSlaConfiguration cmdlet 将企业语音帐户 SLAGroup1 标记为 SLA 实体，SLAGroup1 的数目将成为 SLA 组的数字。 对 SLAGroup1 的所有调用都将响铃整个 SLA 组。

    以下示例为现有企业语音用户 SLAGroup1 创建 SLA 组，并使用为 SLAGroup1 分配的数字作为 SLA 主线编号。

    该命令将新 SLA 组的最大并发调用数设置为 3，并且超过该组的调用将听到繁忙信号：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    可以使用Set-CsSlaConfiguration创建新的 SLA 组或修改现有的 SLA 组。

    > [!NOTE]
    > 请注意，指定`-Identity`的内容必须是已启用企业语音的有效现有用户帐户。

2. 使用 [Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates) cmdlet 将委托添加到组：

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    以下示例将用户添加到 SLA 组。 添加到组中的每个用户都必须是已启用企业语音的有效用户：

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    为要添加到组的每个用户重复 cmdlet。 用户只能属于单个 SLA 组。

## <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

- 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) cmdlet 配置 SLA 组忙碌选项：

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    以下示例设置超过要转发到电话号码 202-555-1234 的最大并发呼叫数的呼叫。 目标可以是组织中的用户，而不是电话号码;在这种情况下，接收转发调用的人员的语法与指定委托时相同： `sip:<NameofDelegate@domain>` 另一个可能的参数是`BusyOption``Voicemail`：

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组“错过呼叫”选项

1. 使用 [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) cmdlet 配置 SLA 组“错过呼叫”选项：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 以下示例指定将未接听的呼叫转发给已命名  `sla_forward_number`的用户。 参数的`-MissedCallOption`有效选项为`Forward`或 `BusySignal``Disconnect`。 如果选择  `Forward`，还必须包含  `-MissedCallForwardTarget` 以用户或电话号码为目标的参数：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>从组中删除委托

- 使用 [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) cmdlet 从组中删除委托：

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>删除 SLA 组

- 使用 [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) cmdlet 删除 SLA 组：

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如：

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
