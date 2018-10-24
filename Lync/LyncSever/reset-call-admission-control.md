---
title: 重置呼叫允许控制
TOCTitle: 重置呼叫允许控制
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49888429
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 重置呼叫允许控制

 

_**上一次修改主题：** 2012-10-11_

如果 Lync Server 2010前端池正在承载呼叫允许控制 (CAC)，您必须将 CAC 承载迁移到 Lync Server 2013 池，然后才能删除 Lync Server 2010前端池。

## 重置 CAC

1.  打开 拓扑生成器。

2.  右键单击站点节点，然后单击“编辑属性”。

3.  在“呼叫允许控制设置”下，确保选择“启用呼叫允许控制”。

4.  在“要运行呼叫允许控制的前端池 (CAC)”下，选择用于承载 CAC 的 Lync Server 2013 池，然后单击“确定”。

5.  发布拓扑。

