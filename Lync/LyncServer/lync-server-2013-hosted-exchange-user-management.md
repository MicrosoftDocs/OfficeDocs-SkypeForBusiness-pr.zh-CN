---
title: Lync Server 2013：托管 Exchange 用户管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange 用户管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

若要为 Lync Server 2013 用户提供其邮箱位于托管 Exchange 服务上的语音邮件服务, 必须为托管语音邮件启用其用户帐户。

<div>


> [!NOTE]  
> 在 Lync Server 2013 用户可启用托管语音邮件之前, 必须部署适用于相应用户帐户的托管语音邮件策略。 策略可以是全局、网站或每用户在范围内, 只要它适用于要启用的用户。 有关详细信息, 请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a>MsExchUCVoiceMailSettings 属性

Lync Server 2013 引入了名为**msExchUCVoiceMailSettings**的新用户属性, 该属性是作为 Lync Server 2013 Active Directory 架构准备的一部分创建的。 此多值属性包含由 Lync Server 2013 和托管 Exchange 服务共享的语音邮件设置。

在某些情况下, 托管 Exchange 服务可能会在启用 Exchange UM 的过程中或在将邮箱传输到托管 Exchange 服务器的过程中设置 msExchUCVoiceMailSettings 属性的值。 如果此属性不是由 Exchange 设置的, 则 Lync Server 2013 管理员必须通过运行 Move-csuser cmdlet 来设置它, 如本主题中前面所述。

属性的键/值对及其作者如下表所示。

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a>MsExchUCVoiceMailSettings 属性键/值对

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>值</th>
<th>授权</th>
<th>含义</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ExchangeHostedVoiceMail = 1</p></td>
<td><p>Exchange</p></td>
<td><p>用户已为 Exchange Server 启用托管 UM 访问。 Exchange UM 路由应用程序将检查用户的托管语音邮件策略中是否有路由详细信息。</p></td>
</tr>
<tr class="even">
<td><p>ExchangeHostedVoiceMail = 0</p></td>
<td><p>Exchange</p></td>
<td><p>Exchange Server 的托管 UM 访问已禁用用户。</p></td>
</tr>
<tr class="odd">
<td><p>CsHostedVoiceMail = 1</p></td>
<td><p>Lync Server</p></td>
<td><p>用户已为 Lync Server 2013 启用托管 UM 访问。 Lync Server 2013 ExUM 路由应用程序将检查用户的托管语音邮件策略中是否有路由详细信息。</p></td>
</tr>
<tr class="even">
<td><p>CsHostedVoiceMail = 0</p></td>
<td><p>Lync Server</p></td>
<td><p>Lync Server 2013 已禁用 "托管 UM 访问" 用户。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 如果该属性已具有除 Lync Server 2013 键/值对之外的值 (CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1), 则会出现一个警告, 指示该属性可能由其他应用程序管理。 例如, 如果 key/value 对 ExchangeHostedVoiceMail = 0 或 ExchangeHostedVoiceMail = 1 已存在, 则会显示警告。 在这种情况下, 你可以通过编辑 Active Directory 来更改该值, 或者运行以下 cmdlet 以将该值设置为 null:<BR>Move-csuser-身份识别用户-HostedVoicemail $null



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a>为用户启用托管语音邮件

若要使用户的语音邮件呼叫能够路由到托管 Exchange UM, 必须运行 Move-csuser cmdlet 以设置*HostedVoiceMail*参数的值。 此参数还会向 Lync Server 2013 发出信号, 以突出 "呼叫语音邮件" 指示器。

  - 以下示例为托管语音邮件启用 Pilar Ackerman 的用户帐户:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    该 cmdlet 验证托管的语音邮件策略 (全局、网站级别或每用户) 是否适用于此用户。 如果未应用任何策略, 则 cmdlet 将失败。

  - 以下示例将禁用托管语音邮件的 Pilar Ackerman 用户帐户:
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    该 cmdlet 验证任何托管语音邮件策略 (全局、网站级别或每用户) 是否适用于此用户。 如果应用了策略, 则 cmdlet 将失败。

有关使用 Move-csuser cmdlet 的详细信息, 请参阅 Lync Server Management Shell 文档。

</div>

</div>

<span> </span>

</div>

</div>

</div>

