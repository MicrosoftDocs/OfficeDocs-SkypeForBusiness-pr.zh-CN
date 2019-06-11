---
title: 标准迁移方案 - 高级别
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>标准迁移方案 - 高级别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-01-30_

将 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器时, 请使用以下项目作为起点。 标准 Lync Server 2013 迁移路径如下所示:

  - 您的组织以前部署了 Lync Server 2010、群组聊天或 Office 通信服务器 2007 R2 群组聊天, 并且您希望部署 Lync Server 2013 和持久聊天服务器。

  - 部署 Lync Server 2013, 然后部署持久聊天服务器池。

  - 准备和规划持久聊天室的迁移, 并确定适当的时间来关闭系统进行迁移。

  - 运行用于迁移的 Windows PowerShell cmdlet (**Export-CsPersistentChatData**和**Import-CsPersistentChatData**) 以将内容移动到持久聊天服务器。

  - 验证迁移是否已成功。

  - 停止旧版部署。

  - 配置持久聊天服务器, 以便旧式客户端可以连接到 Lync Server 2013、持久聊天服务器。 这是必需的, 因为部署新客户需要花费时间, 并且您希望为具有旧客户的现有用户尽快访问其聊天室。

  - 部署新客户端, 同时继续帮助确保具有旧式群组聊天 (客户) 的工作人员可以访问其聊天室。

</div>

<span> </span>

</div>

</div>

</div>

