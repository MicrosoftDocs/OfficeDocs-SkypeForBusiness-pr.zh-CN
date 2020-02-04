---
title: Lync Server 2013：查看网络区域路由信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8299bd598edf18b7ed7f06088e4bfbbcebab354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看网络区域路线信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

呼叫许可控制（CAC）配置中的每个区域都必须有某种方式才能访问其他每个区域。 虽然区域链接为区域之间的连接设置带宽限制，同时也表示物理链接，但路由决定了连接从一个地区到另一个地区的链接路径。 使用以下过程可查看 Lync Server 2013 控制面板中的现有网络区域路由或 Lync Server 2013 管理外壳程序。 有关创建或修改网络区域路由的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)。

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中查看网络区域路线信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。

4.  在 "**区域路线**" 页面上，单击要查看的地区路线。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一个区域路线。

    
    </div>

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络区域路由信息

可以使用 Windows PowerShell 和 CsNetworkInterRegionRoute cmdlet 查看网络区域路线信息。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-region-route-information"></a>查看网络区域路线信息

  - 若要查看有关所有网络区域路由的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkInterRegionRoute
    
    这将返回与以下类似的信息：
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

有关详细信息，请参阅[CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络区域路由](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[删除 Lync Server 2013 中的现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

