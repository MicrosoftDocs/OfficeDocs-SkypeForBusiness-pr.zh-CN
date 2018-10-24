---
title: 共存注意事项
TOCTitle: 共存注意事项
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205131(v=OCS.15)
ms:contentKeyID: 49313746
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共存注意事项

 

_**上一次修改主题：** 2012-10-06_

迁移之后，仅 Lync Server 2013持久聊天服务器池将存在，您可停用旧部署。

迁移完成前以及完全停用当前 群聊服务器部署前，您可能具有下列任何部署：

  - Lync Server 2013持久聊天服务器池，其必须驻留在 Lync Server 2013 池中。

  - Lync Server 2010 群聊池，其必须驻留在 Lync Server 2010 池中。

  - Office Communications Server 2007 R2群聊池，其必须驻留在 Office Communications Server 2007 R2 池中。

这些部署可并行存在。但是一个部署中的类别、聊天室和外接程序不会与伴随部署中的交互。

通过使用手动配置，旧客户端（ 群聊客户端）一次可连接到一个 Office Communications Server 2007 R2、 Lync Server 2010 群聊或 Lync Server 2013 的池。

Lync 2013（客户端）只能与 Lync Server 2013持久聊天服务器池交互，不能与旧 群聊服务器池交互。若要在 Lync 2013 客户端中使用 持久聊天，用户必须驻留在 Lync 2013 上，并且必须按策略启用。

