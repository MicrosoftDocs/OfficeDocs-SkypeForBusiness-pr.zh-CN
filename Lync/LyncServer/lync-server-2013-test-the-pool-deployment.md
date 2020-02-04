---
title: Lync Server 2013：测试池部署
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
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中测试池部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-09-25_

以下过程介绍了如何测试前端池的部署。

<div>

## <a name="to-test-the-pool-deployment"></a>测试池部署

1.  使用 Active Directory 计算机和用户将 Lync Server 2013 部署（安装了 Lync Server 2013 控制面板）的管理员角色的 Active Directory 用户对象添加到**CSAdministrator**组。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果不将相应的用户和组添加到 CsAdministors 组，则打开 Lync Server 控制面板时将收到错误，其中指出 "未经授权：由于基于角色的访问控制（RBAC）授权失败，访问被拒绝。"

    
    </div>

2.  如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    <div>
    

    > [!NOTE]  
    > 用户帐户不能是运行 Lync Server 2013 的任何服务器的本地管理员。

    
    </div>

3.  使用 "管理" 帐户登录到安装了 "Lync Server 控制面板" 的计算机。

4.  启动 Lync Server "控制面板"，然后提供凭据（如果出现提示）。 Lync Server "控制面板" 显示部署信息。

5.  在左侧导航栏中，单击 "**拓扑**"，然后确认 "服务状态" 显示带有绿色箭头的计算机，并且复制状态的绿色复选标记位于已部署并联机的每个 Lync server 服务器角色的旁边。

6.  在左侧导航栏中，单击**用户**，然后单击**启用用户**。

7.  在 "**新建 Lync 服务器" 用户**页面上，单击 "**添加**"。

8.  要为希望查找的对象定义搜索参数，可以在**从 Active Directory 中选择**页上选择**搜索**，然后选择单击**添加筛选器**。 还可以选择**LDAP 搜索**，然后输入 LDAP 表达式以筛选或限制将返回的对象。 确定搜索选项后，clink "**查找**"。

9.  在 "搜索结果" 窗格中，选择此搜索会话的所有对象，然后单击 **"确定"**。

10. 在 "**新建 Lync Server 用户**" 页面上，所选对象将位于 "**用户**" 显示中。 在 "**将用户分配给池**" 列表中，选择应在其中托管对象的服务器。
    
    下面是用于配置对象的许多选项。
    
      - **生成用户的 SIP URI**
    
      - **电话**
    
      - **线路 URI**
    
      - **会议策略**
    
      - **客户端版本策略**
    
      - **PIN 策略**
    
      - **外部访问策略**
    
      - **存档策略**
    
      - **位置策略**
    
      - **客户端策略**
    
    为了测试基本功能，请为 "**生成用户的 SIP URI** " 设置选择所需的选项（配置中的其他选项将使用默认设置），然后单击 "**启用**"。

11. 将显示 "摘要" 页面，显示 "**已启用**" 列中的复选标记，指示对象现在可以使用。 **SIP 地址**列将显示用户登录配置所需的地址。

12. 将一位用户登录到加入域的计算机，另一用户登录到域中的另一台计算机。

13. 在两台客户端计算机上安装 Lync 2013，然后验证这两个用户都可以登录 Lync Server 2013，并且可以互相发送即时消息。

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

