---
title: 验证配置设置的复制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cde1f3a96f249e98bc4e48c2e6d9c40adaad526
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a>验证配置设置的复制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

你可以通过在中央管理存储所在的内部计算机或任何域的内部计算机上**** 运行 Lync server 2013 cmdlet 来验证将配置信息复制到边缘服务器的操作安装了 Lync Server 2013 核心组件的已加入计算机。

初始结果可能表明状态为 "False", 而不是 "True" 用于复制。 如果是这样, 请运行**CsManagementStoreReplication** cmdlet 并留出时间, 以便在再次运行**CsManagementStoreReplicationStatus** cmdlet 之前完成复制。

</div>

<span> </span>

</div>

</div>

</div>

