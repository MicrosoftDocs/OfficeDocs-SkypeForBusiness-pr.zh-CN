---
title: Lync Server 2013：配置网络区域链接
description: Lync Server 2013：配置网络区域链接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92593f3b8fcd5fe3307a9c193ed7cddcf6dfce0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547008"
---
# <a name="configuring-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中配置网络区域链接

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

您可以配置两个网络区域之间的链接，以作为呼叫允许控制 (CAC) 的一部分。 网络内的区域通过物理广域网 (WAN) 连接进行链接。 您可以使用 Lync Server 控制面板定义两个网络区域之间的链接，并设置这些区域之间的音频和视频连接的带宽限制。 有关删除现有网络区域链接的详细信息，请参阅 [删除 Lync Server 2013 中的网络区域链接](lync-server-2013-deleting-network-region-links.md)。

<div>

## <a name="to-create-a-network-region-link"></a>创建网络区域链接

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域链接”****。

4.  在 " **区域链接** " 页上，单击 " **新建**"。

5.  在 " **新区域链接**" 的 " **名称** " 字段中，键入一个值。
    
    <div>
    

    > [!NOTE]  
    > 此值在 Lync Server 2013 部署中必须是唯一的。

    
    </div>

6.  从 " **网络区域 \# 1** " 下拉列表中，选择两个要链接的区域之一。

7.  从 " **网络区域 \# 2** " 下拉列表中，选择要链接的其他区域。 此区域必须不同于为网络区域1选择的区域 \# 。

8.   (可选) 如果要对这些区域之间的音频或视频呼叫设置带宽限制，请从 " **带宽策略** " 下拉列表中选择一个带宽策略配置文件。

9.  单击“提交”****。

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>修改网络区域链接

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域链接”****。

4.  在 " **区域链接** " 页上，单击要修改的区域链接。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 " **编辑区域链接**" 中，可以修改链接的区域或此链接的带宽策略配置文件。

7.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[删除 Lync Server 2013 中的网络区域链接](lync-server-2013-deleting-network-region-links.md)  


[新 CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
