---
title: Set-CsUnassignedNumber
TOCTitle: Set-CsUnassignedNumber
ms:assetid: e7f52423-58d1-410a-9071-731bde45d3d4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399033(v=OCS.15)
ms:contentKeyID: 49314594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsUnassignedNumber

 

_**上一次修改主题：** 2015-03-09_

修改现有的未分配的号码范围和应用于这些号码的路由规则。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsUnassignedNumber [-Identity <XdsGlobalRelativeIdentity>] [-Instance <PSObject>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] <COMMON PARAMETERS>

    Set-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <String> [-Identity <XdsGlobalRelativeIdentity>] [-Instance <PSObject>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] <COMMON PARAMETERS>

    Set-CsUnassignedNumber -AnnouncementName <String> -AnnouncementService <String> [-Identity <XdsGlobalRelativeIdentity>] [-Instance <PSObject>] [-NumberRangeEnd <String>] [-NumberRangeStart <String>] <COMMON PARAMETERS>

    Set-CsUnassignedNumber [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Priority <Int32>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

此示例修改名称为 UNSet1 的未分配号码范围。首先向 Identity 参数传递值 UNSet1，即要修改的未分配号码范围的名称。然后使用 NumberRangeStart (+14255551000) 和 NumberRangeEnd (+14255551900) 参数修改将对其应用指定通知或自动助理的未分配号码范围。

    Set-CsUnassignedNumber -Identity UNSet1 -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## 示例 2

此示例修改所有未分配号码范围设置的通知，这些设置当前具有一个其名称中包含字符串“Welcome”的通知。首先调用 **Get-CsUnassignedNumber** cmdlet 检索所有未分配号码设置。然后，将该设置集合通过管道传递到 **Where-Object** cmdlet，后者将该集合的范围缩小为仅限 AnnouncementName 属性包含 (-match) 字符串 Welcome 的设置。获得这些设置后，将它们通过管道传递到 **Set-CsUnassignedNumber** cmdlet，后者使用 AnnouncementService 参数修改通知服务的应用程序服务器 ID (ApplicationServer:redmond.litwareinc.com)，并使用 AnnouncementName 参数修改新通知的名称 (Help Desk Announcement)。请注意，即使新通知具有不同的名称但有相同的服务 ID，您在指定名称时仍必须指定服务 ID。

    Get-CsUnassignedNumber | Where-Object {$_.AnnouncementName -match "Welcome"} | Set-CsUnassignedNumber -AnnouncementService ApplicationServer:redmond.litwareinc.com -AnnouncementName "Help Desk Announcement"

## 详细说明

未分配的号码是指已分配给组织但尚未分配给特定用户或电话的电话号码。当呼叫未分配的号码时，可设置 Lync Server 将呼叫路由至相应目标。此 cmdlet 可修改定义该路由的设置。

为了使用此 cmdlet 修改某些设置，您的系统必须已定义了通知或设置了 Exchange UM 自动助理。若要确定您是否具有通知，请调用 **Get-CsAnnouncement** cmdlet。若要创建新的通知，请调用 **New-CsAnnouncement** cmdlet。若要检查 Exchange UM 自动助理设置，请运行 **Get-CsExUmContact** cmdlet。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Set-CsUnassignedNumber** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsUnassignedNumber"}

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
<td><p><em>AnnouncementName</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>要用于处理对此号码范围的呼叫的通知的名称。</p></td>
</tr>
<tr class="even">
<td><p><em>AnnouncementService</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>通知服务器的完全限定域名 (FQDN) 或服务 ID。</p></td>
</tr>
<tr class="odd">
<td><p><em>ExUmAutoAttendantPhoneNumber</em></p></td>
<td><p>必需</p></td>
<td><p>String</p></td>
<td><p>要将此范围内的呼叫路由到的 Exchange UM 自动助理的电话号码。必须已设置 Exchange UM 自动助理联系人以便为此参数分配值。</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>XdsGlobalRelativeIdentity</p></td>
<td><p>要修改的未分配号码范围的唯一名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>DisplayAnnouncementVacantNumberRange</p></td>
<td><p>对包含未分配号码设置的对象的引用。此对象的类型必须为 Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange，可通过调用 <strong>Get-CsUnassignedNumber</strong> cmdlet 进行检索。</p></td>
</tr>
<tr class="even">
<td><p><em>NumberRangeEnd</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>未分配号码范围的最后一个号码。必须大于等于为 NumberRangeStart 提供的号码。要指定一个号码的范围，请对 NumberRangeStart 和 NumberRangeEnd 使用相同的号码。</p>
<p>此号码必须符合正则表达式 (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?。这意味着此号码可能以字符串 tel:（如果没有指定此字符串，将自动为您添加）、加号 (+) 以及一个 1 到 9 之间的数字开头。电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</p></td>
</tr>
<tr class="odd">
<td><p><em>NumberRangeStart</em></p></td>
<td><p>可选</p></td>
<td><p>String</p></td>
<td><p>未分配号码范围中的第一个号码。必须小于等于为 NumberRangeEnd 提供的值。</p>
<p>此号码必须符合正则表达式 (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?。这意味着此号码可能以字符串 tel:（如果没有指定此字符串，将自动为您添加）、加号 (+) 以及一个 1 到 9 之间的数字开头。电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</p></td>
</tr>
<tr class="even">
<td><p><em>Priority</em></p></td>
<td><p>可选</p></td>
<td><p>Int32</p></td>
<td><p>未分配号码的范围有可能重叠。如果一个号码可以划分在多个范围内，则具有最高优先级的范围生效。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange 对象。接受通过管道传递的未分配号码对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会修改一个类型为 Microsoft.Rtc.Management.Voice.Helpers.DisplayAnnouncementVacantNumberRange 的对象。

## 另请参阅

#### 其他资源

[New-CsUnassignedNumber](new-csunassignednumber.md)  
[Remove-CsUnassignedNumber](remove-csunassignednumber.md)  
[Get-CsUnassignedNumber](get-csunassignednumber.md)  
[New-CsAnnouncement](new-csannouncement.md)  
[Get-CsAnnouncement](get-csannouncement.md)  
[Get-CsExUmContact](get-csexumcontact.md)

