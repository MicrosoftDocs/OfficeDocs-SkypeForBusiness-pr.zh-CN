---
title: Lync Server 2013：附录 B：管理 Survivable Branch Appliance
TOCTitle: 附录 B：管理 Survivable Branch Appliance
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425797(v=OCS.15)
ms:contentKeyID: 49312378
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 附录 B：在 Lync Server 2013 中管理 Survivable Branch Appliance

 

_**上一次修改主题：** 2012-10-18_

本主题介绍管理 Survivable Branch Appliance 的过程。具体来说就是如何替换和重命名 Survivable Branch Appliance 以及如何更改与 Survivable Branch Appliance 关联的 Lync Server 2013 前端池。

## 替换 Survivable Branch Appliance

1.  停止 Survivable Branch Appliance 上的所有 Lync Server 2013 服务。（请参阅 Survivable Branch Appliance 供应商文档。）

2.  （推荐）从域中删除 Survivable Branch Appliance。

3.  要删除 Active Directory 域服务 中的 Survivable Branch Appliance 计算机对象，请执行以下步骤：
    
      - 以 Enterprise Admins 组成员的身份登录到成员服务器。
    
      - 依次单击“开始”、“管理工具”、“Active Directory 用户和计算机”。
    
      - 右键单击 Survivable Branch Appliance 对象，并单击“删除”。

4.  重新添加 Survivable Branch Appliance 计算机对象。（请参阅[在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)。）

5.  等待进行 Active Directory 复制。

6.  打开 Lync Server 命令行管理程序，键入“Enable-CSTopology”。

7.  将新的 Survivable Branch Appliance 连接到网络，并执行[使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)和[使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)中的步骤。

## 重命名 Survivable Branch Appliance

1.  将用户移至中央站点。有关详细信息，请参阅 [在 Lync Server 2013 中将用户移至另一个池](lync-server-2013-move-users-to-another-pool.md)。

2.  停止 Survivable Branch Appliance 上的所有 Lync Server 2013 服务。（请参阅 Survivable Branch Appliance 供应商文档。）

3.  要从拓扑中删除 Survivable Branch Appliance，请执行以下步骤：
    
      - 依次单击“开始”、“所有程序”、“Microsoft Lync Server”，然后单击“Lync Server 拓扑生成器”。
    
      - 在控制台树中，展开“分支站点”，单击“Survivable Branch Appliance”，然后单击操作窗格上的“删除”。

4.  从域中删除 Survivable Branch Appliance。

5.  要删除 Active Directory 中的 Survivable Branch Appliance 计算机对象，请执行以下步骤：
    
      - 以 Enterprise Admins 组成员的身份登录到域控制器。
    
      - 依次单击“开始”、“管理工具”、“Active Directory 用户和计算机”。
    
      - 右键单击 Survivable Branch Appliance 对象，并单击“删除”。

6.  将 Survivable Branch Appliance 还原到出厂默认设置。（请参阅 Survivable Branch Appliance 供应商文档。）

7.  按照 [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 中央站点任务](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)和 [使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)中的步骤执行操作。

8.  将用户移至重命名的 Survivable Branch Appliance。有关详细信息，请参阅 [在 Lync Server 2013 中将用户移至另一个池](lync-server-2013-move-users-to-another-pool.md)。

## 更改与 Survivable Branch Appliance 关联的 Lync Server 前端池

1.  将用户从 Survivable Branch Appliance 移至中央站点的 Lync Server 前端池。有关详细信息，请参阅 [在 Lync Server 2013 中将用户移至另一个池](lync-server-2013-move-users-to-another-pool.md)。

2.  停止 Survivable Branch Appliance 上的所有 Lync Server 服务。（请参阅 Survivable Branch Appliance 供应商文档）。

3.  按照以下步骤更新与 Survivable Branch Appliance 关联的 Lync Server 前端池：
    
      - 依次单击“开始”、“所有程序”、“Microsoft Lync Server”，然后单击“Lync Server 拓扑生成器”。
    
      - 展开“分支站点”。
    
      - 右键单击要修改的 Survivable Branch Appliance 对象，然后单击“编辑属性”
    
      - 在“复原”下，选择要与 Survivable Branch Appliance 关联的新 前端池，然后单击“下一步”。
    
      - 在控制台树中，右键单击新的 Survivable Branch Appliance，单击“拓扑”，然后单击“发布”。

4.  重新启动 Survivable Branch Appliance 上的所有 Lync Server 服务。

5.  测试 Survivable Branch Appliance。有关详细信息，请参阅 [在 Lync Server 2013 中在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

6.  将用户从中央站点的 Lync Server 前端池移至 Survivable Branch Appliance。

