---
title: 'Lync Server 2013: 查看网络区域链接信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5bec9bdc656a33a34727f29bfc56ad39b2476a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845311"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看网络区域链接信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

您可以查看两个网络区域之间的链接, 作为呼叫许可控制 (CAC) 的一部分。 网络中的区域通过物理广域网络 (WAN) 连接进行链接。 可以使用 Lync Server "控制面板" 查看两个网络区域之间的现有链接。 有关创建或修改网络区域链接的详细信息, 请参阅[在 Lync Server 2013 中配置网络区域链接](lync-server-2013-configuring-network-region-links.md)。

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中查看网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上, 单击要查看的区域链接。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看有关一个区域链接的信息。

    
    </div>

5.  从 "**编辑**" 菜单中, 选择 "**显示详细信息**"。

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络区域链接信息

你可以使用 Windows PowerShell 和**CsNetworkRegionLink** cmdlet 查看网络区域链接。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-region-link-information"></a>查看网络区域链接信息

  - 若要查看有关所有网络区域链接的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
        Get-CsNetworkRegionLink
    
    此命令会返回类似下列信息：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

有关详细信息, 请参阅[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置网络站点链接](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

