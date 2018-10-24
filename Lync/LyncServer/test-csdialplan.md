---
title: Test-CsDialPlan
TOCTitle: Test-CsDialPlan
ms:assetid: e6618394-82c5-4bc2-85cc-97ac4686a1aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399024(v=OCS.15)
ms:contentKeyID: 49314574
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test-CsDialPlan

 

_**上一次修改主题：** 2015-03-09_

针对拨号计划（以前称为位置配置文件）测试一个电话号码，返回将应用于该号码的规范化规则，以及应用该规范化规则后的转换号码。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Test-CsDialPlan -DialedNumber <PhoneNumber> -Dialplan <LocationProfile>

## 示例

## 示例 1

此示例针对 Identity 为 site:Redmond 的拨号计划运行测试。首先，运行 **Get-CsDialPlan** cmdlet，以检索 Identity 为 site:Redmond 的拨号计划。然后，将该拨号计划对象通过管道传递到 **Test-CsDialPlan** cmdlet，后者将针对电话号码 14255559999 测试该拨号计划。输出结果为应用具有匹配模式的语音规范化规则后的 DialedNumber。如果站点内有多个具有匹配模式的规范化规则，则应用 Priority 值最低的规则。如果没有任何规则具有匹配 DialedNumber 值的模式（例如，规范化规则匹配 11 位号码的模式，而您提供的号码为 7 位），则不会返回任何值。

此命令的输出包括一个电话号码和一个规范化规则。规范化规则具有很多属性，默认情况下，将用省略号 (...) 将此输出截断。为了查看返回的语音规范化规则的所有属性和值，在将该输出显示在屏幕上之前，先将其通过管道传递到 **Format-List** cmdlet。这样将分行列出电话号码和规范化规则，规范化规则的属性和值将根据屏幕大小自动换行。

    Get-CsDialPlan -Identity site:Redmond | Test-CsDialPlan -DialedNumber 14255559999 | Format-List

## 示例 2

示例 2 与示例 1 相同，但不是将 Get 操作的结果直接通过管道传递到 **Test-CsDialPlan** cmdlet，而是先将此对象存储在变量 $a 中，然后作为参数 DialPlan 的值传入，用作针对其运行测试的拨号计划。

与在示例 1 中一样，此命令最后将输出通过管道传递到 **Format-List** cmdlet，以便我们能够看到更多有关此语音规范化规则的信息，而不仅仅是默认显示的那些信息。

    $a = Get-CsDialPlan -Identity site:Redmond
    Test-CsDialPlan -DialedNumber 14255559999 -Dialplan $a | Format-List

## 示例 3

此示例针对 Lync Server 部署中定义的所有拨号计划运行拨号计划测试。首先，运行 **Get-CsDialPlan** cmdlet（无参数），以检索所有拨号计划。然后，将返回的拨号计划集合通过管道传递到 **Test-CsDialPlan** cmdlet，后者将针对电话号码 2065559999 测试集合中的每个拨号计划。输出结果为转换后的号码及应用的语音规范化规则的列表（集合中的每个拨号计划对应一个列表）。如果某个拨号计划内没有任何语音规范化规则应用于特定拨号计划的 DialedNumber 值（例如，规范化规则匹配 11 位号码的模式，而提供的电话号码为 7 位），则该拨号计划对应的列表中将包含一个空行。

默认情况下，输出将截断已经应用的语音规范化规则的完整显示。在示例 1 和示例 2 中，我们可以将测试结果通过管道传递到 **Format-List** cmdlet 以查看完整的输出。在此示例中，我们将输出通过管道传递到 **Format-Table** cmdlet，并包含 Wrap 参数。这将按表格式显示每个条目（一列为转换后的号码，一列为所应用的语音规范化规则），但是，该命令将输出设置为自动换行，因此，规范化规则将在其所在列中自动换行。

    Get-CsDialPlan | Test-CsDialPlan -DialedNumber 2065559999 | Format-Table -Wrap

## 详细说明

通过此 cmdlet 可以查看将某个拨号计划应用于给定电话号码的结果。拨号计划提供了企业语音用户进行电话呼叫所需的信息，包括如何应用规范化规则。给定一个已拨电话和拨号计划，此 cmdlet 将验证应用该拨号计划中的哪个规范化规则以及转换后的号码是什么。

可以使用此 cmdlet 解决号码转换的相关问题或验证针对特定号码应用规则的情况。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Test-CsDialPlan** cmdlet：RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Test-CsDialPlan"}

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
<td><p><em>DialedNumber</em></p></td>
<td><p>必需</p></td>
<td><p>PhoneNumber</p></td>
<td><p>要针对其测试 Dialplan 参数中指定的拨号计划的电话号码。</p>
<p>完整数据类型：Microsoft.Rtc.Management.Voice.PhoneNumber</p></td>
</tr>
<tr class="even">
<td><p><em>Dialplan</em></p></td>
<td><p>必需</p></td>
<td><p>LocationProfile</p></td>
<td><p>一个包含对拨号计划的引用的对象，该拨号计划是要针对其测试 DialedNumber 参数中指定的号码的拨号计划。</p>
<p>完整数据类型：Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile</p></td>
</tr>
</tbody>
</table>


## 输入类型

Microsoft.Rtc.Management.WritableConfig.Policy.Voice.LocationProfile 对象。接受通过管道传递的拨号计划对象的输入。

## 返回类型

返回一个类型为 Microsoft.Rtc.Management.Voice.LocationProfileTestResult 的对象。

## 另请参阅

#### 其他资源

[New-CsDialPlan](new-csdialplan.md)  
[Remove-CsDialPlan](remove-csdialplan.md)  
[Set-CsDialPlan](set-csdialplan.md)  
[Get-CsDialPlan](get-csdialplan.md)  
[Grant-CsDialPlan](grant-csdialplan.md)

