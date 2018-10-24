---
title: Get-CsVoicemailReroutingConfiguration
TOCTitle: Get-CsVoicemailReroutingConfiguration
ms:assetid: 25e401eb-6a84-468f-b0eb-5b794f20b5bc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425732(v=OCS.15)
ms:contentKeyID: 49312279
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsVoicemailReroutingConfiguration

 

_**上一次修改主题：** 2015-03-09_

检索提供公用电话交换网 (PSTN) 电话号码以访问 Exchange UM 订阅者访问和自动助理功能的各种设置。此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsVoicemailReroutingConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsVoicemailReroutingConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## 示例

## 示例 1

此示例检索 Lync Server 的此部署中定义的所有语音邮件重新路由配置设置。例如，如果有三个分支机构部署了 Survivable Branch Appliance，则此命令将返回三个语音邮件重新路由配置设置。

    Get-CsVoicemailReroutingConfiguration

## 示例 2

此示例检索站点 BranchOffice\_Portland 的语音邮件重新路由配置设置。

    Get-CsVoicemailReroutingConfiguration -Identity site:BranchOffice_Portland

## 示例 3

此示例检索站点名称以字符串 BranchOffice 开头（例如 BranchOffice\_Portland、BranchOffice\_Sacramento）的所有站点的所有语音邮件重新路由设置。

    Get-CsVoicemailReroutingConfiguration -Filter *:BranchOffice*

## 示例 4

此示例检索未启用的所有语音邮件重新路由配置。该命令首先调用 **Get-CsVoicemailReroutingConfiguration** cmdlet，后者将检索所有语音邮件重新路由配置的集合。然后，将此集合通过管道传递到 **Where-Object** cmdlet。**Where-Object** cmdlet 会缩小该集合的范围，使其仅包括 Enabled 属性等于 (-eq) False 的配置。

    Get-CsVoicemailReroutingConfiguration | Where-Object {$_.Enabled -eq $False}

## 详细说明

此 cmdlet 检索确定当从分支机构站点中的 Lync Server 到位于数据中心内的 Exchange UM 服务器的 IP 连接不可用时将自动助理和订阅者访问呼叫路由到何处的各种设置。

自动助理和订阅者访问都是 Exchange UM 的功能。自动助理功能提供语音识别和电话按键控制（双音多频，简称 DTMF），以便外部呼叫者导航公司的电话系统，以到达所需部门或员工，或者以消息接收模式接受用户的消息。（建议对留言模式采用语音重新路由。）订阅者访问使内部用户可通过电话访问其 Microsoft Outlook 邮箱。通过由这些设置提供的号码，呼叫者可以为企业语音用户（AutoAttendantNumber 设置）和检索语音邮件的用户留语音邮件消息，即使从远程站点上部署的 Lync Server 至数据中心的 Exchange UM 的 IP 连接不可用也是如此（SubscriberAccessNumber 设置）。

在没有任何参数的情况下调用此 cmdlet 将返回所有语音邮件重新路由配置。

谁能运行此 cmdlet：默认情况下，以下各组的成员有权在本地运行 **Get-CsVoicemailReroutingConfiguration** cmdlet：RTCUniversalUserAdmins、RTCUniversalServerAdmins。要返回分配了此 cmdlet 的所有基于角色的访问控制 (RBAC) 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsVoicemailReroutingConfiguration"}

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
<td><p>通过 Filter 参数可根据通配符匹配检索一组特定站点的配置设置。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>要检索的配置的唯一标识符。对于此 cmdlet，Identity 将为 Global 或 site:&lt;站点名称&gt;，其中 &lt;站点名称&gt; 是向其应用设置的站点的名称。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本，而不是从中央管理存储本身检索语音邮件重新路由配置。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。

## 返回类型

检索一个或多个类型为 Microsoft.Rtc.Management.WritableConfig.Settings.ExumRouting.VoicemailReroutingConfiguration 的对象。

## 另请参阅

#### 其他资源

[New-CsVoicemailReroutingConfiguration](new-csvoicemailreroutingconfiguration.md)  
[Remove-CsVoicemailReroutingConfiguration](remove-csvoicemailreroutingconfiguration.md)  
[Set-CsVoicemailReroutingConfiguration](set-csvoicemailreroutingconfiguration.md)

