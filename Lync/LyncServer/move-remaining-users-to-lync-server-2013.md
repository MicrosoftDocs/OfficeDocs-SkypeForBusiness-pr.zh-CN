---
title: 将其余用户移动到 Lync Server 2013
TOCTitle: 将其余用户移动到 Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49888459
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将其余用户移动到 Lync Server 2013

 

_**上一次修改主题：** 2012-09-29_

可使用 Lync Server 控制面板或 Lync Server 命令行管理程序将用户移至新的 Lync Server 2013 部署。您必须满足一些要求，才能确保顺利迁移到 Lync Server 2013。有关完成本主题中的过程要满足的先决条件的详细信息，请参阅 [为客户端配置迁移](configure-clients-for-migration.md)。有关移动用户的详细步骤，请参阅 [第 4 阶段：将测试用户移至试点池中](phase-4-move-test-users-to-the-pilot-pool.md)。

> [!IMPORTANT]
> 不能使用“Active Directory 用户和计算机”管理单元或 Lync Server 2010 管理工具将用户从旧环境移至 Lync Server 2013。


将用户移至 Lync Server 2013 池时，用户的数据会移至与新池关联的后端数据库。

> [!IMPORTANT]
> 这包括由旧用户创建的活动会议。例如，如果旧用户在“我的会议”中配置了一个会议，那么移动用户后，该会议在新 Lync Server 2013 池中仍然有效。访问该会议时仍要使用相同的会议 URL 和会议 ID 。唯一的区别是会议现在托管在 Lync Server 2013 池中，而不是 Lync Server 2010 池中。


> [!NOTE]  
> 在 Lync Server 2013 上驻留用户不需要同时部署升级的客户端。仅在升级到新客户端软件后，用户才能使用新功能。


## 迁移后任务

1.  移动用户后，确保向他们分配会议策略。

2.  要确保驻留在 Lync Server 2013 上的联盟用户可顺利加入由驻留在 Lync Server 2010 上的用户组织的会议，分配给迁移用户的会议策略应允许匿名参与者。

3.  允许匿名参与者的会议策略会在 Lync Server 2013 控制面板中选中“允许参与者邀请匿名用户”，并且在 Lync Server 命令行管理程序的 **Get-CsConferencingPolicy** cmdlet 输出中将 **AllowAnonymousParticipantsInMeetings** 设置为 **True**。

4.  有关使用 Lync Server 命令行管理程序配置会议策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy)。

