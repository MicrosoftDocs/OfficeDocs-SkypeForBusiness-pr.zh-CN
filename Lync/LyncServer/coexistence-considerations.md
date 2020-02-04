---
title: 共存注意事项
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>共存注意事项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

迁移后，仅存在 Lync Server 2013、持久聊天服务器池，并且您可以停止使用旧部署。

在迁移完成之前以及完全取消当前组聊天服务器部署的配置之前，你可能会遇到以下任何部署：

  - Lync Server 2013 持久聊天服务器池，它必须托管在 Lync Server 2013 池。

  - Lync Server 2010、群组聊天池，它必须驻留在 Lync Server 2010 池中。

  - Office 通信服务器 2007 R2 群组聊天池，它必须驻留在 Office 通信服务器 2007 R2 池中。

这些部署可以并排存在。 但是，一个部署中的类别、会议室和外接程序不与附带的部署中的相同。

使用手动配置时，旧客户端（组聊天客户端）可以一次连接到 Office 通信服务器 2007 R2、Lync Server 2010、群组聊天或 Lync Server 2013 的一个池。

Lync 2013 （客户端）只能与 Lync Server 2013、持久聊天服务器池（而不是旧版组聊天服务器池）交互。 若要在 Lync 2013 （客户端）中使用持久聊天，用户必须托管在 Lync 2013 并由策略启用。

</div>

<span> </span>

</div>

</div>

</div>

