---
title: 共存注意事项
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7052042afbc3927e1047a9c2fbb30a71168f317
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>共存注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

迁移后，只有 Lync Server 2013、持久聊天服务器池存在，并且您可以停止使用旧版部署。

在迁移完成之前和完全取消当前组聊天服务器部署之前，可能会有以下任一部署：

  - Lync Server 2013、持久聊天服务器池（必须驻留在 Lync Server 2013 池上）。

  - Lync Server 2010，组聊天池，它必须驻留在 Lync Server 2010 池上。

  - Office 通信服务器 2007 R2 组聊天池，它必须驻留在 Office 通信服务器 2007 R2 池上。

These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.

使用手动配置，旧版客户端（组聊天客户端）可以一次连接到一个池，以获取 Office 通信服务器 2007 R2、Lync Server 2010、组聊天或 Lync Server 2013。

Lync 2013 （客户端）只能与 Lync Server 2013、持久聊天服务器池进行交互，而不能与旧版组聊天服务器池交互。 若要在 Lync 2013 （客户端）中使用持久聊天，用户必须驻留在 Lync 2013 上并由策略启用。

</div>

<span> </span>

</div>

</div>

</div>

