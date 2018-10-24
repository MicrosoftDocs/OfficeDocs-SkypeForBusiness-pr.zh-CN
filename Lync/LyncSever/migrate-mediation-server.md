---
title: 迁移中介服务器
TOCTitle: 迁移中介服务器
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205173(v=OCS.15)
ms:contentKeyID: 49313972
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移中介服务器

 

_**上一次修改主题：** 2012-09-28_

运行合并向导时，您的中介服务器会合并到 Lync Server 2013 试点拓扑中。然而，迁移所有用户后，需要配置 Lync Server 2013 中介服务器，因为 Office Communications Server 2007 R2 池无法与 Lync Server 2013 中介服务器通信。在并行迁移期间， Lync Server 2013 池会与 Office Communications Server 2007 R2 中介服务器进行通信。

配置 Lync Server 2013 中介服务器时，还必须升级或替换 Office Communications Server 2007 R2 网关。 Office Communications Server 2007 R2 网关不支持 Lync Server 2013 中介服务器。您需要部署已通过 Lync Server 2013 认证的网关并将它们与 Lync Server 2013 中介服务器相关联。需要首先完成此步骤，然后才能完全停用 Office Communications Server 2007 R2 部署。

本节中的主题介绍完成 Lync Server 2013 中介服务器的迁移后需要执行的配置任务。将并置的中介服务器转换为独立中介服务器是可选任务。

  - [配置中介服务器](configure-mediation-server.md)

  - [更改语音路由以使用新的 Lync Server 2013 中介服务器](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [将并置中介服务器转换为独立中介服务器（可选）](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

