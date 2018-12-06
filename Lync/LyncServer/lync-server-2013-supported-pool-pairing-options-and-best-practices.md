---
title: Lync Server 2013 支持的池配对选项和最佳做法
TOCTitle: 支持的池配对选项和最佳做法
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204697(v=OCS.15)
ms:contentKeyID: 49312079
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 支持的池配对选项和最佳做法

 

_**上一次修改主题：** 2017-03-09_

要包括互相配对的前端池的两个数据中心之间没有距离限制。建议使用位于相同世界区域的两个数据中心，因为它们之间存在高速链接。最好两个数据中心之间拥有足够距离，以避免一个灾难同时袭击两个数据中心。

跨世界区域分布两个数据中心也是可行的，但可能会因为数据复制延迟而导致丢失较多数据。

当您计划对池进行配对时，必须谨记仅支持以下配对法：

  - Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。

  - 物理池仅能与其他物理池配对。同样，虚拟池仅能与其他虚拟池配对。

拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。但是，不支持进行这些类型的配对。

配对中的每个池应能够在发生灾难时为两个池中的所有用户提供服务。

如果对 Enterprise Edition 进行配对，还可以在后端服务器上实现高可用性，但是对于 Standard Edition 池的配对，仅能采用灾难恢复措施。

