---
title: Lync Server 2013;创建网络 interregion 路由
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 0eff2c1dd75258451002a41e0f284c4ad05c9728
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>在 Lync Server 2013 中创建网络 interregion 路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-20_

*网络 interregion 路线*定义了一对网络区域之间的路线。 您的呼叫许可控制部署中的每对网络区域都需要网络 interregion 路线。 这样部署中的每个网络区域便能够访问任何其他区域。

虽然区域链接为区域之间的连接设置带宽限制, 但 interregion 路由决定了连接将从一个区域遍历到另一个区域的链接路径。

有关使用网络 interregion 路由的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

在示例拓扑中, 必须为三个地区对中的每一对定义网络 interregion 路由: 北美洲/EMEA、EMEA/APAC 和北美/APAC。

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序创建网络 interregion 路由

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。 例如，运行：
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 北美/APAC 网络 interregion 路由需要两个网络区域链接, 因为它们之间没有直接的网络区域链接。

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 创建网络 interregion 路由

1.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“区域路由”**** 导航按钮。

4.  单击“新建”****。

5.  在 "**新建区域路由**" 页面上, 单击 "**名称**", 然后键入网络 interregion 路由的名称。

6.  单击 "**网络\#区域 1**", 然后在列表中单击要路由到 "网络区域\#2" 的网络区域。

7.  单击 "**网络\#区域 2**", 然后在列表中单击要路由到 "网络区域\#1" 的网络区域。

8.  单击 "**网络区域链接**" 字段旁边的 "**添加**", 然后添加将在网络 interregion 路由中使用的网络区域链接。
    
    <div class=" ">
    

    > [!NOTE]  
    > 如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。 例如, 北美/APAC 网络 interregion 路由需要两个网络区域链接, 因为它们之间没有直接的网络区域链接。

    
    </div>

9.  单击“**提交**”。

10. 若要完成为拓扑创建网络 interregion 路由, 请使用其他网络 interregion 路由的设置重复步骤4到步骤9。

</div>

</div>

<span> </span>

</div>

</div>

</div>

