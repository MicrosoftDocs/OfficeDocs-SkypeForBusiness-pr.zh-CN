---
title: 发布更新的拓扑以添加存档数据库
TOCTitle: 发布更新的拓扑以添加存档数据库
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204860(v=OCS.15)
ms:contentKeyID: 49312703
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 发布更新的拓扑以添加存档数据库

 

_**上一次修改主题：** 2012-10-01_

在拓扑生成器中更新拓扑之后，必须在配置和使用存档之前先将拓扑发布至中央管理存储。数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。

## 发布更新后的拓扑

1.  在运行 Lync Server 2013 或安装有 Lync Server 管理工具的计算机上，使用为本地 Users 组成员的帐户（或具有同等用户权限的帐户）登录。
    
    > [!NOTE]  
	> 您可以使用为本地 Users 组成员的帐户定义拓扑，但要发布拓扑（向拓扑中添加服务器时需要），您必须使用为“Domain Admins”组和“RTCUniversalServerAdmins”组成员的帐户，且该帐户对您要用于 Lync Server 2013 文件存储的文件共享具有完全控制权限（即读取、写入和修改）（以便拓扑生成器可以配置必需的随机访问控制列表 (DACL)），或者使用具有同等权限的帐户。
    


2.  使用拓扑生成器打开在前面的部分中创建的拓扑。

3.  在控制台树中，右键单击“Lync Server 2013”，然后单击“发布拓扑”。

4.  在“发布拓扑”页上，单击“下一步”。

5.  在“创建数据库”页上，确认已经选择了数据库，然后单击“下一步”。
    
    > [!NOTE]  
	> 如果没有创建数据库所需的相应权限，则可以取消数据库的选择，并且具有相应权限的人可以创建数据库。有关所需的管理员权限的详细信息，请参阅部署文档中的 <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 中 SQL Server 的部署权限</a>。<br />
    > 只有专用 SQL Server 上的数据库才能使用拓扑生成器进行安装。与其他服务器组件并置的 SQL Server 上的数据库必须通过在该计算机上运行本地安装程序进行安装。
    


6.  在“发布向导完成”页上，确认已成功发布拓扑，然后单击“完成”。
    
    > [!IMPORTANT]
    > 发布拓扑后，必须配置存档选项和策略，然后才能存档任何内容。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-support-for-archiving.md">配置存档支持</a>。

