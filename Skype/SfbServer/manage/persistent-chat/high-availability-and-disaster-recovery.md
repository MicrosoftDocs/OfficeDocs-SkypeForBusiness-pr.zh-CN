---
title: Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器高可用性和灾难恢复。
ms.openlocfilehash: b3535d87f939da1e8dc0caf2368ec5de77573639ca362002a097f1b1d9afd6c9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324281"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015
 
**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复。
  
本主题介绍如何对持久聊天服务器进行故障转移和故障回复。 在阅读本主题之前，请务必阅读在[Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)中规划持久聊天服务器的高可用性和灾难恢复和在[Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。

> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
  
## <a name="fail-over-persistent-chat-server"></a>故障转移持久聊天服务器

持久聊天服务器的故障转移主要是一个手动过程。
  
故障转移过程基于以下假设：辅助数据中心已启动且正在运行，但持久聊天数据库所在的持久聊天服务器服务完全不可用，其中包括：
  
- 持久聊天服务器主数据库和持久聊天服务器镜像数据库已关闭。
    
- Skype for Business Server前端服务器已关闭。
    
该过程主要包含两个基本步骤：
  
- 恢复主持久聊天数据库 (mgc) 。
    
- 建立新的主数据库的镜像。
    
未进行 (mgccomp) 持久聊天合规性数据库。 此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。 作为持久聊天管理员，您有责任正确管理适配器输出以避免数据丢失。
  
对持久聊天服务器进行故障转移：
  
1. 从持久聊天服务器备份日志发货数据库中删除日志寄送。
    
   - 使用 SQL Server Management Studio，连接到持久聊天服务器备份 mgc 数据库所在的数据库实例。
    
   - 打开主数据库的查询窗口。
    
   - 使用以下命令取消日志传送：
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。
    
3. 按顺序将任何未应用的事务日志备份应用到辅助数据库。 有关详细信息，请参阅[如何：将事务日志备份 (Transact-SQL) ](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))。
    
4. 使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：
    
   - 如果包含以下项，将断开与 mgc 数据库的所有连接：
    
   - **exec sp_who2** 标识与 mgc 数据库的连接。
    
   - **kill \<spid\>** 以结束这些连接。
    
   - 使数据库联机：
    
   - **使用恢复 还原数据库 mgc。**
    
5. 在 Skype for Business Server 命令行管理程序 中，使用 **命令 Set-CsPersistentChatState -Identity "service：atl-cs-001.litwareinc.com" -PoolState FailedOver** 故障转移到 mgc 备份数据库。 请务必将持久聊天池的完全限定域名替换为 atl-cs-001.litwareinc.com。
    
    mgc 备份数据库现在充当主数据库。
    
6. 在Skype for Business Server命令行管理程序中，使用 **Install-CsMirrorDatabase** cmdlet 为现在用作主数据库的备份数据库建立高可用性镜像。 使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。 此镜像与最初在安装期间为主数据库配置的镜像不同。
    
7. 设置持久聊天服务器活动服务器。 在命令行Skype for Business Server命令行管理程序中，使用 **Set-CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
    此时，从持久聊天服务器主数据库到持久聊天服务器备份数据库的故障转移将成功完成。
    
## <a name="fail-back-persistent-chat-server"></a>对持久聊天服务器进行故障回复

此过程概述了从持久聊天服务器故障中恢复以及从主数据中心重新建立操作所需的步骤。
  
在持久聊天服务器故障期间，主数据中心完全中断，主数据库和镜像数据库变得不可用。 主数据中心将故障转移到备份服务器。
  
以下过程在备份主数据中心并重新生成服务器后还原正常操作。 该过程假定主数据中心已从整体中断中恢复，并且 mgc 数据库和 mgccomp 数据库已使用拓扑生成器重新生成和重新安装。
  
该过程还假定在故障转移期间没有部署新的镜像和备份服务器，并且部署的唯一服务器是备份服务器及其镜像服务器，如之前故障转移持久聊天服务器中的定义。
  
这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。
  
1. 使用命令行管理程序中的 **Set-CsPersistentChatActiveServer** cmdlet 清除持久聊天服务器活动服务器列表中Skype for Business Server服务器。 这将阻止所有持久聊天服务器在故障回复期间连接到 mgc 数据库和 mgccomp 数据库。
    
    > [!IMPORTANT]
    > 辅助SQL Server持久聊天服务器后端服务器的客户端代理应在特权帐户下运行。 尤其需要指出的是，该帐户必须具有以下权限： 
  
   - 对于放置备份的网络共享的读取权限。
    
   - 对于备份将复制到的特定本地目录的写入权限。
    
2. 在备份 mgc 数据库上禁用镜像：
    
   - 使用 SQL Server Management Studio，连接到备份 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“任务”，然后单击“镜像”。
    
   - 单击“取消镜像”。
    
   - 单击“确定”。
    
   - 对 mgccomp 数据库执行相同步骤。
    
3. 备份 mgc 数据库，使其可以还原为新主数据库：
    
   - 使用 SQL Server Management Studio，连接到备份 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“任务”，然后单击“备份”。随即将显示“备份数据库”对话框。
    
   - 在“备份类型”中，选择“完全”。
    
   - 对于“备份组件”，请单击“数据库”。
    
   - 接受“名称”中建议的默认备份集名称，或为备份集输入不同名称。
    
   -  *\<Optional\>*  在 **"说明**"中，输入备份集的说明。
    
   - 从目标列表中删除默认备份位置。
    
   - 使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。
    
   - 单击“确定”关闭对话框并开始备份过程。
    
4. 使用上一步中创建的备份数据库还原主数据库。
    
   - 使用 SQL Server Management Studio，连接到主 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“任务”，指向“还原”，然后单击“数据库”。随即会显示“还原数据库”对话框。
    
   - 选择“自设备”。
    
   - 单击浏览按钮，将打开“指定备份”对话框。在“备份媒体”中，选择“文件”。单击“添加”，选择您在步骤 3 中创建的备份文件，然后单击“确定”。
    
   - 在“选择用于还原的备份集”中，选择备份。
    
   - 在“选择页”窗格中单击“选项”。
    
   - 在“还原选项”中，选择“覆盖现有数据库”。
    
   - 在“恢复状态”中，选择“使数据库处于可以使用的状态”。
    
   - 单击“确定”开始还原过程。
    
5. 配置SQL Server数据库的日志日志寄送。 按照在[Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复中的过程，为主 mgc 数据库建立日志寄送。
    
6. 设置持久聊天服务器活动服务器。 在命令行Skype for Business Server命令行管理程序中，使用 **Set-CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器都必须与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
若要将池还原到其正常状态，运行以下Windows PowerShell命令：
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

有关详细信息，请参阅 [Set-CsPersistentChatState](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet 的帮助主题。
