---
title: Get-CsConferenceDirectory
TOCTitle: Get-CsConferenceDirectory
ms:assetid: 2b7927ab-c6b3-42ce-9c27-9825cd47fd77
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425771(v=OCS.15)
ms:contentKeyID: 49312339
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConferenceDirectory

 

_**上一次修改主题：** 2015-03-09_

返回有关配置为在组织中使用的会议目录的信息。会议目录用于帮助电话拨入式会议用户查找会议信息。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsConferenceDirectory [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Get-CsConferenceDirectory [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 中显示的命令返回有关配置为在组织中使用的所有会议目录的信息。

    Get-CsConferenceDirectory

## 示例 2

示例 2 返回有关 Identity 为 2 的会议目录的信息。由于标识必须唯一，因此此命令将始终不会返回多个会议目录。

    Get-CsConferenceDirectory -Identity 2

## 示例 3

示例 3 返回服务 UserServer:atl-cs-001.litwareinc.com 上托管的所有会议目录。为此，该命令首先调用不带任何参数的 **Get-CsConferenceDirectory** cmdlet，以返回在组织中找到的所有会议目录的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅选择 ServiceID 与字符串值“UserServer:atl-cs-001.litwareinc.com”匹配的目录。

    Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "UserServer:atl-cs-001.litwareinc.com"}

## 详细说明

在创建电话拨入式会议统一资源标识符 (URI) 时，将会为这些 URI 分配唯一的 SIP 地址。但是，对于无法识别 SIP 的设备，很难转换 SIP 地址；例如，公用电话交换网 (PSTN) 电话无法转换 SIP 地址。因此，Lync Server 使用会议目录作为一种方法，以帮助这些设备查找并连接到电话拨入式会议。这一点是通过创建与每个电话拨入式会议 URI 关联且由整数值而非 SIP URI 标识的 SIP 会议目录实现的。PSTN 电话和其他设备可在连接会议时使用这些数字（而非 SIP URI）；用户在连接电话拨入式会议时输入的 PSTN 会议标识中即包括目录编号。

通过 **Get-CsConferenceDirectory** cmdlet 可返回有关配置为在组织中使用的所有会议目录的信息。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsConferenceDirectory** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsConferenceDirectory"}

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
<td><p>使您可使用通配符指定要检索的会议目录的 Identity。由于目录的 Identity 为数值型，因此此参数可能取最小值。但是，此语法将返回 Identity 以数字 3 开头的所有会议目录：-Filter &quot;3*&quot;。</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要返回的会议目录的数字标识符（例如 7）。如果省略此参数，<strong>Get-CsConferenceDirectory</strong> cmdlet 将返回有关组织中正在使用的所有会议目录的信息。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索会议目录数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsConferenceDirectory** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsConferenceDirectory** cmdlet 将返回 Microsoft.Rtc.Management.WritableConfig.Settings.PstnConf.ConferenceDirectories 对象的实例。

## 另请参阅

#### 其他资源

[Move-CsConferenceDirectory](move-csconferencedirectory.md)  
[New-CsConferenceDirectory](new-csconferencedirectory.md)  
[Remove-CsConferenceDirectory](remove-csconferencedirectory.md)

