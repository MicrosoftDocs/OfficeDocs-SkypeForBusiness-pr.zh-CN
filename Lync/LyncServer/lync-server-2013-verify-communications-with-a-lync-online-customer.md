---
title: 'Lync Server 2013: 验证与 Lync Online 客户的通信'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6707139535ab30909f74b1a3fa51cce24374d09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>在 Lync Server 2013 中验证与 Lync Online 客户的通信

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-08_

若要使你的组织中的 Lync 用户能够与 Microsoft Lync Online 2010 客户的用户进行通信, 你必须已完成以下步骤:

  - 满足所有先决条件。 这包括部署内部和边缘服务器、为你的组织启用联合身份验证支持以及设置用户帐户。 有关详细信息, 请参阅[在 Lync Server 2013 中与 Lync Online 客户进行联盟的先决条件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。

  - 在内部部署中配置了域访问支持。 这包括创建主机提供程序条目和配置你的部署, 以允许从 Lync Online 客户的域访问。 有关详细信息, 请参阅[在 Lync Server 2013 中配置 Lync Online 域的联合身份验证支持](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。

  - 已配置你的用户帐户以支持联合身份验证。 有关详细信息, 请参阅[在 Lync Server 2013 中配置与 Lync Online 客户的联盟的用户访问权限](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。

完成所有这些步骤以及 Lync Online 2010 客户的管理员完成其在线服务的所有配置以支持与组织的联盟, 请通过测试内部通信之间的通信来验证通信您的组织中的用户和 Lync Online 客户的用户。 如果通信不成功, 请使用边缘服务器中的日志记录工具捕获日志和跟踪文件, 以便对问题进行故障排除。 有关使用日志记录工具的详细信息, 请参阅在操作文档中[打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。 有关日志记录工具的详细信息, 请参阅 TechNet 库中的 Lync Server 2010 日志记录工具[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)文档。

</div>

<span> </span>

</div>

</div>

</div>

