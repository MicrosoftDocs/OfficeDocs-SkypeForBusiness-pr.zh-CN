---
title: 在 Lync Server 2013 中配置视频带宽
TOCTitle: 在 Lync Server 2013 中配置视频带宽
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204842(v=OCS.15)
ms:contentKeyID: 49312691
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置视频带宽

 

_**上一次修改主题：** 2012-10-02_

Lync Server 2013 包括用于管理双方呼叫和多方会议的视频的多个设置。在部署 Lync Server 2013 时，您应评估默认设置是否适合您的组织，并根据需要修改这些设置。

本节中描述的参数适用于双方呼叫和多方会议。可使用下列 cmdlet 之一来查看或修改这些设置：

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

验证会议策略中的下列设置：

  - **VideoBitRateKb**   此设置指定用户发送的视频所使用的最大视频比特率（以 kbps 为单位）。默认值为 50000 kbps。有效值介于 0 和 50000 之间。
    
    此设置单独应用于主要视频和全景视频。
    
    示例：如果您指定 2000 kbps，则 Lync Server 可以将 2000 kbps 用于发送主要视频流，2000 kbps 用于发送全景视频流。
    
    > [!NOTE]  
    > 对于主要视频和全景视频而言，Lync 2013 终结点的最大视频网络带宽分别为 8000 kbps 和 2500 kbps。仅当接收或发送多个视频时才达到这些最大值。有关详细信息，请参阅<a href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中的媒体流量的网络带宽要求</a>中的“媒体流量网络使用情况”一节。本节列出了所有受支持的分辨率的最大和典型视频流带宽。
    


  - **TotalReceiveVideoBitRateKb**   此设置是 Lync Server 2013 中的一项新设置，它指定了客户端接收的所有视频流的允许的最大比特率（以 Kbps 为单位）。也就是说，此设置指定了客户端可接收的所有视频流（全景视频流除外）的合并总计。例如，如果您指定 1500 kbps，则客户端最多可接收 1500 kbps 的视频，此视频可能包含多个视频流或单个视频流。此设置仅适用于 Lync Server 2013 客户端。
    
    **TotalReceiveVideoBitRateKb** 的默认值是 50000 kbps。如果将库视图的 **EnableMultiviewJoin** 设置设为 True，则不得将 **TotalReceiveVideoBitRateKb** 设置为小于 420 kbps 的值。如果将库视图的 **EnableMultiviewJoin** 设置设为 False，则不得将 **TotalReceiveVideoBitRateKb** 设置为小于 100 kbps 的值。如果将 **EnableMultiviewJoin** 设为 True 并将值设置为小于 420 kbps 的值，则这些值将默认为阈值。此阈值可帮助阻止可能会导致极差的用户体验的意外配置错误。
    
    > [!NOTE]  
    > 有关 <strong>EnableMultiviewJoin</strong> 设置的详细信息，请参阅<a href="lync-server-2013-configuring-gallery-view.md">配置图库视图</a>。
    


  - **MaxVideoConferencingResolution**   此参数不再用于 Lync Server 2013 会议中的 Lync Server 2013 客户端。Lync Server 2013 会议使用本节前面所述的比特率控制。此设置仍用于加入 Lync Server 2013 会议的旧客户端。此参数确定由驻留在 Lync Server 2013 上的用户组织的会议中的旧客户端可使用的最大分辨率。也就是说，将按照在早期版本的 Lync Server 或 Office Communications Server 中处理旧客户端的方式来处理它。

除了适用于用户的会议策略设置之外，还将评估媒体配置设置。可使用下列 cmdlet 之一来查看或修改这些设置：

  - **Get-CsMediaConfiguration**

  - **Set- CsMediaConfiguration**

  - **New- CsMediaConfiguration**

验证以下设置：

  - **MaxVideoRateAllowed**   这项针对每个池的设置指定客户端终结点允许的最大视频信号传输速率。它仅适用于 Lync Server 客户端的早期版本。
    
    > [!NOTE]  
    > Lync Server 2013 客户端将忽略此设置并改用会议策略中的 TotalReceiveVideoBitRateKb 设置。
    
    
    默认值为 HD720P。有效值为 HD720p15M、VGA600K 和 CIF250K。
    
    示例：如果您指定 1500 kbps，则池中的所有旧客户端最多可接收双方或多方会议中的 1500 kbps 的视频。

下列过程是使用 Lync Server 命令行管理程序修改本节中所述的设置的示例。

## 修改视频设置的会议策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行处，运行以下 cmdlet 以编辑会议策略：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

## 修改旧客户端的媒体配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行处，运行以下 cmdlet 以编辑媒体配置：
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

