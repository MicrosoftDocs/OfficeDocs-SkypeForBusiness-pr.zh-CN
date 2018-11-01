---
title: Lync Server 2013：高级企业语音功能的网络设置
TOCTitle: 高级企业语音功能的网络设置
ms:assetid: 7f6de9e4-c8a4-44e4-8d14-21fe8c45283a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398637(v=OCS.15)
ms:contentKeyID: 49313392
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中高级企业语音功能的网络设置

 

_**上一次修改主题：** 2012-10-10_

Lync Server 有以下三个高级 企业语音功能：呼叫允许控制 (CAC)、紧急服务 (E9-1-1) 和媒体旁路。这些功能针对网络区域、网络站点以及 Lync Server 拓扑中每个子网与网络站点的关联共享特定的配置要求。有关这些功能的部署规划的详细信息，请参阅：

  - [在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)

  - [在 Lync Server 2013 中规划紧急服务 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)

  - [在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

有关部署各个功能的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中部署高级企业语音功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)。

本主题概述了所有三个高级 企业语音功能的通用配置要求。

## 网络区域

网络区域是仅在呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。

> [!NOTE]  
> 网络区域与 Lync Server 电话拨入式会议区域不同，后者需要将电话拨入式会议访问号码与一个或多个 Lync Server 拨号计划相关联。有关电话拨入式会议区域的详细信息，请参阅规划文档中的 <a href="lync-server-2013-dial-in-conferencing-requirements.md">电话拨入式会议要求</a>。



CAC 要求每个网络区域都有一个关联的 Lync Server 中央站点，此站点管理区域内的媒体流量（即，根据已配置的有关是否可以建立实时音频或视频会话的策略来做出决策）。 Lync Server 中央站点不代表地理位置，而是代表配置为一个池或一组池的服务器的逻辑分组。有关中央站点的详细信息，请参阅规划文档中的 [Lync Server 2013 中的参考拓扑](lync-server-2013-reference-topologies.md)。另请参阅可支持性文档中的 [Lync Server 2013 中支持的拓扑](lync-server-2013-supported-topologies.md)。

要配置网络区域，可以使用 Lync Server 控制面板的“网络配置”部分中的“区域”选项卡，或者运行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion**Lync Server 命令行管理程序 cmdlet。如需获得相关说明，请参阅部署文档中的[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)，或者参考 Lync Server 命令行管理程序文档。

所有三个高级 企业语音功能共享相同的网络区域定义。如果已经为某个功能创建了网络区域，则不必再为其他功能新建网络区域。但是，可能需要修改现有的网络区域定义，以应用特定于功能的设置。例如，如果已为 E9-1-1（它不要求有关联的中央站点）创建网络区域，稍后部署呼叫允许控制，则必须修改每个网络区域定义以指定中央站点。

要将 Lync Server 中央站点与某个网络区域相关联，请指定中央站点名称，可以使用 Lync Server 控制面板的“网络配置”部分，也可以通过运行 **New-CsNetworkRegion** 或 **Set-CsNetworkRegion**Lync Server 命令行管理程序 cmdlet 来完成。如需获得相关说明，请参阅部署文档中的[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)，或者参考 Lync Server 命令行管理程序文档。

## 网络站点

网络站点代表地理位置，例如分支机构、地区办事处或总部。每个网络站点都必须与特定网络区域相关联。

> [!NOTE]  
> 网络站点仅供高级 企业语音功能使用。网络站点与您在 Lync Server 拓扑中配置的分支站点不同。有关分支站点的详细信息，请参阅规划文档中的 <a href="lync-server-2013-reference-topologies.md">Lync Server 2013 中的参考拓扑</a>。另请参阅可支持性文档中的 <a href="lync-server-2013-supported-topologies.md">Lync Server 2013 中支持的拓扑</a>。



要配置网络站点并将其与网络区域相关联，可以使用 Lync Server 控制面板的“网络配置”部分，或者运行 Lync Server 命令行管理程序**New-CsNetworkSite** 或 **Set-CsNetworkSite** cmdlet。如需获得相关说明，请参阅部署文档中的[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)，或者参考 Lync Server 命令行管理程序文档。

## 标识 IP 子网

对于每个网络站点，您将需要和网络管理员一起确定分配给每个网络站点的 IP 子网。如果网络管理员已经将 IP 子网组织到网络区域和网络站点中，则您的工作将大为简化。

例如，可为北美区域中的纽约站点分配以下 IP 子网：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。如果通常在底特律工作的 Bob 出差到纽约办事处接受培训，当他打开计算机并连接到网络时，他的计算机将获取分配给纽约的四个范围之一中的 IP 地址，例如 172.29.80.103。

> [!WARNING]  
> 网络配置期间服务器上指定的 IP 子网必须与客户端计算机提供的格式匹配，这样才能正确地用于媒体旁路。 Lync 客户端将占用其本地 IP 地址并使用关联子网掩码屏蔽 IP 地址。确定与每个客户端相关联的绕过 ID 时，注册器将与每个网络站点相关联的 IP 子网列表和客户端提供的子网进行对比，以检查是否完全匹配。因此，网络配置期间应在服务器上输入实际子网而非虚拟子网，这一点十分重要。（如果是部署呼叫允许控制而非媒体旁路，那么即使配置虚拟子网，呼叫允许控制也将正常工作。）<br />
> 例如，如果 Lync 客户端登录到 IP 地址为 172.29.81.57、IP 子网掩码为 255.255.255.0 的计算机上，该客户端将请求与子网 172.29.81.0 关联的绕过 ID。如果子网定义为 172.29.0.0/16，那么即使客户端属于虚拟子网，注册器也不会将此看做匹配，因为注册器会专门查找子网 172.29.81.0。因此，管理员准确输入 Lync 客户端（网络配置期间静态或通过动态主机配置协议 (DHCP) 为子网设置的）提供的子网十分重要。


## 将子网与网络站点相关联

企业网络中的每个子网都必须与网络站点相关联（即每个子网需要与一个地理位置相关联）。通过子网关联，高级 企业语音功能可以在地理位置上找到终结点。例如，通过找到终结点，CAC 可以调节往返于网络站点的实时音频和视频数据流。

要将子网与网络站点相关联，可以使用 Lync Server 控制面板的“网络配置”部分，也可以使用 Lync Server 命令行管理程序。如需获得相关说明，请参阅部署文档中的[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)，或者参考 Lync Server 命令行管理程序文档。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中规划紧急服务 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)  
[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

