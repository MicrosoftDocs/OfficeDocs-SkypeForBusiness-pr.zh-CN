---
title: Lync Server 2013;创建网络 interregion 路由
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 4ab490479e02e92811878a9125c7b318732eeb83
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>在 Lync Server 2013 中创建网络 interregion 路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

“网络区域间路由”** 定义一对网络区域之间的路由。呼叫允许控制部署中的每对网络区域均需要网络区域间路由。这样部署中的每个网络区域便能够访问任何其他区域。

虽然区域链接会对区域之间的连接设置带宽限制，但是区域间路由可确定连接从一个区域到另一个区域将遍历的链接路径。

有关使用网络 interregion 路由的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - [新 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

在示例拓扑中，必须为三个区域对中的每一对定义网络区域间路由：北美/EMEA、EMEA/APAC 以及北美/APAC。

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序创建网络 interregion 路由

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  运行 **New-CsNetworkInterRegionRoute** cmdlet 来定义所需路由。 例如，运行：
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > 北美/APAC 的网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板创建网络 interregion 路由

1.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

2.  在左侧导航栏中，单击“网络配置”****。

3.  单击“区域路由”**** 导航按钮。

4.  单击“新建”****。

5.  在“新建区域路由”**** 页上，单击“名称”****，然后键入网络区域间路由的名称。

6.  单击 "**网络\#区域 1**"，然后在列表中单击要路由到 "网络区域\#2" 的网络区域。

7.  单击 "**网络\#区域 2**"，然后在列表中单击要路由到 "网络区域\#1" 的网络区域。

8.  单击“网络区域链接”**** 字段旁边的“添加”****，然后添加将用于网络区域间路由的网络区域链接。
    
    <div class=" ">
    

    > [!NOTE]  
    > 如果要为彼此之间没有直接网络区域链接的两个网络区域创建路由，则必须添加所有必要的链接来完成路由。例如，北美/APAC 网络区域间路由需要两个网络区域链接，因为它们之间没有直接网络区域链接。

    
    </div>

9.  单击“提交”****。

10. 要为拓扑完成网络区域间路由的创建，请为其他网络区域间路由重复步骤 4 至 步骤 9 的设置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

