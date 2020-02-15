---
title: Lync Server 2013：授予权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 495b556254ab42270aa031861aea0c4390f17602
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="2d6db-102">在 Lync Server 2013 中授予权限</span><span class="sxs-lookup"><span data-stu-id="2d6db-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d6db-103">_**上次修改的主题：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="2d6db-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="2d6db-104">对于安装程序，可以为特定 Active Directory 组织单位（OU）授予对 RTCUniversalServerAdmins 通用组的权限，从而使该 OU 中的 RTCUniversalServerAdmins 组成员能够在指定的域中安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2d6db-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="2d6db-105">为 OU 授予权限时，授予的权限包括：</span><span class="sxs-lookup"><span data-stu-id="2d6db-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="2d6db-106">读取</span><span class="sxs-lookup"><span data-stu-id="2d6db-106">Read</span></span>

  - <span data-ttu-id="2d6db-107">写入</span><span class="sxs-lookup"><span data-stu-id="2d6db-107">Write</span></span>

  - <span data-ttu-id="2d6db-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="2d6db-108">ReadSPN</span></span>

  - <span data-ttu-id="2d6db-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="2d6db-109">WriteSPN</span></span>

<span data-ttu-id="2d6db-110">对于管理，可将权限添加到指定 OU 以便林准备过程创建的 RTC 通用组成员可以访问 OU，而不必是 Domain Admins 组成员。</span><span class="sxs-lookup"><span data-stu-id="2d6db-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="2d6db-111">添加到指定 OU 的权限与 **Enable-CsAdDomain** cmdlet 添加到计算机和用户 OU 容器的权限相同。</span><span class="sxs-lookup"><span data-stu-id="2d6db-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d6db-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="2d6db-112">In This Section</span></span>

  - [<span data-ttu-id="2d6db-113">在 Lync Server 2013 中授予安装程序权限</span><span class="sxs-lookup"><span data-stu-id="2d6db-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="2d6db-114">在 Lync Server 2013 中授予组织单位权限</span><span class="sxs-lookup"><span data-stu-id="2d6db-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

