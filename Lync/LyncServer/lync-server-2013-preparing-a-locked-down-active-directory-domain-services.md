---
title: Lync Server 2013：准备锁定的 Active Directory 域服务
description: Lync Server 2013：准备锁定的 Active Directory 域服务。
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
ms.openlocfilehash: 4aea04b138de2630935713eda7cbef9e4d21572a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566298"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="7a745-103">在 Lync Server 2013 中准备锁定的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="7a745-103">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a745-104">_**上次修改的主题：** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="7a745-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="7a745-105">组织通常会锁定 Active Directory 域服务以帮助缓解安全风险。</span><span class="sxs-lookup"><span data-stu-id="7a745-105">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="7a745-106">但是，锁定的 Active Directory 环境可以限制 Lync Server 2013 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="7a745-106">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="7a745-107">为 Lync Server 2013 正确准备锁定的 Active Directory 环境涉及一些额外的注意事项和步骤。</span><span class="sxs-lookup"><span data-stu-id="7a745-107">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="7a745-108">在锁定的 Active Directory 环境中，权限以如下两种常见方式受到限制：</span><span class="sxs-lookup"><span data-stu-id="7a745-108">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="7a745-109">从容器中删除经过身份验证的用户的访问控制项 (ACE)。</span><span class="sxs-lookup"><span data-stu-id="7a745-109">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="7a745-110">权限继承在用户、联系人、InetOrgPerson 或计算机对象的容器上被禁用。</span><span class="sxs-lookup"><span data-stu-id="7a745-110">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7a745-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="7a745-111">In This Section</span></span>

  - [<span data-ttu-id="7a745-112">在 Lync Server 2013 中删除经过身份验证的用户权限</span><span class="sxs-lookup"><span data-stu-id="7a745-112">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="7a745-113">在 Lync Server 2013 中的计算机、用户或 InetOrgPerson 容器上禁用权限继承</span><span class="sxs-lookup"><span data-stu-id="7a745-113">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

