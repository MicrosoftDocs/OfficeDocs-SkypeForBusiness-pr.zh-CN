---
title: Lync Server 2013：配置未分配号码表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c59b44b31eececd002434b74085be85eaec9cbec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>在 Lync Server 2013 中配置未分配号码表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-30_

在 Lync Server 2013 中, 你可以指定传入呼叫对你的组织有效但未分配给用户或手机的电话号码所发生的情况。 呼叫者可以听到消息, 也可以将消息路由到另一个目标, 或者同时路由到其他目标。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。

<div>


> [!IMPORTANT]  
> 配置 "未分配的号码" 表之前, 您的系统必须已定义公告或 "Exchange 统一消息 (UM)" 自动助理设置。



</div>

<div>


> [!TIP]  
> 当某人呼叫未分配的号码时, Lync Server 将从上到下搜索 "未分配的号码" 表, 并使用第一个匹配区域。 因此，要在万不得已时执行的操作应指定给表中最后一个范围。



</div>

<div>

## <a name="in-this-section"></a>本节内容

[在 Lync Server 2013 中创建或修改未分配的号码范围](lync-server-2013-create-or-modify-an-unassigned-number-range.md)[在 Lync Server 2013 中创建公告](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

