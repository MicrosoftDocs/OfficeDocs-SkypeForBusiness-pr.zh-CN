---
title: Lync Server 2013：环境测试的问题
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7d077b22c147dd677a5db68636b2c68bfafcf23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013 中的环境测试问题

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

最佳实践分析工具提供了一种方法，用于验证 Lync Server 2013 环境是否受支持的配置。 作为 Active Directory 域服务检查的一部分，最佳做法分析器可执行以下操作：

  - 验证 Active Directory 域服务林和架构准备。

  - 标识部署中 Active Directory 域服务站点和域的数量。

  - 检查林和域级别。

  - 检查域控制器版本。

  - 标识域、配置和架构命名上下文。

  - 标识启用的用户的数量。

  - 检查全局 Active Directory 域服务设置存储的位置。

  - 检查 Lync Server 的服务连接点（SCPs）。

  - 标识数据库版本。

<div>

## <a name="resolving-issues-with-the-environment"></a>解决环境问题

如果环境测试发现您的环境存在问题，则这些问题可能是 Active Directory 配置或特定服务器上运行的软件级别问题造成的。例如，如果最佳做法分析器标识运行 Windows Server 2000 的环境中的任何域控制器，则系统将发出一个警告，且您将需要将这些域控制器升级到受支持的 Windows Server 版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

