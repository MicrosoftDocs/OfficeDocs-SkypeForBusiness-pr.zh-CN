---
title: 'Lync Server 2013: 管理响应组'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c0d8ac0fbfa8464fd0cd078fc90784eb9fdd3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a>在 Lync Server 2013 中管理响应组

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2018-02-01_

响应组是一种呼叫管理功能, 可让你对对特定区域 (如帮助桌面) 的呼叫进行排队, 然后将呼叫路由到指定的一组人员 (称为*代理*)。

若要管理响应组, 请配置代理组、队列和工作流, 以便在工程师应答它之前定义呼叫发生的时间。

<div>


> [!NOTE]  
> 如果你的响应组部署中的单个池中有300个以上的工作流, 最好使用 Lync Server Management Shell cmdlet 创建工作流。 如果使用 "响应组配置" 工具为具有超过300个工作流的池创建工作流, 则该网页需要花费很长时间才能加载。 通过队列间接与工作流关联的代理数也会在页面加载时产生比例影响。



</div>

本部分中的主题提供了可执行的任务的分步过程, 可用于在部署中自定义和维护响应组应用程序

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中管理响应组代理组](lync-server-2013-managing-response-group-agent-groups.md)

  - [在 Lync Server 2013 中管理响应组队列](lync-server-2013-managing-response-group-queues.md)

  - [在 Lync Server 2013 中管理响应组工作流](lync-server-2013-managing-response-group-workflows.md)

  - [在 Lync Server 2013 中管理应用程序级别的 "响应" 组设置](lync-server-2013-managing-application-level-response-group-settings.md)

  - [将响应组移动到 Lync Server 2013 中的新池](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [灾难期间在 Lync Server 2013 中管理响应组](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

