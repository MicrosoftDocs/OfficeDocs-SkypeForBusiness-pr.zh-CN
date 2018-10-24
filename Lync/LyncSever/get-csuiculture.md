---
title: Get-CsUICulture
TOCTitle: Get-CsUICulture
ms:assetid: b8df7083-068b-4d5e-a9b4-448602de6586
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412900(v=OCS.15)
ms:contentKeyID: 49314062
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsUICulture

 

_**上一次修改主题：** 2015-03-09_

Returns information about the culture (that is, the language and regional settings) used by the Lync Server 命令行管理程序. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsUICulture

## Examples

## EXAMPLE 1

The command shown in Example 1 returns basic information about the culture currently in use by the Lync Server 命令行管理程序.

    Get-CsUICulture

## Detailed Description

Although Lync Server is available in multiple languages, the software is not a true MUI (multilingual user interface) application. Among other things, this means that the user interface for the Lync Server 命令行管理程序 does not change languages any time you change the operating system language. For example, suppose you have installed the U.S. English version of Lync Server and are also running the Windows operating system under U.S. English. If you change the operating system culture (that is, the language and regional settings) to Danish, the Lync Server 命令行管理程序 will not automatically follow suit; instead, the Lync Server 命令行管理程序 user interface (including error messages and help text) will remain in U.S. English. If you need to change the culture for the Lync Server 命令行管理程序, you must run the **Set-CsUICulture** cmdlet.

The **Get-CsUICulture** cmdlet provides a way for you to determine the culture currently used in the Lync Server 命令行管理程序.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsUICulture** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins, RTCUniversalReadOnlyAdmins.

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
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>This cmdlet provides only common Windows PowerShell parameters.</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsUICulture** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsUICulture** cmdlet returns instances of the System.Globalization.CultureInfo class.

## 另请参阅

#### 其他资源

[Set-CsUICulture](set-csuiculture.md)

