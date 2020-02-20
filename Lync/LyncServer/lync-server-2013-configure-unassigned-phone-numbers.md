---
title: Lync Server 2013：配置未分配的电话号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920dc38010aa82f7c3f970a76f78c23bbf2a486a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a>在 Lync Server 2013 中配置未分配的电话号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

Lync Server 允许您配置对你的组织有效但未分配给用户或电话的电话号码的传入呼叫发生的情况。 若要配置对此类呼叫的处理，请设置未分配号码表。 您可以使用表将呼叫路由到通知应用程序或 Exchange UM 服务器。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码定制所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码并将其分配给提供新号码的通知。

<div>


> [!IMPORTANT]  
> 在配置未分配号码表之前，必须已定义一个或多个通知，或者已设置 Exchange UM 自动助理。 有关创建通知的详细信息，请参阅<A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中创建通知</A>。 若要查看是否已配置 Exchange UM 设置，请运行<STRONG>CsExUmContact</STRONG> cmdlet。 有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中创建或修改未分配号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [在 Lync Server 2013 中删除未分配号码范围](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

