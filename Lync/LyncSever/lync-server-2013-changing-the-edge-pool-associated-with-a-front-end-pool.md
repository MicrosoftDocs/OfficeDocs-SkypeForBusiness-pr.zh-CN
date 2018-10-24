---
title: Lync Server 2013：更改与前端池关联的边缘池
TOCTitle: 更改与前端池关联的边缘池
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49888377
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中更改与前端池关联的边缘池

 

_**上一次修改主题：** 2012-09-21_

如果边缘池出现故障，但同一站点中的前端池仍在运行，您将需要将前端池设置为使用其他站点中的边缘池，直到故障池恢复。

## 更改与前端池关联的边缘池

1.  在拓扑生成器中，导航到需要更改的前端池的名称。

2.  右键单击该池，然后单击“编辑属性”。

3.  在“关联”部分的“关联边缘池（用于媒体组件）”下，使用下拉框选择要与此前端池关联的边缘池。

4.  单击“确定”。

## 另请参阅

#### 概念

[Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)

