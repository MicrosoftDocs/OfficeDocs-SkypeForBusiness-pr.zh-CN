---
title: Lync Server 2013：测试池部署
description: Lync Server 2013：测试池部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28101a252eda5048ded9f1eaf76c092c5cb7f986
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576038"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中测试池部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-09-25_

以下过程介绍如何测试前端池的部署。

<div>

## <a name="to-test-the-pool-deployment"></a>测试池部署

1.  使用 Active Directory 计算机和用户将 lync Server 2013 控制面板上安装的 lync server 2013 部署 (的 "管理员" 角色的 Active Directory 用户对象添加) 到 **CSAdministrator** 组中。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果不将相应的用户和组添加到 CsAdministors 组，则在打开 Lync Server 控制面板时将收到错误，这表明 "未授权：由于基于角色的访问控制 (RBAC) 授权失败而拒绝访问。"

    
    </div>

2.  如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    <div>
    

    > [!NOTE]  
    > 用户帐户不能是运行 Lync Server 2013 的任何服务器的本地管理员。

    
    </div>

3.  使用管理帐户登录到安装了 Lync Server 控制面板的计算机。

4.  启动 Lync Server 控制面板，然后提供凭据（如果出现提示）。 Lync Server "控制面板" 显示部署信息。

5.  在左侧导航栏中，单击 " **拓扑**"，然后确认服务状态显示计算机带有绿色箭头，并且复制状态的绿色复选标记位于已部署并联机的每个 Lync server 服务器角色的旁边。

6.  在左侧导航栏中，单击 " **用户**"，然后单击 " **启用用户**"。

7.  在 " **新建 Lync Server 用户** " 页上，单击 " **添加**"。

8.  若要定义要查找的对象的搜索参数，请在 " **从 Active Directory 中选择** " 页面上，选择 " **搜索**"，然后选择 " **添加筛选器**"。 您还可以选择 " **ldap 搜索** " 并输入 ldap 表达式以筛选或限制将返回的对象。 在确定了搜索选项之后，clink **Find**。

9.  在 "搜索结果" 窗格中，选择此搜索会话的所有对象，然后单击 **"确定"**。

10. 在 " **新建 Lync Server 用户** " 页上，所选的一个或一些对象将显示在 **用户** 的显示中。 在 " **将用户分配给池** " 列表中，选择对象应驻留在其中的服务器。
    
    以下是用于配置对象的多种选项。
    
      - **生成用户的 SIP URI**
    
      - **电话**
    
      - **行 URI**
    
      - **会议策略**
    
      - **客户端版本策略**
    
      - **PIN 策略**
    
      - **外部访问策略**
    
      - **存档策略**
    
      - **位置策略**
    
      - **客户端策略**
    
    出于测试基本功能的目的，请选择 " **生成用户的 SIP URI** " 设置所需的选项 (配置中的其他选项将使用默认设置) ，然后单击 " **启用**"。

11. 将显示一个摘要页，其中显示 " **已启用** " 列中的复选标记，指示这些对象现在可以使用。 " **SIP 地址** " 列显示用户登录配置所需的地址。

12. 将一个用户登录到加入域的计算机，另一个用户登录到域中的另一台计算机上。

13. 在两台客户端计算机上安装 Lync 2013，然后验证这两个用户是否都可以登录 Lync Server 2013 并可以向对方发送即时消息。

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

