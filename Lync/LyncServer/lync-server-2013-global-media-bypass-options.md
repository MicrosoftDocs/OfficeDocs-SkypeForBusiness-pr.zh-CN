---
title: Lync Server 2013：全局媒体旁路选项
description: Lync Server 2013：全局媒体旁路选项。
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
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554548"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a>Lync Server 2013 中的全局媒体旁路选项

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

<div>


> [!NOTE]  
> 本主题假定您已将任何中继的媒体旁路配置为对等方 ( (PSTN) 网关、ip-pbx 或会话边界控制器 (SBC) 在 Internet 电话服务提供程序) 针对您希望媒体绕过中介服务器的特定站点或服务。



</div>

除了为与对等方关联的各个中继连接启用媒体绕过功能外，还必须在全局范围内启用媒体绕过功能。 全局媒体旁路设置可以指定始终尝试媒体绕过对 PSTN 的呼叫，或使用将子网映射到网络站点和网络区域时使用的媒体旁路，类似于呼叫允许控制（另一高级语音功能）所执行的操作。 如果启用了媒体旁路和呼叫允许控制，则在确定是否使用媒体旁路时，将自动使用为呼叫允许控制指定的网络区域、网络站点和子网信息。 这意味着，在启用呼叫允许控制时，不能指定始终尝试将媒体旁路用于对 PSTN 的呼叫。

本主题介绍如何将 Lync Server 控制面板和 Lync Server 命令行管理程序一起使用，以配置全局媒体旁路设置。

<div>


> [!NOTE]  
> 使用这些步骤配置媒体绕过时，假定客户端和中介服务器对等方（例如，SIP 中继提供商的 PSTN 网关、IP-PBX 或 SBC）之间的连接工作正常。 如果链接上有任何带宽限制，则媒体绕过无法应用于呼叫。 媒体绕过将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。 Microsoft 已使用认证的合作伙伴测试了一组 PSTN 网关和 SBCs，并且已通过 Cisco IP Pbx 进行了一些测试。 仅在统一通信开放互操作性计划– Lync Server 上列出的产品和版本支持媒体旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a>后续步骤：选择全局媒体绕过设置

在任何到特定站点或特定服务的对等方的中继连接上启用媒体绕过后，请使用以下内容：

  - 按在 [Lync server 2013 中配置媒体旁路以始终绕过中介服务器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)中所述，始终启用媒体旁路。

  - 或者，将媒体旁路配置为使用站点和区域信息，如在 [Lync Server 2013 中配置媒体旁路全局设置以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)中所述。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置具有媒体旁路功能的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[在 Lync Server 2013 中配置媒体旁路](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 中的媒体旁路和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

