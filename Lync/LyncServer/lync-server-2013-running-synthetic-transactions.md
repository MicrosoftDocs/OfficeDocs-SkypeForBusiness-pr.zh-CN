---
title: Lync Server 2013：运行综合事务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 448e96c03b554970b1ee92166908965ee2a6629c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中运行综合事务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-18_

通常通过两种方式执行综合事务。 您可以使用 CsHealthMonitoringConfiguration cmdlet 为每个注册器池设置测试用户。 这些测试用户是已预配置为与综合事务一起使用的一对用户。 （通常，这些是测试帐户，而不是属于实际用户的帐户。）使用为池配置的测试用户，可以对该池运行综合事务，而无需为测试中涉及的用户帐户指定（并提供凭据）的标识。

或者，您可以使用实际用户帐户运行综合事务。 例如，如果两个用户不能交换即时消息，则可以使用这两个用户帐户（而不是一对一对测试帐户）运行一个综合事务，然后尝试诊断并解决该问题。 如果您决定使用实际用户帐户执行综合事务，则必须为每个用户提供登录名和密码。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置观察程序节点测试用户和配置设置](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013 中的综合事务的特殊设置说明](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

