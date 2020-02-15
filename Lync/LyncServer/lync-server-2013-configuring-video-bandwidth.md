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
ms.openlocfilehash: 2f1eb39099f51da36b62360282bc89c06ab94817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>在 Lync Server 2013 中配置视频带宽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

Lync Server 2013 包括用于管理两方呼叫和多方会议的视频的多个设置。 在部署 Lync Server 2013 时，应评估默认设置是否适用于您的组织，并根据需要进行修改。

本节中描述的参数适用于双方呼叫和多方会议。可使用下列 cmdlet 之一来查看或修改这些设置：

  - **Set-csconferencingpolicy**

  - **Set-csconferencingpolicy**

  - **新 Set-csconferencingpolicy**

验证会议策略中的下列设置：

  - **VideoBitRateKb**   此设置指定用于用户发送的视频的最大视频比特率（以千位/秒（kbps）为单位）。 默认值为 50000 kbps。 有效值介于 0 和 50000 之间。
    
    此设置单独应用于主要视频和全景视频。
    
    示例：如果指定 2000 kbps，则 Lync Server 可以为全景视频流的主视频流和 2000 kbps 发送 2000 kbps。
    
    <div>
    

    > [!NOTE]  
    > 对于用于全景视频的主视频和 2500 kbps，Lync 2013 终结点的最大视频网络带宽为 8000 kbps。 仅当接收或发送多个视频时才达到这些最大值。 有关详细信息，请参阅<A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Lync Server 2013 中的媒体流量要求的网络带宽要求</A>中的 "媒体流量网络使用情况" 部分。 本节列出了所有受支持的分辨率的最大和典型视频流带宽。

    
    </div>

  - **TotalReceiveVideoBitRateKb**   此设置（在 Lync Server 2013 中为 "新建"），指定客户端接收的所有视频流的最大允许比特率（以千位/秒为单位）。 也就是说，此设置指定了客户端可接收的所有视频流（全景视频流除外）的合并总计。 例如，如果您指定 1500 kbps，则客户端最多可接收 1500 kbps 的视频，此视频可能包含多个视频流或单个视频流。 此设置仅适用于 Lync Server 2013 客户端。
    
    **TotalReceiveVideoBitRateKb** 的默认值是 50000 kbps。如果将库视图的 **EnableMultiviewJoin** 设置设为 True，则不得将 **TotalReceiveVideoBitRateKb** 设置为小于 420 kbps 的值。如果将库视图的 **EnableMultiviewJoin** 设置设为 False，则不得将 **TotalReceiveVideoBitRateKb** 设置为小于 100 kbps 的值。如果将 **EnableMultiviewJoin** 设为 True 并将值设置为小于 420 kbps 的值，则这些值将默认为阈值。此阈值可帮助阻止可能会导致极差的用户体验的意外配置错误。
    
    <div>
    

    > [!NOTE]  
    > 有关<STRONG>EnableMultiviewJoin</STRONG>设置的详细信息，请参阅<A href="lync-server-2013-configuring-gallery-view.md">在 Lync Server 2013 中配置库视图</A>。

    
    </div>

  - **MaxVideoConferencingResolution**   该参数不再用于 lync server 2013 会议中的 lync server 2013 客户端。 Lync Server 2013 会议使用此部分前面所述的比特率控件。 此设置仍用于加入 Lync Server 2013 会议的旧版客户端。 此参数确定在由驻留在 Lync Server 2013 上的用户组织的会议中允许的旧客户端的最大分辨率。 也就是说，旧客户端的处理方式与在以前版本的 Lync Server 或 Office 通信服务器中相同。

除了适用于用户的会议策略设置之外，还将评估媒体配置设置。可使用下列 cmdlet 之一来查看或修改这些设置：

  - **Set-csmediaconfiguration**

  - **Set-csmediaconfiguration**

  - **新 Set-csmediaconfiguration**

验证以下设置：

  - **MaxVideoRateAllowed**   此每池设置指定将在客户端终结点传输视频信号的最大速率。 它仅适用于早期版本的 Lync Server 客户端。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 客户端忽略此设置，并改用会议策略中的 TotalReceiveVideoBitRateKb 设置。

    
    </div>
    
    默认值为 HD720P。有效值为 HD720p15M、VGA600K 和 CIF250K。
    
    示例：如果您指定 1500 kbps，则池中的所有旧客户端最多可接收双方或多方会议中的 1500 kbps 的视频。

以下过程是使用 Lync Server 命令行管理程序修改此部分中所述设置的示例。

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>修改视频设置的会议策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行处，运行以下 cmdlet 以编辑会议策略：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>修改旧客户端的媒体配置

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行处，运行以下 cmdlet 以编辑媒体配置：
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

