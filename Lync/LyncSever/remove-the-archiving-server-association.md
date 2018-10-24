---
title: 删除存档服务器关联
TOCTitle: 删除存档服务器关联
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49888637
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除存档服务器关联

 

_**上一次修改主题：** 2012-10-04_

要删除 存档服务器，您需要更改或清除关联的 前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 上的依赖项。您可以编辑 前端池、 前端服务器、 Survivable Branch Appliance 和 Survivable Branch Server 的属性来删除依赖项。在 拓扑生成器中清除依赖项和删除服务器后，系统会通知您 拓扑生成器中关联的数据库存储对象也已删除。

## 删除存档服务器关联

1.  打开 Lync Server 2013 前端服务器，然后打开拓扑生成器。

2.  导航到 Lync Server 2010 节点。

3.  在拓扑生成器中，根据定义存档服务器的位置展开“Enterprise Edition 前端池”、“Standard Edition 前端服务器”或“分支站点”。

4.  如果已关联 Survivable Branch Server，则依次展开“分支站点”、分支站点名称，然后展开“Survivable Branch Appliance”。
    
    > [!NOTE]
    > 用户界面中的“Survivable Branch Appliance”适用于 Survivable Branch Server 和 Survivable Branch Appliance。


5.  右键单击与 存档服务器关联的池、服务器或设备，然后单击“编辑属性”。

6.  在“编辑属性”的“常规”下的“关联”下，清除“关联存档服务器”复选框，然后单击“确定”。

7.  对与要删除的 存档服务器关联的任何其他池、服务器或设备重复上一步。

8.  右键单击 存档服务器，然后单击“删除”。

9.  在“删除相关存储”上，单击“确定”。

10. 发布拓扑，检查复制状态，然后根据需要运行 Lync Server 部署向导。

