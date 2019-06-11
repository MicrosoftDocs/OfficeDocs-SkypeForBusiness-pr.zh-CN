---
title: Lync Server 2013：启用 Kerberos 身份验证的先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

在启用 Kerberos 身份验证之前, 请确保完成所有先决条件配置和基础结构准备:

  - Active Directory 架构已针对 Lync Server 2013 进行了扩展。

  - 已完成 Lync Server 2013 的 Active Directory 林准备。

  - 已完成 Lync Server 2013 的 Active Directory 域准备。

  - 中央管理存储已成功安装且可用。

  - 拓扑结构已使用拓扑生成器创建和发布。

  - 已定义并部署需要 Web 服务的服务器和角色, 包括前端服务器、标准版服务器和控制器。

  - Internet Information Services (IIS) 已使用推荐的角色服务进行配置和部署, 以支持 Lync Server 2013 中的 Web 服务。

满足先决条件后, 您应该准备好创建一个或多个用于部署的 Kerberos 身份验证的 Web 服务帐户。 至少, 你需要为每个部署创建一个 Kerberos 身份验证帐户。 但是, 你可以为每个网站创建一个帐户, 以便在网站上提供本地 Kerberos 身份验证。 你只能为每个站点指定一个 Kerberos 身份验证帐户。

</div>

<span> </span>

</div>

</div>

</div>

