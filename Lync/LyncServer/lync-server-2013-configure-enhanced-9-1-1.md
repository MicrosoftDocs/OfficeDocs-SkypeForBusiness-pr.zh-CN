---
title: Lync Server 2013：配置增强型 9-1-1
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e171d2d3d72675d194a8272dfca1e2f24b8fa150
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>在 Lync Server 2013 中配置增强型 9-1-1

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-24_

增强型 9-1-1 (E9-1-1) 是一种紧急通知功能，可以将呼叫者的电话号码与某个市政地址或街道地址相关联。使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。

若要支持 E9-1，Lync Server 2013 必须能够正确地将某个位置与客户端相关联，并确保使用此信息将紧急呼叫路由到最近的 PSAP。

有关规划 E9 部署的详细信息，请参阅[Lync Server 2013 中的 "规划紧急服务（E9-1-1）](lync-server-2013-planning-for-emergency-services-e9-1-1.md)"。

<div>


> [!IMPORTANT]  
> Lync Server 2013 仅支持美国境内的 E9-1。 若要部署 E9，您需要配置到合格的 E9 服务提供商的 SIP 连接，或将紧急位置识别号码（ELIN）网关部署到基于交换机的公共电话（PSTN）的 E9-1-1 服务提供商。 有关详细信息，请参阅<A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Lync server 2013 中的增强9-1-1 （E9-1）和中介服务器</A>。 有关配置中继连接的详细信息，请参阅<A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">在 Lync Server 2013 中使用 "媒体绕过" 配置主干</A>。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置 E9-1 个语音路由](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)

  - [在 Lync Server 2013 中配置 E9-1 的网站信息](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [在 Lync Server 2013 中配置高级 E9-1-1 功能](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

