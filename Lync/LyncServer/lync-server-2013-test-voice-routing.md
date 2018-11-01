---
title: Lync Server 2013：测试语音路由
TOCTitle: 测试语音路由
ms:assetid: d3aae909-fef6-440f-b144-0b62dc82bf5d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398915(v=OCS.15)
ms:contentKeyID: 49314356
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中测试语音路由

 

_**上一次修改主题：** 2013-02-24_

可以使用 Lync Server 控制面板“测试语音路由”选项卡配置测试用例方案。要定义测试用例，请指定拨号计划、语音策略、PSTN 用法和语音路由，据此测试指定的电话号码。

在实际部署语音路由配置前，建议针对不同的电话号码对其进行测试，以确保达到预期的结果。

> [!TIP]
> 可以使用“导出测试用例”和“导入测试用例”命令保存语音路由测试用例，并在其他计算机中导入这些用例供使用。


> [!CAUTION]
> 如果删除语音路由配置中的部分内容，如拨号计划、语音策略、语音路由或电话用法，应检查并更新语音路由测试用例。当配置更改导致测试用例无效时， Lync Server 控制面板不会就此通知您。


## 本部分内容

  - [在 Lync Server 2013 中创建语音路由测试用例](lync-server-2013-create-a-voice-routing-test-case.md)

  - [在 Lync Server 2013 中导出语音路由测试用例](lync-server-2013-export-voice-routing-test-cases.md)

  - [在 Lync Server 2013 中导入语音路由测试用例](lync-server-2013-import-voice-routing-test-cases.md)

  - [在 Lync Server 2013 中运行语音路由测试](lync-server-2013-running-voice-routing-tests.md)

