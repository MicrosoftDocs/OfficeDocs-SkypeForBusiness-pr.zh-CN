---
title: Get-CsPool
TOCTitle: Get-CsPool
ms:assetid: e0911c68-9a0a-461a-88d6-c610c6cd996c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398992(v=OCS.15)
ms:contentKeyID: 49314500
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPool

 

_**上一次修改主题：** 2015-03-09_

返回有关 Lync Server 部署中使用的池的信息。池是指一个站点中全部运行一组相同 Lync Server 服务的计算机的集合。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsPool [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsPool [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Site <String>]

## 示例

## 示例 1

示例 1 返回在 Lync Server 部署中发现的所有池。

    Get-CsPool

## 示例 2

示例 2 显示有关在每个池中发现的计算机的详细信息。这是通过调用 **Get-CsPool** cmdlet 并将返回的数据通过管道传递到 **Select-Object** cmdlet 实现的。然后，ExpandProperty 参数用于“展开”Computers 属性的值。Computers 属性是表示池中每台计算机的一个对象数组。展开 Computers 属性时，将会返回有关其中每台计算机的详细信息。

    Get-CsPool | Select-Object -ExpandProperty Computers

## 示例 3

在示例 3 中，Identity 参数用于将返回的数据限制为 Identity 为 atl-cs-001.litwareinc.com 的池。

    Get-CsPool -Identity atl-cs-001.litwareinc.com

## 示例 4

示例 4 返回在 Redmond 站点中发现的所有池。为执行此操作，该命令使用了 Site 参数；参数值“Redmond”将返回的数据限制为 Site 属性等于 Redmond 的池。

    Get-CsPool -Site "Redmond"

## 示例 5

示例 5 中显示的命令返回没有安装任何 Lync Server 服务的所有池的集合。为了执行此任务，该命令首先调用不带任何参数的 **Get-CsPool** cmdlet；这将返回组织中当前使用的所有池的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者会挑选出 Services.Count 属性等于 0 的所有池。如果 Count 等于 0，则意味着没有为该池配置任何 Lync Server 服务。

    Get-CsPool | Where-Object {$_.Services.Count -eq 0}

## 详细说明

在 Lync Server 中，池是同一站点中运行同一组服务的一台或多台计算机。例如，如果 Redmond 站点中有一台服务器正在运行中介服务器服务，则您就拥有一个由该计算机组成的中介服务器池。如果 Redmond 站点中有两台计算机正在运行中介服务器，则您就拥有一个由两台计算机组成的中介服务器池。组织中使用的池数取决于您拥有的服务器数以及这些服务器运行的不同服务。

**Get-CsPool** cmdlet 用于检索有关组织中使用的每个池的信息，包括有关在这每个池中运行的服务的信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsPool** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins 和 RTCUniversalReadOnlyAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPool"}

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
<td><p>使您可以在指定要返回的池的 Identity 时使用通配符。例如，以下语法将返回 Identity 以字符串值“.fabrikam.com”结尾的所有池：-Filter &quot;*.fabrikam.com&quot;。</p>
<p>请注意，不能在同一个命令中同时使用 Filter 和 Identity 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要返回的池的完全限定域名 (FQDN)。例如：-Identity atl-cs-001.litwareinc.com。</p>
<p>如果此参数不存在，将会返回组织中的所有池。</p></td>
</tr>
<tr class="odd">
<td><p><em>Site</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>返回在指定站点中发现的所有池。应使用站点的 DisplayName（例如，Redmond）而不是站点 Identity（例如，site:Redmond）来引用相关站点。例如：-Site &quot;Redmond&quot;。可运行以下命令检索站点的显示名称：</p>
<p>Get-CsSite | Select-Object Identity, DisplayName</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsPool** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsPool** cmdlet 返回 Microsoft.Rtc.Management.Deploy.Internal.Cluster 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsSite](get-cssite.md)  
[Get-CsTopology](get-cstopology.md)

