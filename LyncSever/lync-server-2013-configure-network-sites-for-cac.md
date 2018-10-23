---
title: 在 Lync Server 2013 中为 CAC 配置网络站点
TOCTitle: 在 Lync Server 2013 中为 CAC 配置网络站点
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412840(v=OCS.15)
ms:contentKeyID: 49313960
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为 CAC 配置网络站点

 

_**上一次修改主题：** 2012-09-05_

> [!IMPORTANT]  
> 如果您已为 E9-1-1 或媒体旁路创建网络站点，则可以使用 <strong>Set-CsNetworkSite</strong> cmdlet 修改现有的网络站点，以应用带宽策略配置文件。有关如何修改网络站点的示例，请参阅<a href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络站点</a>。


*网络站点*是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。使用以下过程创建网络站点，这些网络站点与 CAC 的示例网络拓扑中的网络站点一致。这些过程显示如何创建并配置受 WAN 带宽限制，并因此需要用于限制实时音频或视频流量的带宽策略的网络站点。

在示例 CAC 部署中，北美区域有六个站点。其中三个站点受 WAN 带宽限制：里诺、波特兰和阿尔布开克。其他三个站点*不*受 WAN 带宽限制：纽约、芝加哥和底特律。有关如何创建或修改其他网络站点的示例，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)。

要查看示例网络拓扑，请参阅规划文档中的[示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

> [!NOTE]  
> 在以下过程中，Lync Server 命令行管理程序用于创建网络站点。有关使用 Lync Server 控制面板创建网络站点的详细信息，请参阅<a href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络站点</a>。



## 为呼叫允许控制创建网络站点

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行 **New-CsNetworkSite** cmdlet 以创建网络站点并将相应带宽策略配置文件应用到每个站点。例如，运行：
    
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link

       &nbsp;
    
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link

       &nbsp;
    
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link

3.  要为整个示例拓扑完成网络站点的创建，请针对 EMEA 和 APAC 区域中受带宽限制的网络站点重复步骤 2。

