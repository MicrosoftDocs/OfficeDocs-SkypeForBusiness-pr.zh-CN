---
title: 管理 Lync Online 会议
TOCTitle: 管理 Lync Online 会议
ms:assetid: a4d0c070-4df2-47df-a1e2-6ce62600a287
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362833(v=OCS.15)
ms:contentKeyID: 56271190
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理 Lync Online 会议

 

_**上一次修改主题：** 2015-06-22_

以下 cmdlet 可用于管理会议设置：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="disable-csmeetingroom.md">Disable-CsMeetingRoom</a><br />
<a href="enable-csmeetingroom.md">Enable-CsMeetingRoom</a><br />
<a href="get-csmeetingroom.md">Get-CsMeetingRoom</a><br />
<a href="set-csmeetingroom.md">Set-CsMeetingRoom</a></p></td>
<td><p>管理会议室的终结点设备。</p>
<p>在 Skype for Business Online 中，会议室是独立的计算机设备，安装在会议室中并提供高级会议功能。要管理这些新的终结点设备，最重要的是您必须创建并启用设备的 Exchange 资源邮箱帐户，然后针对 Skype for Business Online 启用该资源帐户。</p></td>
</tr>
<tr class="even">
<td><p><a href="get-csaudioconferencingprovider.md">Get-CsAudioConferencingProvider</a></p></td>
<td><p>返回有关您的组织与其签订合同的音频会议提供商的信息。</p>
<p>音频会议提供商是一个第三方公司，它向组织提供会议服务，包括最高端服务，如实时翻译、转录和每个会议的实时接线员协助。</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-csmeetingconfiguration.md">Get-CsMeetingConfiguration</a><br />
<a href="set-csmeetingconfiguration.md">Set-CsMeetingConfiguration</a></p></td>
<td><p>控制用户可创建的会议类型，并确定会议如何对待匿名用户和电话拨入式会议用户。</p>
<p>会议是 Skype for Business Online 必不可少的一部分。使用这些 cmdlet，例如，您可以配置会议，以便拨入用户不会自动加入会议，而是路由到会议厅。这些拨入用户将在会议厅中处于等待状态，直到演示者允许他们加入会议。</p></td>
</tr>
</tbody>
</table>


您也可以使用 Skype for Business Online 管理中心管理一小部分会议配置属性：

![Lync 管理中心 - 常规选项属性](images/Dn362826.acf90793-7ee4-4faf-b791-f149dd5df2a5(OCS.15).png "Lync 管理中心 - 常规选项属性")

## 另请参阅

#### 概念

[Lync Online Cmdlet](the-skype-for-business-online-cmdlets.md)  
[快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务](quick-reference-using-windows-powershell-to-do-common-skype-for-business-online-management-tasks.md)

