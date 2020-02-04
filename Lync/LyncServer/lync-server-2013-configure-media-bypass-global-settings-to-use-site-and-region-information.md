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
ms.openlocfilehash: ac820c444f894aabf060c06d6f034f7d92b696c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a>Configure media bypass global settings in Lync Server 2013 to use site and region information

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

<div>


> [!NOTE]
> 本主题假定你已将来自中介服务器的任何主干连接的所有主干连接配置为 "Internet 电话服务" （公共交换电话网络（PSTN）网关、IP PBX 或会话边界控制器（SBC））的媒体旁路您希望媒体绕过中介服务器的特定网站或服务的提供商（ITSP）。<BR>本主题还假设你已按照在 lync server <A href="lync-server-2013-create-or-modify-a-network-region.md">2013 中创建或修改网络区域</A>中的步骤（在 lync server 中创建或修改网络<A href="lync-server-2013-create-or-modify-a-network-site.md">2013 站点</A>，以及<A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">将子网与 lync server 2013 中的网络站点相关联</A>），在拓扑结构生成器中定义了所有中心网站和分支网站的方式。 如果它们不匹配，则 "媒体绕过" 将不会成功。



</div>

除了为与对等相关联的单个中继连接启用媒体旁路外，还必须配置全局设置。 如果你使用本主题中的步骤来配置媒体绕过的全局设置，则假设以下一种或两种情况会影响你的配置：

  - 您*的*Lync 服务器终结点和任何对等的用户在中继连接上配置了媒体旁路的任何对等连接之间没有连接良好的连接。

  - 启用了 "带宽管理" 的 "呼叫许可控制（CAC）"。
    
    <div>
    

    > [!NOTE]
    > 有关呼叫许可控制和媒体绕过的注意事项的详细信息，请参阅规划文档中<A href="lync-server-2013-media-bypass-and-mediation-server.md">Lync server 2013</A>中的 "呼叫对 PSTN 连接的接入控制" 部分。

    
    </div>

启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。

或者，如果你想要使用现场和区域信息进行跳过决策，但不想启用呼叫许可控制，请按照以下步骤操作。 在这种情况下，带宽受限链接仍需要通过网络站点间策略来表示，如在[Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)中所述。 在这种情况下，实际带宽限制不太重要，因为通话许可控制尚未启用。 相反，这些链接用于对子网进行分区以指定那些没有带宽限制的子网，因此可以使用媒体旁路。 请注意，当同时启用 "呼叫许可控制" 和 "媒体旁路" 时，也是如此。

此外，若要使 "回避" 正常工作，在拓扑生成器中定义的站点和在配置网络区域和网络站点时定义的站点之间必须保持一致。 例如，如果您在拓扑生成器中定义了一个已部署 PSTN 网关的分支站点，则必须使用企业语音策略配置分支网站，以便分支站点用户通过 PSTN 路由其 PSTN 呼叫分支站点上的网关。

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a>为媒体旁路配置站点和区域信息

1.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”****。

3.  双击表中的“全局”**** 配置。

4.  在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。

5.  单击“使用站点和区域配置”****。

6.  如有必要，请选中“为非映射站点启用旁路”**** 复选框。
    
    <div>
    

    > [!NOTE]
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。

    
    </div>

7.  单击“**提交**”。

接下来，将子网添加到网络站点，如[将子网与网络站点关联到 Lync Server 2013 中的 "媒体绕过](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)" 中所述。 （有关将子网与网络站点相关联的实际过程，请参阅[将子网与 Lync Server 2013 中的网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)。）将所有子网与网络站点关联后，将完成 "媒体绕过部署"。

<div>


> [!IMPORTANT]
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。 有关详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中创建或修改网络区域</A>，并<A href="lync-server-2013-create-or-modify-a-network-site.md">在 lync Server 2013 中创建或修改网络网站</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[将子网与 Lync Server 2013 中的媒体绕过的网络站点关联](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

