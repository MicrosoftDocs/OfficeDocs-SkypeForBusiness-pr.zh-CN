---
title: Lync Server 2013：将聊天室从一个类别移动到另一个类别
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40077d8092f8b0b78b6e9ce78cd16c6f1e0812f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

我们建议您在创建聊天室后，不要更改持久聊天室的类别。 但是，如果聊天室管理员在其他类别中具有 **Creator** 特权，则他/她可以将聊天室从一个类别移动到另一个类别。 将不会删除和重新创建该聊天室。 这是数据库中的关联的更改。

应该尽量不要更改聊天室类别。类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。例如，如果用户是聊天室的成员，且不再是新类别中的 **AllowedMember**，则系统会修改聊天室成员身份，并将用户从聊天室中删除。

有关使用 Windows PowerShell 命令行界面移动聊天室的详细信息，请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

有关配置聊天室的详细信息，请参阅部署文档中的在[Lync Server 2013 中配置会议室](lync-server-2013-configure-rooms.md)。

</div>

<span> </span>

</div>

</div>

</div>

