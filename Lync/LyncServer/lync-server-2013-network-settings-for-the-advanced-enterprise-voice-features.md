---
title: 'Lync Server 2013: 用于高级企业语音功能的网络设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network settings for the advanced Enterprise Voice features
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398637(v=OCS.15)
ms:contentKeyID: 48184632
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d633d111e9df09cde57b91f32f4592b7f80c9f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-settings-for-the-advanced-enterprise-voice-features-in-lync-server-2013"></a>Network settings for the advanced Enterprise Voice features in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-10_

Lync 服务器具有三个高级的企业语音功能: 呼叫许可控制 (CAC)、紧急服务 (E9-1) 和媒体旁路。 这些功能在 Lync Server 拓扑中与网络站点共享网络区域、网络站点和每个子网关联的某些配置要求。 有关规划部署这些功能的详细信息, 请参阅:

  - [在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)

  - [在 Lync Server 2013 中规划紧急服务 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

有关部署这些功能的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)"。

本主题概述了所有三种高级企业语音功能所共有的配置要求。

<div>

## <a name="network-regions"></a>网络区域

网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。

<div>


> [!NOTE]  
> 网络区域与 Lync Server 拨入式会议区域不同, 后者是将电话拨入式会议访问号码与一个或多个 Lync Server 拨号计划相关联所必需的。 有关电话拨入式会议区域的详细信息, 请参阅规划文档中<A href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的电话拨入式会议要求</A>。



</div>

CAC 要求每个网络区域都有一个关联的 Lync Server 中心网站, 该网站管理区域内的媒体流量 (即, 它根据已配置的策略做出决策, 有关实时音频或视频会话是否可以被建立)。 Lync Server 中心网站不表示地理位置, 而是指配置为池或池集的逻辑服务器组。 有关中心网站的详细信息, 请参阅规划文档中[Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)。 另请参阅支持文档中的[Lync Server 2013 中支持的拓扑](lync-server-2013-supported-topologies.md)。

若要配置网络区域, 可以使用 Lync Server 控制面板的 "**网络配置**" 部分中的 "**区域**" 选项卡, 或者运行**CsNetworkRegion**或**CsNetworkRegion** Lync server 命令行管理程序powershell. 有关说明, 请参阅在部署文档中的[Lync server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md), 或者参阅 Lync Server Management Shell 文档。

所有三个高级企业语音功能都共享相同的网络区域定义。 如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。 但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。 例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。

若要将 Lync Server 中央站点与网络区域相关联, 请指定中心网站名称, 方法是使用 Lync Server 控制面板的 "**网络配置**" 部分, 或者运行 " **CsNetworkRegion** " 或 "**设置" CsNetworkRegion**Lync Server Management Shell cmdlet。 有关说明, 请参阅在部署文档中的[Lync server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md), 或者参阅 Lync Server Management Shell 文档。

</div>

<div>

## <a name="network-sites"></a>网络站点

网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。

<div>


> [!NOTE]  
> 网络站点仅由高级企业语音功能使用。 它们与您在 Lync Server 拓扑中配置的分支站点不同。 有关分支站点的详细信息, 请参阅规划文档中<A href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的参考拓扑</A>。 另请参阅支持文档中的<A href="lync-server-2013-supported-topologies.md">Lync Server 2013 中支持的拓扑</A>。



</div>

若要配置网络网站并将其与网络区域关联, 你可以使用 Lync Server 控制面板的 "**网络配置**" 部分, 或者运行 Lync Server Management Shell **CsNetworkSite**或**Set CsNetworkSite**powershell. 有关详细信息, 请参阅在部署文档的[Lync server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md), 或者参阅 Lync Server Management Shell 文档。

</div>

<div>

## <a name="identify-ip-subnets"></a>标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。

<div>


> [!WARNING]  
> 在服务器上的网络配置期间指定的 IP 子网必须与客户端计算机提供的格式匹配, 才能正确用于媒体绕过。 Lync 客户端使用其本地 IP 地址并使用关联的子网掩码屏蔽 IP 地址。 确定与每个客户端关联的绕过 ID 时, 注册机构会将与每个网络站点相关联的 IP 子网的列表与客户端提供的子网进行比较, 以精确匹配。 出于此原因, 在服务器上的网络配置期间输入的子网必须是实际的子网, 而不是虚拟子网。 (如果您部署了 "呼叫许可控制", 但没有媒体旁路, 则即使配置了虚拟子网, 呼叫许可控制也能正常运行。)<BR>例如, 如果 Lync 客户端使用 ip 地址为255.255.255.0 的 ip 地址在计算机上登录, 则它将请求与子网172.29.81.0 关联的绕过 ID。 如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。 因此, 管理员应严格按照 Lync 客户端提供的方式输入子网 (这些子网是在网络配置期间使用子网进行配置的, 无论是静态还是动态主机配置协议 (DHCP)。)



</div>

</div>

<div>

## <a name="associating-subnets-with-network-sites"></a>将子网与网络站点相关联

企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。 此子网关联使高级企业语音功能能够在地理位置找到终结点。 例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。

若要将子网与网络站点关联, 您可以使用 Lync Server 控制面板的 "**网络配置**" 部分, 也可以使用 Lync Server 命令行管理程序。 有关说明, 请参阅在部署文档中[将子网与 Lync server 2013 中的网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md), 或者参阅 Lync Server Management Shell 文档。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中规划紧急服务 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

