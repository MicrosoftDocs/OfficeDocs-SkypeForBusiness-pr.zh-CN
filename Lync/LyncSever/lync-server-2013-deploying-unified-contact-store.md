---
title: Lync Server 2013：部署统一联系人存储
TOCTitle: 部署统一联系人存储
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204963(v=OCS.15)
ms:contentKeyID: 49313134
ms.date: 06/07/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署统一联系人存储

 

_**上一次修改主题：** 2016-06-06_

在 Lync Server 2013 中启用统一的联系人存储库不要求进行任何拓扑设置。为用户启用统一的联系人存储库需要满足以下条件：

  - 启用统一的联系人存储库策略（将启用默认值）。

  - 用户至少使用 Lync 2013 登录一次。

在迁移用户的联系人之后（当用户用 Lync 2013 登录时，会自动执行此操作），用户可从 Lync 2013、 Outlook 2013 或 Outlook Web Access 中访问和管理其 Lync 联系人。用户不必登录 Lync 即可从 Outlook 或 Outlook Web Access 中管理其联系人。

> [!IMPORTANT]
> 如果用户在迁移后从 Lync 2010 中登录，则联系人和组可用并且保持最新，但用户无法管理（即添加、删除、移动、标记、取消标记或修改）这些联系人。


## 本部分内容

  - [在 Lync Server 2013 中为用户启用统一联系人存储](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [在 Lync Server 2013 中将用户迁移到统一联系人存储](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [在 Lync Server 2013 中回滚已迁移用户](lync-server-2013-roll-back-migrated-users.md)

