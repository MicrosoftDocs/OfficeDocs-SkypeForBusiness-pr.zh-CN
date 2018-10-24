---
title: Set-CsConferenceDisclaimer
TOCTitle: Set-CsConferenceDisclaimer
ms:assetid: 97afce6d-b031-466d-a170-3ca50d6df245
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398776(v=OCS.15)
ms:contentKeyID: 49313676
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsConferenceDisclaimer

 

_**上一次修改主题：** 2015-03-09_

修改组织中使用的会议免责声明的属性值。会议免责声明是向通过使用超链接（例如，通过将指向会议的链接粘贴到诸如 Windows Internet Explorer 等浏览器中）加入会议的用户显示的消息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsConferenceDisclaimer [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsConferenceDisclaimer [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Body <String>] [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Header <String>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

示例 1 中显示的命令修改您组织的会议免责声明的 Header 和 Body 属性。由于您只能拥有一个此类免责声明，因此运行 **Set-CsConferenceDisclaimer** cmdlet 时不需要指定 Identity。

    Set-CsConferenceDisclaimer -Header "Litwareinc.com Online Conference" -Body "Important note: Conferencing proceedings are recorded and archived."

## 详细说明

在配置会议设置时，管理员可以包括法律免责声明，以在参与者加入由 Lync Server 托管的会议时向这些人员显示。此免责声明通常用于说明与会议相关的法律和知识产权法。如果用户不同意免责声明中规定的条款，将无法加入会议。但请注意，此免责声明仅向使用超链接加入会议的用户显示。

Lync Server 允许使用一个会议免责声明全局实例。通过 **Set-CsConferenceDisclaimer** cmdlet，您可以修改组织中使用的会议免责声明。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsConferenceDisclaimer** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsConferenceDisclaimer"}

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
<td><p><em>Body</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>会议免责声明的内容。</p></td>
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
<td><p><em>Header</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>会议免责声明的标题。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>会议免责声明的唯一标识。由于您只能拥有会议免责声明的单个全局实例，因此调用 <strong>Set-CsConferenceDisclaimer</strong> cmdlet 时不需要指定 Identity。然而，您可以使用以下语法引用全局免责声明：-Identity global。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>会议免责声明对象</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer 对象。**Set-CsConferenceDisclaimer** cmdlet 接受通过管道传递的会议免责声明对象的输入。

## 返回类型

**Set-CsConferenceDisclaimer** cmdlet 不会返回任何对象或值。此 cmdlet 会修改 Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsConferenceDisclaimer](get-csconferencedisclaimer.md)  
[Remove-CsConferenceDisclaimer](remove-csconferencedisclaimer.md)

