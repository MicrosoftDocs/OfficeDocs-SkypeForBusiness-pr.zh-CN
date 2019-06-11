---
title: 还原镜像的企业版后端服务器-镜像
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 113d69d7aa39673686ff870c36a64bd1a8fe90f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a>在 Lync Server 2013 中还原镜像的企业版后端服务器-镜像

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-19_

如果在镜像配置中有企业版后端服务器且只有镜像失败, 请按照本部分中的步骤操作。 如果主数据库和镜像均失败, 请参阅[在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 如果只有主服务器出现故障, 请参阅[在 Lync server 2013 中还原镜像的企业版后端服务器-主要](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。 如果托管中央管理存储的数据库失败, 请参阅[在 Lync server 2013 中还原托管中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是后端服务器的企业版成员服务器出现故障, 请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

我们建议你先拍摄系统的映像副本, 然后再开始还原。 你可以将此映像用作回退点, 以防在还原过程中出现问题。 您可能希望在安装操作系统和 SQL Server 后获取图像副本, 并还原或重新注册证书。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a>还原企业版后端服务器镜像数据库

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  卸载镜像。 首先, 键入以下 cmdlet:
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    对此服务器上的所有数据库类型执行此操作。

4.  创建具有与失败计算机相同的完全限定的域名 (FQDN) (DB1.contoso.com) 的干净或新服务器, 安装操作系统, 然后还原或重新注册证书。 此服务器将作为新镜像运行。

5.  从 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。

6.  安装 SQL Server 2012 或 SQL Server 2008 R2, 使实例名称与失败之前保持相同。

7.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

8.  使用拓扑生成器安装镜像数据库。 执行下列操作:
    
      - 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。
    
      - 右键单击 "Lync Server 2013" 节点, 单击 "**拓扑结构**", 然后单击 "**安装数据库**"。
    
      - 按照**安装数据库**向导操作。 在 "**创建数据库**" 页面上, 选择要重新创建的数据库。
    
      - 按照向导中的步骤操作, 直到出现 "**创建镜像" 数据库**的提示。 选择要安装的数据库并完成此过程。
        
        <div>
        

        > [!TIP]
        > 你可以使用<STRONG>CsMirrorDatabase</STRONG> cmdlet 配置镜像, 而不是运行拓扑生成器。 有关详细信息, 请参阅 Lync Server Management Shell 文档。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

