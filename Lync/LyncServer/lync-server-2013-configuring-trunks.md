---
title: Lync Server 2013：配置中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80f5bf646dbed73beb7d9dd102e7e7b2bf802e49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>在 Lync Server 2013 中配置中继

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

作为企业语音部署的一部分，您可以在中介服务器和以下一个或多个对等方之间配置中继，为企业语音客户端和组织中的设备提供公共交换电话网络（PSTN）连接：

  - 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接

  - PSTN 网关

  - 专用交换机 (PBX)

有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)。

<div>


> [!IMPORTANT]  
> 在开始中继配置之前，请确认已创建了拓扑，并且已将中介服务器及其对等方配置为与另一个关联。 有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">拓扑生成器中定义网关在 Lync Server 2013</A>中。



</div>

<div>


> [!NOTE]  
> 作为中继配置的一部分，您可以启用 Lync Server 2013 媒体旁路功能，该功能使媒体能够绕过中介服务器。 配置中继时可以启用媒体旁路，也可以不启用媒体旁路，但我们强烈建议您启用该功能。 有关详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中规划媒体旁路</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的多中继支持](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 中的中继间路由](lync-server-2013-inter-trunk-routing.md)

  - [在 Lync Server 2013 中查看中继配置信息](lync-server-2013-view-trunk-configuration-information.md)

  - [在 Lync Server 2013 中配置具有媒体旁路功能的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [在 Lync Server 2013 中配置无媒体旁路功能的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [在 Lync Server 2013 中创建一个新的中继配置设置集合](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [删除 Lync Server 2013 中现有的 SIP 中继配置设置集合](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中修改 SIP 中继配置设置](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中测试 SIP 中继配置设置](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中查看有关各个 SIP 中继的信息](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 的拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)  
[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

