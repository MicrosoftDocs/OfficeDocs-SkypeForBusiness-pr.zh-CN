---
title: Lync Server 2013：验证拓扑设计
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e8dae20a945194fb4fda2bcc84eab232d9b34e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518589"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a>验证 Lync Server 2013 中的拓扑设计

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-01-02_

拓扑生成器将自动验证拓扑。 任何拓扑错误均被标识为验证错误，由服务器角色旁边的验证错误图标指示。 验证拓扑是否正确代表部署的拓扑也很重要。

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>发布前验证拓扑

1.  检查所有简单 URL 是否配置正确。

2.  确认基于 SQL Server 的服务器处于联机状态，并且可用于安装了拓扑生成器的计算机，包括任何必要的防火墙规则。

3.  确认文件共享可用，并已定义适当的权限。

4.  确认拓扑中定义了满足部署要求的正确服务器角色。

5.  验证服务器是否存在于 Active Directory 域服务中。 如果已将服务器加入域，将自动验证。

如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。 如果出现验证错误，则必须先更正错误，然后才能发布拓扑。 有关发布拓扑的详细信息，请参阅 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

