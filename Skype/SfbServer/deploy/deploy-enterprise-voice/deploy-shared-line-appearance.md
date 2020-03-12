---
title: 在 Skype for Business Server 2015 中部署共享线路外观
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 阅读本主题，了解如何在 Skype for Business Server 2015 2015 年11月11日累积更新中部署共享线路外观（SLA）。 SLA 是一项用于处理对特定号码（称为共享号码）的多个呼叫的功能。
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604219"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中部署共享线路外观

阅读本主题，了解如何在 Skype for Business Server 2015 2015 年11月11日累积更新中部署共享线路外观（SLA）。 SLA 是一项用于处理对特定号码（称为共享号码）的多个呼叫的功能。

有关此功能的详细信息，请参阅[在 Skype For Business Server 2015 中规划共享线路外观](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)。

共享线路外观（SLA）是 Skype for Business Server 中的一项新功能，即2015年11月累积更新。 若要启用此功能，必须先部署此累积更新。

### <a name="install-shared-line-appearance"></a>安装共享线路外观

1. 在 Skype for Business Server 后，部署了11月2015累积更新， `SkypeServerUpdateInstaller.exe`在池中的每台前端服务器上运行修补程序。

2. 安装程序将部署最新版本的 SLA 应用程序，但默认情况下不启用该应用程序。 通过执行以下概述的步骤启用：

    a. 通过对每个池运行以下命令，将 SLA 注册为服务器应用程序：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   其中，% FQDN% 是池的完全限定的域名。

    b. 运行以下命令以更新 SLA cmdlet 的 RBAC 角色：

   ```powershell
   Update-CsAdminRole
   ```

    c. 在已安装并启用了 SLA 的所有池中重新启动所有前端服务器（RTCSRV 服务）：

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>创建 SLA 组并向其添加用户

1. 使用[set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) CMDLET 创建 SLA 组：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Set-csslaconfiguration cmdlet 将企业语音帐户 SLAGroup1 标记为 SLA 实体，SLAGroup1 数将成为 SLA 组的编号。 对 SLAGroup1 的所有呼叫都将拨打整个 SLA 组。

    下面的示例为现有企业语音用户 SLAGroup1 创建 SLA 组，并使用分配给 SLAGroup1 的号码作为 SLA 主线编号。

    该命令将新 SLA 组的最大并发呼叫数设置为3，而超出该限制的呼叫数会听到占线信号：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    您可以使用 Set-csslaconfiguration 创建新的 SLA 组或修改现有 SLA 组。

    > [!NOTE]
    > 请注意，指定的必须`-Identity`是有效的现有企业语音的用户帐户。

2. 使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet 向组添加委派：

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    下面的示例将用户添加到 SLA 组。 添加到该组的每个用户都必须是有效的企业语音启用的用户：

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    为要添加到组中的每个用户重复此 cmdlet。 用户只能属于一个 SLA 组。

### <a name="configure-the-sla-group-busy-option"></a>配置 SLA 组忙碌选项

- 使用[set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) CMDLET 配置 SLA 组忙碌选项：

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    以下示例将超过要转接到电话号码202-555-1234 的最大并发呼叫数设置为呼叫。 目标可以是组织中的用户，而不是电话号码;在这种情况下，接收转发呼叫的人的语法与您指定代理时的语法相同： `sip:<NameofDelegate@domain>`。 的其他可能的参数`BusyOption`为`Voicemail`：

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>配置 SLA 组未接来电选项

1. 使用[set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) CMDLET 配置 SLA 组未接来电选项：

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. 下面的示例指定将未接来电转发给名为`sla_forward_number`的用户。 `-MissedCallOption`参数的有效选项为`Forward`、 `BusySignal`或`Disconnect`。 如果选择`Forward`此`-MissedCallForwardTarget`选项，则还必须包括参数，以用户或电话号码作为目标：

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>从组中删除委派

- 使用[CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet 从组中删除委派：

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    例如：

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>删除 SLA 组

- 使用[set-csslaconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) CMDLET 删除 SLA 组：

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    例如：

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


