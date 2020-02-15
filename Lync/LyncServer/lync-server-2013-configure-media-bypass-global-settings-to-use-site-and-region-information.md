---
title: 配置媒体旁路全局设置以使用站点和区域信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>在 Lync Server 2013 中配置媒体旁路全局设置以使用站点和区域信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

<div>


> [!NOTE]
> 本主题假定，对于希望媒体绕过中介服务器的特定站点或特定服务，已为从中介服务器到对等方（Internet 电话服务提供商的公用电话交换网 (PSTN) 网关、IP-PBX 或会话边界控制器）的所有中继连接配置媒体旁路。<BR>本主题还假设您已按照在 lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013 中创建或修改网络区域</A>中的步骤，在 lync server 2013 中<A href="lync-server-2013-create-or-modify-a-network-site.md">创建或修改网络站点</A>，并<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">将子网与 lync server 2013 中的网络站点关联</A>，以匹配网络区域、网络站点和子网配置的方式定义拓扑生成器中的所有中央站点和分支站点。 如果它们不匹配，则媒体旁路将会失败。



</div>

除了为与对等方关联的各个中继连接启用媒体旁路外，还必须配置全局设置。如果使用本主题中的步骤为媒体旁路配置全局设置，则假定以下一种或两种情况将影响您的配置：

  - 您*在*Lync 服务器终结点和任何对等方之间没有足够的连接，在中继连接上为其配置了媒体旁路。

  - 已启用用于带宽管理的呼叫允许控制 (CAC)。
    
    <div>
    

    > [!NOTE]
    > 有关呼叫允许控制和媒体旁路注意事项的详细信息，请参阅规划文档中的在<A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013 中的媒体旁路和中介服务器</A>中的 "呼叫对 PSTN 连接的呼叫允许控制" 部分。

    
    </div>

启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。

或者，如果要使用站点和区域信息来作出旁路决定，但不想启用呼叫允许控制，则请按照这些步骤进行操作。 在这种情况下，带宽限制的链接仍需要通过网络站点间策略表示，如在[Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)中所述。 实际带宽限制并不像本示例中那么重要，因为尚未启用呼叫允许控制。 相反，这些链接可用于对子网进行分区，以指定没有带宽限制的链接，从而使用媒体旁路。 请注意，这也适用于呼叫允许控制和媒体旁路都启用的情况。

此外，若要使回避功能正常工作，在拓扑生成器中定义的站点与在配置网络区域和网络站点时定义的站点之间的一致性必须一致。 例如，如果您在拓扑生成器中定义了一个仅部署了 PSTN 网关的分支站点，那么该分支站点必须配置有企业语音策略，这样分支站点用户才能通过 PSTN 路由其 PSTN 呼叫。分支站点上的网关。

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>为媒体旁路配置站点和区域信息

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“网络配置”****。

3.  双击表中的“全局”**** 配置。

4.  在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。

5.  单击“使用站点和区域配置”****。

6.  如有必要，请选中“为非映射站点启用旁路”**** 复选框。
    
    <div>
    

    > [!NOTE]
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。

    
    </div>

7.  单击“提交”****。

接下来，将子网添加到网络站点，如在[Lync Server 2013 中将子网与网络站点关联以实现媒体旁路的子网](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)中所述。 （有关将子网与网络站点相关联的实际过程，请参阅在[Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。）将所有子网与网络站点关联之后，将完成媒体旁路部署。

<div>


> [!IMPORTANT]
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。 有关详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 lync server 2013 中创建或修改网络区域</A>和<A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中创建或修改网络站点</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[将子网与 Lync Server 2013 中的媒体旁路的网络站点相关联](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

