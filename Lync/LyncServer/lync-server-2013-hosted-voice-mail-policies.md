---
title: Lync Server 2013：托管的语音邮件策略
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
ms.openlocfilehash: 4ee078a96350b2796cb3535ee4099a075cc0f622
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a>Lync Server 2013 中的托管语音邮件策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

*托管的语音邮件策略*向 Lync Server 2013 ExUM 路由应用程序提供有关邮箱位于托管 Exchange 服务上的用户的路由呼叫的位置的信息。

<div>


> [!NOTE]  
> 仅在与托管 Exchange UM 集成 Lync Server 2013 时，才需要托管语音邮件策略。 与本地 Exchange UM 的集成不需要它们。



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a>托管的语音邮件策略作用域

托管语音邮件策略作用域确定策略适用的层次结构级别。 您可以配置具有以下范围级别的托管语音邮件策略：

  - *全局*策略可能会影响 Lync Server 2013 部署中的所有用户。 如果为用户启用了托管 Exchange UM 访问且尚未分配每用户策略，且尚未向用户的网站分配网站策略，则应用全局策略。 已使用 Lync Server 2013 安装全局策略。 可以根据需要修改该策略，但不能重命名或删除它。

  - *网站*策略可能会影响托管在为其定义策略的网站上的所有用户。 如果为用户配置了托管 Exchange UM 访问且尚未分配每用户策略，则会应用站点策略。

  - *每用户*策略只能影响单个用户或组。 若要强制实施每用户策略，您必须将策略明确分配给各个用户、组和联系人对象。

<div>


> [!NOTE]  
> 在大多数情况下，只需要一个托管的语音邮件策略。 您通常可以修改全局策略以满足您的所有需求。 如果您部署多个托管的语音邮件策略，则所有此类策略都具有每用户作用域。



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a>托管的语音邮件策略属性

语音邮件策略定义了 Lync Server 2013 ExUM 路由应用程序在发送到托管 Exchange UM 实现的邀请邮件的请求 URI 中插入的两个属性：

  - **目标：** 托管 Exchange UM 服务的完全限定的域名（FQDN）。 本地 Lync Server 边缘服务器使用此值进行路由。
    
    <div>
    

    > [!NOTE]  
    > Exchange Online 的 FQDN 为 exap.um.outlook.com。

    
    </div>

  - **组织：** 承载 Lync Server 2013 用户邮箱的托管 Exchange UM 服务上的租户的 FQDN。 语音邮件策略可以包含多个组织。 如果策略中包含多个组织，则此属性必须是主你的 Lync Server 2013 用户邮箱的 Exchange Server 租户的逗号分隔列表。

<div>


> [!NOTE]  
> 托管 Exchange UM 服务的租户管理员将为您的目标和组织属性设置提供必要的值。 若要配置策略，您必须运行 CsHostedVoicemailPolicy cmdlet 或使用 CsHostedVoicemailPolicy cmdlet 修改存在的项（例如，全局策略）。



</div>

有关管理托管的语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - 新 CsHostedVoicemailPolicy

  - CsHostedVoicemailPolicy

  - CsHostedVoicemailPolicy

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a>每用户语音邮件策略分配

如果托管的语音邮件策略是使用每用户作用域定义的，则必须显式分配它。 您可以运行 CsHostedVoicemailPolicy cmdlet，将策略分配给单个用户或组。

有关分配或删除每用户托管语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - Grant-CsHostedVoicemailPolicy

  - CsHostedVoicemailPolicy

</div>

</div>

<span> </span>

</div>

</div>

</div>

