---
title: 还原镜像的企业版后端服务器-主服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>在 Lync Server 2013 中还原镜像的企业版后端服务器-主要

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-17_

如果在镜像配置中有企业版后端服务器, 并且只有主数据库出现故障, 请按照本部分中的步骤操作。 如果主数据库和镜像均失败, 请参阅[在 Lync Server 2013 中还原企业版后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。 如果只有镜像失败, 请参阅[在 Lync server 2013-镜像中还原镜像的企业版后端服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。 如果托管中央管理存储的数据库失败, 请参阅[在 Lync server 2013 中还原托管中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。 如果不是后端服务器的企业版成员服务器出现故障, 请参阅[在 Lync server 2013 中还原企业版成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

我们建议你先拍摄系统的映像副本, 然后再开始还原。 你可以将此映像用作回退点, 以防在还原过程中出现问题。 您可能希望在安装操作系统和 SQL Server 后获取图像副本, 并还原或重新注册证书。

在本主题中, 示例主数据库将具有 BE1.contoso.com 的完全限定的域名 (FQDN), 并且镜像数据库将具有 BE2.contoso.com 的 FQDN。

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>还原企业版后端服务器主数据库

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

2.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

3.  强制所有已配置的数据库故障转移到镜像。 对于您在此服务器上配置的每个数据库类型, 请键入以下 cmdlet:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    例如：
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > 如果你已将后端数据库配置为使用与见证的同步镜像, 则自动故障转移。

    
    </div>

4.  完成故障转移后, 请执行以下操作:
    
      - 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。
    
      - 在后端服务器上禁用镜像: 右键单击 "**企业版前端池**" 下的 "池", 然后选择 "**编辑属性**"。 在 "**常规**" 选项卡上的 "**关联**" 下, 清除 "**启用 SQL Server 应用商店镜像**" 复选框。 根据需要执行此操作以进行存档和监视。 然后单击 **"确定"**。
    
      - 右键单击 "Lync Server 2013" 节点, 单击 "**拓扑**", 然后单击 "**发布**"。
    
      - 将仍在运行的后端 (BE2.contoso.com) 选为新的 SQL 应用商店。 若要执行此操作, 请右键单击 "**企业版前端池**" 下的 "池", 然后选择 "**编辑属性**"。 在 "**常规**" 选项卡上的 "**关联**" 下, 在 " **SQL Server 应用商店**" 字段中键入运行后的后端的 FQDN (在我们的示例中为 BE2.contoso.com)。
    
      - 右键单击 "Lync Server 2013" 节点, 单击 "**拓扑**", 然后单击 "**发布**"。
    
      - 重启服务, 以便每台服务器可以读取新拓扑。 从 Lync Server 命令行管理程序中, 在属于此池的每个前端服务器上运行以下 cmdlet:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  卸载镜像。 从 Lync Server 命令行管理程序中, 运行以下 cmdlet:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    对此服务器上的所有数据库类型执行此操作。

6.  创建具有相同 FQDN (在此示例中为 DB1.contoso.com) 的干净或新服务器作为失败的计算机, 安装操作系统, 然后还原或重新注册证书。 此服务器将作为新镜像运行。

7.  从 RTCUniversalServerAdmins 组成员的用户帐户登录到新服务器。

8.  安装 SQL Server 2012 或 SQL Server 2008 R2, 使实例名称与失败之前保持相同。

9.  从作为 RTCUniversalServerAdmins 组成员的用户帐户登录到前端服务器。

10. 使用拓扑生成器安装镜像数据库。 执行以下步骤:
    
      - 启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。
    
      - 在后端服务器上启用镜像。 若要执行此操作, 请右键单击 "**企业版前端池**" 下的 "池", 然后选择 "**编辑属性**"。 在 "**常规**" 选项卡上的 "**关联**" 下, 选中 "**启用 SQL Server 应用商店镜像**" 复选框。 如果需要, 还可执行存档和监视等操作。
        
        然后, 在 "**镜像 SQL Server 应用商店**" 字段中, 键入新服务器的 FQDN (n 本示例, BE1.contoso.com)。 然后单击 **"确定"**。
    
      - 右键单击 "Lync Server 2013" 节点, 单击 "**拓扑结构**", 然后单击 "**安装数据库**"。
    
      - 按照**安装数据库**向导操作。 在 "**创建数据库**" 页面上, 选择要重新创建的数据库。
    
      - 按照向导中的步骤操作, 直到出现提示 "**创建镜像数据库**"。 选择要安装的数据库, 然后完成此过程。

</div>

</div>

<span> </span>

</div>

</div>

</div>

