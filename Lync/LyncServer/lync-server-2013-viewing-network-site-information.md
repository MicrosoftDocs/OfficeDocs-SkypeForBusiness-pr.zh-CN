---
title: Lync Server 2013：查看网络网站信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d3c6b0e4855cd8620205a70d6538465c32c0f0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看网络站点信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

网络站点是在呼叫许可控制（CAC）或增强的9-1-1 部署的每个区域内配置的办公室或位置。 可以在 Lync Server 2013 控制面板或 Lync Server 命令行管理程序中查看网络网站信息。 有关创建或修改网络站点的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)。

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中查看网络站点信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**网站**"。

4.  在 "**网站**" 页面上，单击要查看的网站。
    
    <div>
    

    > [!NOTE]  
    > 您一次只能查看一个网站的信息。

    
    </div>

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看网络网站信息

你可以使用 Windows PowerShell 和 CsNetworkSite cmdlet 查看网络网站信息。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-site-information"></a>查看网络站点信息

  - 若要查看有关所有网络网站的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsNetworkSite
    
    这将返回与以下类似的信息：
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

有关详细信息，请参阅[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)  
[在 Lync Server 2013 中删除现有网络网站](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

