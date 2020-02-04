---
title: Lync Server 2013：创建或修改网络区域路由
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
ms.openlocfilehash: d877de116cc2cf3e0c3354bb6e53d69c211cb482
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改网络区域路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-08_

呼叫许可控制（CAC）配置中的每个区域都必须有某种方式才能访问其他每个区域。 虽然区域链接为区域之间的连接设置带宽限制，同时也表示物理链接，但路由决定了连接从一个地区到另一个地区的链接路径。 您可以使用 Lync Server "控制面板" 配置网络区域路由。 从 Lync Server 控制面板中，你可以创建、修改或删除网络区域路由。 使用本主题创建或修改网络区域路线。 有关删除现有网络区域路由的详细信息，请参阅[在 Lync Server 2013 中删除现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)。

<div>

## <a name="to-create-a-network-region-route"></a>创建网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。

4.  在 "**区域路由**" 页面上，单击 "**新建**"。

5.  在 "**新区域路由**" 中，在 "**名称**" 字段中键入值。
    
    <div>
    

    > [!NOTE]  
    > 此值在 Microsoft Lync Server 2013 部署中必须是唯一的。

    
    </div>

6.  从 "**网络区域\#1** " 下拉列表中，选择两个要通过此路由连接的区域之一。

7.  从 "**网络区域\#2** " 下拉列表中，选择此路由的其他区域。 此区域必须与为 "网络区域\#1" 选择的区域不同。

8.  使用 "**网络区域链接**" 列表框将区域链接添加到路由。 单击 "**添加**" 按钮以显示 "**区域链接**" 页面。 单击要添加到此路由的区域链接，然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 继续单击 "<STRONG>添加</STRONG>" 按钮以添加更多链接，或选择一个链接，然后单击 "<STRONG>删除</STRONG>" 以删除链接。

    
    </div>

9.  单击“**提交**”。

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>修改网络区域路由

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**区域路由**"。

4.  在 "**区域路由**" 页面上，单击要修改的区域路由。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在 "**编辑区域" 路由**中，可以修改此路由所联接的区域和与该路由关联的区域链接。

7.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[删除 Lync Server 2013 中的现有网络区域路由](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

