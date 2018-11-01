---
title: Get-CsComputer
TOCTitle: Get-CsComputer
ms:assetid: 493931a9-1670-4a76-abba-7d3c7723d2e1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425959(v=OCS.15)
ms:contentKeyID: 49312745
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsComputer

 

_**上一次修改主题：** 2015-03-09_

返回有关在 Lync Server 基础结构中执行服务角色的计算机的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsComputer [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsComputer [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Local <SwitchParameter>] [-Pool <String>]

## 示例

## 示例 1

在示例 1 中，**Get-CsComputer** cmdlet 用于返回有关在 Lync Server 基础结构中执行服务角色的所有计算机的信息。

    Get-CsComputer

## 示例 2

示例 2 中显示的命令使用 Filter 参数，以便仅返回属于 litwareinc.com 域的服务角色计算机。通配符字符串 \*.litwareinc.com 将返回的信息限制为 FQDN 以字符串值“.litwareinc.com”结尾的计算机。

    Get-CsComputer -Filter "*.litwareinc.com"

## 示例 3

在示例 3 中，使用 Identity 参数将返回的数据限制为 FQDN 等于 atl-cs-001.litwareinc.com 的一台计算机。

    Get-CsComputer -Identity "atl-cs-001.litwareinc.com"

## 示例 4

在示例 4 中，Pool 参数用于返回在池 atl-cs-001.litwareinc.com 中找到的所有计算机的信息。

    Get-CsComputer -Pool "atl-cs-001.litwareinc.com"

## 详细说明

**Get-CsComputer** cmdlet 提供了一种方法，用于快速标识正在运行 Lync Server 服务或服务器角色的计算机。如果不带任何参数进行调用，**Get-CsComputer** cmdlet 将返回正在运行 Lync Server 服务或服务器角色的所有计算机的集合；此集合包括每台计算机的标识、池名称和完全限定域名 (FQDN)。此外，您也可以使用可选参数（如 Identity、Filter 或 Pool）将返回的数据限制为单台计算机或一组计算机。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsComputer** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins 和 RTCUniversalReadOnlyAdmins。

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
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您可以在指定要返回的计算机的 Identity 时使用通配符。例如，以下命令将返回有关 Identity 以字符串值“atl-”开头的所有计算机的信息：-Filter &quot;atl-*&quot;。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要返回的计算机的 FQDN。例如：-Identity &quot;atl-cs-001.litwareinc.com&quot;。</p>
<p>如果未指定此参数，将返回所有运行 Lync Server 的计算机。</p></td>
</tr>
<tr class="odd">
<td><p><em>Local</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>如果存在此参数，则只返回本地计算机的信息。</p></td>
</tr>
<tr class="even">
<td><p><em>Pool</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>Lync Server 池的 FQDN。使用此参数时，将返回有关指定池中所有计算机的信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsComputer** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsComputer** cmdlet 返回 Microsoft.Rtc.Management.Deploy.Internal.Machine 对象的实例。

## 另请参阅

#### 其他资源

[Disable-CsComputer](disable-cscomputer.md)  
[Enable-CsComputer](enable-cscomputer.md)  
[Test-CsComputer](test-cscomputer.md)

