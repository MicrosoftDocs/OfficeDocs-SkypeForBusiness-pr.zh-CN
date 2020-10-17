---
title: 还原镜像的企业版后端服务器-主要
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e28b3657e5e64b1372b924d04b9d42a58460658
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511569"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>在 Lync Server 2013 中还原镜像的企业版后端服务器-主要

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-17_

如果在镜像配置中有一个企业版后端服务器，并且只有主数据库出现故障，请按照本节中的过程操作。 如果主数据库和镜像都失败，请参阅 [在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 如果只有镜像失败，请参阅 [在 Lync Server 2013-镜像中还原镜像的企业版后端服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。 如果承载中央管理存储的数据库失败，请参阅 [在 Lync server 2013 中还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是后端服务器的企业版成员服务器出现故障，请参阅 [在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

我们建议您先获取系统的图像副本，然后再开始还原。 您可以将此图像用作回滚点，以防还原过程中出现问题。 您可能需要在安装操作系统和 SQL Server 后拍摄图像副本，并还原或重新注册证书。

在本主题中，示例主数据库将具有一个完全限定的域名 (FQDN) 为 BE1.contoso.com，镜像数据库将拥有一个 BE2.contoso.com 的 FQDN。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>还原企业版后端服务器主数据库

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  强制所有已配置的数据库故障转移到镜像。 对于您在此服务器上配置的每个数据库类型，请键入以下 cmdlet：
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    例如：
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > 如果已将后端数据库配置为使用具有见证的同步镜像，则故障转移是自动的。

    
    </div>

4.  完成故障转移后，请执行以下操作：
    
      - 启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
      - 在后端服务器上禁用镜像：右键单击 " **Enterprise Edition 前端池** " 下的 "池"，然后选择 " **编辑属性**"。 在 " **常规** " 选项卡上的 " **关联**" 下，清除 " **启用 SQL Server 存储镜像** " 复选框。 执行此操作以根据需要进行存档和监视。 单击" **确定**"。
    
      - 右键单击 "Lync Server 2013" 节点，单击 " **拓扑**"，然后单击 " **发布**"。
    
      - 选择 "仍在运行后端 (BE2.contoso.com) 为新的 SQL 存储。 为此，请右键单击 " **Enterprise Edition 前端池** " 下的 "池"，然后选择 " **编辑属性**"。 在 " **常规** " 选项卡上的 " **关联**" 下，在 BE2.contoso.com 中的示例中，键入 " **SQL Server 存储** " 字段中的 "正常运行后端的 FQDN" () 。
    
      - 右键单击 "Lync Server 2013" 节点，单击 " **拓扑**"，然后单击 " **发布**"。
    
      - 重新启动服务，以便每个服务器可以读取新的拓扑。 在 Lync Server 命令行管理程序中，在属于此池的每台前端服务器上运行以下 cmdlet：
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  卸载镜像。 在 Lync Server 命令行管理程序中，运行以下 cmdlet：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    对此服务器上的所有数据库类型执行此操作。

6.  创建具有相同 FQDN (的干净或新服务器。在此示例中，DB1.contoso.com) 为故障计算机，安装操作系统，然后还原或重新注册证书。 此服务器将作为新镜像运行。

7.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。

8.  安装 SQL Server 2012 或 SQL Server 2008 R2，并保持实例名称与失败前相同。

9.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

10. 使用拓扑生成器安装镜像数据库。 执行以下步骤：
    
      - 启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。
    
      - 在后端服务器上启用镜像。 为此，请右键单击 " **Enterprise Edition 前端池** " 下的 "池"，然后选择 " **编辑属性**"。 在 " **常规** " 选项卡上的 " **关联**" 下，选中 " **启用 SQL Server 存储镜像** " 复选框。 如果需要，还可以执行存档和监控。
        
        然后，在 " **镜像 SQL Server 存储** " 字段中，键入新服务器的 FQDN (n 在此示例中，BE1.contoso.com) 。 单击" **确定**"。
    
      - 右键单击 "Lync Server 2013" 节点，单击 " **拓扑**"，然后单击 " **安装数据库**"。
    
      - 按照 " **安装数据库** " 向导操作。 在 " **创建数据库** " 页上，选择要重新创建的数据库。
    
      - 按照向导操作，直到出现提示， **创建镜像数据库**。 选择要安装的数据库，并完成此过程。

</div>

</div>

<span> </span>

</div>

</div>

</div>

