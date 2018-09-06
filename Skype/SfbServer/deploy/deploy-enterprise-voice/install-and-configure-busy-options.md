---
title: 安装和配置适用于 Skype for Business Server 的忙碌选项
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb0faac8-ca1c-4abb-9959-d19def294c64
description: 阅读有关如何安装和配置忙选项中 Skype 业务服务器。
ms.openlocfilehash: 97b478a9b50d948fb221ade7519e591c630bccfb
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23241603"
---
# <a name="install-and-configure-busy-options-for-skype-for-business-server"></a>安装和配置适用于 Skype for Business Server 的忙碌选项

阅读有关如何安装和配置忙选项中 Skype 业务服务器。

忙碌选项是 2016 年 7 月累积更新中引入的新语音策略，允许你配置当用户正在接听电话或参加会议或将呼叫置于等待状态时传入呼叫的处理方式。 可以通过忙音信号拒绝新呼叫或传入呼叫，也可以将新呼叫或传入呼叫转接到语音邮件。

如果已为组织启用忙碌选项，则企业中的所有用户（企业语音用户和非企业语音用户）都可以使用以下配置选项：

- Busy on Busy - 如果用户忙碌，将通过忙音信号拒绝新的传入呼叫。

- Voicemail on Busy - 如果用户忙碌，新的传入呼叫会转接到语音邮件。

无论其忙碌选项如何配置，都不会阻止通话或会议中的用户或将呼叫置于等待状态的用户发起新呼叫或会议。  

有关的忙选项功能的详细信息，请参阅[Plan for Business Server 的 Skype 忙选项](../../plan-your-deployment/enterprise-voice-solution/busy-options.md)。

## <a name="install"></a>安装 

确保已安装的业务服务器 Skype 的最新版本，并且您已安装最新的修补程序。 若要执行此操作，先停止所有服务，然后运行 Skype 的业务服务器更新安装程序，如下所示：

1. 运行 Stop-CsWindowsService 命令。

2. 在池中的每台前端服务器上运行 SkypeServerUpdateInstaller.exe 安装程序。

3. 在每个 Survivable Branch Server (SBS) 上运行 SkypeServerUpdateInstaller.exe 安装程序（如果要确保支持在 SBS 上进行故障转移）。

安装程序将部署最新版本的忙碌选项应用程序。但是，该应用程序默认情况下不启用。要启用该应用程序，请执行以下步骤：

1. 运行[Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/set-csvoicepolicy?view=skype-ps) cmdlet 来全局启用忙选项，如下面的示例中所示：

  ```
  Set-CsVoicePolicy -EnableBusyOptions $true
  ```

2. 接下来，如果站点具备语音策略，则必须按如下所示为该语音策略启用忙碌选项：

    首先，运行[Get-cssite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)检索网站的名称：

   ```
   Get-CsSite
   ```

    使用 Identity 值 (例如： 网站： Redmond1) 检索从 Get-cssite 检索网站的语音策略，如下所示：

   ```
   Get-CsVoicePolicy -Identity Site:Redmond1
   ```

    如果站点存在语音策略，请运行以下命令：

   ```
   Set-CsVoicePolicy -Identity Site:Redmond1 -EnableBusyOptions $true
   ```

3. 接下来，运行[新建 CsServerApplication](https://docs.microsoft.com/powershell/module/skype/new-csserverapplication?view=skype-ps) cmdlet 将忙选项添加到下面的示例中所示的服务器应用程序的列表：

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/BusyOptions' -Uri https://www.microsoft.com/LCS/BusyOptions -Critical $False -Enabled $True -Priority (Get-CsServerApplication -Identity 'Service:Registrar:%FQDN%/UserServices').Priority
   ```

    > [!NOTE]
    > 您必须使用特定池的完全限定域名替换 %FQDN%。

4. 接下来，运行[Update-csadminrole](https://docs.microsoft.com/powershell/module/skype/update-csadminrole?view=skype-ps) cmdlet 更新下面的示例中所示的忙选项 cmdlet 的基于角色的访问控制 (RBAC) 角色：

   ```
   Update-CsAdminRole
   ```

5. 最后，其中忙选项已安装并启用通过运行[Start-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/start-cswindowsservice?view=skype-ps)命令的所有池的所有前端服务器上启动业务 Windows 服务器服务的 Skype:

   ```
   Start-CsWindowsService
   ```

## <a name="configure"></a>配置

若要配置忙选项，请使用[集 CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx) cmdlet。

例如，以下命令可配置用户“Ken Myer”的忙碌选项。在此配置中，当“Ken Myer”已接听电话时，向其发起的任何呼叫都将返回忙音：

```
Set-CsBusyOptions -Identity "Ken Myer"  -ActionType BusyOnBusy
```

在下一个示例中，该命令可配置用户“Chrystal Velasquez”的忙碌选项。在此配置中，当“Chrystal Velasquez”已接听电话时，向其发起的新传入呼叫都将转接到语言邮件。


```
Set-CsBusyOptions -Identity "Chrystal Velasquez" -ActionType VoicemailOnBusy
```

您可以通过使用[Get-CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx) cmdlet 检索有关忙选项的配置信息。 以下示例返回"KenMyer@Contoso.com"的忙选项设置：

```
Get-CsBusyOptions -Identity sip:KenMyer@Contoso.com
```

您可以通过使用[删除 CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx) cmdlet 删除忙选项。 以下命令将删除“Ken Myer”的忙碌选项。

```
Remove-CsBusyOptions -Identity "Ken Myer"
```

有关 cmdlet 用于配置忙选项的详细信息，请参阅[设置 CsBusyOptions](https://technet.microsoft.com/library/8ffbb832-3e55-4d6c-9a7c-5ce2df22de2e.aspx)、 [Get CsBusyOptions](https://technet.microsoft.com/library/ff0e3b1c-c41d-41e4-9468-0cb057aef9fb.aspx)，和[删除 CsBusyOptions](https://technet.microsoft.com/library/159e5931-10f1-4226-bcc4-38548f88f0d4.aspx)的技术参考内容。

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

安装后忙选项，可以验证已成功安装使用[Get-csserverapplication](https://docs.microsoft.com/powershell/module/skype/get-csserverapplication?view=skype-ps) cmdlet 检索服务器应用程序的列表。 如果忙碌选项已正确安装，该 cmdlet 的输出应显示忙碌选项配置，如下所示：

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

您还可以使用 Windows 事件查看器验证忙选项安装成功和 Skype 业务服务器成功加载忙选项。 若要验证忙选项，请打开**事件查看器-\>应用程序和服务日志-\> Skype （或 Lync） Server** ，然后搜索事件 ID = 30253。