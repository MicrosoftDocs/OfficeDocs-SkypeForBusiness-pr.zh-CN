---
title: Lync Server 2013：准备域
description: Lync Server 2013：准备域。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7700bbdd10a96949f892858ae03da8de60d86a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549978"
---
# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="fdfce-103">准备 Lync Server 2013 的域</span><span class="sxs-lookup"><span data-stu-id="fdfce-103">Preparing domains for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdfce-104">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="fdfce-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="fdfce-105">准备 Active Directory 域服务以获取 Lync Server 2013 的最后一个步骤是 "域准备"。</span><span class="sxs-lookup"><span data-stu-id="fdfce-105">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="fdfce-106">域准备步骤中将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。</span><span class="sxs-lookup"><span data-stu-id="fdfce-106">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="fdfce-107">域准备过程中将在域根和以下三个内置容器中创建 ACE：用户、计算机和域控制器。</span><span class="sxs-lookup"><span data-stu-id="fdfce-107">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="fdfce-108">您可以在要部署 Lync Server 的域中的任何计算机上运行域准备工作。</span><span class="sxs-lookup"><span data-stu-id="fdfce-108">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="fdfce-109">您必须准备将承载 Lync Server 或用户的每个域。</span><span class="sxs-lookup"><span data-stu-id="fdfce-109">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="fdfce-110">如果在组织中禁用了权限继承，或者禁用了经过身份验证的用户权限，则在域准备期间还必须执行其他步骤。</span><span class="sxs-lookup"><span data-stu-id="fdfce-110">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="fdfce-111">有关详细信息，请参阅 [在 Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="fdfce-111">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="fdfce-112">如果组织使用组织单位 (OU) 代替三个内置容器（即“用户”、“计算机”和“域控制器”），则必须为 Authenticated Users 组授予 OU 的读取权限。</span><span class="sxs-lookup"><span data-stu-id="fdfce-112">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="fdfce-113">域准备需要具有容器的读取权限。</span><span class="sxs-lookup"><span data-stu-id="fdfce-113">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="fdfce-114">如果 Authenticated Users 组没有对 OU 的读取权限，请按照以下代码示例中所示运行 **Grant-CsOuPermission** cmdlet，授予对每个 OU 的读取权限。</span><span class="sxs-lookup"><span data-stu-id="fdfce-114">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="fdfce-115">有关 CsOuPermission cmdlet 的详细信息，请参阅 Lync Server 命令行管理 **程序** 文档。</span><span class="sxs-lookup"><span data-stu-id="fdfce-115">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="fdfce-116">有关在域根和用户、计算机和域控制器容器中创建的 Ace 的详细信息，请参阅 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的域准备所做的更改</A>。</span><span class="sxs-lookup"><span data-stu-id="fdfce-116">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fdfce-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="fdfce-117">In This Section</span></span>

  - [<span data-ttu-id="fdfce-118">为 Lync Server 2013 运行域准备</span><span class="sxs-lookup"><span data-stu-id="fdfce-118">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="fdfce-119">使用 cmdlet 对 Lync Server 2013 执行反向域准备</span><span class="sxs-lookup"><span data-stu-id="fdfce-119">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

