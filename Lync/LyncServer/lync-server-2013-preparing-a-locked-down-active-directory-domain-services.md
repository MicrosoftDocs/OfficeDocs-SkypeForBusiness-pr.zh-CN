---
title: Lync Server 2013：准备锁定的 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="28259-102">在 Lync Server 2013 中准备锁定的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="28259-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28259-103">_**主题上次修改时间:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="28259-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="28259-104">组织通常会锁定 Active Directory 域服务以帮助降低安全风险。</span><span class="sxs-lookup"><span data-stu-id="28259-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="28259-105">但是, 锁定的活动目录环境可以限制 Lync Server 2013 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="28259-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="28259-106">正确为 Lync Server 2013 准备锁定的活动目录环境涉及一些其他注意事项和步骤。</span><span class="sxs-lookup"><span data-stu-id="28259-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="28259-107">在锁定的活动目录环境中, 权限受到限制的两种常见方式如下所示:</span><span class="sxs-lookup"><span data-stu-id="28259-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="28259-108">已从容器中删除经过身份验证的用户访问控制项 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="28259-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="28259-109">在用户、联系人、InetOrgPerson 或计算机对象的容器上禁用权限继承。</span><span class="sxs-lookup"><span data-stu-id="28259-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="28259-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="28259-110">In This Section</span></span>

  - [<span data-ttu-id="28259-111">在 Lync Server 2013 中删除经过身份验证的用户的权限</span><span class="sxs-lookup"><span data-stu-id="28259-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="28259-112">Lync Server 2013 中权限继承在计算机、用户或 InetOrgPerson 容器上被禁用</span><span class="sxs-lookup"><span data-stu-id="28259-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

