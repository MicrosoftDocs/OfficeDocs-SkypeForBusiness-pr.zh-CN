---
title: Lync Server 2013：部署企业语音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b2784c5cb04994004503010426ebc98763c0250
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531145"
---
# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中部署企业语音

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

Lync Server 2013，企业语音是 Lync Server 2013 基础结构的一部分。

部署企业语音时要求您：

<div id="sectionSection0" class="section">

1.  请参阅规划文档的 " [在 Lync Server 2013 中规划企业语音](lync-server-2013-planning-for-enterprise-voice.md) " 一节。

2.  最终确定使用此工作负荷部署功能和组件的计划。

3.  运行规划工具以设计反映部署决策的拓扑。

4.  如在部署文档的 [Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md) 中所述，在拓扑生成器中打开拓扑设计。
    
    <div>
    

    > [!NOTE]  
    > 拓扑生成器的安装是内部池的部署过程的一部分。 有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理工具</A> 。

    
    </div>

此外，还必须已在中央站点和分支站点上部署了 Lync Server、Enterprise Edition，这些分支站点与您选择部署的参考拓扑相对应。 只有在定义、发布和安装了至少一个内部池的文件之后，才能部署企业语音组件，并且必须使用拓扑生成器来定义和发布内部池。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

若要查看有关可以在其中部署企业语音服务器角色的示例的参考拓扑 (及其与其他 Lync Server 2013 服务器角色的关系) ，请参阅规划文档中的 " [Lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md) "。

若要查看说明并解释了示例呼叫允许控制部署（包括网络区域、网络站点和子网）的参考拓扑，请参阅规划文档中的 [示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 若要在中央站点部署企业语音，请继续阅读本节中的主题。 若要在分支站点部署企业语音，请跳过部署文档中的 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中的 "部署分支站点</A> "。



</div>

本节包含中介服务器并置到每个前端服务器或 Standard Edition Server 上的部署过程（推荐），以及独立的中介服务器池的部署过程。

如果您使用拓扑生成器定义和发布在每台前端服务器或 Standard Edition server 上 collocates 中介服务器的拓扑，则可以跳过以下内容，因为部署向导已在您为前端服务器池或 Standard Edition server 安装文件时自动为中介服务器安装了文件：

  - [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)

如果您使用拓扑生成器在独立池中定义和发布中介服务器，则可以使用以下内容：

  - 验证您的拓扑是否符合软件和环境先决条件，如 [Lync Server 2013 的企业语音先决条件](lync-server-2013-enterprise-voice-prerequisites.md)中所述。

</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - <span></span>  
    [Lync Server 2013 的企业语音先决条件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [在 Lync Server 2013 中部署中介服务器和定义对等方](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [在 Lync Server 2013 中导出和导入语音路由配置](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [在 Lync Server 2013 中发布对语音路由配置所做的挂起更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [部署本地 Exchange UM 以提供 Lync Server 2013 语音邮件](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [配置本地 Lync Server 2013 与 Exchange Online 集成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [关于 Lync Server 2013 中的网络区域、站点和子网](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [在 Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [在 Lync Server 2013 中配置呼叫允许控制](lync-server-2013-configure-call-admission-control.md)
    
      - [在 Lync Server 2013 中配置增强型9-1-1](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [在 Lync Server 2013 中配置媒体旁路](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [在 Lync Server 2013 中为用户启用企业语音](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署分支站点](lync-server-2013-deploying-branch-sites.md)  
[在 Lync Server 2013 中配置电话拨入式会议](lync-server-2013-configuring-dial-in-conferencing.md)  
[在 Lync Server 2013 中配置呼叫寄存](lync-server-2013-configuring-call-park.md)  
[在 Lync Server 2013 中配置未分配号码的公告](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[在 Lync Server 2013 中部署监控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

