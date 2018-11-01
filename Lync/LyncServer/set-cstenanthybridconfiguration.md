---
title: Set-CsTenantHybridConfiguration
TOCTitle: Set-CsTenantHybridConfiguration
ms:assetid: 805ac9ee-df40-40e1-baaa-adffb6bd8cf6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994046(v=OCS.15)
ms:contentKeyID: 52061052
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsTenantHybridConfiguration

 

_**上一次修改主题：** 2015-03-09_

在混合方案中用于向驻留在 Microsoft Lync Online 上的用户授予对内部部署企业语音功能（例如，媒体旁路、增强型 9-1-1 和呼叫寄存）的访问权限。混合方案（也称为“拆分域方案”）是一种 Lync Server 部署，在该部署中，一些用户的帐户驻留在内部部署中，而其他用户的帐户驻留在 Lync Online 上。

此 cmdlet 只能与 Skype for Business Online 一起使用。

## 语法

    Set-CsTenantHybridConfiguration [[-Identity] <XdsIdentity>] [-Tenant <guid>] [-PeerDestination <string>] [-HybridConfigServiceInternalUrl <string>] [-HybridConfigServiceExternalUrl <string>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]Set-CsTenantHybridConfiguration [-Tenant <guid>] [-PeerDestination <string>][-HybridConfigServiceInternalUrl <string>] [-HybridConfigServiceExternalUrl <string>] [-Instance <psobject>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]

## 示例

## 示例 1

示例 1 中显示的命令为租户混合配置设置的全局集合设置内部服务 URL。要配置全局设置，请包括 Identity 参数以及参数值“global”。

    Set-CsTenantHybridConfiguration -Identity "global" - HybridConfigServiceInternalUrl "https://internal.litwareinc.com"

## 示例 2

在示例 2 中，为特定租户配置了内部服务 URL；在此示例中是租户 ID 为“bf19b7db-6960-41e5-a139-2aa373474354”的租户。当某属性值明确分配给单个租户时，该租户将由其租户混合配置设置（而不是全局设置）控制。

    Set-CsTenantHybridConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" HybridConfigServiceInternalUrl "https://internal.litwareinc.com"

## 示例 3

示例 3 中显示的命令为您的组织的所有租户配置内部服务 URL。要执行此操作，命令首先使用 **Get-CsTenant** cmdlet 返回所有可用租户的集合；然后该集合通过管道传递到 **ForEach-Object** cmdlet。而 **ForEach-Object** cmdlet 将针对集合中的每个租户运行 **Set-CsTenantHybridConfiguration** cmdlet，将各个租户的内部服务 URL 设置为“https://internal.litwareinc.com”。

    Get-CsTenant | ForEach-Object {Set-CsTenantHybridConfiguration -Tenant $_.TenantID -HybridConfigServiceInternalUrl "https://internal.litwareinc.com"}

## 详细说明

在混合或“拆分域”部署中，组织的一些用户的帐户驻留在 Lync Online 上，同时，其他用户的帐户驻留在Lync Server 上。默认情况下，驻留在 Lync Online 上的用户无法访问企业语音提供的整套功能；这是因为 Lync Online 服务器对内部部署 Lync Server 部署和网络配置信息不具有直接访问权限。其中，Lync Online 用户对以下类似内容不具有默认访问权限：

  - 增强型 9-1-1：用于发出紧急电话呼叫的 Lync Server 服务。

  - 呼叫寄存：该 Lync Server 服务使用户能够从电话 A 将呼叫置于保持状态，而从电话 B 取回该呼叫。

  - 媒体旁路：使发往和来自公用电话交换网 (PSTN) 的呼叫能够绕过中介服务器，从而帮助最大程度减少代码转换和网络延迟。

  - PSTN 会议拨入和拨出：使用户能够使用任何 PSTN 电话或移动设备参与联机会议的音频部分。

  - 响应组应用程序：为您提供一种将电话呼叫自动路由至诸如技术支持或客户支持线路等实体的方法。默认情况下，Lync Online 用户不能充当响应组代理。

为了向 Lync Online 用户提供对这些企业语音功能的访问权限，管理员需要向混合配置设置（例如，内部和外部 Web 服务 URL 以及组织的访问边缘服务器的完全限定的名称）分配合适的值。这些值只能使用 **Set-CsTenantHybridConfiguration** cmdlet 进行分配，可向 Lync Online 服务器提供使用这些高级企业语音功能所需的信息。

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
<td><p><em>Confirm</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p></p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>禁止显示运行此命令时可能出现的任何非严重错误消息。</p></td>
</tr>
<tr class="odd">
<td><p><em>HybridConfigServiceExternalUrl</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>外部 Web 服务 URL。</p></td>
</tr>
<tr class="even">
<td><p><em>HybridConfigServiceInternalUrl</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>内部 Web 服务 URL。</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要修改的租户混合配置设置的唯一标识。由于您被限制为混合配置设置的单个全局集合，因此可使用 Identity 参数修改的唯一集合是全局集合：</p>
<p>-Identity global</p>
<p>要修改个别租户的设置，请使用 Tenant 参数而不是 Identity 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>PeerDestination</em></p></td>
<td><p>可选</p></td>
<td><p>System.String</p></td>
<td><p>您的内部部署访问边缘服务器的完全限定的域名。</p></td>
</tr>
<tr class="even">
<td><p><em>Tenant</em></p></td>
<td><p>可选</p></td>
<td><p>System.Guid</p></td>
<td><p>其混合配置设置将被修改的租户帐户的全局唯一标识符 (GUID)。例如：</p>
<p>–Tenant &quot;38aad667-af54-4397-aaa7-e94c79ec2308&quot;</p>
<p>可以通过运行以下命令来返回每个租户的租户 ID：</p>
<p>Get-CsTenant | Select-Object DisplayName, TenantID</p>
<p>如果您正在使用 Windows PowerShell 的远程会话，并且仅连接到 Skype for Business Online，那么您不必包括 Tenant 参数。相反，将基于您的连接信息自动为您填充租户 ID。Tenant 参数主要用于混合部署。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述如果执行命令会发生什么情况（无需实际执行命令）。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。 **Set-CsTenantHybridConfiguration** cmdlet 不接受通过管道传递的输入。

## 返回类型

无。但 **Set-CsTenantHybridConfiguration** cmdlet 会修改 Microsoft.Rtc.Management.WritableConfig.Settings.HybridConfiguration.TenantHybridConfiguration 对象的现有实例。

## 另请参阅

#### 其他资源

[Get-CsTenantHybridConfiguration](get-cstenanthybridconfiguration.md)

