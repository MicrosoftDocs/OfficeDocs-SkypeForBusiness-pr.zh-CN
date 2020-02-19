---
title: Lync Server 2013：为 Lync Server 启用的用户帐户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3545ba99f55e0fa11bcee09791d1a618b92c3d78
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a><span data-ttu-id="1ee09-102">为 Lync Server 2013 启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="1ee09-102">User accounts enabled for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ee09-103">_**上次修改的主题：** 2014-04-18_</span><span class="sxs-lookup"><span data-stu-id="1ee09-103">_**Topic Last Modified:** 2014-04-18_</span></span>

<span data-ttu-id="1ee09-104">本节中的主题提供了配置用户设置的分步过程，您可以使用 Lync Server 2013 控制面板来执行这些设置。</span><span class="sxs-lookup"><span data-stu-id="1ee09-104">Topics in this section provide step-by-step procedures for configuring user settings that you can perform using the Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ee09-105">您不能使用 Lync Server 控制面板来管理属于 Active Directory Domain Admins 组成员的用户。</span><span class="sxs-lookup"><span data-stu-id="1ee09-105">You cannot use Lync Server Control Panel to manage users who are members of the Active Directory Domain Admins group.</span></span> <span data-ttu-id="1ee09-106">对于域管理员用户，只能使用 Lync Server 控制面板执行只读的搜索操作。</span><span class="sxs-lookup"><span data-stu-id="1ee09-106">For Domain Admins users, you can use Lync Server Control Panel only to perform read-only search operations.</span></span> <span data-ttu-id="1ee09-107">若要对域管理员用户执行写入操作（例如，为 Lync Server 控制面板启用或禁用，更改池或策略分配，电话设置，SIP 地址），则必须在以域管理员用户身份登录时使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1ee09-107">To perform write operations on Domain Admins users (for example, enable or disable for Lync Server Control Panel, change pool or policy assignments, telephony settings, SIP address), you must use Windows PowerShell cmdlets while logged on as a Domain Admins user.</span></span> <span data-ttu-id="1ee09-108">有关使用 Windows PowerShell cmdlet 管理用户的详细信息，请参阅<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 命令行管理</A>程序。</span><span class="sxs-lookup"><span data-stu-id="1ee09-108">For details about using Windows PowerShell cmdlets to manage users, see <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A>.</span></span>



</div>

<span data-ttu-id="1ee09-109">当您执行涉及搜索用户或筛选用户搜索结果的任何 Lync Server 2013 管理任务时，会有一些用户属性作为属性存在于 Active Directory 域服务中，但不会复制到全局编录中。在部署 Microsoft Exchange Server 之前。</span><span class="sxs-lookup"><span data-stu-id="1ee09-109">When you perform any Lync Server 2013 administrative task that involves searching for a user or filtering user search results, there are some user properties that exist as attributes in Active Directory Domain Services but are not replicated to the global catalog until Microsoft Exchange Server is deployed.</span></span> <span data-ttu-id="1ee09-110">Microsoft Exchange （而不是 Lync Server）在安装时将以下属性标记为用于复制到全局编录：</span><span class="sxs-lookup"><span data-stu-id="1ee09-110">Microsoft Exchange, not Lync Server, marks the following attributes for replication to the global catalog when it is installed:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ee09-111">用户信息</span><span class="sxs-lookup"><span data-stu-id="1ee09-111">User Information</span></span></th>
<th><span data-ttu-id="1ee09-112">地址和电话</span><span class="sxs-lookup"><span data-stu-id="1ee09-112">Address and Phone</span></span></th>
<th><span data-ttu-id="1ee09-113">组织</span><span class="sxs-lookup"><span data-stu-id="1ee09-113">Organization</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ee09-114">缩写</span><span class="sxs-lookup"><span data-stu-id="1ee09-114">Initials</span></span></p></td>
<td><p><span data-ttu-id="1ee09-115">街道地址</span><span class="sxs-lookup"><span data-stu-id="1ee09-115">Street address</span></span></p>
<p><span data-ttu-id="1ee09-116">国家/地区</span><span class="sxs-lookup"><span data-stu-id="1ee09-116">Country/region</span></span></p>
<p><span data-ttu-id="1ee09-117">值班</span><span class="sxs-lookup"><span data-stu-id="1ee09-117">Pager</span></span></p>
<p><span data-ttu-id="1ee09-118">传真</span><span class="sxs-lookup"><span data-stu-id="1ee09-118">Fax</span></span></p>
<p><span data-ttu-id="1ee09-119">移动设备</span><span class="sxs-lookup"><span data-stu-id="1ee09-119">Mobile</span></span></p></td>
<td><p><span data-ttu-id="1ee09-120">标题</span><span class="sxs-lookup"><span data-stu-id="1ee09-120">Title</span></span></p>
<p><span data-ttu-id="1ee09-121">公司</span><span class="sxs-lookup"><span data-stu-id="1ee09-121">Company</span></span></p>
<p><span data-ttu-id="1ee09-122">部门</span><span class="sxs-lookup"><span data-stu-id="1ee09-122">Department</span></span></p>
<p><span data-ttu-id="1ee09-123">办公室</span><span class="sxs-lookup"><span data-stu-id="1ee09-123">Office</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="1ee09-124">本部分内容</span><span class="sxs-lookup"><span data-stu-id="1ee09-124">In This Section</span></span>

  - [<span data-ttu-id="1ee09-125">查看有关为 Lync Server 2013 启用的用户帐户的信息</span><span class="sxs-lookup"><span data-stu-id="1ee09-125">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [<span data-ttu-id="1ee09-126">为 Lync Server 2013 启用和禁用用户</span><span class="sxs-lookup"><span data-stu-id="1ee09-126">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [<span data-ttu-id="1ee09-127">在 Lync Server 2013 中管理用户的企业语音语音</span><span class="sxs-lookup"><span data-stu-id="1ee09-127">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [<span data-ttu-id="1ee09-128">在 Lync Server 2013 中修改用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="1ee09-128">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)

  - [<span data-ttu-id="1ee09-129">在 Lync Server 2013 中管理外部访问策略</span><span class="sxs-lookup"><span data-stu-id="1ee09-129">Manage external access policy in Lync Server 2013</span></span>](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [<span data-ttu-id="1ee09-130">在 Lync Server 2013 中分配每用户策略</span><span class="sxs-lookup"><span data-stu-id="1ee09-130">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ee09-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee09-131">See Also</span></span>


[<span data-ttu-id="1ee09-132">Lync Server 2013 中的用户管理 cmdlet</span><span class="sxs-lookup"><span data-stu-id="1ee09-132">User management cmdlets in Lync Server 2013</span></span>](lync-server-2013-user-management-cmdlets.md)  


[<span data-ttu-id="1ee09-133">在 Lync Server 2013 中管理用户</span><span class="sxs-lookup"><span data-stu-id="1ee09-133">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

