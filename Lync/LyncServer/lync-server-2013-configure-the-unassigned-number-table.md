---
title: Lync Server 2013：配置未分配号码表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a6f1db9f933394a8d8c33a6e002bb52e56341b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a>在 Lync Server 2013 中配置未分配号码表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

在 Lync Server 2013 中，您可以指定对组织有效但未分配给用户或电话的电话号码传入呼叫发生的情况。 呼叫者可以收听消息或将消息路由到其他目标，或同时实现这两者。

配置未分配号码表的方式取决于要使用该表的方式。可以使用组织的所有有效分机、仅使用未分配的分机或使用这两类号码的组合来配置该表。未分配号码表可以同时包含已分配和未分配的号码，但仅当呼叫者拨打当前未分配号码时，才会调用该表。如果在未分配号码表中包含所有有效分机，则可以指定某人离开组织时所执行的操作，而无需重新配置该表。如果在该表中包含未分配的分机，则可以为特定号码修改所执行的操作。例如，如果更改客户服务台的分机，则可以在该表中包含旧的客户服务号码，然后将其分配给提供新号码的通知。

<div>


> [!IMPORTANT]  
> 在配置未分配号码表之前，系统必须已定义通知或已设置 Exchange 统一消息（UM）自动助理。



</div>

<div>


> [!TIP]  
> 当某人呼叫未分配的号码时，Lync Server 将从上到下搜索未分配号码表，并使用第一个匹配的范围。 因此，要在万不得已时执行的操作应指定给表中最后一个范围。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

[在 lync server 2013 中创建或修改未分配号码范围在](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 2013 中创建通知](lync-server-2013-create-an-announcement.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

