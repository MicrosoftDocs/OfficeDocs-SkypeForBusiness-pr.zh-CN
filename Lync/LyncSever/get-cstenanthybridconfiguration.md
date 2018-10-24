---
title: Get-CsTenantHybridConfiguration
TOCTitle: Get-CsTenantHybridConfiguration
ms:assetid: 4b2e6781-8f46-4ba3-be76-3a95460e3132
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994034(v=OCS.15)
ms:contentKeyID: 52061008
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsTenantHybridConfiguration

 

_**上一次修改主题：** 2015-03-09_

返回使托管在 Microsoft Lync Online 上的用户能够访问媒体旁路、增强型 9-1-1 和呼叫寄存等企业语音功能的混合配置设置的值。混合方案（也称为“拆分域方案”）是一种 Lync Server 部署，在该部署中，一些用户的帐户托管在内部部署中，而其他用户的帐户托管在 Lync Online 上。

Get-CsTenantHybridConfiguration cmdlet 只能与 Skype for Business Online 一起使用。

## 语法

    Get-CsTenantHybridConfiguration [[-Identity] <XdsIdentity>] [-Tenant <guid>] [-LocalStore] [<CommonParameters>]Get-CsTenantHybridConfiguration [-Tenant <guid>] [-Filter <string>] [-LocalStore] [<CommonParameters>]

## 示例

## 示例 1

示例 1 中显示的命令返回租户混合配置设置的全局集合的属性值。

    Get-CsTenantHybridConfiguration -Identity "Global"

## 示例 2

示例 2 返回应用于租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户的自定义租户混合配置设置的属性值。

    Get-CsTenantHybridConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## 示例 3

示例 3 返回您的所有可用租户的租户混合配置信息。为此，命令首先调用 **Get-CsTenant** cmdlet 以返回所有这些租户的集合。然后，将此集合通过管道传递到 **ForEach-Object** cmdlet，后者将选取集合中的每个租户并逐一执行两个任务。首先，该 cmdlet 输出租户的 Active Directory 显示名称；这确保可轻松识别每个设置集合。之后，**ForEach-Object** cmdlet 运行 **Get-CsTenantHybridConfiguration** cmdlet 来返回相关租户的租户混合配置设置。

    Get-CsTenant | ForEach-Object {$_.DisplayName; Get-CsTenantHybridConfiguration -Tenant $_.TenantId}

## 详细说明

在混合或“拆分域”部署中，组织的一些用户的帐户托管在 Lync Online 上，同时，其他用户的帐户托管在 Lync Server 的内部部署版本上。默认情况下，托管在 Lync Online 上的用户无法访问企业语音提供的整套功能；这是因为 Lync Online 服务器对 Lync Server 部署和网络配置信息不具有直接访问权限。其中，Lync Online 用户对以下类似内容不具有默认访问权限：

  - 增强型 9-1-1：用于拨打紧急电话的 Lync Server 服务。

  - 呼叫寄存：Lync Server 服务使用户能够从电话 A 将呼叫置于保持状态，而从电话 B 取回该呼叫。

  - 媒体旁路：使发往和来自公用电话交换网 (PSTN) 的呼叫能够绕过中介服务器，从而帮助最大程度减少代码转换和网络延迟。

  - PSTN 会议拨入和拨出：使用户能够使用任何 PSTN 电话或移动设备参与联机会议的音频部分。

  - 响应组应用程序：为您提供一种将电话呼叫自动路由至诸如技术支持或客户支持线路等实体的方法。默认情况下，Lync Server 用户不能充当响应组代理。

为了向 Lync Online 用户提供对这些企业语音功能的访问权限，管理员需要向混合配置设置（例如，内部和外部 Web 服务 URL 以及组织的访问边缘服务器的完全限定的域名）分配合适的值。这些值只能使用 **Set-CsTenantHybridConfiguration** cmdlet 进行分配，可向 Lync Online 服务器提供使用这些高级企业语音功能所需的信息。

您可以使用 **Get-CsTenantHybridConfiguration** cmdlet 返回有关您的组织中当前正在使用的租户混合配置设置的信息。

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
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Filter</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>使您能够使用通配符，以便返回租户混合配置设置的集合。由于您被限制为使用混合配置设置的单个全局集合，无需使用 Filter 参数。但是，这是 <strong>Get-CsTenantHybridConfiguration</strong> cmdlet 的有效语法：</p>
<p>Get-CsTenantHybridConfiguration –Filter &quot;g*&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要返回的租户混合配置设置的唯一标识。由于您被限制为混合配置设置的单个全局集合，因此可使用 Identity 参数返回的唯一集合是全局集合：</p>
<p>-Identity global</p>
<p>要修改个别租户的设置，请使用 Tenant 参数而不是 Identity 参数。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本中检索租户混合配置数据，而不是从中央管理存储自身中进行检索。</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>返回其混合配置设置的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>如果您使用的是 Windows PowerShell 的远程会话，而且只连接到 Skype for Business Online，就不必包括 Tenant 参数。将根据您的连接信息自动为您填充租户 ID。Tenant 参数主要用于混合环境中。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsTenantHybridConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsTenantHybridConfiguration** cmdlet 返回 Microsoft.Rtc.Management.WritableConfig.Settings.HybridConfiguration.TenantHybridConfiguration 对象的实例。

## 另请参阅

#### 其他资源

[Set-CsTenantHybridConfiguration](set-cstenanthybridconfiguration.md)

