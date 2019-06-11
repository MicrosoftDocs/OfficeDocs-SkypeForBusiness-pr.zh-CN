---
title: Lync Server 2013：减少垃圾 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>减少 Lync Server 2013 的垃圾 IM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-12-05_

智能 IM 筛选器应用程序可帮助保护 Microsoft Lync Server 2013 部署, 使其不会受到最常见病毒的攻击, 最大程度地降低用户体验。 智能 IM 筛选器提供以下内容:

  - 增强的 URL 筛选

  - 增强的文件传输筛选

使用智能 IM 筛选器配置筛选器, 阻止来自公司防火墙外的未知终结点的未经请求或可能有害的即时消息。 通过指定用于确定应阻止的条件的条件 (如包含超链接的即时消息和具有特定扩展名的文件) 来配置筛选器。

在部署智能 IM 消息筛选器应用程序之前, 应了解当邮件从一个 Lync Server 2013 服务器路由到另一个时如何应用筛选选项。 应用这些筛选选项的方式是一致的, 无论服务器位于单个组织还是跨组织边界。 此一致性适用于将自定义通知和警告文本插入到邮件中并在服务器上发送的方式。

建议的筛选选项是允许带有超链接的即时消息, 但需要智能 IM 筛选器通过在其前面插入下划线来禁用链接。 如果选择此选项, 则可以选择向用户提供通知, 该选项显示在包含超链接的每个即时消息的开头。

第二个筛选选项允许带有未修改的超链接的即时消息。 如果选择此选项, 则会有附加选项 (推荐), 对插入到每封邮件中的用户撰写警告。

第三个选项是阻止所有包含超链接的即时消息。 如果选择此选项, 服务器会向用户发送警告。 必须编写此警告。

</div>

<span> </span>

</div>

</div>

</div>

