---
title: 还原镜像的企业版后端服务器-镜像
description: 还原镜像的企业版后端服务器镜像。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 011c0aaa10ffed6fef7d579dbc16993fd3341070
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543798"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>在 Lync Server 2013-镜像中还原镜像的企业版后端服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-19_

如果在镜像配置中有企业版后端服务器且只有镜像失败，请按照本节中的过程操作。 如果主数据库和镜像都失败，请参阅 [在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 如果只有主服务器出现故障，请参阅 [在 Lync Server 2013 中还原镜像的企业版后端服务器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。 如果承载中央管理存储的数据库失败，请参阅 [在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是后端服务器的企业版成员服务器出现故障，请参阅 [在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

我们建议您先获取系统的图像副本，然后再开始还原。 您可以将此图像用作回滚点，以防还原过程中出现问题。 您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>还原企业版后端服务器镜像数据库

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  卸载镜像。 首先，键入以下 cmdlet：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    对此服务器上的所有数据库类型执行此操作。

4.  创建具有相同完全限定的域名 (FQDN)  (DB1.contoso.com) 作为故障计算机的全新或新服务器，安装操作系统，然后还原或重新注册证书。 此服务器将作为新镜像运行。

5.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。

6.  安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与失败前相同。

7.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

8.  使用拓扑生成器安装镜像数据库。 执行以下操作：
    
      - 启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
      - 右键单击 "Lync Server 2013" 节点，单击 " **拓扑**"，然后单击 " **安装数据库**"。
    
      - 按照 " **安装数据库** " 向导操作。 在 " **创建数据库** " 页上，选择要重新创建的数据库。
    
      - 按照向导操作，直到出现 " **创建镜像数据库** " 的提示。 选择要安装的数据库并完成此过程。
        
        <div>
        

        > [!TIP]
        > 您可以使用 <STRONG>CsMirrorDatabase</STRONG> cmdlet 配置镜像，而无需运行拓扑生成器。 有关详细信息，请参阅 Lync Server 命令行管理程序文档。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

