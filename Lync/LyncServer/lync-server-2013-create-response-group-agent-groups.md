---
title: Lync Server 2013：创建响应组代理组
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be70adae85256178defca0269e6663bad76dabfc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>创建响应组代理组 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-12_

创建代理组时要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。

必须登录和注销组（不同于登录或注销 Lync Server）的代理称为*正式代理*。 正式代理必须登录到组，然后才能接收路由至该组的呼叫。 这对于以兼职形式应答组中的呼叫的代理很有用。 正式代理通过单击 Lync 2013 中的菜单项来打开 Windows Internet Explorer Internet 浏览器并显示网页控制台，以登录和注销其组。

不登录到组或从组注销的代理称为*非正式代理*。 非正式代理在登录 Lync Server 时自动登录到组，并且无法注销组。

<div>


> [!NOTE]  
> 只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

[在 Lync Server 2013 中创建或修改代理组](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

