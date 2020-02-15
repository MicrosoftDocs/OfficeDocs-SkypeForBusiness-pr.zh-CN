---
title: Lync Server 2013：还原持久聊天数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78d43cedaec50adac895b143a3643a6a1a1a8a48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>在 Lync Server 2013 中还原持久聊天数据

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-18_

持久聊天聊天室内容存储在持久聊天数据库（mgc）中。 这是应定期备份的关键业务数据。 除了聊天室内容之外，主体（如用户和组）以及必须与聊天室和聊天室内容聊天的角色和访问也存储在持久聊天数据库中。

还原持久聊天数据的方式取决于您用于备份持久聊天数据的方法。

  - 如果您使用的是 SQL Server 备份过程，则必须使用 SQL Server 还原过程。

  - 如果您使用**export-cspersistentchatdata** cmdlet 来备份持久聊天数据，则必须使用**export-cspersistentchatdata** cmdlet 来还原数据。

</div>

<span> </span>

</div>

</div>

</div>

