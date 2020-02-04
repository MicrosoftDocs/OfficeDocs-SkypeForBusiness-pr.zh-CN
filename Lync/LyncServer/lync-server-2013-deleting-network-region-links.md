---
title: Lync Server 2013：删除网络区域链接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 158537f2473beba686daa51c5384a45f01432320
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a>删除 Lync Server 2013 中的网络区域链接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

你可以配置两个网络区域之间的链接作为呼叫许可控制（CAC）的一部分。 网络中的区域通过物理广域网络（WAN）连接进行链接。 可以使用 Lync Server "控制面板" 删除两个网络区域之间的现有链接。 有关创建或修改网络区域链接的详细信息，请参阅[在 Lync Server 2013 中配置网络区域链接](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>删除网络区域链接

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域链接**"。

4.  在 "**区域链接**" 页面上，单击要删除的区域链接。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个区域链接。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个区域链接。 或者，若要选择所有区域链接，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  从 "**编辑**" 菜单中，选择 "**删除**"。

6.  单击“**确定**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置网络区域链接](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

