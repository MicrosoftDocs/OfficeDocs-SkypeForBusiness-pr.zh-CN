---
title: 为 CAC 配置网络区域
TOCTitle: 为 CAC 配置网络区域
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399051(v=OCS.15)
ms:contentKeyID: 49314620
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 CAC 配置网络区域

 

_**上一次修改主题：** 2012-09-21_

> [!IMPORTANT]  
> 如果已为 E9-1-1 或媒体旁路创建网络区域，则可以通过使用 <strong>Set-CsNetworkRegion</strong> cmdlet 添加特定于呼叫允许控制 (CAC) 的设置来修改现有网络区域。有关如何修改网络区域的示例，请参阅<a href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</a>。


“网络区域”是在配置 CAC、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。使用以下过程创建网络区域，这些网络区域与 CAC 的示例网络拓扑中的网络区域一致。要查看示例网络拓扑，请参阅规划文档中的[示例：在 Lync Server 2013 中收集呼叫允许控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

CAC 的示例网络拓扑有三个区域：北美、EMEA 和 APAC。每个区域都有一个指定的中央站点。对于 North America 区域，指定的中央站点名为 CHICAGO。以下过程显示了如何使用 **New-CsNetworkRegion** cmdlet 创建 North America 区域的示例。

> [!NOTE]  
> 在以下过程中，使用 Lync Server 命令行管理程序创建网络区域。有关使用 Lync Server 控制面板创建网络区域的详细信息，请参阅<a href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</a>。



## 创建呼叫允许控制的网络区域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  对于每个需要创建的区域，运行 **New-CsNetworkRegion** cmdlet。例如，要创建 North America 区域，请运行：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  重复步骤 2 以创建网络区域、EMEA 和 APAC。

