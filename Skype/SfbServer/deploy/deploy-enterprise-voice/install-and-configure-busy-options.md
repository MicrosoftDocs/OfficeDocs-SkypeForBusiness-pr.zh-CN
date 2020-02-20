---
title: 为 Skype for Business Server 安装和配置忙碌选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 阅读有关如何在 Skype for Business Server 中安装和配置忙碌选项的信息。
ms.openlocfilehash: 5078041401c710a249470ed6d3871f38a98a7420
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113115"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>为 Skype for Business Server 安装和配置忙碌选项

阅读有关如何在 Skype for Business Server 中安装和配置忙碌选项的信息。

"忙碌选项" 是在2016累积更新中引入的新语音策略，允许您配置当用户已在通话或会议中，或具有处于保留状态的呼叫时如何处理传入呼叫。 可以使用占线信号拒绝新的或传入的呼叫，或将其转接到语音邮件。

如果为组织启用忙碌选项，企业中的所有用户（企业语音用户和非企业语音用户）都可以使用以下配置选项：

- 占线-如果用户忙碌，将使用占线信号拒绝新的传入呼叫。

- 占线中的语音邮件-如果用户忙碌，将向语音邮件转发新的传入呼叫。

无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或呼叫处于保留状态的用户发起新呼叫或会议。

有关忙碌选项功能的详细信息，请参阅[Plan For Busy options For Skype For Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>安装

请确保已安装最新版本的 Skype for Business Server，并且已安装最新的修补程序。 若要执行此操作，请先停止所有服务，然后运行 Skype for Business Server 更新安装程序，如下所示：

1. 运行 Start-cswindowsservice 命令。

2. 在池中的每台前端服务器上运行 Skypeserverupdateinstaller.exe 安装程序。

3. 如果要确保在 SBS 上支持故障转移，请在每个 Survivable 分支服务器（SBS）上运行 Skypeserverupdateinstaller.exe 安装程序。

安装程序将部署最新版本的 Busy Options 应用程序。 但是，默认情况下不会启用该应用程序。 若要启用该应用程序，请执行以下步骤：

1. 运行[set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet 以全局启用忙碌选项，如下面的示例所示：

   ```powershell
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 接下来，如果网站有语音策略，则必须为语音策略启用忙碌选项，如下所示：

    首先，运行[get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)以检索网站的名称：

   ```powershell
   Get-CsSite
   ```

    使用从 Get-cssite 检索到的标识值（例如： Site： Redmond1）来检索网站的语音策略，如下所示：

   ```powershell
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    如果网站存在语音策略，请运行以下命令：

   ```powershell
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 接下来，运行[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet 以将忙碌选项添加到服务器应用程序列表中，如以下示例所示：

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > 您必须将% FQDN% 替换为特定池的完全限定域名。

4. 接下来，运行[CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet 以更新 "忙碌选项" cmdlet 的基于角色的访问控制（RBAC）角色，如以下示例所示：

   ```powershell
   Update-CsAdminRole
   ```

5. 最后，在通过运行[start-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)命令安装和启用忙碌选项的所有池的所有前端服务器上启动 Skype For Business Server Windows 服务：

   ```powershell
   Start-CsWindowsService
   ```

## <a name="configure"></a>配置

若要配置忙碌选项，请使用[set-csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet。

例如，以下命令配置用户 "Ken Myer" 的忙碌选项。 在此配置中，对 "Ken Myer" 的任何调用将在他已处于呼叫中时返回一个占线信号：

```powershell
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

在下一个示例中，该命令将为用户 "Chrystal Velasquez" 配置忙碌选项。 在此配置中，当她已经在呼叫中时，会将对 "Chrystal Velasquez" 的新传入呼叫转发到语音邮件：

```powershell
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

您可以使用[set-csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet 检索有关忙碌选项的配置信息。 下面的示例返回 "KenMyer@Contoso.com" 的 "忙碌选项" 设置：

```powershell
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

您可以使用[set-csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) Cmdlet 删除忙碌选项。 以下命令将删除 "Ken Myer" 的忙碌选项：

```powershell
Remove-CsBusyOptions -Identity "Ken Myer"
```

有关用于配置忙碌选项的 cmdlet 的详细信息，请参阅 " [set-csbusyoptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)"、" [set-csbusyoptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)" 和 " [set-csbusyoptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)" 的技术参考内容。

## <a name="enable-logging"></a>启用日志记录

若要使用集中日志记录服务启用忙碌选项的日志记录，请指定以下内容：

```powershell
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>验证和故障排除

安装忙碌选项后，可以使用[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet 检索服务器应用程序的列表，以验证安装是否成功。 如果忙选项安装正确，则 cmdlet 的输出应显示 "忙碌选项" 配置，如下所示：

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

您还可以使用 Windows 事件查看器来验证 "忙碌" 选项安装是否成功，以及 Skype for Business Server 是否已成功加载 "忙碌" 选项。 若要验证忙碌选项，请打开 "**事件查看器-\>应用\>程序和服务日志-Skype （或 Lync）服务器**"，然后搜索事件 ID = 30253。
