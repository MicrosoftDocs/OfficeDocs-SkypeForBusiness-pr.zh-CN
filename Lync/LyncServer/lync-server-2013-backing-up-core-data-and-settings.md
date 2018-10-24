---
title: 备份核心数据和设置
TOCTitle: 备份核心数据和设置
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202170(v=OCS.15)
ms:contentKeyID: 52060981
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 备份核心数据和设置

 

_**上一次修改主题：** 2014-04-23_

下列过程使用 Lync Server 命令行管理程序 cmdlet 为核心服务的设置和数据创建备份文件。有关本节中使用的工具（包括它们的位置）的详细信息，请参阅[备份和还原要求：工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。有关备份存档和监控数据的详细信息，请参阅[备份存档和监控数据库](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。

> [!NOTE]  
> 本节中备份中央管理存储的步骤包括备份存档和监控的设置和配置。



您可以在本地运行本节所述的 cmdlet，也可以远程运行它们。

## 备份核心数据和设置

1.  通过 RTCUniversalServerAdmins 组成员的用户帐户，登录内部部署中的任意计算机。

2.  若要采用以下步骤存储创建的备份，请创建新的共享文件夹，并将 **$Backup** 引用的路径更新到该新共享文件夹。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

4.  备份中央管理存储配置文件。在命令行中键入：
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    > [!NOTE]  
    > 该步骤会将 Lync Server 拓扑、策略和配置设置导出到一个文件中。无需使用其他步骤来备份拓扑数据。
    


5.  将备份的中央管理存储配置文件复制到 $Backup\\ 下。

6.  备份位置信息服务数据。在命令行中键入：
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    例如：
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  将备份的位置信息服务配置文件复制到 $Backup\\ 下。

8.  备份前端池每个后端数据库和每个 Standard Edition Server 上的用户数据。在命令行中键入：
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    例如：
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  将备份的用户文件复制到 $Backup\\ 下。

10. 在运行响应组应用程序的每个池上，备份响应组配置。请执行以下操作：
    
    1.  在命令行中键入：
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        例如：
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. 将备份的响应组配置文件复制到 $Backup\\ 下。

