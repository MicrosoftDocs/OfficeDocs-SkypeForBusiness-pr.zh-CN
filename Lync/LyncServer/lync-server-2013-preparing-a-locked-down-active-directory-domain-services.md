---
title: Lync Server 2013：准备锁定的 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b3e1eb33568bbc0e1742e31638a20879e4fffdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513359"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>在 Lync Server 2013 中准备锁定的 Active Directory 域服务

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-05-14_

组织通常会锁定 Active Directory 域服务以帮助缓解安全风险。 但是，锁定的 Active Directory 环境可以限制 Lync Server 2013 所需的权限。 为 Lync Server 2013 正确准备锁定的 Active Directory 环境涉及一些额外的注意事项和步骤。

在锁定的 Active Directory 环境中，权限以如下两种常见方式受到限制：

  - 从容器中删除经过身份验证的用户的访问控制项 (ACE)。

  - 权限继承在用户、联系人、InetOrgPerson 或计算机对象的容器上被禁用。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中删除经过身份验证的用户权限](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [在 Lync Server 2013 中的计算机、用户或 InetOrgPerson 容器上禁用权限继承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

