---
title: 安装和配置 Skype for Business Server 的忙碌选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 了解如何在 Skype for Business Server 中安装和配置忙碌选项。
ms.openlocfilehash: e1480809eb1f14dd25837d11fd54ed6bb5cac534
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830802"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>安装和配置 Skype for Business Server 的忙碌选项

了解如何在 Skype for Business Server 中安装和配置忙碌选项。

忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户已接听电话或参加会议或将呼叫置于保留状态时如何处理传入呼叫。 可以使用忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转发到语音邮件。

如果为组织启用了忙碌选项，企业版中的所有用户（企业语音和非 企业语音用户）都可以使用以下配置选项：

- 忙碌 - 在用户忙碌时，新传入呼叫将因忙音信号被拒绝。

- Voicemail on Busy - 其中的新传入呼叫将在用户忙碌时转发到语音邮件。

无论如何配置忙碌选项，呼叫或会议中的用户或呼叫保持的用户不会阻止发起新呼叫或会议。

有关忙碌选项功能的详细信息，请参阅 Plan [for Busy Options for Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)

## <a name="install"></a>安装

请确保已安装最新版本的 Skype for Business Server，并且已安装最新的修补程序。 为此，首先停止所有服务，然后运行 Skype for Business Server 更新安装程序，如下所示：

1. 运行Stop-CsWindowsService命令。

2. 在SkypeServerUpdateInstaller.exe每台前端服务器上运行前端安装程序。

3. 如果希望确保支持 SBS 上的故障转移，SkypeServerUpdateInstaller.exe Survivable Branch Server (SBS) 运行此安装程序。

安装程序将部署最新版本的忙碌选项应用程序。 但是，默认情况下不会启用该应用程序。 若要启用应用程序，请执行以下步骤：

1. 运行 [Set-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet 以全局启用忙碌选项，如以下示例所示：

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 接下来，如果站点具有语音策略，则必须为语音策略启用忙碌选项，如下所示：

    首先，运行 [Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps) 以检索网站的名称：

   ```powershell
   Get-CsSite
   ```

    使用 Identity 值 (例如：Site：Redmond1) 从 Get-CsSite 检索站点的语音策略，如下所示：

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    如果站点存在语音策略，请运行以下命令：

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 接下来，运行 [New-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet 将忙碌选项添加到服务器应用程序列表中，如以下示例所示：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > 必须将 %FQDN% 替换为特定池的完全限定域名。

4. 接下来，运行 [Update-CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet 更新忙碌选项 cmdlet 的基于角色的访问控制 (RBAC) 角色，如以下示例所示：

   ```powershell
   Update-CsAdminRole
   ```

5. 最后，通过运行 [Start-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) 命令，在安装和启用忙碌选项的所有池中的所有前端服务器上启动 Skype for Business Server Windows 服务：

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>配置

若要配置忙碌选项，请使用 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet。

例如，以下命令为用户"Ken Myer"配置忙碌选项。 在此配置中，当"Ken Myer"已呼叫时，任何对"Ken Myer"的呼叫都将返回繁忙信号：

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

下一个示例中，该命令为用户"Chrystal Velasquez"配置忙碌选项。 在此配置中，"Chrystal Velasquez"的新传入呼叫将在她已接听电话时转发到语音邮件：

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

您可以使用 [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet 检索有关忙碌选项的配置信息。 以下示例返回"KenMyer@Contoso.com"的忙碌选项设置：

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

您可以使用 [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet 删除忙碌选项。 以下命令删除"Ken Myer"的忙碌选项：

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

有关用于配置忙碌选项的 cmdlet 的详细信息，请参阅[Set-CsBusyOptions、Get-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)和[Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技术参考内容。 [](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)

## <a name="enable-logging"></a>启用日志记录

若要使用集中日志记录服务为忙碌选项启用日志记录，请指定以下内容：

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>验证和疑难解答

安装忙碌选项后，您可以通过使用 [Get-CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet 检索服务器应用程序列表来验证安装是否成功。 如果忙碌选项安装正确，cmdlet 的输出应显示忙碌选项配置，如下所示：

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : https://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

您还可以使用 Windows 事件查看器验证忙碌选项安装是否成功，以及 Skype for Business Server 已成功加载忙碌选项。 若要验证忙碌选项，请打开事件查看器 - 应用程序和服务 **日志 - Skype (或 Lync) \> \> Server，** 并搜索事件 ID = 30253。
