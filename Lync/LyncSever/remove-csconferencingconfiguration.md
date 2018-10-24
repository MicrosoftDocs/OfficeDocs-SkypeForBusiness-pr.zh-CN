---
title: Remove-CsConferencingConfiguration
TOCTitle: Remove-CsConferencingConfiguration
ms:assetid: a3dff4b0-100b-46fa-9078-d3b0d4914d87
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412767(v=OCS.15)
ms:contentKeyID: 49313818
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsConferencingConfiguration

 

_**上一次修改主题：** 2015-03-09_

删除指定的会议配置设置的集合。会议设置可确定诸如会议内容和讲义允许的最大大小、内容宽限期，以及用于内部和外部下载支持的客户端的 URL 等信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsConferencingConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 删除应用于 Redmond 站点的会议配置设置。删除此类站点设置时，站点中的用户将自动继承全局会议配置设置中包含的设置。

    Remove-CsConferencingConfiguration -Identity site:Redmond

## 示例 2

在示例 2 中，此命令删除所有应用于站点范围的会议配置设置。为执行此操作，该命令首先调用带有 Filter 参数的 **Get-CsConferencingConfiguration** cmdlet，筛选器值“site:”可确保仅返回 Identity 以字符“site:”开头的设置。然后，将筛选出的集合通过管道传递到 **Remove-CsConferencingConfiguration** cmdlet，后者将删除集合中的每一项。

    Get-CsConferencingConfiguration -Filter site:* | Remove-CsConferencingConfiguration

## 示例 3

示例 3 删除未将组织设置为 Litwareinc 的所有会议配置设置。为执行此操作，该命令首先调用不带任何参数的 **Get-CsConferencingConfiguration** cmdlet，以返回在组织中使用的所有会议配置设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，该 cmdlet 将仅挑选出 Organization 属性不等于 Litwareinc 的设置。最后，将筛选出的集合通过管道传递到 **Remove-CsConferencingConfiguration** cmdlet，后者会删除集合中的所有设置。

    Get-CsConferencingConfiguration | Where-Object {$_.Organization -ne "Litwareinc"} | Remove-CsConferencingConfiguration

## 详细说明

对于会议，由两个 cmdlet 集分开进行管理。如果您要管理用户可否执行的操作（例如，用户可否邀请匿名与会者加入会议，是否允许用户在会议中提供应用程序共享，是否允许用户在会议中传输文件），则需要使用 **CsConferencingPolicy** cmdlet。

除了用户活动外，管理员还需要管理 Web 会议服务。例如，要求管理员能够执行诸如指定分配给单个会议的最大内容存储和指定自动删除会议内容之前的宽限期等操作。此外，还必须能够指定用于应用程序共享和文件传输等活动的端口。

可以使用 **CsConferencingConfiguration** cmdlet 管理后面的这些活动。通过这些 cmdlet，您可以管理实际服务器本身。**CsConferencingConfiguration** cmdlet（可应用于 global、site 和服务范围）不会用于指定用户是否可以在会议期间共享应用程序，但是，如果允许共享应用程序，则可通过这些 cmdlet 指示要用于该活动的端口。同样，通过这些 cmdlet，您也可以指定存储限制、有效期以及指向内部和外部 URL（用户可在其中获取会议帮助和资源）的指针等信息。

**Remove-CsConferencingConfiguration** cmdlet 提供了一种删除任何创建为在组织中使用的会议配置设置的自定义集合的方法。删除设置集合时，先前受这些设置影响的任何服务器都会自动出现在层次结构（service – site – 范围）中下一个集合区域的下面。如果删除了在服务范围应用的设置，则服务器将由站点设置管理。如果在站点范围没有设置，则服务器将由全局设置管理。同样，如果删除站点范围的设置，则先前由这些站点设置管理的服务器将由全局设置管理。

请注意，您也可以针对全局设置运行 **Remove-CsConferencingConfiguration** cmdlet。但是在这种情况下，将不会删除全局设置，原因是 Lync Server 不允许您删除全局设置。全局集合中的所有属性都将重置为其默认值。例如，如果您之前已将最大内容存储的值更改为 200 MB，则此属性将恢复为默认值（100 MB）。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsConferencingConfiguration** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsConferencingConfiguration"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要删除的会议配置设置集合的唯一标识符。要删除在站点范围配置的设置，请使用以下类似语法：-Identity &quot;site:Redmond&quot;。要删除在服务范围配置的设置，请使用类似如下的语法：-Identity &quot;service:ConferencingServer:atl-cs-001.litwareinc.com&quot;。</p>
<p><strong>Remove-CsConferencingConfiguration</strong> cmdlet 也可以针对全局设置运行。但是，在这种情况下，不会删除这些设置，而只会将所有属性重置为其默认值。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConfSettings 对象。**Remove-CsConferencingConfiguration** cmdlet 接受通过管道传递的会议配置对象的实例。

## 返回类型

无。但 **Remove-CsConferencingConfiguration** cmdlet 会删除 Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConfSettings 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsConferencingConfiguration](get-csconferencingconfiguration.md)  
[New-CsConferencingConfiguration](new-csconferencingconfiguration.md)  
[Set-CsConferencingConfiguration](set-csconferencingconfiguration.md)

