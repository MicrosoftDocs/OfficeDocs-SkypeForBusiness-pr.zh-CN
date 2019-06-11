---
title: Lync Server 2013：验证外部用户连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>在 Lync Server 2013 中验证外部用户连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

验证外部用户的连接需要确保将用户与服务器和端口连接到访问边缘服务。

一个有价值的资源, 可用于确认您的配置, 以及连接、发送和接收外部用户访问所需方案的正确消息的功能是远程连接分析器<http://www.testocsconnectivity.com>网站 ()。 网站由 Microsoft 支持人员管理和维护。 若要访问远程连接分析器, 请在浏览器中打开网站, 然后按照说明选择方案。

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>测试外部用户和外部访问的连接性

外部用户访问的测试应包括你的组织支持的每种类型的外部用户, 包括以下任何或所有类型:

  - 至少一个联盟域中的用户, 并测试即时消息、状态、A/V 和桌面共享。

  - 您的组织支持的每个公共 IM 服务提供商的用户 (以及已完成的预配)。

  - 匿名用户。

  - 组织内远程登录 Lync 但不使用 VPN 的用户。

这些测试确定你的边缘服务器是否:

  - 使用 Telnet 客户端从网络外侦听所需端口。
    
      - 示例: telnet sip.contoso.com 443
    
      - 根据你的部署, 对你在 Edge 服务器或 Edge 服务器池中使用的端口执行上述测试。

  - 执行准确的外部 DNS 解析。
    
      - 从你的网络外部 ping 你的边缘或边缘池的每个外部 FQDN。 即使 ping 失败, 您也可以看到 IP 地址, 您可以将其与您分配的 IP 地址进行比较。

</div>

</div>

<span> </span>

</div>

</div>

</div>

