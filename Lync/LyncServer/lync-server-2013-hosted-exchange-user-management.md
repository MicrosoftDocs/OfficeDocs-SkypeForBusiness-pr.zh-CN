---
title: Lync Server 2013：托管 Exchange 用户管理
TOCTitle: 托管 Exchange 用户管理
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399037(v=OCS.15)
ms:contentKeyID: 49314600
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的托管 Exchange 用户管理

 

_**上一次修改主题：** 2015-03-09_

要为邮箱位于托管 Exchange 服务上的 Lync Server 2013 用户提供语音邮件服务，必须为这些用户帐户启用托管语音邮件。

> [!NOTE]  
> 在可以为 Lync Server 2013 用户启用托管语音邮件之前，必须已部署应用于对应用户帐户的托管语音邮件策略。该策略的作用域可以是 global、site 或每用户，只要适用于要启用的用户即可。有关详细信息，请参阅 <a href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</a>。



## msExchUCVoiceMailSettings 属性

Lync Server 2013 引入一个名为 **msExchUCVoiceMailSettings** 的新用户属性，该属性是在 Lync Server 2013 Active Directory 架构准备过程中创建的。该多值属性用于保存由 Lync Server 2013 和托管 Exchange 服务共享的语音邮件设置。

在某些情况下，托管 Exchange 服务可能会在启用 Exchange UM 或在将邮箱传输到托管 Exchange Server 的过程中设置 msExchUCVoiceMailSettings 属性的值。如果 Exchange 没有设置该属性， Lync Server 2013 管理员必须通过运行 Set-CsUser cmdlet 来设置该属性，如本主题前面所述。

该属性的键/值对及其作者显示在下表中。

### msExchUCVoiceMailSettings 属性键/值对

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>值</th>
<th>作者</th>
<th>含义</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail=1</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 已为用户启用托管 UM 访问。 Exchange UM 路由应用程序会检查用户的托管语音邮件策略，查看路由详细信息。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail=0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 已为用户禁用托管 UM 访问。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail=1</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 已为用户启用托管 UM 访问。 Lync Server 2013 ExUM 路由应用程序会检查用户的托管语音邮件策略，查看路由详细信息。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail=0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 已为用户禁用托管 UM 访问。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 如果该属性已具有 Lync Server 2013 键/值对（CSHostedVoiceMail=0 或 CSHostedVoiceMail=1）以外的值，则会出现警告，指示该属性可能由其他应用程序管理。例如，如果键/值对 ExchangeHostedVoiceMail=0 或 ExchangeHostedVoiceMail=1 已存在，则显示警告。在这种情况下，可以通过在 Active Directory 中编辑来更改值，或运行以下 cmdlet 将值设置为 null：<br />
Set-CsUser –identity user –HostedVoicemail $null



## 为用户启用托管语音邮件

要使用户的语音邮件呼叫可以路由到托管 Exchange UM，必须运行 Set-CsUser cmdlet 来设置 *HostedVoiceMail* 参数的值。该参数还会向 Lync Server 2013 发信号，以点亮“呼叫语音邮件”指示器。

  - 以下示例为 Pilar Ackerman 的用户帐户启用托管语音邮件：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    该 cmdlet 验证是否有适用于该用户的托管语音邮件策略（全局、站点级别或每用户）。如果没有适用的策略，该 cmdlet 将失败。

  - 以下示例为 Pilar Ackerman 的用户帐户禁用托管语音邮件：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    该 cmdlet 验证是否没有适用于该用户的托管语音邮件策略（全局、站点级别或每用户）。如果有适用的策略，该 cmdlet 将失败。

有关使用 Set-CsUser cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

