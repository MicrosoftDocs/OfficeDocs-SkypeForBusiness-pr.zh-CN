---
title: 删除监视服务器关联
TOCTitle: 删除监视服务器关联
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49888600
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除监视服务器关联

 

_**上一次修改主题：** 2012-10-04_

要删除 监控服务器，您需要更改或清除对相关联的 前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 的依赖关系。可以编辑 前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 的属性，以删除依赖关系。在 拓扑生成器中清除依赖关系并删除服务器之后，系统会通知您也将删除 拓扑生成器中相关联的数据库存储对象。

## 删除监控服务器关联

1.  打开 Lync Server 2013 前端服务器，然后打开拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  在拓扑生成器中，根据定义监控服务器的位置展开“Enterprise Edition 前端池”、“Standard Edition 前端服务器”或“分支站点”。

4.  如果已关联 Survivable Branch Server，则依次展开“分支站点”、分支站点名称，然后展开“Survivable Branch Appliance”。
    
    > [!NOTE]
    > 用户界面中的“Survivable Branch Appliance”适用于 Survivable Branch Server 和 Survivable Branch Appliance。


5.  右键单击与 监控服务器关联的池、服务器或设备，然后单击“编辑属性”。

6.  在“编辑属性”中，在“常规”的“关联”下，清除“关联监控服务器”复选框，然后单击“确定”。

7.  针对与 监控服务器关联的任何其他池、服务器或设备重复先前的步骤。

8.  右键单击 监控服务器，然后单击“删除”。

9.  在“删除相关存储”上，单击“确定”。

10. 发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

