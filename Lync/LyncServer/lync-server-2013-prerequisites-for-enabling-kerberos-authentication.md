---
title: Lync Server 2013：启用 Kerberos 身份验证的先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecbba3403024663e529cef7653b310148faa2e2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

在启用 Kerberos 身份验证之前，请确保完成所有先决条件配置和基础结构准备：

  - 为 Lync Server 2013 扩展了 Active Directory 架构。

  - Lync Server 2013 的 Active Directory 林准备已完成。

  - Lync Server 2013 的 Active Directory 域准备已完成。

  - 中央管理存储已成功安装且可用。

  - 已使用拓扑生成器创建并发布拓扑。

  - 已定义和部署需要 Web 服务的服务器和角色，包括前端服务器、Standard Edition 服务器和控制器。

  - Internet Information Services （IIS）使用推荐的角色服务进行配置和部署，以支持 Lync Server 2013 中的 Web 服务。

满足先决条件后，应准备好创建一个或多个帐户，以供用于部署的 Kerberos 身份验证的 Web 服务使用。 至少需要为每个部署创建一个 Kerberos 身份验证帐户。 但是，可以为每个站点创建一个帐户，以在该站点提供本地 Kerberos 身份验证。 只能为每个站点指定一个 Kerberos 身份验证帐户。

</div>

<span> </span>

</div>

</div>

</div>

