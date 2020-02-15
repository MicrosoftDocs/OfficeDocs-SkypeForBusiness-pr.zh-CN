---
title: Lync Server 2013：创建或修改网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e7c3db5b37cba514a0c07e11a907628dcc7823f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-08_

网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。 您可以使用 Microsoft Lync Server 2013 控制面板配置网站并将其与区域相关联。 例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。 必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。 在 Lync Server 控制面板中，您可以创建、修改和删除网络站点。 使用下面的过程可创建或修改网络站点。 有关删除现有网络站点的详细信息，请参阅[在 Lync Server 2013 中删除现有网络站点](lync-server-2013-deleting-an-existing-network-site.md)。

<div>

## <a name="to-create-a-network-site"></a>创建网络站点

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“站点”****。

4.  在“站点”**** 页上，单击“新建”****。

5.  在“新建站点”**** 的“名称”**** 字段中，键入此站点的名称。
    
    <div>
    

    > [!NOTE]  
    > 站点名称在 Lync Server 2013 部署中必须是唯一的。

    
    </div>

6.  在“区域”**** 下拉列表中，选择与此站点关联的网络区域。

7.  （可选）如果要对此站点的音频或视频呼叫设置带宽限制，请从“带宽策略”**** 下拉列表中选择具有相应设置的带宽策略配置文件。
    
    <div>
    

    > [!NOTE]  
    > 在“网络配置”<STRONG></STRONG>组的“策略配置文件”<STRONG></STRONG>页上，可以查看可用带宽策略配置文件的详细信息，或创建新的带宽策略配置文件。 有关详细信息，请参阅<A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">在 Lync Server 2013 中创建或修改带宽策略配置文件</A>。

    
    </div>

8.  （可选）如果要为此站点提供位置设置，请从“位置策略”**** 下拉列表中选择位置策略。
    
    <div>
    

    > [!NOTE]  
    > 位置策略会将特定的增强型 9-1-1 (E9-1-1) 和客户端位置设置分配给站点。 在“网络配置”<STRONG></STRONG>组的“位置策略”<STRONG></STRONG>页上，可以查看可用位置策略的详细信息，或创建新的位置策略。 有关详细信息，请参阅<A href="lync-server-2013-viewing-location-policy-information.md">在 Lync Server 2013 中查看位置策略信息</A>。

    
    </div>

9.  （可选）在“说明”**** 字段中键入值，用以提供仅通过名称无法表达的更多有关该站点的信息。

10. 单击“提交”****。
    
    <div>
    

    > [!NOTE]  
    > 创建新网络站点时，不要使用“关联子网”<STRONG></STRONG>表。 创建或修改子网时，会将子网与站点相关联。 有关详细信息，请参阅<A href="lync-server-2013-create-or-modify-network-subnets.md">在 Lync Server 2013 中创建或修改网络子网</A>。

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a>修改网络站点

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“站点”****。

4.  在“站点”**** 页上，单击要修改的站点。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在“编辑站点”**** 页上，可以修改与站点关联的说明、区域、带宽策略配置文件以及位置策略。有关详细信息，请参阅本主题前面的“创建网络站点”一节。

7.  单击“提交”****。

不能修改此页面中的“关联子网”**** 表。关联子网列表仅供参考，以使您注意修改站点设置时将影响的子网。

</div>

<div>

## <a name="to-delete-a-network-site"></a>删除网络站点

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“站点”****。

4.  在“站点”**** 页上，单击要删除的站点。
    
    <div>
    

    > [!NOTE]  
    > 可一次性删除多个站点。要执行此操作，请按住 Ctrl 键，同时选择多个站点。或者，要选择全部站点，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。

    
    </div>

5.  在“编辑”**** 菜单上，单击“删除”****。

6.  单击“确定”****。
    
    <div>
    

    > [!WARNING]  
    > 不能删除与网络子网关联的网络站点。如果尝试删除与某个子网关联的站点，您将收到错误消息。要查看站点是否与任何子网关联，请单击相应的站点，然后单击“编辑”<STRONG></STRONG>菜单中的“显示详细信息”<STRONG></STRONG>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[删除 Lync Server 2013 中的现有网络站点](lync-server-2013-deleting-an-existing-network-site.md)  


[新 CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

