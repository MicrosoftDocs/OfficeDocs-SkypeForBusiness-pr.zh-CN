---
title: 还原 Enterprise Edition 后端服务器
TOCTitle: 还原 Enterprise Edition 后端服务器
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202163(v=OCS.15)
ms:contentKeyID: 52060963
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原 Enterprise Edition 后端服务器

 

_**上一次修改主题：** 2013-02-18_

在下列两种情况下使用本主题中介绍的过程：

  - 镜像的 Enterprise Edition 后端服务器的主数据库和镜像数据库均出现故障。

  - 未镜像的 Enterprise Edition 后端服务器出现故障。

如果您拥有镜像的 Enterprise Edition 后端，并且只有镜像数据库或主数据库出现故障，请参阅[还原镜像企业版后端服务器 - 主服务器](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md)还原主数据库，参阅[还原镜像企业版后端服务器 - 镜像](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)还原镜像。

如果中央管理存储出现故障，请参阅[还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。如果不是后端服务器的 Enterprise Edition 成员服务器出现故障，请参阅[还原 Enterprise Edition 成员服务器](lync-server-2013-restoring-an-enterprise-edition-member-server.md)。

> [!TIP]
> 建议在开始还原之前制作系统的映像副本。您可以在还原过程中出现问题时将该映像作为回滚点。您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。


## 还原 Enterprise Edition 后端服务器

1.  首先准备与出现故障的计算机具有相同完全限定域名 (FQDN) 的干净或新服务器，接着安装操作系统，然后还原或重新注册证书。
    
    > [!NOTE]  
	> 按照您组织的服务器部署过程来执行该步骤。
    


2.  使用具有 RTCUniversalServerAdmins 组成员身份的用户帐户登录到要还原的服务器。

3.  安装 SQL Server 2012 或 SQL Server 2008 R2，使实例名称与出现故障前相同。
    
    > [!NOTE]  
	> 根据您的部署，后端服务器可能包含多个并置或独立数据库。按照先前部署服务器时使用的过程来安装 SQL Server，包括 SQL Server 权限和登录名。
    


4.  安装 SQL Server 后，执行以下操作：
    
    1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
    2.  单击“从现有部署下载拓扑”，然后单击“确定”。
    
    3.  选择拓扑，然后单击“保存”。单击“是”确认您的选择。
    
    4.  右键单击“Lync Server 2013”节点，然后单击“发布拓扑”。
    
    5.  按照“发布拓扑”向导操作。在“创建数据库”页上，选择要重新创建的数据库。
        
        > [!NOTE]  
		> 只有独立数据库会显示在“创建数据库”页上。
        
    
    6.  如果要还原镜像的后端，则继续按照向导的其余部分操作，直到出现“创建镜像数据库”的提示。选择要安装的数据库，然后完成该过程。
    
    7.  按照向导的其余部分操作，然后单击“完成”。
    
    > [!TIP]
    > 可以使用 <strong>Install-CsDatabase</strong> cmdlet 创建每个数据库，使用 <strong>Install-CsMirrorDatabase</strong> cmdlet 配置镜像，而不是运行拓扑生成器。有关详细信息，请参阅 Lync Server 命令行管理程序文档。


5.  执行以下操作以还原用户数据：
    
    1.  将 ExportedUserData.zip 从 $Backup\\ 复制到本地目录。
    
    2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。
    
    3.  还原用户数据之前，必须停止 Lync 服务。为此，请键入：
        
            Stop-CsWindowsService
    
    4.  若要还原用户数据，请在命令行中键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  键入以下命令重新启动 Lync 服务：
        
            Start-CsWindowsService

6.  如果在该池中部署了响应组，请还原响应组配置数据。有关详细信息，请参阅[还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

7.  如果要还原的后端服务器包含存档或监控数据库，请使用 SQL Server 工具（如 SQL Server Management Studio）还原存档或监控数据。有关详细信息，请参阅[还原监控或存档数据](lync-server-2013-restoring-monitoring-or-archiving-data.md)。

