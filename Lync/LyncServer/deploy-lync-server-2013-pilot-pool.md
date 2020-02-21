---
title: 部署 Lync Server 2013 试点池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb620a4846b05c7f81ecea4d5cc525c9c16c0c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>部署 Lync Server 2013 试点池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-22_

迁移到 Lync Server 2013 所需的第一步是部署试点池。 试点池是您在 Lync server 2010 部署中测试 Lync Server 2013 共存的地方。 共存是在将所有用户和池移到 Lync Server 2013 之前一直持续的临时状态。

部署试点池时，应使用“定义新前端池”向导。 您应在 lync Server 2010 池中部署 Lync Server 2013 引导池中的相同功能和工作负载。 如果您部署了存档服务器、监视服务器或 System Center Operations Manager 以存档或监视 Lync Server 2010 环境，并且您希望在整个迁移过程中继续进行存档或监控，则还需要部署这些试点环境中的功能。 您部署的用于存档或监视 Lync Server 2010 环境的版本将不会在 Lync Server 2013 环境中捕获数据。

<div>


> [!NOTE]  
> 随后的过程讨论应被视为试点池总体部署过程一部分的功能和设置。 本节只着重介绍在部署试点池的过程中应考虑的关键点。 有关详细步骤，请参阅<A href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</A>部署指南。



</div>

**部署 Lync Server 2013 引导池**

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  展开树，直至您进入**Lync Server 2013** **Enterprise Edition 前端池**。

3.  右键单击 " **Enterprise Edition 前端池**"，然后选择 "**新建前端池**"。
    
    ![拓扑生成器服务器池选择子菜单](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "拓扑生成器服务器池选择子菜单")

4.  输入池 FQDN。 在定义试点池时，可以选择部署企业版前端池或 Standard Edition server。 Lync Server 2013 不要求您的引导池功能与您的旧版池中部署的功能相匹配。
    
    <div>
    

    > [!WARNING]  
    > 您为试点定义的池或服务器的完全限定域名 (FQDN) 必须是唯一的。 它无法匹配当前部署的 Lync Server 2010 池的名称，或当前部署的任何其他服务器的名称。

    
    </div>
    
    ![定义新的前端池向导 FQDN 页](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "定义新的前端池向导 FQDN 页")

5.  在“选择功能”**** 页上，选中希望此前端池具有的功能的复选框。 例如，如果您仅部署即时消息 (IM) 和状态功能，可以选中“会议”复选框以允许多方 IM，但不能选中“电话拨入式(PSTN)会议”、“企业语音”或“呼叫允许控制”复选框，因为它们代表语音、视频和协作会议功能。 有关选择功能的其他信息，请参阅部署文档中的在[Lync server 2013 中定义和配置前端池或 Standard Edition server](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 。
    
    ![前端池选择功能页](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "前端池选择功能页")

6.  在 "**选择并置服务器角色**" 页上，我们建议您在 Lync server 2013 中并置中介服务器。 将旧版拓扑与 Lync Server 2013 合并时，我们需要您首先并置 Lync Server 2010 中介服务器。 在合并拓扑并配置 Lync Server 2013 中介服务器之后，您可以决定是否保留并置中介服务器，或在部署中将中介服务器角色移到 Lync Server 2013 时将其更改为独立服务器过程.
    
    ![前端池选择 "并置服务器角色" 页](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "前端池选择 "并置服务器角色" 页")

7.  在部署试点池过程中，不要选择“将服务器角色与此前端池关联”**** 页上的“启用此前端池的媒体组件要使用的边缘池”**** 选项。这是您将启用并使其在后面的迁移阶段进入联机状态的功能。目前请清除此设置。
    
    ![将服务器角色与前端池页面关联](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "将服务器角色与前端池页面关联")

8.  在“选择 Office Web Apps 服务器”**** 页上，单击“新建”**** 并指定应用程序服务器的 FQDN。
    
    ![定义新的 Office Web Apps Server FQDN 属性](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "定义新的 Office Web Apps Server FQDN 属性")

9.  在 "**定义存档 Sql server 存储**" 页上，定义 Lync server 存档和监视的 sql server 存储区时，请选择之前为 lync server 2013 创建的 sql server 实例。
    
    ![定义 "存档 SQL Server 存储" 页](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "定义 "存档 SQL Server 存储" 页")

10. 若要发布拓扑，请右键单击 " **Lync Server** " 节点，然后单击 "**发布拓扑**"。
    
    ![显示已配置拓扑的拓扑生成器](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "显示已配置拓扑的拓扑生成器")

11. 发布过程完成后，单击“完成”****。

若要安装配置存储的本地副本并启动所需的服务，请参阅部署文档中的为[Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)。


</div>

<span> </span>

</div>

</div>

</div>

