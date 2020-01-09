---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器高可用性和灾难恢复。
ms.openlocfilehash: d46e34485f231d313475b4fdc5948a7262b324ed
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991977"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理持久聊天服务器的高可用性和灾难恢复
 
**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器高可用性和灾难恢复。
  
本主题介绍了如何故障切换和故障回复持久聊天服务器。 阅读本主题之前，请务必阅读适用于 Skype for business [server 2015 中持久聊天服务器的高可用性和灾难恢复计划](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)，并[在 Skype for business Server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。

> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。 
  
## <a name="fail-over-persistent-chat-server"></a>持久聊天服务器故障切换

持久聊天服务器的故障转移主要用于手动过程。
  
故障转移过程基于辅助数据中心已启动并正在运行的假设，但主要持久聊天数据库所在的持久聊天服务器服务完全不可用，包括以下内容：
  
- 持久聊天服务器主数据库和持久聊天服务器镜像数据库处于关闭状态。
    
- Skype for business 服务器前端服务器已关闭。
    
该过程主要包含两个基本步骤：
  
- 恢复主持久聊天数据库（mgc）。
    
- 建立新的主数据库的镜像。
    
持久聊天合规性数据库（mgccomp）未进行故障转移。 此数据库的内容具有临时性并将在合规性适配器处理数据时被清除。 作为持久聊天管理员，您有责任正确地管理适配器输出以避免数据丢失。
  
对持久聊天服务器进行故障转移：
  
1. 从持久聊天服务器备份日志传送数据库中删除日志传送。
    
   - 使用 SQL Server Management Studio，连接到持久聊天服务器备份 mgc 数据库所在的数据库实例。
    
   - 打开主数据库的查询窗口。
    
   - 使用以下命令取消日志传送：
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. 从备份共享将任何未复制的备份文件复制到备份服务器的复制目标文件夹。
    
3. 按顺序将任何未应用的事务日志备份应用到辅助数据库。 有关详细信息，请参阅[操作方法：应用事务日志备份（transact-sql）](https://go.microsoft.com/fwlink/p/?linkid=247428)。
    
4. 使备份 mgc 数据库联机。使用在步骤 1b 中打开的查询窗口，执行下列操作：
    
   - 如果包含以下项，将断开与 mgc 数据库的所有连接：
    
   - **exec sp_who2**，用于识别与 mgc 数据库的连接。
    
   - **kill \<spid\> **以结束这些连接。
    
   - 使数据库联机：
    
   - **通过恢复还原数据库 mgc**。
    
5. 在 Skype for Business Server Management Shell 中，使用命令**集 CsPersistentChatState-Identity "service： atl-cs-001.litwareinc.com"-PoolState FailedOver**故障转移到 mgc 备份数据库。 确保用您的“持久聊天”池的完全限定的域名替换 atl-cs-001.litwareinc.com。
    
    mgc 备份数据库现在充当主数据库。
    
6. 在 Skype for Business Server Management Shell 中，使用**CsMirrorDatabase** cmdlet 为现在用作主数据库的备份数据库建立高可用性镜像。 使用备份数据库实例作为主数据库并使用备份镜像数据库实例作为镜像实例。 此镜像与最初在安装期间为主数据库配置的镜像不同。
    
7. 设置持久聊天服务器活动服务器。 在 Skype for Business Server Management Shell 中，使用**CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
    此时，从持久聊天服务器主数据库到持久聊天服务器备份数据库的故障转移已成功完成。
    
## <a name="fail-back-persistent-chat-server"></a>故障恢复持久聊天服务器

此过程概述了从持久聊天服务器故障中恢复所需的步骤，以及从主数据中心重新建立操作的步骤。
  
在持久聊天服务器出现故障期间，主数据中心将受到完全中断，并且主数据库和镜像数据库将变得不可用。 主数据中心将故障转移到备份服务器。
  
以下过程在备份主数据中心并重新生成服务器后还原正常操作。 该过程假设主数据中心已从整体中断恢复，并且已使用拓扑生成器重新生成并重新安装了 mgc 数据库和 mgccomp 数据库。
  
该过程还假定在故障转移期间未部署新镜像和备份服务器，并且唯一部署的服务器是故障转移持久聊天服务器中之前定义的备份服务器及其镜像服务器。
  
这些步骤旨在恢复配置在导致从主服务器故障转移到备份服务器的灾难发生之前的状态。
  
1. 通过使用 Skype for Business Server Management Shell 中的**CsPersistentChatActiveServer** cmdlet，从持久聊天服务器活动服务器列表中清除所有服务器。 这将阻止所有持久聊天服务器在故障回复期间连接到 mgc 数据库和 mgccomp 数据库。
    
    > [!IMPORTANT]
    > 辅助持久聊天服务器上的 SQL Server 代理应在特权帐户下运行。 尤其需要指出的是，该帐户必须具有以下权限： 
  
   - 对于放置备份的网络共享的读取权限。
    
   - 对于备份将复制到的特定本地目录的写入权限。
    
2. 在备份 mgc 数据库上禁用镜像：
    
   - 使用 SQL Server Management Studio 连接到 backup mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，然后单击“**镜像**”。
    
   - 单击“**取消镜像**”。
    
   - 单击“**确定**”。
    
   - 对 mgccomp 数据库执行相同步骤。
    
3. 备份 mgc 数据库，使其可以还原为新主数据库：
    
   - 使用 SQL Server Management Studio 连接到 backup mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，然后单击“**备份**”。随即将显示“**备份数据库**”对话框。
    
   - 在“**备份类型**”中，选择“**完全**”。
    
   - 对于“**备份组件**”，请单击“**数据库**”。
    
   - 接受“**名称**”中建议的默认备份集名称，或为备份集输入不同名称。
    
   -  * \<可选\> * 在 "**说明**" 中，输入备份集的描述。
    
   - 从目标列表中删除默认备份位置。
    
   - 使用您建立用于日志传送的共享位置的路径向列表中添加文件。主数据库和备份数据库均可使用此路径。
    
   - 单击“**确定**”关闭对话框并开始备份过程。
    
4. 使用上一步中创建的备份数据库还原主数据库。
    
   - 使用 SQL Server Management Studio 连接到主 mgc 实例。
    
   - 右键单击 mgc 数据库，指向“**任务**”，指向“**还原**”，然后单击“**数据库**”。随即会显示“**还原数据库**”对话框。
    
   - 选择“**自设备**”。
    
   - 单击浏览按钮，将打开“**指定备份**”对话框。在“**备份媒体**”中，选择“**文件**”。单击“**添加**”，选择您在步骤 3 中创建的备份文件，然后单击“**确定**”。
    
   - 在“**选择用于还原的备份集**”中，选择备份。
    
   - 在“**选择页**”窗格中单击“**选项**”。
    
   - 在“**还原选项**”中，选择“**覆盖现有数据库**”。
    
   - 在“**恢复状态**”中，选择“**使数据库处于可以使用的状态**”。
    
   - 单击“**确定**”开始还原过程。
    
5. 为主数据库配置 SQL Server 日志传送。 按照在[Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中的过程，为主 mgc 数据库建立日志传送。
    
6. 设置持久聊天服务器活动服务器。 在 Skype for Business Server Management Shell 中，使用**CsPersistentChatActiveServer** cmdlet 设置活动服务器的列表。
    
    > [!IMPORTANT]
    > 所有活动服务器必须都与新主数据库位于同一数据中心中，或位于与数据库之间存在低延迟/高带宽连接的数据中心中。 
  
若要将池还原到其正常状态，请运行以下 Windows PowerShell 命令：
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

有关详细信息，请参阅 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet 的帮助主题。
  

