---
title: 在 Lync Server 2013 中升级或更新后端服务器或 Standard Edition Server
TOCTitle: 在 Lync Server 2013 中升级或更新后端服务器或 Standard Edition Server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49888688
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中升级或更新后端服务器或 Standard Edition Server

 

_**上一次修改主题：** 2012-11-01_

本主题介绍如何在 企业版后端服务器 或 标准版 服务器上安装更新。

如果在您升级后端服务器时它至少要停机 30 分钟，则用户可能会进入恢复能力模式。升级完成，且后端服务器又与池中的前端服务器连接后，用户会返回到全部功能。如果升级所用时间少于 30 分钟，将不会对用户造成影响。

## 更新后端服务器或 Standard Edition Server

1.  以 CsAdministrator 角色的成员身份登录到要升级的服务器。

2.  下载更新并将其提取到本地硬盘。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 命令行管理程序”。

4.  停止 Lync Server 服务。在命令行中键入：
    
        Stop-CsWindowsService

5.  停止万维网服务。在命令行中键入：
    
        net stop w3svc

6.  关闭所有 Lync Server 命令行管理程序窗口。

7.  安装该更新。

8.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 命令行管理程序”。

9.  再次停止 Lync Server 服务以缓存全局程序集缓存 (GAC) –d 程序集。在命令行中键入：
    
        Stop-CsWindowsService

10. 重新启动万维网服务。在命令行中键入：
    
        net start w3svc

11. 通过执行以下操作之一将 LyncServerUpdateInstaller.exe 进行的更改应用于 SQL Server 数据库：
    
      - 如果这是 企业版后端服务器，且此服务器上没有并置数据库（例如，存档数据库或监控数据库），则在命令行处键入下列内容：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - 如果这是 企业版后端服务器，且在此服务器上没有并置数据库，则在命令行处键入下列内容：
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - 如果这是 标准版 服务器，则在命令行处键入下列内容：
        
            Install-CsDatabase -Update -LocalDatabases

