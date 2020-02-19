---
title: Lync Server 2013：查看网络区域链接信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12e6cb2ec4d86f24e169bfd925c9dcdf08973646
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看网络区域链接信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

您可以查看两个网络区域之间作为呼叫允许控制 (CAC) 的一部分的链接。 网络内的区域通过物理广域网 (WAN) 连接进行链接。 您可以使用 Lync Server 控制面板查看两个网络区域之间的现有链接。 有关创建或修改网络区域链接的详细信息，请参阅[在 Lync Server 2013 中配置网络区域链接](lync-server-2013-configuring-network-region-links.md)。

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>在 "Lync Server 控制面板" 中查看网络区域链接

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域链接”****。

4.  在“区域链接”**** 页上，单击要查看的区域链接。
    
    <div>
    

    > [!NOTE]  
    > 您一次只能查看一个区域链接的相关信息。

    
    </div>

5.  从“编辑”**** 菜单中选择“显示详细信息”****。

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络区域链接信息

您可以使用 Windows PowerShell 和**CsNetworkRegionLink** cmdlet 查看网络区域链接。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-view-network-region-link-information"></a>查看网络区域链接信息

  - 若要查看有关所有网络区域链接的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkRegionLink
    
    此命令返回与以下内容类似的信息：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

有关详细信息，请参阅[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。

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

