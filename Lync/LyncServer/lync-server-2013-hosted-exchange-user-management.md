---
title: Lync Server 2013：托管 Exchange 用户管理
description: Lync Server 2013：托管 Exchange 用户管理。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ceda9352fc627fc7b762b5995d788ffafa159ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550108"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange 用户管理

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

若要为其邮箱位于托管 Exchange 服务上的 Lync Server 2013 用户提供语音邮件服务，必须为其用户帐户启用托管语音邮件。

<div>


> [!NOTE]  
> 在可以对 Lync Server 2013 用户启用托管语音邮件之前，必须部署适用于相应用户帐户的托管语音邮件策略。 该策略的作用域可以是 global、site 或每用户，只要适用于要启用的用户即可。 有关详细信息，请参阅 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>msExchUCVoiceMailSettings 属性

Lync Server 2013 引入了一个名为 **msExchUCVoiceMailSettings**的新用户属性，该属性是作为 Lync Server 2013 Active Directory 架构准备的一部分创建的。 此多值属性保存由 Lync Server 2013 和托管 Exchange 服务共享的语音邮件设置。

在某些情况下，托管 Exchange 服务可能会在启用 Exchange UM 或在将邮箱传输到托管 Exchange Server 的过程中设置 msExchUCVoiceMailSettings 属性的值。 如果 Exchange 不设置此属性，则 Lync Server 2013 管理员必须通过运行 Set-CsUser cmdlet 来设置它，如本主题前面所述。

该属性的键/值对及其作者显示在下表中。

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>msExchUCVoiceMailSettings 属性键/值对

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
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 已为用户启用托管 UM 访问。 Exchange UM 路由应用程序将检查用户的托管语音邮件策略以了解路由详细信息。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 已为用户禁用托管 UM 访问。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>用户已为 Lync Server 2013 启用了托管 UM 访问。 Lync Server 2013 ExUM 路由应用程序将检查用户的托管语音邮件策略以了解路由详细信息。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>已为 Lync Server 2013 禁用托管 UM 访问的用户。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果该属性已经有一个除 Lync Server 2013 键/值对之外的值 (CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1) ，则将显示一条警告，指示该属性可能由不同的应用程序管理。 例如，如果键/值对 ExchangeHostedVoiceMail=0 或 ExchangeHostedVoiceMail=1 已存在，则显示警告。 在这种情况下，可以通过在 Active Directory 中编辑来更改值，或运行以下 cmdlet 将值设置为 null：<BR>Set-CsUser –identity user –HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>为用户启用托管语音邮件

要使用户的语音邮件呼叫可以路由到托管 Exchange UM，必须运行 Set-CsUser cmdlet 来设置 *HostedVoiceMail* 参数的值。 此参数还会向 Lync Server 2013 发出信号，以使 "呼叫语音邮件" 指示器亮起来。

  - 以下示例为 Pilar Ackerman 的用户帐户启用托管语音邮件：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    该 cmdlet 验证是否有适用于该用户的托管语音邮件策略（全局、站点级别或每用户）。如果没有适用的策略，该 cmdlet 将失败。

  - 以下示例为 Pilar Ackerman 的用户帐户禁用托管语音邮件：
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    该 cmdlet 验证是否没有适用于该用户的托管语音邮件策略（全局、站点级别或每用户）。如果有适用的策略，该 cmdlet 将失败。

有关使用 Set-CsUser cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

</div>

</div>

<span> </span>

</div>

</div>

</div>

