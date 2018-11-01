---
title: Lync Server 2013：发布拓扑
TOCTitle: 发布拓扑
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425880(v=OCS.15)
ms:contentKeyID: 49312556
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中发布拓扑

 

_**上一次修改主题：** 2013-10-01_

要在添加或删除服务器角色后成功发布、启用或禁用拓扑，您应该以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。还有可能委派相应的管理员权限。有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。

在 拓扑生成器中定义拓扑后，必须将该拓扑发布到中央管理存储。中央管理存储提供定义、设置、维护、管理、描述和运行 Lync Server 2013 部署所需的数据的强大图式化存储。它还会验证数据，以确保配置的一致性。对此配置数据的所有更改都在中央管理存储进行，这样可以消除“不同步”问题。数据的只读副本将复制到拓扑中的所有服务器，包括边缘服务器。

> [!NOTE]  
> SQL Server 至少需要 20 GB 的可用空间才能成功发布初始拓扑并创建中央管理服务器。



> [!NOTE]  
> 仅限 Enterprise Edition：为了发布该拓扑，基于 SQL Server 的后端服务器必须处于联机状态，并且可以通过启用的防火墙例外规则访问。有关指定防火墙例外的详细信息，请参阅 <a href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">了解 SQL Server 与 Lync Server 2013 一起使用时的防火墙要求</a>。有关配置 SQL Server 的详细信息，请参阅 <a href="lync-server-2013-configure-sql-server-for-lync-server.md">为 Lync Server 2013 配置 SQL Server</a>。



## 发布拓扑

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  选择从本地文件打开拓扑。如果位于定义拓扑的计算机上，则将位于前面步骤中所保存的位置。通常，这是配置该拓扑的用户的“文档”文件夹。

3.  右键单击“Lync Server 2013”节点，然后单击“发布拓扑”。

4.  在“发布拓扑”页上，单击“下一步”。

5.  在“创建数据库”页上，选择要发布的数据库。
    
    > [!NOTE]  
	> 如果您没有创建数据库的相应权限，可以清除这些数据库旁边的复选框，稍后可以由具有相应权限的用户创建数据库。有关详细信息，请参阅 <a href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync Server 2013 中 SQL Server 的部署权限</a>。
    


6.  也可以单“高级”。通过高级 SQL Server 数据文件放置选项，您可以在以下选项之间进行选择：
    
      - **自动确定数据库文件位置** – 此选项将通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器上的磁盘配置确定最佳运行性能。
    
      - **使用 SQL Server 实例默认值** – 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”，然后单击“下一步”。

7.  在“选择中央管理服务器”页上，选择 前端池。

8.  也可以单击“高级”。通过高级 SQL Server 数据文件放置选项，您可以在以下选项之间进行选择：
    
      - **自动确定数据库文件位置** – 此选项将通过向最佳位置分发日志和数据文件，根据基于 SQL Server 的服务器上的磁盘配置确定最佳运行性能。
    
      - **使用 SQL Server 实例默认值** – 此选项通过使用实例设置将日志和数据文件置于基于 SQL Server 的服务器上。此选项不会使用基于 SQL Server 的服务器的运行功能来确定日志和数据的最佳位置。通常，SQL Server 管理员会将日志和数据文件移动到适用于基于 SQL Server 的服务器和组织管理过程的位置。
    
    单击“确定”。

9.  单击“下一步”完成发布过程。

10. 发布过程完成后，单击“完成”。
    
    成功发布拓扑后，您可以开始在拓扑中运行 Lync Server 2013 的每台服务器上安装 中央管理存储的本地副本。我们建议您从第一个 前端池开始。

## 另请参阅

#### 其他资源

[为 Lync Server 2013 设置前端服务器和前端池](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)

