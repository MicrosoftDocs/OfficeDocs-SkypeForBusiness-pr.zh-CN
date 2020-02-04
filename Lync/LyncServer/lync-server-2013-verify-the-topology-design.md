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
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a>在 Lync Server 2013 中验证拓扑设计

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-01-02_

拓扑生成器会自动验证拓扑。 任何拓扑错误均标识为验证错误，该错误由服务器角色旁边的验证错误图标指示。 还必须验证拓扑是否正确表示你的部署的拓扑。

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a>在发布之前验证拓扑

1.  检查所有简单 URL 是否配置正确。

2.  确认基于 SQL Server 的服务器处于联机状态，并可供安装拓扑生成器（包括所有必要防火墙规则）的计算机使用。

3.  确认文件共享可用且已定义适当的权限。

4.  确认拓扑中定义了满足部署要求的正确服务器角色。

5.  验证服务器是否存在于 Active Directory 域服务中。 如果已将服务器加入域，则会自动发生此情况。

如果已验证拓扑并且未出现验证错误，则发布拓扑的准备工作应该已经就绪。 如果存在验证错误，则必须先更正这些错误，然后才能发布拓扑。 有关发布拓扑的详细信息，请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

