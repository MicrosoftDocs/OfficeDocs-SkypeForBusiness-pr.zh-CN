---
title: Lync Server 2013：定义规范化规则
TOCTitle: 定义规范化规则
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399071(v=OCS.15)
ms:contentKeyID: 49314653
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义规范化规则

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 规范化规则使用 .NET Framework 正则表达式将拨打的电话号码转换为 E.164 格式；换句话说，规范化规则获取用户拨打的电话号码并将该号码转换为 Lync Server 在内部使用的格式。 必须将每个拨号计划分配给一个或多个规范化规则。

有关规范化规则的详细信息，请参阅规划文档中的 [Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。

有关如何编写正则表达式的详细信息，请参阅“.NET Framework 正则表达式”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)。

可以使用以下任一方法定义或编辑规范化规则：

  - 使用“建立规范化规则”工具指定起始数字、长度、要删除的数字和添加的数字的值，然后使 Lync Server 控制面板生成对应的匹配模式和转换规则。

  - 手动编写正则表达式以定义匹配模式和转换规则。

## 本部分内容

  - [在 Lync Server 2013 中使用“构建规范化规则”创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [在 Lync Server 2013 中手动创建或修改规范化规则](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

## 另请参阅

#### 任务

[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)

