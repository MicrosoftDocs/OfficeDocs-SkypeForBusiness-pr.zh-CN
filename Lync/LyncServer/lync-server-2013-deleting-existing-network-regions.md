---
title: Lync Server 2013：删除现有网络区域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3a1c1e697e681eec4886dca9e942d9bc133b0f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525399"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a>在 Lync Server 2013 中删除现有网络区域

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

网络区域将跨多个地理区域的网络的各个部分相互连接起来。 每个网络区域都必须与中央站点关联。 中央站点是运行呼叫允许控制 (CAC) 带宽策略服务的数据中心站点。 您可以使用 Lync Server 控制面板配置网络区域。 网络区域包括确定音频和视频连接是否可以使用通过 Internet 的备用路径的设置。 在 Lync Server 控制面板中，您可以创建、修改或删除网络区域。 使用此主题可删除现有网络区域。 有关创建或修改现有网络区域的详细信息，请参阅 [在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-delete-a-network-region"></a>删除网络区域

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域”****。

4.  在“区域”**** 页上，单击要删除的区域。
    
    <div>
    

    > [!NOTE]  
    > 可一次性删除多个区域。要执行此操作，请按住 Ctrl 键，同时选择多个区域。或者，要选择全部区域，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。

    
    </div>

5.  在“编辑”**** 菜单上，单击“删除”****。

6.  单击“确定”****。
    
    <div>
    

    > [!WARNING]  
    > 如果网络区域与某个网络站点关联，则不能删除该网络区域。如果尝试删除与某个站点关联的区域，您将收到错误消息。要查看区域是否与任何站点关联，请选择相应的区域，然后单击“编辑”<STRONG></STRONG>菜单中的“显示详细信息”<STRONG></STRONG>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

