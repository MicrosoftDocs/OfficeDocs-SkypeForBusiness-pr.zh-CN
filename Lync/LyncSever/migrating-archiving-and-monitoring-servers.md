---
title: 迁移存档和监控服务器
TOCTitle: 迁移存档和监控服务器
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205015(v=OCS.15)
ms:contentKeyID: 49313303
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移存档和监控服务器

 

_**上一次修改主题：** 2012-10-02_

如果在 Lync Server 2010 环境中部署了存档服务器和监控服务器，则可在迁移前端池后在 Lync Server 2013 环境中部署这些服务器。不过，如果存档和监控功能对您的组织至关重要，则应在迁移之前在 Lync Server 2013 试点池中添加存档和监控功能，以便迁移过程中可使用这些功能。

如果迁移过程中需要存档和监控功能，应注意以下问题：

  - 存档数据和监控数据不会移至 Lync Server 2013 部署。在停用旧环境之前备份的数据将成为 Lync Server 2010 环境中的活动历史记录。

  - Lync Server 2010 版本的存档服务器和监控服务器只能与 Lync Server 2010 前端池相关联。在 Lync Server 2013 中，存档和监控不再是服务器角色，而是集成到 Lync Server 2013 前端池中的服务。

  - 在旧部署与 Lync Server 2013 部署共存的阶段， Lync Server 2010 版本的存档服务器和监控服务器收集驻留在 Lync Server 2010 池中的用户的数据。 Lync Server 2013 中的存档和监控收集驻留在 Lync Server 2013 池中的用户的数据。
    
    > [!NOTE]
    > 迁移阶段仍将旧边缘服务器与新 Lync Server 2013 试点池结合使用时， Lync Server 2010 版本的存档服务器继续收集驻留在 Lync Server 2010 池中的用户的数据， Lync Server 2013 中的存档收集驻留在 Lync Server 2013 池中的用户的数据。


  - 如果将第三方存档和监控解决方案与 Lync Server 2013 中的存档和监控结合使用，请咨询供应商，了解何时需要将第三方解决方案与 Lync Server 2013 集成以及如何集成。

