---
title: Lync Server 2013：将聊天室从一个类别移动到另一个类别
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

我们建议您不要在创建聊天室后更改持久聊天室的类别。 但是, 如果聊天室管理器具有其他类别的**创建者**权限, 则可以将该会议室从一个类别移动到另一个类别。 将不会删除和重新创建该聊天室。 这是数据库中的关联的更改。

更改聊天室类别的操作很少。 类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。 例如, 如果用户是聊天室的成员, 并且不再是新类别中的**AllowedMember** , 则会修改聊天室成员身份, 并将用户从聊天室中删除。

有关使用 Windows PowerShell 命令行界面移动聊天室的详细信息, 请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

有关配置聊天室的详细信息, 请参阅部署文档中[Lync Server 2013](lync-server-2013-configure-rooms.md)中的 "配置聊天室"。

</div>

<span> </span>

</div>

</div>

</div>

