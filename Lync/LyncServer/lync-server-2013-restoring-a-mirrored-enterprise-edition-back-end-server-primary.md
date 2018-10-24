---
title: 还原镜像企业版后端服务器 - 主服务器
TOCTitle: 还原镜像企业版后端服务器 - 主服务器
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945648(v=OCS.15)
ms:contentKeyID: 52061127
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原镜像企业版后端服务器 - 主服务器

 

_**上一次修改主题：** 2013-02-17_

如果您的 Enterprise Edition 后端服务器位于镜像配置中并且只有主数据库出现故障，请按照本节中的过程操作。如果主数据库和镜像数据库都出现故障，请参阅[还原 Enterprise Edition 后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。如果只有镜像数据库出现故障，请参阅[还原镜像企业版后端服务器 - 镜像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)。如果承载中央管理存储的数据库出现故障，请参阅[还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。如果不是后端服务器的 Enterprise Edition 成员服务器出现故障，请参阅[还原 Enterprise Edition 成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

建议在开始还原之前制作系统的映像副本。在还原过程中出现问题时可将该映像作为回滚点。您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。

在本主题中，示例主数据库的完全限定域名 (FQDN) 为 BE1.contoso.com，镜像数据库的 FQDN 为 BE2.contoso.com。

## 还原 Enterprise Edition 后端服务器主数据库

1.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到前端服务器。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  强制所有配置的数据库故障转移到镜像数据库。对于您在此服务器上配置的每种数据库类型，键入以下 cmdlet：
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    例如：
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    > [!WARNING]
    > 如果已将后端数据库配置为使用具有见证的同步镜像，则故障转移是自动的。


4.  完成故障转移后，执行以下操作：
    
      - 启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
      - 在后端服务器上禁用镜像：右键单击“Enterprise Edition 前端池”下面的池，然后选择“编辑属性”。在“常规”选项卡上的“关联”下，清除“启用 SQL Server 存储镜像”复选框。必要时对存档和监控功能执行此操作。然后单击“确定”。
    
      - 右键单击“Lync Server 2013”节点，单击“拓扑”，然后单击“发布拓扑”。
    
      - 选择仍然正常运行的后端 (BE2.contoso.com) 作为新的 SQL 存储。为此，请右键单击“Enterprise Edition 前端池”下面的池，然后选择“编辑属性”。在“常规”选项卡上的“关联”下，在“SQL Server 存储”字段中键入正常运行的后端的 FQDN（在本例中为 BE2.contoso.com）。
    
      - 右键单击“Lync Server 2013”节点，单击“拓扑”，然后单击“发布拓扑”。
    
      - 重新启动服务以便每台服务器都可以读取新拓扑。从 Lync Server 命令行管理程序中，对属于该池的每台前端服务器运行以下 cmdlet：
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  卸载镜像。从 Lync Server 命令行管理程序中，运行以下 cmdlet：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    对此服务器上的所有数据库类型执行此操作。

6.  创建与出现故障的计算机具有相同 FQDN（在本例中 DB1.contoso.com）的干净或新服务器，接着安装操作系统，然后还原或重新注册证书。此服务器将用作新的镜像服务器。

7.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到新服务器。

8.  安装 SQL Server 2012 或 SQL Server 2008 R2，保留出现故障之前的实例名称。

9.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到前端服务器。

10. 使用拓扑生成器安装镜像数据库。执行以下步骤：
    
      - 启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
      - 在后端服务器上启用镜像。为此，请右键单击“Enterprise Edition 前端池”下面的池，然后选择“编辑属性”。在“常规”选项卡上的“关联”上，选中“启用 SQL Server 存储镜像”复选框。必要时对存档和监控功能执行此操作。
        
        然后，在“镜像 SQL Server 存储”字段中，键入新服务器的 FQDN（在本例中为 BE1.contoso.com）。然后单击“确定”。
    
      - 右键单击“Lync Server 2013”节点，单击“拓扑”，然后单击“安装数据库”。
    
      - 按照“安装数据库”向导操作。在“创建数据库”页上，选择要重新创建的数据库。
    
      - 按照向导中的步骤操作，直到出现“创建镜像数据库”提示。选择要安装的数据库并完成此过程。

