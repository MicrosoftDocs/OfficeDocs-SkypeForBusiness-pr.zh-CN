---
title: Lync Server 2013：发布更新的拓扑以添加存档数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5834c6c7d0386f7943c523a184ea63f8ba129a89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512239"
---
# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a>发布更新后的拓扑以在 Lync Server 2013 中添加存档数据库

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

在拓扑生成器中更新拓扑之后，必须先将拓扑发布到中央管理存储，然后才能配置和使用存档。 数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。

<div>

## <a name="to-publish-your-updated-topology"></a>发布更新后的拓扑

1.  在运行 Lync Server 2013 的计算机上或安装了 Lync Server 管理工具的计算机上，使用属于本地用户组成员的帐户登录 (或具有同等用户权限的帐户) 。
    
    <div>
    

    > [!NOTE]  
    > 您可以通过使用属于本地用户组成员的帐户来定义拓扑，但若要发布将服务器添加到拓扑所需的拓扑，必须使用属于 <STRONG>Domain Admins</STRONG> 组和 <STRONG>RTCUniversalServerAdmins</STRONG> 组成员的帐户。并且具有 "完全控制" 权限 (即读取、写入和修改您在为 Lync server 2013 文件存储 (使用的文件共享上的) ，因此拓扑生成器可以配置所需的任意自由访问控制列表 (dacl) 或具有等效权限的帐户。

    
    </div>

2.  使用拓扑生成器打开在上一节中创建的拓扑。

3.  在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 " **发布拓扑**"。

4.  在“发布拓扑”**** 页上，单击“下一步”****。

5.  在“创建数据库”**** 页上，确认已经选择了数据库，然后单击“下一步”****。
    
    <div>
    

    > [!NOTE]  
    > 如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。 有关所需的管理员权限和权限的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013 中部署 SQL Server 的权限</A> 。<BR>只能使用拓扑生成器安装专用 SQL Server 服务器上的数据库。 与其他服务器组件并置的 SQL Server 服务器上的数据库必须通过在该计算机上运行本地安装程序来安装。

    
    </div>

6.  在“发布向导完成”**** 页上，确认已成功发布拓扑，然后单击“完成”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。 有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-support-for-archiving.md">Lync Server 2013 中配置存档支持</A> 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

