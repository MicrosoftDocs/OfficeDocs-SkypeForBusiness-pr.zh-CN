---
title: Lync Server 2013：配置网络区域链接
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
ms.openlocfilehash: 5d069bb5215fc977a35481a916f49e86fa644284
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>在 Lync Server 2013 中配置网络区域链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 网络中的区域通过物理广域网络（WAN）连接进行链接。 你可以使用 Lync Server 控制面板定义两个网络区域之间的链接，并设置这些区域之间的音频和视频连接的带宽限制。 有关删除现有网络区域链接的详细信息，请参阅[在 Lync Server 2013 中删除网络区域链接](lync-server-2013-deleting-network-region-links.md)。

<div>

## <a name="to-create-a-network-region-link"></a>创建网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击 "**新建**"。

5.  在 "**新区域链接**" 中，在 "**名称**" 字段中键入值。
    
    <div>
    

    > [!NOTE]  
    > 此值在 Lync Server 2013 部署中必须是唯一的。

    
    </div>

6.  从 "**网络区域\#1** " 下拉列表中，选择要链接的两个区域之一。

7.  从 "**网络区域\#2** " 下拉列表中，选择要链接的其他区域。 此区域必须与为 "网络区域\#1" 选择的区域不同。

8.  可选如果您想要对这些区域之间的音频或视频通话设置带宽限制，请从 "**带宽策略**" 下拉列表中选择一个带宽策略配置文件。

9.  单击“**提交**”。

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>修改网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击要修改的区域链接。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑区域" 链接**中，可以修改链接的区域或此链接的 "带宽策略" 配置文件。

7.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[删除 Lync Server 2013 中的网络区域链接](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
