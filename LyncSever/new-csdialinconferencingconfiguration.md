---
title: New-CsDialInConferencingConfiguration
TOCTitle: New-CsDialInConferencingConfiguration
ms:assetid: ac0b6e22-3883-4884-aa94-18f4029c7f1e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412816(v=OCS.15)
ms:contentKeyID: 49313929
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsDialInConferencingConfiguration

 

_**上一次修改主题：** 2015-03-09_

创建新的电话拨入式会议配置设置集合。这些设置确定当用户加入或离开电话拨入式会议时 Lync Server 如何响应。特别是，返回有关是否要求参会者在加入会议时记录其姓名的信息，以及系统如何（甚至是否）通知某人已加入或退出呼叫的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsDialInConferencingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-EnableNameRecording <$true | $false>] [-EntryExitAnnouncementsEnabledByDefault <$true | $false>] [-EntryExitAnnouncementsType <UseNames | ToneOnly>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令创建一个新的应用于 Redmond 站点的电话拨入式会议配置设置集合。此外，还包含可选参数 EnableNameRecording，以便将 EnableNameRecording 属性设置为 False。

    New-CSDialInConferencingConfiguration -Identity site:Redmond -EnableNameRecording $False

## 示例 2

在示例 2 中，使用 InMemory 参数创建新的电话拨入式会议配置设置集合，该集合最初仅存在于内存中。为执行此操作，本示例首先调用 **New-CSDialInConferencingConfiguration** cmdlet 和 InMemory 参数以创建一个存储在变量 $x 中的虚拟设置集合（请注意，为此集合指定的 Identity 为 site:Redmond）。在创建该虚拟集合之后，第 2 行用于修改 EnableNameRecording 属性的值。最后，示例中的第 3 行调用 **Set-CSDialInConferencingConfiguration** cmdlet，将存储在 $x 中的虚拟配置设置转换为应用于 Redmond 站点的一个实际设置集合。

    $x = New-CSDialInConferencingConfiguration -Identity site:Redmond -InMemory
    $x.EnableNameRecording = $False
    Set-CSDialInConferencingConfiguration -Instance $x

## 详细说明

当用户加入（或离开）电话拨入式会议时，Lync Server 可以不同方式响应。例如，可能会要求参与者先记录自己的姓名，然后才能进入会议。同样，管理员可以决定其是否希望让 Lync Server 通知电话拨入参与者已离开或已加入会议。

这些会议“加入行为”使用电话拨入式会议配置设置进行管理；可在全局范围或站点范围配置这些设置。（在站点范围配置的设置的优先级比在全局范围配置的设置高。）首次安装 Lync Server 时，您将拥有的电话拨入式会议配置设置只包括那些在全局范围配置的设置；但是，可以使用 **New-CSDialInConferencingConfiguration** cmdlet 在站点范围创建新设置。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **New-CsDialInConferencingConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsDialInConferencingConfiguration"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>是否必需</th>
<th>类型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>必需</p></td>
<td><p>XdsIdentity</p></td>
<td><p>指示要创建的电话拨入式会议配置设置的标识。由于这些设置只能在站点范围创建，因此请使用类似如下的语法，前缀“site:”后跟站点的名称：-Identity site:Redmond。</p>
<p>请注意，每个站点只能有一组电话拨入式会议配置设置。如果已存在 Identity 为 site:Redmond 的设置集合，此示例命令将失败。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableNameRecording</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>确定在用户进入会议之前是否要求用户记录其姓名。设置为 True ($True) 将要求进行姓名记录；设置为 False ($False) 将绕过姓名记录。默认值为 True。</p></td>
</tr>
<tr class="even">
<td><p><em>EntryExitAnnouncementsEnabledByDefault</em></p></td>
<td><p>可选</p></td>
<td><p>Boolean</p></td>
<td><p>如果设置为 True，则每次参会者进入或退出会议时将播放通知。如果设置为 False（默认值），则不会播放进入和退出通知。</p></td>
</tr>
<tr class="odd">
<td><p><em>EntryExitAnnouncementsType</em></p></td>
<td><p>可选</p></td>
<td><p>EntryExitAnnouncementsType</p></td>
<td><p>指示每次参会者进入或离开会议时系统采取的操作。有效值是：</p>
<p>UseNames。每次用户加入或离开会议时，将通知用户的姓名（例如“Ken Myer 正在退出会议”）。</p>
<p>ToneOnly。每次参会者进入或离开会议时播放声音。</p>
<p>默认值为 UseNames。请注意，只有将 EntryExitAnnouncementsEnabledByDefault 属性设置为 True 时，才会播放通知。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**New-CsDialInConferencingConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

创建 Microsoft.Rtc.Management.WritableConfig.Settings.DialInConferencingSettings.DialInConferencingConfiguration 对象的新实例。

## 另请参阅

#### 其他资源

[Get-CsDialInConferencingConfiguration](get-csdialinconferencingconfiguration.md)  
[Remove-CsDialInConferencingConfiguration](remove-csdialinconferencingconfiguration.md)  
[Set-CsDialInConferencingConfiguration](set-csdialinconferencingconfiguration.md)

