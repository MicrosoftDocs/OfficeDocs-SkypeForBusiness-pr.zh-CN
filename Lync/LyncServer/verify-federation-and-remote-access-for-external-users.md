---
title: 验证联盟和外部用户的远程访问
description: 验证外部用户的联盟和远程访问。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555068"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>验证联盟和外部用户的远程访问

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-18_

将联合身份验证路由转换为 Lync Server 2013 边缘服务器后，应执行一些功能测试，以验证联合身份验证是否按预期执行。 外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>测试外部用户和外部访问的连接

  - 至少一个联盟域中的用户、Lync Server 2013 上的内部用户以及 Lync Server 2010 上的用户。 测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。

  - 您的组织支持 (的每个公共 IM 服务提供商的用户和已完成的设置) 与 Lync Server 2013 上的用户通信，以及 Lync Server 2010 上的用户。

  - 验证匿名用户是否能够加入会议。

  - 在 Lync Server 2010 上托管的用户使用远程用户访问 (登录到 intranet 外部的 Lync Server 2010，但没有 VPN) 与 Lync Server 2013 上的用户以及 Lync Server 2010 上的用户。 测试 IM、状态、A/V 和桌面共享。

  - 在 Lync Server 2013 上托管的用户使用远程用户访问 (登录到 intranet 外部的 Lync Server 2013，但没有 VPN) 与 Lync Server 2013 上的用户以及 Lync Server 2010 上的用户。 测试 IM、状态、A/V 和桌面共享。

</div>

</div>

<span> </span>

</div>

</div>

</div>

