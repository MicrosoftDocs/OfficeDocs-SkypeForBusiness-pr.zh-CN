---
title: Lync Server 2013：减少未经请求的 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>为 Lync Server 2013 减少未经请求的 IM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-12-05_

智能 IM 筛选器应用程序可帮助保护 Microsoft Lync Server 2013 部署不受最常见病毒的攻击，最大程度地降低用户体验。 智能 IM 筛选器提供下列功能：

  - 增强的 URL 筛选功能

  - 增强的文件传输筛选功能

使用智能 IM 筛选器可以对筛选器进行配置，以阻止来自企业防火墙外部的未知终结点的未经请求或可能有害的即时消息。可通过指定用于确定应阻止的内容（例如，包含超链接的即时消息和具有特定扩展名的文件）的条件来配置筛选器。

在部署智能 IM 邮件筛选器应用程序之前，应了解在将邮件从一台 Lync Server 2013 服务器路由到另一台时如何应用筛选选项。 应用这些筛选选项的方式是一致的，无论服务器是位于单个组织中还是跨越多个组织。 在消息中插入自定义通知和警告文本以及在服务器之间发送这些消息的方式也是一致的。

建议的筛选选项是允许带有超链接的即时消息，但要求智能 IM 筛选器在链接前插入下划线字符来禁用链接。如果选择此选项，则还可以选择撰写一则用户通知，显示在包含超链接的每条即时消息的开头。

第二个筛选选项是允许带有未经修改的超链接的即时消息。如果选择此选项，则还可以选择撰写将插入到每条消息中的用户警告（推荐）。

第三个选项是阻止包含超链接的所有即时消息。如果选择此选项，则服务器将向用户发送警告。您必须编写此警告。

</div>

<span> </span>

</div>

</div>

</div>

