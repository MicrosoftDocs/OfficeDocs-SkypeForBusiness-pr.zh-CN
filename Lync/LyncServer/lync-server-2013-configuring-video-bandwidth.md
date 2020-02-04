---
title: Lync Server 2013：配置视频带宽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>在 Lync Server 2013 中配置视频带宽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

Lync Server 2013 包括多个用于管理两方呼叫和多方会议的视频的设置。 部署 Lync Server 2013 时，应评估默认设置是否适用于你的组织，并根据需要进行修改。

本部分中所述的参数适用于两方呼叫和多方会议。 使用以下 cmdlet 之一查看或修改这些设置：

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

验证会议策略中的以下设置：

  - **VideoBitRateKb**   此设置指定由用户发送的视频的最大视频比特率，以千位每秒（kbps）为单位。 默认值为 50000 kbps。 有效值为0到50000。
    
    此设置分别适用于主视频和全景视频。
    
    示例：如果你指定 2000 kbps，则 Lync Server 可以为全景视频流的主视频流和 2000 kbps 发送 2000 kbps。
    
    <div>
    

    > [!NOTE]  
    > 对于全景视频，Lync 2013 终结点的最大视频网络带宽是 8000 kbps 的视频和 2500 kbps。 仅当接收或发送多个视频时，才达到这些最大值。 有关详细信息，请参阅<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中针对媒体流量的网络带宽要求</A>中的 "媒体流量网络使用情况" 部分。 本部分列出了所有支持的分辨率的最大和最典型视频流带宽。

    
    </div>

  - **TotalReceiveVideoBitRateKb**   此设置（Lync Server 2013 中的新增功能）指定客户端接收的所有视频流的最大比特率（以 kb/秒为单位）。 也就是说，它指定客户端可以接收的除全景视频流之外的所有视频流的合并总计。 例如，如果你指定 1500 kbps，则客户端最多可接收 1500 kbps 的视频，其中可能包含多个视频流或单个视频流。 此设置仅适用于 Lync Server 2013 客户端。
    
    **TotalReceiveVideoBitRateKb**的默认值为 50000 kbps。 如果库视图的**EnableMultiviewJoin**设置为 True，则不能在 420 kbps 以下设置**TotalReceiveVideoBitRateKb** 。 如果库视图的**EnableMultiviewJoin**设置为 False，则不能在 100 kbps 以下设置**TotalReceiveVideoBitRateKb** 。 如果**EnableMultiviewJoin**设置为 True，并且您将值设置为 420 kbps 的值，则这些值将默认为 "阈值" 值。 此阈值有助于防止意外的错误配置，可能导致用户体验不良。
    
    <div>
    

    > [!NOTE]  
    > 有关<STRONG>EnableMultiviewJoin</STRONG>设置的详细信息，请参阅<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中配置库视图</A>。

    
    </div>

  - **MaxVideoConferencingResolution**   此参数不再用于 lync server 2013 会议中的 lync server 2013 客户端。 Lync Server 2013 会议使用本部分前面所述的比特率控件。 此设置仍用于加入 Lync Server 2013 会议的旧客户端。 此参数确定由在 Lync Server 2013 上托管的用户组织的会议中的旧客户端所允许的最大分辨率。 也就是说，旧客户端的处理方式与以前版本的 Lync Server 或 Office 通信服务器相同。

除了适用于用户的会议策略设置外，评估媒体配置设置。 使用以下 cmdlet 之一查看或修改这些设置：

  - **CsMediaConfiguration**

  - **Set-CsMediaConfiguration**

  - **新-CsMediaConfiguration**

验证以下设置：

  - **MaxVideoRateAllowed**   此每个池的设置指定将在客户端终结点传输视频信号的最大速率。 它仅适用于以前版本的 Lync Server 客户端。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 客户端忽略此设置，而改为使用会议策略中的 TotalReceiveVideoBitRateKb 设置。

    
    </div>
    
    默认值为 HD720P。 有效值为 HD720p15M、VGA600K 和 CIF250K。
    
    示例：如果你指定 1500 kbps，则池中的所有旧客户端在两方或多方会议中最多可接收 1500 kbps 的视频。

以下过程是使用 Lync Server Management Shell 修改本部分中所述设置的示例。

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>修改视频设置的会议策略

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  在命令行中，运行以下 cmdlet 以编辑会议策略：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>修改旧客户端的媒体配置

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  在命令行中，运行以下 cmdlet 以编辑媒体配置：
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

