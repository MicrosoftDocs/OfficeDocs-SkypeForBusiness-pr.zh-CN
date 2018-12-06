---
title: Get-CsNetworkInterface
TOCTitle: Get-CsNetworkInterface
ms:assetid: 06a5fedf-d87e-4469-9bd6-ad16c1f9a801
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398121(v=OCS.15)
ms:contentKeyID: 49311887
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsNetworkInterface

 

_**上一次修改主题：** 2015-03-09_

返回有关运行 Lync Server 服务或服务器角色的计算机上正在使用的网络接口的信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsNetworkInterface [-Identity <NetworkInterfaceIdentity>] <COMMON PARAMETERS>

    Get-CsNetworkInterface [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-ComputerFqdn <Fqdn>]

## 示例

## 示例 1

示例 1 返回配置为在组织中使用的所有网络接口的信息。

    Get-CsNetworkInterface

## 示例 2

示例 2 中显示的命令返回有关一个网络接口的信息：即 Identity 为 atl-cs-001.litwareinc.com.com/Primary/1 的接口。

    Get-CsNetworkInterface -Identity atl-cs-001.litwareinc.com/Primary/1

## 示例 3

示例 3 返回域 litwareinc.com 中所有网络接口的信息。为执行此操作，请包含 Filter 参数以及筛选器值“\*.litwareinc.com\*”。此筛选器值使返回的数据限于其 Identity 中含有字符串值“litwareinc.com”的接口。

    Get-CsNetworkInterface -Filter "*.litwareinc.com*"

## 示例 4

示例 4 返回有关为 IP 地址 192.168.0.240 配置的所有网络接口的信息。为执行此操作，该命令首先调用不带任何参数的 **Get-CsNetworkInterface** cmdlet，以返回配置为在组织中使用的所有网络接口的集合。然后，将该集合通过管道传递到 **Where-Object** cmdlet，后者将仅选取 IPAddress 属性等于 192.168.0.240 的那些接口。

    Get-CsNetworkInterface | Where-Object {$_.IPAddress -eq "192.168.0.240"}

## 示例 5

示例 5 中显示的命令是示例 4 中所示命令的一种变化形式；但在本例中，将返回为子网“192.168.0.\*”配置的所有网络接口的信息。为完成此任务，该命令检索所有网络接口的集合，将该集合通过管道传递到 **Where-Object** cmdlet，后者将仅选取 IPAddress 以字符串值“192.168.0.”开头的那些接口。

    Get-CsNetworkInterface | Where-Object {$_.IPAddress -like "192.168.0.*"}

## 示例 6

示例 6 返回已配置为进行外部访问的所有网络接口。为执行此操作，该命令首先调用不带任何参数的 **Get-CsNetworkInterface** cmdlet，以返回当前正在使用的所有网络接口的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅选择 Interface 属性等于 External 的那些项。

    Get-CsNetworkInterface | Where-Object {$_.Interface -eq "External"}

## 详细说明

要将信息从一台计算机传输到另一台计算机，计算机需要网络接口：也就是计算机与网络之间的连接。运行 Lync Server 服务或服务器角色的计算机必须至少有一个网络接口；否则，这些计算机将无法与其他计算机通信。但是，这些计算机也可以具备多个网络接口；例如，边缘服务器 可能会用一个接口连接到内部网络，用另一个接口连接到 Internet。**Get-CsNetworkInterface** cmdlet 提供一种方式，管理员通过此方式可返回有关运行 Lync Server 服务或服务器角色的计算机上当前正在使用的网络接口的信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsNetworkInterface** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsNetworkInterface"}

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
<td><p><em>ComputerFqdn</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>要返回其网络接口信息的计算机的 FQDN。例如，要返回计算机 atl-cs-001.litwareinc.com（以及仅限该计算机）的网络接口信息，请使用此语法：-ComputerFqdn atl-cs-001.litwareinc.com。</p></td>
</tr>
<tr class="even">
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您在指定要返回的网络接口时可使用通配符。例如，以下语法返回有关运行 Lync Server 服务或服务器角色的所有计算机上使用的 Primary 网络接口的信息：-Filter &quot;*/Primary/*&quot;。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.NetworkInterfaceIdentity</p></td>
<td><p>要返回的网络接口的唯一标识符。网络接口标识由以下三部分组成：</p>
<p>计算机自身的完全限定域名 (FQDN)（例如 atl-cs-001.litwareinc.com）。</p>
<p>网络接口所属的“端”（Primary、Internal、External、公用电话交换网）。端指示端口所用于的流量的类型。</p>
<p>该特定端的网络接口编号。</p>
<p>例如：-Identity &quot;atl-cs-001.litwareinc.com/Primary/1&quot;。</p>
<p>必须单独使用 Identity、ComputerFqdn 和 Filter 参数；例如，不能运行同时使用 ComputerFqdn 和 Identity 的命令。此外，指定 Identity 时不能使用通配符。要使用通配符，请使用 Filter 参数。</p>
<p>如果不使用 Identity、ComputerFqdn 和 Filter 参数中的任何一个，<strong>Get-CsNetworkInterface</strong> cmdlet 将返回有关运行 Lync Server 服务或服务器角色的计算机上当前正在使用的所有网络接口的信息。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsNetworkInterface** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsNetworkInterface** cmdlet 将返回 Microsoft.Rtc.Management.Xds.DisplayNetworkInterface 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsComputer](get-cscomputer.md)

