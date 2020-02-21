---
title: Lync Server 2013：删除现有网络区域路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91a8674e635bb5663ebbca994d7d8f865601a193
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有网络区域路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。 虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。 您可以使用 Lync Server 控制面板配置网络区域路由。 从 Lync Server 控制面板中，您可以创建、修改或删除网络区域路由。 使用本主题可删除现有网络区域路由。 有关创建或修改网络区域路由的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。

<div>

## <a name="to-delete-a-network-region-route"></a>删除网络区域路由

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域路由”****。

4.  在“区域路由”**** 页上，单击要删除的区域路由。
    
    <div>
    

    > [!NOTE]  
    > 可一次性删除多个区域路由。要执行此操作，请按住 Ctrl 键，同时选择多个区域路由。或者，要选择全部区域路由，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。

    
    </div>

5.  在“编辑”**** 菜单上，单击“删除”****。

6.  单击“确定”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[配置网络区域路由](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[新 CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

