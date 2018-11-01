---
title: Get-CsConferencingConfiguration
TOCTitle: Get-CsConferencingConfiguration
ms:assetid: db4ab3bc-071c-4f73-a3a0-62dc8aed48a1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398965(v=OCS.15)
ms:contentKeyID: 49314454
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConferencingConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回有关组织的会议配置设置的信息。会议设置可确定诸如会议内容和讲义允许的最大大小、内容宽限期（即内容在被删除前存储的时间）以及用于内部和外部下载支持的客户端的 URL 等信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsConferencingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsConferencingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 返回有关组织中当前正在使用的所有会议配置设置的信息。这是通过调用不带任何参数的 **Get-CsConferencingConfiguration** cmdlet 来实现的。

    Get-CsConferencingConfiguration

## 示例 2

在示例 2 中，返回 Redmond 站点 (-Identity site:Redmond) 的会议配置信息。由于 Identitiy 必须唯一，因此此命令最多只会返回一个会议配置设置集合。

    Get-CsConferencingConfiguration -Identity site:Redmond

## 示例 3

示例 3 中显示的命令返回有关在站点范围应用的所有会议配置设置的信息。为执行此操作，调用带有 Filter 参数的 **Get-CsConferencingConfiguration** cmdlet，筛选器值“site:\*”确保仅返回 Identity 以字符串值“site:”开头的设置。

    Get-CsConferencingConfiguration -Filter "site:*"

## 示例 4

示例 4 返回有关未将 Organization 设置为 Litwareinc 的所有会议配置设置的信息。为完成此任务，该命令首先调用不带任何参数的 **Get-CsConferencingConfiguration** cmdlet，这将返回组织中使用的所有会议配置设置的集合。然后将生成的集合通过管道传递到 **Where-Object** cmdlet，后者将仅选择 Organization 属性不等于 Litwareinc 的设置。

    Get-CsConferencingConfiguration | Where-Object {$_.Organization -ne "Litwareinc"}

## 示例 5

在示例 5 中，仅返回有关最大内容存储空间大于 100 MB 的会议配置设置的信息。为执行此操作，该命令首先调用不带任何参数的 **Get-CsConferencingConfiguration** cmdlet，以返回所有会议配置设置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将挑选出内容存储空间大于 100 MB 的设置。

    Get-CsConferencingConfiguration | Where-Object {$_.MaxContentStorageMB -gt 100}

## 详细说明

对于会议，由两个 cmdlet 集分开进行管理。如果您要管理用户可否执行的操作（例如，用户可否邀请匿名与会者加入会议，是否允许用户在会议中提供应用程序共享，或是否允许用户在会议中传输文件），则需要使用 **CsConferencingPolicy** cmdlet。

除了用户活动外，管理员还需要管理 Lync Server Web 会议服务。例如，要求管理员能够执行诸如指定分配给单个会议的最大内容存储和指定自动删除会议内容之前的宽限期等操作。此外，还必须能够指定用于应用程序共享和文件传输等活动的端口。

可以使用 **CsConferencingConfiguration** cmdlet 管理后面的这些活动。通过这些 cmdlet，您可以管理实际服务器本身。**CsConferencingConfiguration** cmdlet（可应用于 global、site 和服务范围）不会用于指定用户是否可以在会议期间共享应用程序，但是，如果允许共享应用程序，则可通过这些 cmdlet 指示要用于该活动的端口。同样，通过这些 cmdlet，您也可以指定存储限制、有效期以及指向内部和外部 URL（用户可在其中获取会议帮助和资源）的指针等信息。

**Get-CsConferencingConfiguration** cmdlet 为管理员提供了一种返回有关组织中当前正在使用的所有会议配置设置的信息的方法。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsConferencingConfiguration** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsConferencingConfiguration"}

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
<td><p>使您在指定要返回的会议配置设置的 Identity 时可使用通配符。例如，以下语法返回在站点范围配置的所有设置：-Filter &quot;site:*&quot;。此语法可返回在服务范围配置的所有设置：-Filter &quot;service:*&quot;。</p>
<p>请注意，不能在同一命令中同时使用 Identity 和 Filter 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要检索的会议配置设置集合的唯一标识符。要检索全局设置，请使用以下语法：-Identity global。要检索在站点范围配置的设置，请使用类似如下的语法：-Identity &quot;site:Redmond&quot;。要检索在服务范围配置的设置，请使用类似如下的语法：-Identity &quot;service:ConferencingServer:atl-cs-001.litwareinc.com&quot;。</p>
<p>如果不包含此参数，则 <strong>Get-CsConferencingConfiguration</strong> cmdlet 将返回组织中当前正在使用的所有会议配置设置。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索会议配置数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsConferencingConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsConferencingConfiguration** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConfSettings 对象的实例。

## 另请参阅

#### 其他资源

[New-CsConferencingConfiguration](new-csconferencingconfiguration.md)  
[Remove-CsConferencingConfiguration](remove-csconferencingconfiguration.md)  
[Set-CsConferencingConfiguration](set-csconferencingconfiguration.md)

