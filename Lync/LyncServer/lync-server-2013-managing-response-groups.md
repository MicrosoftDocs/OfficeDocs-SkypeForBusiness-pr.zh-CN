---
title: Lync Server 2013：管理响应组
description: Lync Server 2013：管理响应组。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138ece386d55895893402e5a1fdead58790504f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572628"
---
# <a name="managing-response-groups-in-lync-server-2013"></a>在 Lync Server 2013 中管理响应组

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2018-02-01_

响应组是一项呼叫管理功能，通过该功能可以将拨打至特定区域（如技术支持）的呼叫置于队列中，然后将呼叫路由至指定的用户组（称为*代理*）。

要管理响应组，请对代理组、队列和工作流进行配置，以定义从发出呼叫到代理应答该呼叫期间对呼叫执行的操作。

<div>


> [!NOTE]  
> 如果您的响应组部署中的一个池中的工作流多于300个，最好使用 Lync Server 命令行管理程序 cmdlet 来创建工作流。 如果使用响应组配置工具为包含 300 个以上工作流的池创建工作流，加载网页将需要很长时间。 通过队列间接与工作流相关联的代理数量在页面加载上也有一个比例的影响。



</div>

本节中的主题提供了可执行的任务的分步过程，可用于自定义和维护部署中的响应组应用程序

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中管理响应组代理组](lync-server-2013-managing-response-group-agent-groups.md)

  - [在 Lync Server 2013 中管理响应组队列](lync-server-2013-managing-response-group-queues.md)

  - [在 Lync Server 2013 中管理响应组工作流](lync-server-2013-managing-response-group-workflows.md)

  - [在 Lync Server 2013 中管理应用程序级响应组设置](lync-server-2013-managing-application-level-response-group-settings.md)

  - [将响应组移动到 Lync Server 2013 中的新池](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [在灾难发生期间管理 Lync Server 2013 中的响应组](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

