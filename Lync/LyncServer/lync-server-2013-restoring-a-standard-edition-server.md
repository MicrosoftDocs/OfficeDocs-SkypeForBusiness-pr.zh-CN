---
title: 还原 Standard Edition Server
TOCTitle: 还原 Standard Edition Server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202190(v=OCS.15)
ms:contentKeyID: 52061133
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原 Standard Edition Server

 

_**上一次修改主题：** 2013-02-21_

如果未托管中央管理存储的 Standard Edition Server 出现故障，请按照本节中的过程操作。如果中央管理存储出现故障，请参阅[还原承载中央管理存储的服务器](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)。

> [!TIP]
> 建议在开始还原之前制作系统的映像副本，以便在还原过程中出现问题时可将该映像作为回滚点。您可能需要在安装操作系统和 SQL Server 之后制作映像副本，然后再还原或重新注册证书。


## 还原 Standard Edition Server

1.  首先准备与出现故障的计算机具有相同完全限定域名 (FQDN) 的干净或新服务器，接着安装操作系统，然后还原或重新注册证书。
    
    > [!NOTE]  
	> 按照您组织的服务器部署过程来执行该步骤。
    


2.  使用具有 RTCUniversalServerAdmins 组和本地 Administrators 组成员身份的用户帐户登录到要还原的服务器。

3.  通过将相应文件存储从 $Backup 复制到服务器上的文件存储位置来还原文件存储，然后共享该文件夹。
    
    > [!IMPORTANT]
    > 还原的文件存储的路径和文件名应与备份的文件存储完全相同，以便使用这些文件的组件可以访问它们。


4.  运行拓扑生成器：
    
    1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。
    
    2.  单击“从现有部署下载拓扑”，然后单击“确定”。
    
    3.  选择拓扑，然后单击“保存”。单击“是”确认您的选择。

5.  浏览到 Lync Server 安装文件夹或介质，然后启动位于 \\setup\\amd64\\Setup.exe 中的 Lync Server 部署向导。使用 Lync Server 部署向导执行以下操作：
    
    1.  运行“步骤 1: 安装本地配置存储”以安装本地配置文件。
    
    2.  运行“步骤 2: 安装或删除 Lync Server 组件”以安装 Lync Server 服务器角色。
    
    3.  运行“步骤 3: 请求、安装或分配证书”以分配证书。
    
    4.  运行“步骤 4: 启动服务”以在服务器上启动服务。
    
    有关运行部署向导的详细信息，请参阅适用于您要还原的服务器角色的部署文档。

6.  执行以下操作以还原用户数据：
    
    1.  将 ExportedUserData.zip 从 $Backup\\ 复制到本地目录。
    
    2.  在还原用户数据之前，您必须停止 Lync 服务。为此，请键入以下命令：
        
            Stop-CsWindowsService
    
    3.  若要还原用户数据，请在命令行中键入：
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        例如：
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  键入以下命令重新启动 Lync 服务：
        
            Start-CsWindowsService

7.  如果在此 Standard Edition Server 上部署了响应组，请还原响应组配置数据。有关详细信息，请参阅[还原响应组设置](lync-server-2013-restoring-response-group-settings.md)。

8.  如果在此 Standard Edition Server 上部署了持久聊天，请还原持久聊天数据库 (mgc.mdf)。
    
    如果在备份持久聊天数据库时使用的是 SQL Server 备份，请使用 SQL Server 还原过程来还原该数据库。
    
    如果在备份数据时使用的是 Export-CsPersistentChatData cmdlet，请使用 Import-CsPersistentChatData 来还原这些数据。

