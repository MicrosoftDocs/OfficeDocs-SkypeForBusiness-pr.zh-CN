---
title: Lync Server 2013：配置 CAC 的网络站点
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
ms.openlocfilehash: 0958c74d6f1ce587886b7a8456aee44381c00ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中配置 CAC 的网络站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> 如果你已为 E9 或媒体旁路创建了网络站点，则可以通过使用<STRONG>CsNetworkSite</STRONG> cmdlet 修改现有网络站点以应用带宽策略配置文件。 有关如何修改网络网站的示例，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync Server 2013 中创建或修改网络网站</A>。



</div>

*网络站点*是呼叫许可控制（CAC）、E9-1 和媒体绕过部署的每个网络区域内的办公室或位置。 使用以下过程创建网络站点，这些站点与 CAC 的示例网络拓扑中的网络站点对齐。 这些过程演示了如何创建和配置受 WAN 带宽限制的网络站点，因此需要带宽策略来限制实时音频或视频流量流。

在示例 CAC 部署中，北美地区有六个站点。 以下三个网站受 WAN 带宽的约束： Reno、伯克基和。 *不*受 WAN 带宽约束的其他三个站点：纽约、芝加哥和底特律。 有关如何创建或修改其他网络网站的示例，请参阅[在 Lync Server 2013 中创建或修改网络网站](lync-server-2013-create-or-modify-a-network-site.md)。

若要查看示例网络拓扑，请参阅：在规划文档中[收集 Lync Server 2013 中的呼叫许可控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

<div class=" ">


> [!NOTE]  
> 在以下过程中，Lync Server Management Shell 用于创建网络网站。 有关使用 Lync Server "控制面板" 创建网络网站的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-site.md">在 Lync server 2013 中创建或修改网络网站</A>。



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>为呼叫许可控制创建网络站点

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  运行**CsNetworkSite** cmdlet 以创建网络站点并将相应的带宽策略配置文件应用到每个站点。 例如，运行：
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  若要完成为整个示例拓扑创建网络网站，请对 EMEA 和 APAC 区域中带宽受限的网络网站重复步骤2。

</div>

</div>

<span> </span>

</div>

</div>

</div>

