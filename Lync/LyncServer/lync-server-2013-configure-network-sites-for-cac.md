---
title: Lync Server 2013：为 CAC 配置网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2c956eb4f50a0a5e7ce1bafe955b5cea092cd2c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中配置 CAC 的网络站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> 如果您已为 E9-1-1 或媒体旁路创建网络站点，则可以使用 <STRONG>Set-CsNetworkSite</STRONG> cmdlet 修改现有的网络站点，以应用带宽策略配置文件。 有关如何修改网络站点的示例，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络站点</A>。



</div>

*网络站点*是指部署了呼叫允许控制 (CAC)、E9-1-1 和媒体旁路的每个网络区域内的办公室或位置。使用以下过程创建网络站点，这些网络站点与 CAC 的示例网络拓扑中的网络站点一致。这些过程显示如何创建并配置受 WAN 带宽限制，并因此需要用于限制实时音频或视频流量的带宽策略的网络站点。

在示例 CAC 部署中，北美区域有六个站点。 其中三个站点受 WAN 带宽限制：里诺、波特兰和阿尔布开克。 其他三个站点*不*受 WAN 带宽限制：纽约、芝加哥和底特律。 有关如何创建或修改其他网络站点的示例，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)。

若要查看示例网络拓扑，请参阅规划文档中的[示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div class=" ">


> [!NOTE]  
> 在下面的过程中，将使用 Lync Server 命令行管理程序创建网络站点。 有关使用 Lync Server 控制面板创建网络站点的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中创建或修改网络站点</A>。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>为呼叫允许控制创建网络站点

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 **New-CsNetworkSite** cmdlet 以创建网络站点并将相应带宽策略配置文件应用到每个站点。 例如，运行：
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  要为整个示例拓扑完成网络站点的创建，请针对 EMEA 和 APAC 区域中受带宽限制的网络站点重复步骤 2。

</div>

</div>

<span> </span>

</div>

</div>

</div>

