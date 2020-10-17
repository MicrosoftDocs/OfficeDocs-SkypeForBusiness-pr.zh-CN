---
title: Lync Server 2013 中央管理存储故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508039"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存储故障转移

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

中央管理存储包含有关 Lync 2013 部署中的服务器和服务的配置数据。 它提供了用于定义、设置、维护、管理、描述和操作 Lync 2013 部署所需的数据的可靠、架构化的存储。 它还会验证数据，以确保配置的一致性。

每个 Lync 部署都包含一个中央管理存储，该存储由一个前端池的后端服务器托管。

建立包括承载中央管理存储的池的池配对时，将在备份池中设置备份中央管理存储数据库，并在两个池中安装中央管理存储服务。 在任何时间点，两个中央管理存储数据库之一是活动主控形状，另一个是备用的。 内容将由后端服务从活动主机复制到备用主机。

在涉及承载中央管理存储的池的池故障转移过程中，管理员必须先对中央管理存储进行故障转移，然后才能对前端池进行故障转移。

修复灾难后，无需对中央管理存储进行故障回复。 修复后，原始备份池中的中央管理存储可以保留为活动主控形状。

集中管理存储故障转移的工程目标为5分钟，恢复时间目标 (RTO) ，5分钟用于恢复点目标 (RPO) 。

</div>

<span> </span>

</div>

</div>

</div>

