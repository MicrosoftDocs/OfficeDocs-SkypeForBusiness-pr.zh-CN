---
title: 按类别划分的 Lync Server 2013 Cmdlet
TOCTitle: 按类别划分的 Lync Server 2013 Cmdlet
ms:assetid: 4ce274d7-b0ec-40b8-b85e-9a0613916ffb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398306(v=OCS.15)
ms:contentKeyID: 49312782
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 按类别划分的 Lync Server 2013 Cmdlet

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 附带将近 550 个专门设计用于允许管理员从命令行管理 Lync Server 的 cmdlet。可从 Lync Server 命令行管理程序访问这些 cmdlet。可通过键入类似如下的命令直接从命令行检索有关某个 cmdlet 的帮助：

    Get-Help New-CsVoicePolicy -Full

上述命令将检索提供的有关 **New-CsVoicePolicy** cmdlet 的所有帮助。将对 **New-CsVoicePolicy** 的引用替换为要检索其帮助信息的 cmdlet 的名称。

要检索可用于管理 Microsoft Lync Server 2013 的 cmdlet 的完整列表，请在 Lync Server 命令行管理程序命令提示符处键入以下内容：

    Get-Command * -Module Lync -CommandType cmdlet

如果不确定需要哪些 cmdlet，我们还提供了 cmdlet 的分类列表及其帮助主题。您将发现某些 cmdlet 出现在多个类别中，我们是有意这样划分的，因为这些 cmdlet 可以应用于多个产品领域。类别列表如下：

## 本部分内容


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-user-management-cmdlets.md">用户管理 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-voice-application-cmdlets.md">语音应用程序 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-client-management-cmdlets.md">客户端管理 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-advanced-enterprise-voice-cmdlets.md">高级企业语音 Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-im-and-presence-cmdlets.md">IM 和状态 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-pstn-connectivity-cmdlets.md">PSTN 连接 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencing-cmdlets.md">会议 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-phones-and-devices-cmdlets.md">电话和设备 Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-infrastructure-and-deployment-cmdlets.md">基础结构和部署 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-migration-and-coexistence-cmdlets.md">迁移和共存 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-security-cmdlets.md">安全性 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-lync-server-management-shell-configuration-cmdlets.md">Lync Server 命令行管理程序配置 Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-roles-and-services-cmdlets.md">服务器角色和服务 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-mobility-cmdlets.md">移动 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-application-management-cmdlets.md">应用程序管理 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-persistent-chat-server-cmdlets.md">持久聊天服务器 Cmdlet</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-federation-and-external-access-cmdlets.md">联盟和外部访问 Cmdlet</a></p></td>
<td><p><a href="lync-server-2013-centralized-logging-cmdlets.md">集中日志记录 Cmdlet</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-enterprise-voice-cmdlets.md">企业语音 Cmdlet</a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 其他资源

[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x804)

