---
title: Lync Server 2013：删除现有网络站点
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf46820309937cb6c5b45ef7e25341335e833e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>删除 Lync Server 2013 中的现有网络站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

网络站点是指在部署了呼叫允许控制 (CAC) 或增强型 9-1-1 的每个区域中配置的办公室或位置。 您可以使用 Lync Server 2013 控制面板配置网站并将其与区域相关联。 例如，可将北美网络区域与 Chicago、Redmond 和 Vancouver 之类的网络站点关联。 必须为组织中的每个站点创建一个 CAC 网络站点，即使该站点没有带宽限制也应如此。 在 Lync Server 控制面板中，您可以创建、修改和删除网络站点。 使用以下过程可删除现有网络站点。 有关创建或修改网络站点的详细信息，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)

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

</div>

<span> </span>

</div>

</div>

</div>

