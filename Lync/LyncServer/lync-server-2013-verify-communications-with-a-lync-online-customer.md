---
title: Lync Server 2013：验证与 Lync Online 客户的通信
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518659"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>在 Lync Server 2013 中验证与 Lync Online 客户的通信

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-08_

若要使组织中的 Lync 用户能够与 Microsoft Lync Online 2010 客户的用户通信，您必须完成以下步骤：

  - 满足所有先决条件。 这包括部署内部和边缘服务器，为组织实现联盟支持以及设置用户帐户。 有关详细信息，请参阅 [Lync Server 2013 中与 Lync Online 客户进行联盟的先决条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。

  - 配置内部部署中的域访问支持。 这包括创建主机提供程序条目和配置您的部署，以允许从 Lync Online 客户的域访问。 有关详细信息，请参阅 [在 Lync Server 2013 中配置 Lync Online 域的联合支持](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。

  - 将用户帐户配置为支持联盟。 有关详细信息，请参阅 [Lync Server 2013 中的为具有 Lync Online 客户的联盟配置用户访问权限](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。

完成所有这些步骤，并且 Lync Online 2010 客户的管理员完成了其在线服务的所有配置以支持与组织的联盟，请通过测试组织中的内部用户与 Lync Online 用户之间的通信来验证通信。 如果通信不成功，请使用边缘服务器中的日志记录工具捕获日志和跟踪文件，以便对问题进行故障排除。 有关使用日志记录工具的详细信息，请参阅操作文档中的 [打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md) 。 有关日志记录工具的详细信息，请参阅 TechNet Library 上的 Lync Server 2010 日志记录工具文档 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。

</div>

<span> </span>

</div>

</div>

</div>

