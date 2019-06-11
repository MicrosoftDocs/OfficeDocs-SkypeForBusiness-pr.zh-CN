---
title: Lync Server 2013：在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>在 Lync Server 2013 中在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

如果主持久聊天数据库故障转移到其镜像数据库, 请执行以下步骤, 以使日志传送继续进行。

1.  将主持久聊天数据库手动故障转移到镜像。 这可通过使用 Lync Server 命令行管理程序和**CsDatabaseFailover** cmdlet 来完成。 有关详细信息, 请参阅在[Lync server 2013 中部署 SQL 镜像以获得后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的 "使用 Lync Server Management Shell cmdlet"。

2.  使用 SQL Server Management Studio 连接到主持久聊天服务器镜像实例。

3.  请确保 SQL Server 代理正在运行。

4.  右键单击 mgc 数据库，然后单击“**属性**”。

5.  在“**选择页**”下，单击“**事务日志传送**”。

6.  选中“**将此数据库启用为日志传送配置中的主数据库**”复选框。

7.  在“**事务日志备份**”下，单击“**备份设置**”。

8.  在 "**备份文件夹的网络路径**" 框中, 键入为 "事务日志备份" 文件夹创建的共享的网络路径。

9.  如果备份文件夹位于主服务器上, 请在 "**如果备份文件夹位于主服务器上**" 中键入备份文件夹的本地路径, 请在 "文件夹" 框中键入本地路径。 (如果备份文件夹不在主服务器上, 你可以将此框留空。)
    
    <div>
    

    > [!IMPORTANT]  
    > 如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行, 则必须在主服务器上创建备份文件夹, 并指定该文件夹的本地路径。

    
    </div>

10. 配置“**删除文件，如果其保留时间超过**”和“**在以下时间内没有执行备份时报警**”参数。

11. 查看“**备份作业**”下的“**计划**”框中所列的备份计划。 若要自定义安装的计划, 请单击 "**计划**", 然后根据需要调整 SQL Server 代理计划。
    
    <div>
    

    > [!IMPORTANT]  
    > 使用您用于主数据库的相同设置。

    
    </div>

12. 在 "**压缩**" 下, 选择 "**使用默认服务器设置**", 然后单击 **"确定"**。

13. 在“**辅助服务器实例和数据库**”下，单击“**添加**”。

14. 单击 "**连接**", 并连接到已配置为辅助服务器的 SQL Server 实例。

15. 在“**辅助数据库**”框中，从列表中选择“**mgc**”数据库。

16. 在 "**初始化辅助数据库**" 选项卡上, 选择 "**否, 辅助数据库已初始化**"。

17. 在 "**复制**文件" 选项卡上, 在 "**复制的文件的目标文件夹**" 中, 键入应将事务日志备份复制到其中的文件夹的路径, 然后单击 **"确定"**。 此文件夹通常位于辅助服务器上。

18. 打开 "**脚本配置**" 下拉列表, 然后选择 "**对新查询进行脚本配置" 窗口**。

19. 在 "新建查询" 窗口的 "**数据库属性**" 中, 单击 **"确定"** 开始配置过程。

20. 选择并运行查询的第一半 (请参阅步骤 18 \* \* \* \* \* \* ) 至行:--结束: 要在主要\* \* \* \* \* \*位置运行的脚本:。
    
    <div>
    

    > [!IMPORTANT]  
    > 必须手动运行此脚本, 因为 SQL Server Management Studio 不支持 SQL Server 日志传送配置中的多个主数据库。

    
    </div>

21. 选择 "**取消**" 以关闭日志文件传输配置面板, 并建立可正确为主数据库和镜像数据库 (如果故障转移) 实现日志文件传送的工作设置。

22. 将主持久聊天数据库手动故障恢复到主数据库。 这可通过使用 Lync Server 命令行管理程序和**CsDatabaseFailover** cmdlet 来完成。 有关详细信息, 请参阅在[Lync server 2013 中部署 SQL 镜像以获得后端服务器高可用性](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)的 "使用 Lync Server Management Shell cmdlet"。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

