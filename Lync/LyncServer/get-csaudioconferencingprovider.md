---
title: Get-CsAudioConferencingProvider
TOCTitle: Get-CsAudioConferencingProvider
ms:assetid: 4632e9d0-aa87-459f-ad7e-27125c11da5b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994030(v=OCS.15)
ms:contentKeyID: 52061007
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsAudioConferencingProvider

 

_**上一次修改主题：** 2015-03-09_

返回有关获得授权在组织中使用的音频会议提供商的信息。音频会议提供商是为组织提供会议服务的第三方公司。

**Get-CsAudioConferencingProvider**只能与 Microsoft Lync Online 一起使用。

## 语法

    Get-CsAudioConferencingProvider [[-Identity] <XdsGlobalRelativeIdentity>] [-LocalStore][<CommonParameters>]Get-CsAudioConferencingProvider [-Filter <string>] [-LocalStore] [<CommonParameters>]

## 示例

## 示例 1

示例 1 中显示的命令返回有关可供在您的组织中使用的所有音频会议提供商的信息。

    Get-CsAudioConferencingProvider

## 示例 2

示例 2 将返回单个音频会议提供商的信息：Identity 为 Fabrikam Telecom 的提供商。

    Get-CsAudioConferencingProvider -Identity "Fabrikam Telecom"

## 示例 3

示例 3 说明如何使用通配符值（和 Filter 参数）返回有关音频会议提供商的信息。在此示例中，筛选值“\*Fabrikam\*”返回其 Identity 的任何位置具有字符串值“Fabrikam”的所有音频会议提供商。

    Get-CsAudioConferencingProvider -Filter "*Fabrikam*"

## 详细说明

音频会议提供商是为组织提供会议服务的第三方公司。音频会议提供商的功能之一是为外出且未连接到企业网络或 Internet 的用户提供了一种通过音频参加会议的方法。音频会议提供商通常会提供一些高端服务，如实时翻译、转录和每个会议的实时接线员协助。

在组织与音频会议提供商签订合同之后，可以使用 **Set-CsUserAcp** cmdlet 将用户分配给该提供商。管理员可以使用 **Get-CsAudioConferencingProvider** cmdlet 检索有关可供他们使用的音频会议提供商的信息。

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
<td><p>使您可以在指示要返回的音频会议提供商时使用通配符。例如，此语法返回有关其 Identity 中某位置包含字符串值“fabrikam”的所有音频会议提供商的信息：</p>
<p>-Filter &quot;*fabrikam*&quot;</p>
<p>请注意，不能在同一个命令中同时使用 Filter 参数和 Identity 参数。</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>可选</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>要返回的音频会议提供商的唯一标识符。例如：</p>
<p>-Identity &quot;Fabrikam Telecom&quot;</p>
<p>如果命令中既没有 Identity 参数，也没有 Filter 参数，<strong>Get-CsAudioConferencingProvider</strong> cmdlet 将返回所有可用提供商的信息。</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>可选</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>从中央管理存储的本地副本中检索音频会议提供商数据，而不是从中央管理存储自身中进行检索。</p></td>
</tr>
</tbody>
</table>


## 输入类型

无。**Get-CsAudioConferencingProvider** cmdlet 不接受通过管道传递的输入。

## 返回类型

**Get-CsAudioConferencingProvider** cmdlet 将返回 Microsoft.Rtc.Management.WritableConfig.Settings.AudioConferencingProvider.AudioConferencingProvider\#Decorated 对象的实例。

## 另请参阅

#### 其他资源

[Get-CsUserAcp](get-csuseracp.md)  
[Remove-CsUserAcp](remove-csuseracp.md)  
[Set-CsUserAcp](set-csuseracp.md)

