---
title: Lync Server 2013：备份持久聊天数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f186552b9e0d5c78d0f40416cd92e41d5705e93a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>在 Lync Server 2013 中备份持久聊天数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-17_

持久聊天室内容存储在持久聊天数据库（Mgc）中。 这是应定期备份的业务关键型数据。 除了聊天室内容，持久聊天数据库还存储有关主体（如用户和用户组）的信息，以及他们拥有的用于聊天室和聊天室的角色和访问权限。

备份持久聊天数据有两种方法。

  - SQL Server 备份

  - 将`Export-CsPersistentChatData`永久聊天数据导出为文件的 cmdlet

通过使用 SQL Server 备份创建的数据需要更多的磁盘空间，这可能比创建的过程要多 20 `Export-CsPersistentChatData`倍，但 SQL Server 备份更可能是管理员熟悉的过程。

</div>

<span> </span>

</div>

</div>

</div>

