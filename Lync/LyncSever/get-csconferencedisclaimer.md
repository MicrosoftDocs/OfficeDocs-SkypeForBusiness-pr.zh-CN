---
title: Get-CsConferenceDisclaimer
TOCTitle: Get-CsConferenceDisclaimer
ms:assetid: 2382aaef-9c5e-43f8-99de-6c880134db7d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425714(v=OCS.15)
ms:contentKeyID: 49312255
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsConferenceDisclaimer

 

_**上一次修改主题：** 2015-03-09_

返回有关组织中使用的会议免责声明的信息。会议免责声明是一条消息，该消息显示给通过超链接加入会议的用户（例如将会议链接粘贴到诸如 Windows Internet Explorer 等浏览器的用户）。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsConferenceDisclaimer [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsConferenceDisclaimer [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

示例 1 中显示的命令返回有关配置为在组织中使用的会议免责声明的信息。由于您只能有单个免责声明（在全局范围配置），因此在运行此命令时无需指定 Identity。

    Get-CSConferenceDisclaimer

## 详细说明

在配置会议设置时，管理员可以包括法律免责声明，以在参与者加入由 Lync Server 托管的会议时向这些人员显示。此免责声明通常用于说明与会议相关的法律和知识产权法。如果用户不同意免责声明中规定的条款，将无法加入会议。请注意，此免责声明只显示给使用超链接加入会议的用户。

使用 **Get-CsConferenceDisclaimer** cmdlet 可以查看组织的免责声明的正文和标题。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsConferenceDisclaimer** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsConferenceDisclaimer"}

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
<td><p>使您可以在引用会议免责声明时使用通配符值。由于您只能有一个会议免责声明全局实例，因此完全不必使用 Filter 参数。然而，您可以使用以下语法引用全局免责声明：-Filter &quot;g*&quot;。该语法返回 Identity 以字母“g”开头的所有会议免责声明。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>会议免责声明的唯一标识。由于您只能有一个会议免责声明的全局实例，因此在调用 <strong>Get-CsConferenceDisclaimer</strong> cmdlet 时无需指定 Identity。然而，您可以使用以下语法引用全局免责声明：-Identity global。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索会议免责声明数据。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

**Get-CsConferenceDisclaimer** cmdlet 将返回 Microsoft.Rtc.Management.WritableConfig.Settings.WebConf.ConferenceDisclaimer 对象的实例。

## 另请参阅

#### 其他资源

[Remove-CsConferenceDisclaimer](remove-csconferencedisclaimer.md)  
[Set-CsConferenceDisclaimer](set-csconferencedisclaimer.md)

