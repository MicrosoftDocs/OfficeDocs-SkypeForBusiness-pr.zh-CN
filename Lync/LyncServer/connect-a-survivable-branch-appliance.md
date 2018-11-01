---
title: 连接 Survivable Branch Appliance
TOCTitle: 连接 Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49888699
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 连接 Survivable Branch Appliance

 

_**上一次修改主题：** 2012-10-19_

每个 Survivable Branch Appliance (SBA) 都与其充作 SBA 的备份注册器的前端池相关联。如果将前端池迁移到 Lync Server 2013 时，则升级该池时必须从 Lync Server 2010 前端池取消关联 SBA。将该池迁移到 Lync Server 2013 后，SBA 可与升级的前端池重新关联。这涉及从拓扑生成器中的旧 Lync Server 2010 拓扑删除 SBA，然后将 SBA 添加到 Lync Server 2013 拓扑。驻留在旧 Lync Server 2010 SBA 上的用户必须移动到另一前端池，然后才能从该拓扑删除 SBA。将 SBA 添加到 Lync Server 2013 拓扑后，这些用户可移回到 SBA。将这些步骤总结如下：

1.  将驻留在旧 SBA Lync Server 2010 上的分支用户移动到另一个前端池。

2.  从旧 Lync Server 2010 拓扑删除 SBA，作为备份注册器断开现有前端池的连接。

3.  将 SBA 添加到 Lync Server 2013 拓扑，并作为备份注册器配置此新前端池。

4.  将分支用户移动到新的 Lync Server 2013 SBA。

**将 Lync Server 2010 SBA 分支站点添加到您的拓扑**

1.  打开“拓扑生成器”。

2.  在左窗格中右键单击“分支站点”，然后单击“新建分支站点”。

3.  在“定义新的分支站点”对话框中，单击“名称”，然后键入分支站点的名称。

4.  （可选）单击“说明”，然后为分支站点键入有一定含义的说明。

5.  单击“下一步”。

6.  （可选）在下一个“定义新的分支站点”对话框中，执行以下任一操作：
    
    1.  单击“市/县”，然后键入分支站点所在的市/县的名称。
    
    2.  单击“国家/地区”，然后键入分支站点所在的国家或地区的名称。
    
    3.  单击“国家/地区代码”，然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击“下一步”，然后执行以下操作之一：
    
    1.  如果在此站点使用的是 Lync 2010 Survivable Branch Appliance 或 Lync 2010 Survivable Branch Server，确保取消选中“此向导关闭后将打开新建 Survivable 向导”选项。单击“完成”。

8.  要将旧 Lync Server 2010 SBA 关联到 Lync Server 2013 前端池，请执行以下操作：
    
    1.  展开已创建的分支站点。
    
    2.  右键单击“Lync Server 2010”，然后单击“新建”。
    
    3.  单击“Survivable Branch Appliance…”

9.  按照打开的向导中的说明执行操作。有关向导项的信息，请参阅 [在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。
    
    > [!NOTE]  
    > Lync Server 2010 Survivable Branch Appliance 仅可与 Lync Server 2010 监控存储相关联。
    


10. 如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭后将打开新建 Survivable 向导”复选框，然后单击“完成”。

11. 对要添加到拓扑的每个分支站点重复之前的步骤。

