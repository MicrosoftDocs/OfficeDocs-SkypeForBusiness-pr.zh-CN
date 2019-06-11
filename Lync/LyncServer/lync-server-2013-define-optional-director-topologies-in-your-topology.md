---
title: Lync Server 2013：在拓扑中定义可选控制器拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>针对 Lync Server 2013 在拓扑中定义可选控制器拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

Lync Server 2013 控制器可以是单实例服务器, 也可以作为多个控制器的负载平衡池进行安装以实现更高的可用性和容量。 硬件负载平衡和域名系统 (DNS) 负载平衡均受支持。 本主题介绍如何为控制器池配置 DNS 负载平衡。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑, 您应以**RTCUniversalServerAdmins**和**域管理员**组成员的用户身份登录。 你还可以委派适当的管理员权限来添加服务器角色。 有关详细信息, 请参阅在标准版服务器或企业版服务器部署文档中[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)"。 对于其他配置更改, 仅需要**RTCUniversalServerAdmins**组中的成员身份。

本主题介绍了为两个控制器拓扑定义和发布拓扑的步骤:

  - 定义导演 (单实例)

  - 定义控制器 (多个控制器池)

<div>

## <a name="to-define-the-director-single-instance"></a>定义导演 (单实例)

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在 "欢迎" 页面上, 单击 "**从现有部署下载拓扑**"。

3.  在 "**将拓扑另存为**" 对话框中, 键入现有拓扑的本地副本的名称和位置, 然后单击 "**保存**"。

4.  展开计划添加 Director 的网站, 右键单击 "**控制器池**", 然后单击 "**新建控制器池**"。

5.  在 "**定义控制器池 FQDN** " 对话框中, 执行下列操作:
    
      - 在 "**池 FQDN**" 中, 键入 Director 池的 FQDN。
    
      - 单击 "**单计算机池**", 然后单击 "**下一步**"。

6.  在 "**定义文件共享**" 对话框中, 执行下列操作之一:
    
    1.  若要使用现有文件共享, 请单击 "**使用以前定义的文件共享**", 从列表中选择文件共享, 然后单击 "**下一步**"。
    
    2.  若要创建新的文件共享, 请单击 "**定义新的文件共享**", 在 "**文件服务器 FQDN**" 中键入文件共享位置的 FQDN, 在 "**文件共享**" 中键入共享的名称, 然后单击 "**下一步**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在此步骤中指定或创建的文件共享必须存在或在发布拓扑之前创建。<BR>不会实际使用分配给 Director 的文件共享, 因此你可以分配组织中任何池的文件共享。

    
    </div>

7.  在 "**指定 Web 服务 URL** " 对话框的 "**外部基础 URL**" 中, 指定控制器的 FQDN, 然后单击 "**完成**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 该名称必须可从 Internet DNS 服务器解析, 并指向反向代理的公共 IP 地址, 后者侦听该 URL 的 HTTP/HTTPS 请求并将它们代理到该 Director 上的外部 Web 服务虚拟目录。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有多个前端池或前端服务器, 则外部 Web 服务 FQDN 必须是唯一的。 例如, 如果你将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>, 则不能将<STRONG>Pool01.contoso.com</STRONG>用于其他前端池或前端服务器。 如果你还部署控制器, 则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果决定使用自定义的 FQDN 替代内部 web 服务, 则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。

    
    </div>

8.  发布拓扑。

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>定义控制器 (多个控制器池)

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在 "欢迎" 页面上, 单击 "**从现有部署下载拓扑**"。

3.  在 "**将拓扑另存为**" 对话框中, 键入现有拓扑的本地副本的名称和位置, 然后单击 "**保存**"。

4.  展开计划添加 Director 的网站, 右键单击 "**控制器池**", 然后单击 "**新建控制器池**"。

5.  在 "**定义控制器池 FQDN** " 对话框中, 执行下列操作:
    
      - 在 "**池 FQDN**" 中, 键入 Director 池的 FQDN。
    
      - 单击 "**多台计算机池**", 然后单击 "**下一步**"。

6.  在 "**定义此池内的计算机**" 对话框中, 执行下列操作:
    
      - 指定第一个池成员的计算机 FQDN, 然后单击 "**添加**"。
    
      - 对要添加的每台计算机重复上一步骤。 完成后, 单击 "**下一步**"。

7.  在 "**定义文件共享**" 对话框中, 执行下列操作之一:
    
      - 若要使用现有文件共享, 请单击 "**使用以前定义的文件共享**", 从列表中选择文件共享, 然后单击 "**下一步**"。
    
      - 若要创建新的文件共享, 请单击 "**定义新的文件共享**", 在 "**文件服务器 FQDN**" 中键入文件共享位置的 FQDN, 在 "**文件共享**" 中键入共享的名称, 然后单击 "**下一步**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 您在此步骤中指定或创建的文件共享必须存在或在发布拓扑之前创建。<BR>不会实际使用分配给 Director 的文件共享, 因此你可以分配组织中任何池的文件共享。

    
    </div>

8.  在 "**指定 Web 服务 URL** " 对话框的 "**外部基础 URL**" 中, 指定控制器的 FQDN, 然后单击 "**完成**"。
    
    <div>
    

    > [!IMPORTANT]  
    > 该名称必须可从 Internet DNS 服务器解析, 并指向反向代理的公共 IP 地址, 后者侦听发送到该 URL 的 HTTP/HTTPS 请求, 并将它们代理到该 Director 池中的外部 Web 服务虚拟目录。

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > 如果您有多个前端池或前端服务器, 则外部 Web 服务 FQDN 必须是唯一的。 例如, 如果你将前端服务器的外部 Web 服务 FQDN 定义为<STRONG>pool01.contoso.com</STRONG>, 则不能将<STRONG>Pool01.contoso.com</STRONG>用于其他前端池或前端服务器。 如果你还部署控制器, 则为任何控制器或控制器池定义的外部 Web 服务 FQDN 必须是任何其他 Director 或控制器池以及任何前端池或前端服务器的唯一。 如果决定使用自定义的 FQDN 替代内部 web 服务, 则每个 FQDN 都必须与任何其他前端池、Director 或控制器池唯一。

    
    </div>

9.  发布拓扑。

</div>

</div>

<span> </span>

</div>

</div>

</div>

