---
title: Lync Server 2013：将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑
TOCTitle: 将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49888627
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Server 2013 Survivable Branch Appliance 分支站点添加到您的拓扑

 

_**上一次修改主题：** 2012-10-07_

Microsoft Lync Server 2013Survivable Branch Appliance (SBA) 无法作为备份注册器与 Microsoft Lync Server 2010前端池关联。SBA 必须与 Microsoft Lync Server 2013前端池关联。以下步骤采用 Microsoft Lync Server 2013 SBA。请在中央站点执行此过程。

## 通过 Microsoft Lync Server 2013 SBA 将分支站点添加到拓扑中

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在控制台树中，展开中央站点，再展开“分支站点”，然后单击“新建分支站点”。

3.  在“定义新的分支站点”对话框中，单击“名称”，然后键入新分支站点的名称。

4.  （可选）单击“说明”，然后为分支站点键入有一定含义的说明。

5.  单击“下一步”。

6.  （可选）在下一个“定义新的分支站点”对话框中，执行以下任一操作：
    
      - 单击“市/县”，然后键入分支站点所在的市/县的名称。
    
      - 单击“国家/地区”，然后键入分支站点所在的国家或地区的名称。
    
      - 单击“国家/地区代码”，然后键入分支站点所在的国家/地区的两位数呼叫代码。

7.  单击“下一步”，然后执行以下操作之一：
    
      - 如果要在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请确保选中“此向导关闭时打开新建 Survivable 向导”复选框。
    
      - 如果不在该站点上使用 Survivable Branch Appliance 或 Survivable Branch Server，请清除“此向导关闭时打开新建 Survivable 向导”复选框。
    
      - 单击“完成”，然后按照打开的向导中的说明进行操作。有关向导项的信息，请参阅 [在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)。

8.  对要添加到拓扑的每个分支站点重复之前的步骤。

## 另请参阅

#### 任务

[在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[在 Lync Server 2013 中为分支站点定义 PSTN 网关](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[在 Lync Server 2013 中配置无媒体旁路功能的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)

