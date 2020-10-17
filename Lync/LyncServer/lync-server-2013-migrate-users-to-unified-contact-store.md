---
title: Lync Server 2013：将用户迁移到统一联系人存储
description: Lync Server 2013：将用户迁移到统一联系人存储。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568588"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中将用户迁移到统一联系人存储

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-15_

当用户处于以下情况时，会自动将用户的联系人迁移到 Exchange 2013 服务器：

  - 为其分配了将 UcsAllowed 设置为 True 的用户服务策略。

  - 已使用 Exchange 2013 邮箱进行了预配，并至少已登录到邮箱一次。

  - 使用 Lync 2013 富客户端登录。

如果用户使用 Lync 2010 或更早版本的客户端登录，或者如果用户未连接到 Exchange 2013 服务器，则用户服务策略将被忽略，并且用户的联系人仍保留在 Lync Server 中。

您可以通过以下任一方法来确定是否已迁移用户的联系人：

  - 在客户端计算机上检查以下注册表项：
    
    HKEY \_ 当前 \_ 用户 \\ 软件 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ \<SIP URL\> \\ UCS
    
    如果用户的联系人存储在 Exchange 2013 中，则此项包含值为2165的值 InUCSMode。

  - 运行 **Test-CsUnifiedContactStore** cmdlet。 在 Lync Server Management Shell 命令行中，键入：
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    如果 **Test-CsUnifiedContactStore** 成功，表明用户的联系人已迁移到统一联系人存储中。

</div>

<span> </span>

</div>

</div>

</div>

