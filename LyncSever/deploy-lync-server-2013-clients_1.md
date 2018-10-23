---
title: 部署 Lync Server 2013 客户端
TOCTitle: 部署 Lync Server 2013 客户端
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204883(v=OCS.15)
ms:contentKeyID: 49312829
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 部署 Lync Server 2013 客户端

 

_**上一次修改主题：** 2012-10-19_

将用户迁移到 Lync Server 2013 后，执行以下操作：

1.  在新的 Lync Server 2013 服务器上使用客户端版本筛选器，以仅允许安装了最新更新的客户端登录。

2.  如果需要，请配置客户端引导所需的组策略设置。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)。仅当要更改现有客户端引导策略或者要设置新客户端引导策略时才需要配置这些设置。如果您不打算配置客户端引导策略，或者希望旧客户端引导策略继续生效，则无需执行任何操作。

3.  使用 Lync Server 2013 控制面板和/或 Lync Server 2013 命令行管理程序为特定用户或用户组配置其他用户和客户端策略。有关详细信息，请参阅规划文档中的 [Lync 2013 的新增和更改的设置](lync-server-2013-new-and-changed-settings-for-lync-2013.md)。

4.  部署 Lync Server 2013 客户端的最新版本和最新累积更新。有关详细信息，请参阅部署文档中的 [在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)。

5.  （可选）如果贵组织需要 Lync Server 2013 增强状态隐私模式，请在迁移完成后，定义客户端版本策略规则，以便阻止早期客户端版本登录。然后，启用增强状态隐私模式。
    
    > [!IMPORTANT]  
    > 在给定服务器池上的每个用户都安装了最新客户端版本之前，请不要启用 Lync 2013 增强状态隐私模式。

