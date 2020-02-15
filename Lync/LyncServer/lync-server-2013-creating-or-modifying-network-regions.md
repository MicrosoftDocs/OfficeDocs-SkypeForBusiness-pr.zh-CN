---
title: Lync Server 2013：创建或修改网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04f85e4546d8cfa3154c2fc5a87676ff0377795b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络区域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

网络区域将跨多个地理区域的网络的各个部分相互连接起来。 每个网络区域都必须与中央站点关联。 中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。 您可以使用 Lync Server 控制面板配置网络区域。 网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。 在 Lync Server 控制面板中，您可以创建、修改或删除网络区域。 使用此主题创建和修改网络区域。 有关删除现有网络区域的详细信息，请参阅[在 Lync Server 2013 中删除现有网络区域](lync-server-2013-deleting-existing-network-regions.md)。

<div>

## <a name="to-create-a-network-region"></a>创建网络区域

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域”****。

4.  在 "**区域**" 页上，单击 "**新建**"。

5.  在 "**新区域**" 页上，在 "**名称**" 字段中键入一个值。 此值在 Microsoft Lync Server 2013 部署中必须是唯一的。

6.  从 "**中央站点**" 下拉列表中，选择此网络区域的中央站点。

7.  默认情况下，"**启用音频备用路径**" 复选框处于选中状态。 如果主路径中不存在足够的带宽，则此字段将确定是否通过备用路径路由音频呼叫。 仅当需要关闭到 Internet 的卸载时，才清除此复选框。 如果你的任何呼叫将成为 Internet 呼叫，则必须选中此复选框，而不考虑带宽设置。

8.  默认情况下，"**启用视频备用路径**" 复选框处于选中状态。 如果主路径中不存在足够的带宽，则此字段将确定是否通过备用路径路由视频呼叫。 仅当需要关闭到 Internet 的卸载时，才清除此复选框。 如果你的任何呼叫将成为 Internet 呼叫，则必须选中此复选框，而不考虑带宽设置。

9.  Optional在 "**说明**" 字段中键入一个值，以提供有关无法单独表示的此区域的详细信息。

10. 单击“提交”****。

"**关联的网站**" 表不用于创建网络区域。 您在创建或修改网站时将网站与区域相关联。 有关详细信息，请参阅[在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-creating-or-modifying-network-sites.md)。

</div>

<div>

## <a name="to-modify-a-network-region"></a>修改网络区域

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域”****。

4.  在 "**区域**" 页上，单击要修改的区域。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑区域**" 页上，您可以修改用于启用和禁用音频和视频备用路径的设置，并更改说明（有关详细信息，请参阅本主题前面的 "创建网络区域" 一节。

7.  单击“提交”****。

您无法修改此页面上的**关联网站**。 将提供相关网站的列表以供参考，以便您知道在修改区域设置时哪些网站将受到影响。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除现有网络区域](lync-server-2013-deleting-existing-network-regions.md)  
[在 Lync Server 2013 中配置 CAC 的网络区域](lync-server-2013-configure-network-regions-for-cac.md)  


[新 CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

