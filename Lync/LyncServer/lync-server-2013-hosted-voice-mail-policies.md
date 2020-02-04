---
title: Lync Server 2013：托管语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 811f975868dad7bc0fcf6d5a2867ca2f3b81cd59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 中的托管语音邮件策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

*托管语音邮件策略*向 Lync Server 2013 ExUM 路由应用程序提供有关邮箱位于托管 Exchange 服务上的用户的路由位置的信息。

<div>


> [!NOTE]  
> 仅在与托管 Exchange UM 的 Lync Server 2013 集成中需要托管语音邮件策略。 它们不是与本地 Exchange UM 集成所必需的。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>托管语音邮件策略作用域

托管语音邮件策略范围确定策略适用的层次结构级别。 你可以配置具有以下范围级别的托管语音邮件策略：

  - *全局*策略可能会影响 Lync Server 2013 部署中的所有用户。 如果用户已启用托管 Exchange UM 访问，并且尚未分配每用户策略，并且尚未向用户的网站分配网站策略，则应用全局策略。 全局策略随 Lync Server 2013 一起安装。 你可以对其进行修改以满足你的需求，但不能重命名或删除它。

  - *网站*策略可能会影响托管在定义了该策略的网站上的所有用户。 如果用户已配置为托管 Exchange UM 访问，并且尚未分配每用户策略，则应用网站策略。

  - *每用户*策略只能影响单个用户或组。 若要强制执行每用户策略，必须将策略显式分配给单个用户、组和联系人对象。

<div>


> [!NOTE]  
> 在大多数情况下，只需要一个托管语音邮件策略。 你可以经常修改全局策略以满足你的所有需求。 如果你部署多个托管语音邮件策略，则所有此类策略都具有每用户范围。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>托管语音邮件策略属性

语音邮件策略定义 Lync Server 2013 ExUM 路由应用程序在发送到托管 Exchange UM 实现的邀请邮件的请求 URI 中插入的两个属性：

  - **目标：** 托管 Exchange UM 服务的完全限定的域名（FQDN）。 此值由本地 Lync Server Edge 服务器用于路由用途。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online 的 FQDN 为 exap.um.outlook.com。

    
    </div>

  - **组织：** 寄存 Lync Server 2013 用户邮箱的托管 Exchange UM 服务上的租户的 FQDN。 语音邮件策略可以包含多个组织。 如果策略中包含多个组织，则此属性必须为主 Lync Server 2013 用户邮箱的 Exchange Server 租户的逗号分隔列表。

<div>


> [!NOTE]  
> 托管 Exchange UM 服务的租户管理员将为目标和组织属性设置提供必要的值。 若要配置你的策略，你必须运行 CsHostedVoicemailPolicy cmdlet 或使用 CsHostedVoicemailPolicy cmdlet 修改存在的（例如，全局策略）。



</div>

有关管理托管语音邮件策略的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：

  - 新-CsHostedVoicemailPolicy

  - Set-CsHostedVoicemailPolicy

  - CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>每用户语音邮件策略分配

如果托管语音邮件策略是使用每用户范围定义的，则必须显式分配它。 你可以运行 CsHostedVoicemailPolicy cmdlet，将策略分配给单个用户或组。

有关分配或删除每用户托管语音邮件策略的详细信息，请参阅以下 cmdlet 的 Lync Server Management Shell 文档：

  - 授权-CsHostedVoicemailPolicy

  - Remove-CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

