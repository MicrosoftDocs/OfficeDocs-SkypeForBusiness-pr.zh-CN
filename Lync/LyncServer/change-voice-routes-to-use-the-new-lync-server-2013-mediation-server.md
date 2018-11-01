---
title: 更改语音路由以使用新的 Lync Server 2013 中介服务器
TOCTitle: 更改语音路由以使用新的 Lync Server 2013 中介服务器
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205162(v=OCS.15)
ms:contentKeyID: 49313934
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 更改语音路由以使用新的 Lync Server 2013 中介服务器

 

_**上一次修改主题：** 2012-09-28_

此过程将语音路由更改为使用 Lync Server 2013 中介服务器，而不是旧的 Office Communications Server 2007 R2 中介服务器。

## 将语音路由更改为使用新中介服务器

1.  Lync Server 2013 控制面板

2.  在左窗格中，选择“语音路由”，然后选择“路由”。

3.  单击“新建”以创建新语音路由。

4.  填写以下字段：
    
      - **名称** ：键入语音路由的描述性名称。在本文档中，我们使用 **W15PSTNRoute** 。
    
      - **说明** ：键入语音路由的简要说明。

5.  跳过所有其余部分，直到到达“关联网关”。单击“添加”。选择新默认网关，然后单击“确定”。

6.  在“关联的 PSTN 用法”下，单击“选择”。

7.  从“选择 PSTN 用法记录”页中，选择一个记录名称，然后单击“确定”。

8.  从“新建语音路由”页中，单击“确定”以创建“语音路由”。

9.  从“语音路由”页中，选择“路由”。

10. 将新创建的路由移至列表的顶部，然后选择“提交”。

