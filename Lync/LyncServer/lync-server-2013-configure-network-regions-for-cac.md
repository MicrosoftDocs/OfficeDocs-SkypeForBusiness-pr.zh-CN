---
title: Lync Server 2013：为 CAC 配置网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acafaca86af1943d2614349ff42f04fa87faddaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中配置 CAC 的网络区域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

<div>


> [!IMPORTANT]  
> 如果已为 E9-1-1 或媒体旁路创建网络区域，则可以通过使用 <STRONG>Set-CsNetworkRegion</STRONG> cmdlet 添加特定于呼叫允许控制 (CAC) 的设置来修改现有网络区域。 有关如何修改网络区域的示例，请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</A>。



</div>

“网络区域”** 是在配置 CAC、E9-1-1 和媒体旁路的配置中使用的网络中心或网络中枢。 使用以下过程创建网络区域，这些网络区域与 CAC 的示例网络拓扑中的网络区域一致。 若要查看示例网络拓扑，请参阅规划文档中的[示例：在 Lync Server 2013 中收集呼叫允许控制的要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

CAC 的示例网络拓扑有三个区域：北美、EMEA 和 APAC。 每个区域都有一个指定的中央站点。 对于 North America 区域，指定的中央站点名为 CHICAGO。 以下过程显示了如何使用 **New-CsNetworkRegion** cmdlet 创建 North America 区域的示例。

<div>


> [!NOTE]  
> 在下面的过程中，将使用 Lync Server 命令行管理程序创建网络区域。 有关使用 Lync Server 控制面板创建网络区域的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中创建或修改网络区域</A>。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>创建呼叫允许控制的网络区域

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  对于每个需要创建的区域，运行 **New-CsNetworkRegion** cmdlet。 例如，要创建 North America 区域，请运行：
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  重复步骤 2 以创建网络区域、EMEA 和 APAC。

</div>

</div>

<span> </span>

</div>

</div>

</div>

