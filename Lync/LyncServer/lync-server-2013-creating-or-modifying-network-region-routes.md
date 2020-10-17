---
title: Lync Server 2013：创建或修改网络区域路由
description: Lync Server 2013：创建或修改网络区域路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89106c905419778776ea16341f247027d49f1195
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544088"
---
# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络区域路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-08_

呼叫允许控制服务 (CAC) 配置中的每个区域必须采用某种方式才能访问其他每个区域。 虽然区域链接会对区域之间的连接设置带宽限制，并代表物理链接，但路由可确定连接从一个区域到另一个区域将遍历的链接路径。 您可以使用 Lync Server 控制面板配置网络区域路由。 从 Lync Server 控制面板中，您可以创建、修改或删除网络区域路由。 使用本主题创建或修改网络区域路由。 有关删除现有网络区域路由的详细信息，请参阅 [在 Lync Server 2013 中删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)。

<div>

## <a name="to-create-a-network-region-route"></a>创建网络区域路由

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域路由”****。

4.  在“区域路由”**** 页上，单击“新建”****。

5.  在“新建区域路由”**** 的“名称”**** 字段中键入值。
    
    <div>
    

    > [!NOTE]  
    > 此值在 Microsoft Lync Server 2013 部署中必须是唯一的。

    
    </div>

6.  从 " **网络区域 \# 1** " 下拉列表中，选择两个要通过此路由连接的区域之一。

7.  从 " **网络区域 \# 2** " 下拉列表中，选择此路由的其他区域。 此区域必须不同于为网络区域1选择的区域 \# 。

8.  使用“网络区域链接”**** 列表框向路由添加区域链接。单击“添加”**** 按钮以显示“区域链接”**** 页面。单击某个区域链接将其添加到此路由，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 继续单击“添加”<STRONG></STRONG>按钮添加更多链接，还可选择某个链接，然后单击“删除”<STRONG></STRONG>删除该链接。

    
    </div>

9.  单击“提交”****。

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>修改网络区域路由

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“区域路由”****。

4.  在“区域路由”**** 页上，单击要修改的区域路由。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在“编辑区域路由”**** 中，可以修改此路由连接的区域以及与此路由关联的区域链接。

7.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

