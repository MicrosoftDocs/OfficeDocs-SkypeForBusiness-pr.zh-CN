---
title: Remove-CsCallParkOrbit
TOCTitle: Remove-CsCallParkOrbit
ms:assetid: b8e7c236-f8de-45bd-966b-60c815b37aed
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412901(v=OCS.15)
ms:contentKeyID: 49314038
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsCallParkOrbit

 

_**上一次修改主题：** 2015-03-09_

删除特定的呼叫寄存轨道范围。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsCallParkOrbit -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## 示例

## 示例 1

在此示例中，使用 **Remove-CsCallParkOrbit** cmdlet 删除名称为 Redmond CPO 1 的呼叫寄存轨道范围。

    Remove-CsCallParkOrbit -Identity "Redmond CPO 1"

## 示例 2

此示例中的命令删除为某个组织定义的所有呼叫寄存轨道范围。此命令首先调用不带任何参数的 **Get-CsCallParkOrbit** cmdlet，以检索已定义的所有呼叫寄存轨道范围。然后将该呼叫寄存轨道范围集合通过管道传递到 **Remove-CsCallParkOrbit** cmdlet，该 cmdlet 将删除每个呼叫寄存轨道。

    Get-CsCallParkOrbit | Remove-CsCallParkOrbit

## 示例 3

此命令删除标识中包含字符串“Redmond”（如“Redmond 501”、“CP Redmond 1”和“ARedmond”）的所有呼叫寄存轨道范围。此命令首先调用带有 Filter 参数的 **Get-CsCallParkOrbit** cmdlet，以检索 Identity 中包含字符串“Redmond”的所有呼叫寄存轨道范围。此集合将通过管道传递到 **Remove-CsCallParkOrbit** cmdlet，后者将删除集合中的所有项目。

    Get-CsCallParkOrbit -Filter *Redmond* | Remove-CsCallParkOrbit

## 详细说明

**Remove-CsCallParkOrbit** cmdlet 可用于删除具有传递到 Identity 参数（必需参数）的名称的呼叫寄存轨道范围。组织内的每个呼叫寄存轨道都必须具有唯一的号码范围。删除某个呼叫寄存轨道将释放此呼叫寄存轨道覆盖的范围。释放的号码可用于新定义的呼叫寄存轨道。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Remove-CsCallParkOrbit** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsCallParkOrbit"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>呼叫寄存轨道范围的名称。该名称由管理员在定义呼叫寄存轨道范围时指定。</p></td>
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
<td><p>禁止显示在进行更改前本该显示的任何确认提示。</p></td>
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

Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit 对象。接受通过管道传递的呼叫寄存轨道对象的输入。

## 返回类型

此 cmdlet 不会返回值。它会删除一个类型为 Microsoft.Rtc.Management.Voice.Helpers.DisplayCallParkOrbit 的对象。

## 另请参阅

#### 其他资源

[New-CsCallParkOrbit](new-cscallparkorbit.md)  
[Set-CsCallParkOrbit](set-cscallparkorbit.md)  
[Get-CsCallParkOrbit](get-cscallparkorbit.md)

