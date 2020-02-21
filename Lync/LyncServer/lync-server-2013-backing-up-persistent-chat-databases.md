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
ms.openlocfilehash: 218c011d2acc970028bfd0be529d89542d684758
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>在 Lync Server 2013 中备份持久聊天数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-17_

持久聊天聊天室内容存储在持久聊天数据库（Mgc）中。 这是应定期备份的关键业务数据。 除了聊天室内容之外，持久聊天数据库还存储有关主体（如用户和用户组）的信息，以及他们必须与聊天室和聊天室聊天的角色和访问权限。

有两种备份持久聊天数据的方法。

  - SQL Server 备份

  - 将`Export-CsPersistentChatData`持久聊天数据导出为文件的 cmdlet

使用 SQL Server 备份创建的数据需要显著更多的磁盘空间-可能比创建的数据更多20倍`Export-CsPersistentChatData`，但 SQL Server 备份更可能是管理员熟悉的过程。

</div>

<span> </span>

</div>

</div>

</div>

