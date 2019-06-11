---
title: 'Lync Server 2013: 环境测试的问题'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ed158c598b9dc5596df23cb845f0adac4c6fed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Lync Server 2013 中的环境测试问题

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-21_

最佳做法分析器为你提供一种验证 Lync Server 2013 环境是否支持配置的方法。 作为 Active Directory 域服务检查的一部分, 最佳做法分析器将执行以下操作:

  - 验证 Active Directory 域服务林和架构准备。

  - 标识部署中的 Active Directory 域服务站点和域的数量。

  - 检查林和域级别。

  - 检查域控制器版本。

  - 标识域、配置和架构命名上下文。

  - 标识已启用的用户数。

  - 检查全局 Active Directory 域服务设置的存储位置。

  - 检查 Lync Server 的服务连接点 (SCPs)。

  - 标识数据库版本。

<div>

## <a name="resolving-issues-with-the-environment"></a>解决环境中的问题

如果环境测试发现你的环境存在问题, 这些问题可能是由于你的 Active Directory 配置或特定服务器上运行的软件级别的问题导致的。 例如, 如果最佳做法分析器识别你的环境中运行 Windows Server 2000 的任何域控制器, 它将发出警告, 并且你需要将这些域控制器升级到受支持的 Windows Server 版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

