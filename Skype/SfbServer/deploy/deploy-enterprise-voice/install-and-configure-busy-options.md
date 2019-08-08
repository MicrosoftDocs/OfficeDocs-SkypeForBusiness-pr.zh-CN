---
title: 安装和配置适用于 Skype for Business Server 的忙碌选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 阅读有关如何在 Skype for Business 服务器中安装和配置 Busy 选项的信息。
ms.openlocfilehash: a0fd235d5db645035ac9a6344c233dfe12a78b7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240308"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>安装和配置适用于 Skype for Business Server 的忙碌选项

阅读有关如何在 Skype for Business 服务器中安装和配置 Busy 选项的信息。

忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户正在接听电话或参加会议或将呼叫置于等待状态时传入呼叫的处理方式。 可以通过忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转接到语音邮件。

如果已为组织启用忙碌选项，则企业中的所有用户（企业语音用户和非企业语音用户）都可以使用以下配置选项：

- Busy on Busy - 如果用户忙碌，将通过忙音信号拒绝新的传入呼叫。

- Voicemail on Busy - 如果用户忙碌，新的传入呼叫会转接到语音邮件。

无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或将呼叫置于等待状态的用户发起新呼叫或会议。  

有关忙碌选项功能的详细信息，请参阅[Plan for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>安装 

请确保安装了最新版本的 Skype for Business 服务器, 并且已安装了最新的修补程序。 若要执行此操作, 请首先停止所有服务, 然后运行 Skype for Business 服务器更新安装程序, 如下所示:

1. 运行 Stop-CsWindowsService 命令。

2. 在池中的每台前端服务器上运行 SkypeServerUpdateInstaller.exe 安装程序。

3. 在每个 Survivable Branch Server (SBS) 上运行 SkypeServerUpdateInstaller.exe 安装程序（如果要确保支持在 SBS 上进行故障转移）。

安装程序将部署最新版本的忙碌选项应用程序。但是，该应用程序默认情况下不启用。要启用该应用程序，请执行以下步骤：

1. 运行[CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet 以全局启用 Busy 选项, 如以下示例中所示:

   ```
   Set-CsVoicePolicy -EnableBusyOptions $true
   ```

2. 接下来，如果站点具备语音策略，则必须按如下所示为该语音策略启用忙碌选项：

    首先, 运行[CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)以检索网站的名称:

   ```
   Get-CsSite
   ```

    使用从 Get CsSite 检索到的标识值 (例如: Site: Redmond1), 以检索网站的语音策略, 如下所示:

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    如果站点存在语音策略，请运行以下命令：

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 接下来, 运行[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet 以将 Busy 选项添加到服务器应用程序列表中, 如下例所示:

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri http://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > 必须将% FQDN% 替换为特定池的完全限定的域名。

4. 接下来, 运行[CsAdminRole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet 以更新 "繁忙选项" cmdlet 的基于角色的访问控制 (RBAC) 角色, 如下例中所示:

   ```
   Update-CsAdminRole
   ```

5. 最后, 通过运行 "[开始-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps) " 命令, 在安装和启用 "忙碌" 选项的所有池中的所有前端服务器上启动 Skype For Business 服务器 Windows 服务:

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>配置

要配置忙碌选项，请使用 [Set-CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet。  

例如，以下命令可配置用户“Ken Myer”的忙碌选项。在此配置中，当“Ken Myer”已接听电话时，向其发起的任何呼叫都将返回忙音：

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

在下一个示例中，该命令可配置用户“Chrystal Velasquez”的忙碌选项。 在此配置中，当“Chrystal Velasquez”已接听电话时，向其发起的新传入呼叫都将转接到语言邮件。

```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

你可以通过使用 [Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet 检索有关忙碌选项的配置信息。 以下示例返回 "KenMyer@Contoso.com" 的 Busy 选项设置:

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

你可以通过使用 [Remove-CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet 删除忙碌选项。 以下命令将删除“Ken Myer”的忙碌选项。

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

有关用于配置 Busy 选项的 cmdlet 的详细信息, 请参阅[设置 CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)和[CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技术参考内容。

## <a name="enable-logging"></a>启用日志记录

要通过使用集中日志记录服务对忙碌选项启用日志记录，请指定以下各项：

```
$p1 = New-CsClsProvider -Name S4 -Type WPP -Level Info -Flags All
$p2 = New-CsClsProvider -Name Sipstack -Type WPP -Level Info -Flags
 "TF_PROTOCOL,TF_CONNECTION,TF_SECURITY,TF_DIAG,TF_SHOW_CONFERENCE,TF_SHOW_ALLREQUESTS,TF_SHOW_ALLSIPHEADERS" -Role Registrar
$p3 = New-CsClsProvider -Name BusyOptions -Type WPP -Level Verbose -Flags All
New-CsClsScenario -Parent Global -Name BusyOptions -Provider @{Add=$p1,$p2,$p3}
```

## <a name="verify-and-troubleshoot"></a>验证和故障排除

安装 Busy 选项后, 可以使用[CsServerApplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet 检索服务器应用程序列表, 验证安装是否成功。 如果忙碌选项已正确安装，该 cmdlet 的输出应显示忙碌选项配置，如下所示：

<pre>
Identity   : Service:Registrar:pool0.vdomain.com/BusyOptions
Priority   : 5
Uri        : http://www.microsoft.com/LCS/BusyOptions
Name       : BusyOptions
Enabled    : True
Critical   : False
ScriptName :
Script     :
</pre>

你还可以使用 Windows 事件查看器验证 "忙碌" 选项安装是否成功, 以及 Skype for Business 服务器是否已成功加载了 "忙碌" 选项。 若要验证 Busy 选项, 请打开**事件\>查看器-应用程序\>和服务日志-Skype (或 Lync) 服务器**, 然后搜索事件 ID = 30253。
