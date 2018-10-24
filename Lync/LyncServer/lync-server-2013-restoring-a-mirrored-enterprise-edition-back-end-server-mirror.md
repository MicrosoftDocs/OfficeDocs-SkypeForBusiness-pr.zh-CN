---
title: 还原镜像企业版后端服务器 - 镜像
TOCTitle: 还原镜像企业版后端服务器 - 镜像
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945626(v=OCS.15)
ms:contentKeyID: 52061016
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原镜像企业版后端服务器 - 镜像

 

_**上一次修改主题：** 2013-02-19_

如果您的 Enterprise Edition 后端服务器位于镜像配置中并且只有镜像数据库出现故障，请按照本节中的过程操作。如果主数据库和镜像数据库都出现故障，请参阅[还原 Enterprise Edition 后端服务器](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)。如果只有主数据库出现故障，请参阅[还原镜像企业版后端服务器 - 主服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)。如果承载中央管理存储的数据库出现故障，请参阅[还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。如果不是后端服务器的 Enterprise Edition 成员服务器出现故障，请参阅[还原 Enterprise Edition 成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

建议在开始还原之前制作系统的映像副本。在还原过程中出现问题时可将该映像作为回滚点。您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。

## 还原 Enterprise Edition 后端服务器镜像数据库

1.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到前端服务器。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  卸载镜像。首先键入以下 cmdlet：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    例如：
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    对此服务器上的所有数据库类型执行此操作。

4.  创建与出现故障的计算机具有相同完全限定域名 (FQDN) (DB1.contoso.com) 的干净或新服务器，接着安装操作系统，然后还原或重新注册证书。此服务器将用作新的镜像服务器。

5.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到新服务器。

6.  安装 SQL Server 2012 或 SQL Server 2008 R2，保留出现故障之前的实例名称。

7.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到前端服务器。

8.  使用拓扑生成器安装镜像数据库。执行以下操作：
    
      - 启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
      - 右键单击“Lync Server 2013”节点，单击“拓扑”，然后单击“安装数据库”。
    
      - 按照“安装数据库”向导操作。在“创建数据库”页上，选择要重新创建的数据库。
    
      - 按照向导中的步骤操作，直到出现“创建镜像数据库”提示。选择要安装的数据库并完成此过程。
        
        > [!TIP]  
        > 可使用 <strong>Install-CsMirrorDatabase</strong> cmdlet 配置镜像，而不是运行拓扑生成器。有关详细信息，请参阅 Lync Server 命令行管理程序文档。

