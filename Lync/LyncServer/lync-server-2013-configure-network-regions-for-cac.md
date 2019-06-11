---
title: 'Lync Server 2013: 配置 CAC 的网络区域'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>在 Lync Server 2013 中配置 CAC 的网络区域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

<div>


> [!IMPORTANT]  
> 如果你已为 E9 或 media 旁路创建了网络区域, 则可以通过使用<STRONG>CsNetworkRegion</STRONG> cmdlet 添加特定于呼叫许可控制 (CAC) 的设置来修改现有网络区域。 有关如何修改网络区域的示例, 请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync Server 2013 中创建或修改网络区域</A>。



</div>

*网络区域*是用于配置 CAC、E9-1 和媒体旁路的网络中心或 backbones。 在 CAC 的示例网络拓扑中, 使用以下过程创建与网络区域对齐的网络区域。 若要查看示例网络拓扑, 请参阅: 在规划文档中[收集 Lync Server 2013 中的呼叫许可控制要求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)。

CAC 的示例网络拓扑有三个区域: 北美洲、EMEA 和 APAC。 每个区域都有一个指定的中心网站。 对于北美地区, 指定的中心网站称为芝加哥。 以下过程显示了如何使用**CsNetworkRegion** Cmdlet 创建北美区域的示例。

<div>


> [!NOTE]  
> 在以下过程中, Lync Server Management Shell 用于创建网络区域。 有关使用 Lync Server "控制面板" 创建网络区域的详细信息, 请参阅<A href="lync-server-2013-create-or-modify-a-network-region.md">在 Lync server 2013 中创建或修改网络区域</A>。



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>为 "呼叫许可控制" 创建网络区域

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  对于你需要创建的每个区域, 请运行**CsNetworkRegion** cmdlet。 例如, 若要创建北美地区, 请运行:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  重复步骤2创建网络区域、EMEA 和 APAC。

</div>

</div>

<span> </span>

</div>

</div>

</div>

