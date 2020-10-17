---
title: Lync Server 2013：部署统一联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94d19026d2df00caf8079914d8b93bd70a87f6d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522849"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中部署统一联系人存储

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-06-06_

在 Lync Server 2013 中启用统一的联系人存储不需要任何拓扑设置。 为用户启用统一的联系人存储库需要满足以下条件：

  - 启用统一的联系人存储库策略（将启用默认值）。

  - 用户至少使用 Lync 2013 登录一次。

迁移用户的联系人后，当用户使用 Lync 2013 登录时，用户可以在 lync 2013、Outlook 2013 或 Outlook Web Access 中访问和管理其 Lync 联系人。 用户不必登录到 Lync 即可从 Outlook 或 Outlook Web Access 管理其联系人。

<div>


> [!IMPORTANT]  
> 如果用户在迁移后从 Lync 2010 登录，则 "联系人" 和 "组" 可用且处于最新状态，但用户无法管理 (，即添加、删除、移动、标记、untag 或修改) 这些联系人。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中为用户启用统一联系人存储](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [在 Lync Server 2013 中将用户迁移到统一联系人存储](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [在 Lync Server 2013 中回滚已迁移的用户](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

