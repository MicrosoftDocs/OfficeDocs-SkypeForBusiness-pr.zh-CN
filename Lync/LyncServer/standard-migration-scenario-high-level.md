---
title: 标准迁移方案-高级别
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5b2dd76a071c01c74f3d42f9c1ffbfa76c4a924
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>标准迁移方案-高级别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

将 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天迁移到 Lync Server 2013、持久聊天服务器时，请使用以下项目作为起点。 标准 Lync Server 2013 迁移路径如下所示：

  - 您的组织之前已部署 Lync Server 2010、组聊天或 Office 通信服务器 2007 R2 组聊天，并且您希望部署 Lync Server 2013、持久聊天服务器。

  - 部署 Lync Server 2013，然后部署持久聊天服务器池。

  - 准备并规划持久聊天室的迁移，并确定适当的时间来关闭系统以进行迁移。

  - 运行用于迁移的 Windows PowerShell cmdlet （**export-cspersistentchatdata**和**Import-export-cspersistentchatdata**）以将内容移动到持久聊天服务器。

  - 验证该迁移是否成功。

  - 停用旧版部署。

  - 配置持久聊天服务器，以便旧版客户端可以连接到 Lync Server 2013、持久聊天服务器。 这是必需的，因为部署新的客户端需要一些时间，且您想使用旧版客户端支持现有用户来尽快取得对其聊天室的访问权限。

  - 部署新客户端，同时继续帮助确保具有旧式组聊天（客户端）的工作人员可以访问其聊天室。

</div>

<span> </span>

</div>

</div>

</div>

