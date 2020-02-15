---
title: Lync Server 2013：配置呼叫寄存通道表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbeb465bd9ac4e62a51ab562238db9a6c0828f99
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a>在 Lync Server 2013 中配置呼叫寄存通道表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-10_

呼叫寄存使用用于停车呼叫的轨道式。 在用户可以寄存和检索呼叫之前，您必须配置呼叫寄存通道表。 您需要指定您的组织将为停车呼叫保留的分机号码范围（概述），并通过指定处理每个范围的呼叫寄存池来定义这些区域的路由。 定义通道范围时，目标是具有足够的通道，以便不会在短时间内重用任何一个通道，但又不能有太多通道，以致于不得不限制用户或其他服务可使用的分机数量。 您可以为部署呼叫寄存应用程序的每个 Lync Server 池创建多个呼叫寄存通道范围。 每个呼叫寄存通道范围必须具有一个全局唯一的名称和一组唯一的分机号。

<div>


> [!IMPORTANT]  
> 每个通道范围包含的通道数通常不超过 100。范围可以更大一点，只要每个范围的通道数小于最大值 10,000 且每个池的通道数小于 50,000。如果范围太小，很快就会重用通道。



</div>

请使用虚拟分机（未向其分配用户或电话的分机）块作为通道范围。

<div>


> [!NOTE]  
> 不支持将直接向内拨号（已）号码分配为呼叫寄存通道表中的轨道编号。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

[在 Lync Server 2013 中创建或修改呼叫寄存通道范围](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

