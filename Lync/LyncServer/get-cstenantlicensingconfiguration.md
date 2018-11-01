---
title: Get-CsTenantLicensingConfiguration
TOCTitle: Get-CsTenantLicensingConfiguration
ms:assetid: 0df23143-f1aa-4850-b0f7-750422762925
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362770(v=OCS.15)
ms:contentKeyID: 56271126
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantLicensingConfiguration

 

_**上一次修改主题：** 2015-03-09_

指明指定租户的授权信息是否在 Lync 管理中心中可用。

此 cmdlet 只能与 Lync Online 一起使用。

## 语法

    Get-CsTenantLicensingConfiguration [-Filter] <Object>] [-Identity] <Object>] [-Tenant] <Object>] [-LocalStore]

## 详细说明

Get-CsTenantLicensingConfiguration cmdlet 指明指定租户的授权信息是否在 Lync 管理中心中可用。该 cmdlet 将返回以下类似信息：

Identity : Global  
Status : Enabled

如果 Status 等于 Enabled，则授权信息在 Lync 管理中心中可用。如果不，则授权信息在 Lync 管理中心中不可用。

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
<th>必需</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Filter</strong></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您能够使用通配符，以便返回租户授权配置设置的集合。由于每个租户限制为授权配置设置的单个全局集合，无需使用 Filter 参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>Identity</strong></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>指定要返回的租户授权配置设置的集合。由于每个租户限制为单个授权设置全局集合，在调用 Get-CsTenantLicensingConfiguration cmdlet 时无需包括此参数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LocalStore</strong></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本中检索租户授权配置数据，而不是从中央管理存储自身中进行检索。</p></td>
</tr>
<tr class="even">
<td><p><strong>Tenant</strong></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>返回其授权设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p></td>
</tr>
</tbody>
</table>


## 输入类型

Get-CsTenantLicensingConfiguration cmdlet 不接受通过管道传递的输入。

## 返回类型

Get-CsTenantLicensingConfiguration cmdlet 返回 Deserialized.Microsoft.Rtc.Management.WritableConfig.Settings.TenantConfiguration.TenantLicensingConfiguration 对象的实例。

## 示例

示例 1 中显示的命令返回当前租户的授权配置信息：

    Get-CsTenantLicensingConfiguration

