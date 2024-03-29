---
title: Business Server 2015：为持久聊天服务器配置高可用性和灾难恢复
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 了解如何在 Skype for Business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复。
ms.openlocfilehash: b98f4c49cb3643faa6d6bbe7b899634a4ef6b159
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397455"
---
# <a name="business-server-2015-configure-high-availability-and-disaster-recovery-for-persistent-chat-server"></a>Business Server 2015：为持久聊天服务器配置高可用性和灾难恢复
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中为持久聊天服务器配置高可用性和灾难恢复。
  
Skype for Business Server支持多种模式的后端服务器高可用性，包括数据库镜像。 有关详细信息，请参阅 [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> 持久聊天服务器不支持 AlwaysOn 可用性组。 
  
在配置持久聊天部署以用于高可用性和灾难恢复之前，请确保您熟悉在 [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) 中规划持久聊天服务器的高可用性和灾难恢复中的概念。 这些主题中介绍的持久聊天服务器的灾难恢复解决方案是在拉伸的持久聊天服务器池上构建的。 规划内容介绍了资源要求以及支持持久聊天服务器的高可用性和灾难恢复的扩展池拓扑，包括使用 SQL Server 镜像实现高可用性和实现灾难恢复的 SQL Server 日志。
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>使用拓扑生成器配置高可用性和灾难恢复

在拓扑生成器中，执行以下步骤以配置持久聊天服务器的高可用性和灾难恢复。
  
1. 在存储中添加镜像数据库和日志SQL Server数据库。
    
2. 编辑持久聊天服务器服务属性以：
    
    a. 为主数据库启用镜像。
    
    b. 添加主镜像SQL Server存储。
    
    c. 启用SQL Server日志寄送数据库。
    
    d. 添加SQL Server日志寄送辅助SQL Server存储。
    
    e. 为SQL Server数据库添加数据库存储镜像。
    
    f. 发布拓扑。
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>设置SQL Server持久聊天服务器主数据库的日志日志寄送

使用 SQL Server Management Studio，连接到持久聊天服务器辅助日志日志交付数据库实例，并确保SQL Server代理正在运行。 然后连接到持久聊天主数据库实例并执行以下步骤：
  
1. 右键单击 mgc 数据库，然后单击“属性”。
    
2. 在“选择页”下，单击“事务日志传送”。
    
3. 选中“将此数据库启用为日志传送配置中的主数据库”复选框。
    
4. 在“事务日志备份”下，单击“备份设置”。
    
5. 在“备份文件夹的网络路径”框中，键入您为事务日志备份文件夹创建的共享的网络路径。
    
6. 如果备份文件夹位于主服务器上，请在“如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup):”框中键入该备份文件夹的本地路径。（如果备份文件夹不在主服务器上，则可将此框留空。）
    
    > [!IMPORTANT]
    > 如果主SQL Server上的备份服务帐户在本地系统帐户下运行，则必须在主服务器上创建备份文件夹并指定该文件夹的本地路径。 
  
7. 配置“删除文件，如果其保留时间超过”和“在以下时间内没有执行备份时报警”参数。
    
8. 查看“备份作业”下的“计划”框中所列的备份计划。 若要自定义安装计划，请单击"计划"，然后根据需要SQL Server代理计划。
    
9. 在“压缩”下，选择“使用默认服务器设置”，然后单击“确定”。
    
10. 在“辅助服务器实例和数据库”下，单击“添加”。
    
11. 单击 **连接** 并连接到SQL Server配置为辅助服务器的服务器实例。
    
12. 在“辅助数据库”框中，从列表中选择“mgc”数据库。
    
13. 在" **初始化** 辅助数据库"选项卡上，选择选项"是，生成主数据库的完整备份，并还原到辅助数据库 **(** 如果辅助数据库) "。
    
14. 在“复制文件”选项卡上的“复制文件的目标文件夹”框中，键入应将事务日志备份复制到的文件夹的路径。此文件夹通常位于辅助服务器上。
    
15. 注意“复制作业”下的“计划”框中列出的复制计划。 若要自定义安装计划，请单击"计划"，然后根据需要SQL Server代理计划。 此计划应与备份计划大致相同。
    
16. 在“还原”选项卡上的“还原备份时的数据库状态”下，选择“无恢复模式”选项。
    
17. 在“延迟还原备份操作至少:”下，选择“0 分钟”。
    
18. 在“在以下时间内没有执行还原时报警”下选择报警阈值。
    
19. 查看“还原作业”下的“计划”框中列出的还原计划。 若要自定义安装计划，请单击"计划"，根据需要SQL Server代理计划"，然后单击"确定 **"**。 此计划应与备份计划大致相同。
    
20. 在“数据库属性”对话框中，单击“确定”开始配置过程。
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>设置SQL Server镜像和辅助数据库之间的日志日志寄送

如果主持久聊天数据库出现故障到其镜像数据库，请执行以下步骤以继续日志寄送。
  
1. 手动将主持久聊天数据库故障转移到镜像。 这是通过使用命令行管理程序Skype for Business Server **Invoke-CsDatabaseFailover** cmdlet 完成。
    
2. 使用 SQL Server Management Studio，连接到主持久聊天服务器镜像实例。
    
3. 确保运行SQL Server代理。
    
4. 右键单击 mgc 数据库，然后单击“属性”。
    
5. 在“选择页”下，单击“事务日志传送”。
    
6. 选中“将此数据库启用为日志传送配置中的主数据库”复选框。
    
7. 在“事务日志备份”下，单击“备份设置”。
    
8. 在“备份文件夹的网络路径”框中，键入您为事务日志备份文件夹创建的共享的网络路径。
    
9. 如果备份文件夹位于主服务器上，则在“如果备份文件夹位于主服务器上，则键入该文件夹的本地路径(示例: c:\backup)”框中键入备份文件的本地路径。（如果备份文件夹不在主服务器上，则可以将此框留空。）
    
    > [!IMPORTANT]
    > 如果主SQL Server上的备份服务帐户在本地系统帐户下运行，则必须在主服务器上创建备份文件夹并指定该文件夹的本地路径。 
  
10. 配置“删除文件，如果其保留时间超过”和“在以下时间内没有执行备份时报警”参数。
    
11. 查看“备份作业”下的“计划”框中所列的备份计划。 若要自定义安装计划，请单击"计划"，然后根据需要SQL Server代理计划。
    
    > [!IMPORTANT]
    > 使用您对主数据库使用的相同设置。 
  
12. 在“压缩”下，选择“使用默认服务器设置”，然后单击“确定”。
    
13. 在“辅助服务器实例和数据库”下，单击“添加”。
    
14. 单击“连接”，然后连接到您已作为辅助服务器配置的 SQL Server 实例。
    
15. 在“辅助数据库”框中，从列表中选择“mgc”数据库。
    
16. 在“初始化辅助数据库”选项卡上，选择“否，辅助数据库已初始化”选项。
    
17. 在“复制文件”选项卡上的“复制文件的目标文件夹”中，键入事务日志备份应复制到的文件夹的路径，然后单击“确定”。此文件夹通常位于辅助服务器上。
    
18. 打开“脚本配置”下拉列表，然后选择“将配置脚本保存到‘新建查询’窗口”。
    
19. 在新建查询窗口中的“数据库属性”上，单击“确定”开始配置过程。
    
20. Select and run the first half of the query (see step 18) up to the line： -- \*\*\*\*\*\*End： Script to be run at Primary： . \*\*\*\*\*\*
    
    > [!IMPORTANT]
    > 手动运行此脚本是必需的，因为SQL Server Management Studio日志寄送配置中不支持SQL Server主数据库。 
  
21. 选择“取消”以关闭日志文件传送配置面板并建立正确实现主数据库和镜像数据库的日志文件传送的工作设置（在故障转移的情况下）。
    
22. 手动将主持久聊天数据库故障回复到主持久聊天数据库。 这是通过使用命令行管理程序Skype for Business Server **Invoke-CsDatabaseFailover** cmdlet 完成。
    

