---
title: 'Lync Server 2013: 部署企业语音'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中部署企业语音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-03_

Lync Server 2013, 企业语音是 Lync Server 2013 基础结构的一部分。

部署企业语音需要:

<div id="sectionSection0" class="section">

1.  查看规划文档的 " [Lync Server 2013 中的企业语音规划](lync-server-2013-planning-for-enterprise-voice.md)" 部分。

2.  最终确定要与此工作负荷一起部署的功能和组件的计划。

3.  运行规划工具以设计反映部署决策的拓扑。

4.  如在 "部署文档" 中的[Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)中所述, 在拓扑生成器中打开拓扑设计。
    
    <div>
    

    > [!NOTE]  
    > 拓扑生成器的安装是内部池的部署过程的一部分。 有关详细信息, 请参阅在部署文档中<A href="lync-server-2013-install-lync-server-administrative-tools.md">安装 Lync Server 2013 管理工具</A>。

    
    </div>

此外, 您还必须已在中心站点和分支站点上部署了 Lync Server、企业版和与您选择部署的参考拓扑对应的分支站点。 只有在为至少一个内部池定义、发布和安装文件后, 才能部署企业语音组件, 并且必须使用拓扑生成器定义和发布内部池。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

若要查看可在其中部署企业语音服务器角色的示例 (以及它们与其他 Lync Server 2013 服务器角色之间的关系) 的参考拓扑, 请参阅规划文档中[Lync server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)。

若要查看阐释和解释示例呼叫许可控制部署 (包括网络区域、网络站点和子网) 的参考拓扑, 请参阅[示例: 在 Lync Server 2013 的 "呼叫许可控制" 中收集您的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)规划文档。

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 若要在中心网站部署企业语音, 请继续阅读本部分中的主题。 若要在分支站点部署企业语音, 请跳过部署文档中<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中的 "部署分支站点</A>"。



</div>

本节包含中介服务器并置到每个前端服务器或 Standard Edition Server 上的部署过程（推荐），以及独立的中介服务器池的部署过程。

如果你使用拓扑生成器定义和发布在每台前端服务器或标准版服务器上 collocates 中介服务器的拓扑, 则可以跳过以下内容, 因为部署向导已自动安装了文件在安装前端服务器池或标准版服务器的文件时, 中介服务器:

  - [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)

如果你使用拓扑生成器在独立池中定义和发布中介服务器, 你可以使用以下内容:

  - 验证你的拓扑是否符合[Lync Server 2013 的企业语音先决条件](lync-server-2013-enterprise-voice-prerequisites.md)中所述的软件和环境先决条件。

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - <span></span>  
    [Lync Server 2013 的企业语音先决条件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [在 Lync Server 2013 中部署中介服务器和定义对等方](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [在 Lync Server 2013 中配置语音策略、PSTN 使用记录和语音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [在 Lync Server 2013 中导出和导入语音路由配置](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [将挂起的更改发布到 Lync Server 2013 中的语音路由配置](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

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
    
      - [在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [在 Lync Server 2013 中配置呼叫许可控制](lync-server-2013-configure-call-admission-control.md)
    
      - [在 Lync Server 2013 中配置增强型 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [在 Lync Server 2013 中配置媒体绕过](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [在 Lync Server 2013 中启用企业语音用户](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署分支站点](lync-server-2013-deploying-branch-sites.md)  
[在 Lync Server 2013 中配置拨入式会议](lync-server-2013-configuring-dial-in-conferencing.md)  
[在 Lync Server 2013 中配置呼叫寄存](lync-server-2013-configuring-call-park.md)  
[在 Lync Server 2013 中配置未分配号码的通知](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[在 Lync Server 2013 中部署监视](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

