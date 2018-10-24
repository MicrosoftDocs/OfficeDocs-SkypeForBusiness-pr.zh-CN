---
title: Lync Server 2013：在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送
TOCTitle: 在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204887(v=OCS.15)
ms:contentKeyID: 49312809
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中在主镜像和日志传送辅助数据库之间设置 SQL Server 日志传送

 

_**上一次修改主题：** 2013-02-21_

如果主 持久聊天数据库故障转移到其镜像数据库，请执行以下步骤以便日志传送能够继续。

1.  手动将主持久聊天数据库故障转移到镜像。这可通过使用 Lync Server 命令行管理程序和 **Invoke-CsDatabaseFailover** cmdlet 完成。有关详细信息，请参阅[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)中的“使用 Lync Server 命令行管理程序 Cmdlet”。

2.  使用 SQL Server Management Studio，连接到主 持久聊天服务器镜像实例。

3.  确保 SQL Server 代理正在运行。

4.  右键单击 mgc 数据库，然后单击“属性”。

5.  在“选择页”下，单击“事务日志传送”。

6.  选中“将此数据库启用为日志传送配置中的主数据库”复选框。

7.  在“事务日志备份”下，单击“备份设置”。

8.  在“备份文件夹的网络路径”框中，键入您为事务日志备份文件夹创建的共享的网络路径。

9.  如果备份文件夹位于主服务器上，请在“如果备份文件夹位于主服务器上，则键入该文件夹的本地路径（示例: c:\\backup）：”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）
    
    > [!IMPORTANT]
    > 如果主服务器上的 SQL Server 服务帐户在本地系统帐户下运行，则必须在主服务器上创建备份文件夹并指定该文件夹的本地路径。


10. 配置“删除文件，如果其保留时间超过”和“在以下时间内没有执行备份时报警”参数。

11. 查看“备份作业”下的“计划”框中所列的备份计划。若要自定义安装的计划，请单击“计划”，然后根据需要调整 SQL Server 代理计划。
    
    > [!IMPORTANT]
    > 使用您对主数据库使用的相同设置。


12. 在“压缩”下，选择“使用默认服务器设置”，然后单击“确定”。

13. 在“辅助服务器实例和数据库”下，单击“添加”。

14. 单击“连接”，然后连接到您已作为辅助服务器配置的 SQL Server 实例。

15. 在“辅助数据库”框中，从列表中选择“mgc”数据库。

16. 在“初始化辅助数据库”选项卡上，选择“否，辅助数据库已初始化”选项。

17. 在“复制文件”选项卡上的“复制文件的目标文件夹”中，键入事务日志备份应复制到的文件夹的路径，然后单击“确定”。此文件夹通常位于辅助服务器上。

18. 打开“脚本配置”下拉列表，然后选择“将配置脚本保存到 "新建查询" 窗口”。

19. 在新建查询窗口中的“数据库属性”上，单击“确定”开始配置过程。

20. 选择并运行查询（参见第 18 步）中以下行之前的前半部分：-- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*。
    
    > [!IMPORTANT]
    > 必须手动运行此脚本，因为 SQL Server Management Studio 在 SQL Server 日志传送配置中不支持多个主数据库。


21. 选择“取消”以关闭日志文件传送配置面板并建立正确实现主数据库和镜像数据库的日志文件传送的工作设置（在故障转移的情况下）。

22. 手动将主持久聊天数据库故障回复到主数据库。这可通过使用 Lync Server 命令行管理程序和 **Invoke-CsDatabaseFailover** cmdlet 完成。有关详细信息，请参阅[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)中的“使用 Lync Server 命令行管理程序 Cmdlet”。

## 另请参阅

#### 概念

[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[在 Lync Server 2013 中针对后端服务器高可用性部署 SQL 镜像](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

