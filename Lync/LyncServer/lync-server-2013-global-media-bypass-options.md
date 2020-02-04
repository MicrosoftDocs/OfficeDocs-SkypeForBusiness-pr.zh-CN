---
title: Lync Server 2013：全局媒体绕过选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013 中的全局媒体绕过选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

<div>


> [!NOTE]  
> 本主题假设你已针对特定网站或服务将针对任何中继的任何将媒体绕过配置到 Internet 电话服务提供商的任何对等（公共交换电话网络（PSTN）网关、IP PBX 或会话边界控制器（SBC））您希望媒体绕过中介服务器。



</div>

除了为与对等方关联的各个中继连接启用媒体旁路功能外，还必须在全局范围内启用媒体旁路功能。全局媒体旁路设置可以指定始终为对 PSTN 的呼叫尝试媒体旁路，或者指定通过将子网映射到网络站点和网络区域来使用媒体旁路，这与呼叫允许控制（另一高级语音功能）所执行的操作类似。同时启用媒体旁路和呼叫允许控制后，在确定是否使用媒体旁路时，会自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。这意味着，启用呼叫允许控制后无法指定始终为对 PSTN 的呼叫尝试媒体旁路。

本主题介绍了如何将 Lync Server 控制面板和 Lync Server Management Shell 一起使用来配置全局媒体绕过设置。

<div>


> [!NOTE]  
> 使用这些步骤配置媒体旁路时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。 如果链接上有任何带宽限制，则媒体旁路无法应用于呼叫。 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。 只有在统一通信中列出的产品和版本才支持媒体绕开互操作性计划- <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>Lync Server at。



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>后续步骤：选择全局媒体绕过设置

在针对特定网站或服务对等方的任何中继连接上启用了媒体旁路后，请使用以下内容之一：

  - 按 "在[Lync server 2013 中配置媒体旁路](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)" 中所述，始终启用媒体绕过，以始终绕过中介服务器。

  - 或者，将媒体旁路配置为使用网站和区域信息，如在[Lync Server 2013 中配置媒体绕过全局设置以使用网站和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[在 Lync Server 2013 中配置媒体绕过](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的媒体绕过和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

