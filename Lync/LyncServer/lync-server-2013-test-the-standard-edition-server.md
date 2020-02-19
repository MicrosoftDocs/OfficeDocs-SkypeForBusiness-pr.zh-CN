---
title: Lync Server 2013：测试 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26610b3619977413f3afa24027c7dfd757189a85
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Standard Edition 服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

以下过程介绍如何测试 Standard Edition server 的部署。

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>测试 Standard Edition Server 的部署

1.  使用 Active Directory 计算机和用户将 Lync Server 2013 部署（安装了 Lync Server 控制面板）的管理员角色的 Active Directory 用户对象添加到**CSAdministrator**组中。

2.  如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    <div>
    

    > [!NOTE]  
    > 用户帐户不能是运行 Lync Server 2013 Standard Edition 的服务器的本地管理员。 如果不将相应的用户和组添加到 CsAdministors 组中，则在打开 Lync Server 2013 控制面板时将收到错误，指出 "未经授权：由于基于角色的访问控制（RBAC）授权失败，访问被拒绝"。

    
    </div>

3.  使用管理帐户登录到安装了 Lync Server 控制面板的计算机。

4.  如果出现提示，请启动 Lync Server 控制面板并提供凭据。 Lync Server 2013 控制面板显示部署信息。

5.  在左侧导航栏中，单击 "**拓扑**"，然后确认服务状态是否为带有绿色箭头的计算机图标，并且每个已部署并联机的 Lync server 服务器角色旁边都有一个绿色的复选标记。

6.  在左侧导航栏中，单击 "**用户**"，然后为两个用户启用 Lync Server 2013。

7.  使其中一个用户登录已加入域的计算机，另一个用户登录域中的其他计算机。

8.  在两台客户端计算机上安装 Lync Server 2013，然后验证这两个用户是否都可以登录 Lync Server 2013 并可以向对方发送即时消息。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

