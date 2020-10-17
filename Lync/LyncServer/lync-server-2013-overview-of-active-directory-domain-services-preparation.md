---
title: Lync Server 2013： Active Directory 域服务准备概述
description: Lync Server 2013： Active Directory 域服务准备概述。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b22e11a73ad7a181e2eaf887b1b49b934d9db5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566838"
---
# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="f4abd-103">Lync Server 2013 中的 Active Directory 域服务准备概述</span><span class="sxs-lookup"><span data-stu-id="f4abd-103">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4abd-104">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f4abd-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="f4abd-105">若要为 Lync Server 2013 部署准备 Active Directory 域服务，必须按特定顺序执行三个步骤。</span><span class="sxs-lookup"><span data-stu-id="f4abd-105">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="f4abd-106">下表介绍为 Lync Server 准备 AD DS 所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="f4abd-106">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="f4abd-107">Active Directory 准备步骤</span><span class="sxs-lookup"><span data-stu-id="f4abd-107">Active Directory Preparation Steps</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f4abd-108">步骤</span><span class="sxs-lookup"><span data-stu-id="f4abd-108">Step</span></span></th>
<th><span data-ttu-id="f4abd-109">说明</span><span class="sxs-lookup"><span data-stu-id="f4abd-109">Description</span></span></th>
<th><span data-ttu-id="f4abd-110">运行位置</span><span class="sxs-lookup"><span data-stu-id="f4abd-110">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="f4abd-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">在 Lync Server 2013 中准备 Active Directory 架构</a></span><span class="sxs-lookup"><span data-stu-id="f4abd-111"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4abd-112">通过添加 Lync Server 使用的新类和属性扩展 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="f4abd-112">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="f4abd-113">对将在其中部署 Lync Server 的部署中的每个林运行一次。</span><span class="sxs-lookup"><span data-stu-id="f4abd-113">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="f4abd-114">对将在其中部署 Lync Server 的每个林的根域中的架构主机。</span><span class="sxs-lookup"><span data-stu-id="f4abd-114">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4abd-p101">如果在架构主机上具有权限，则无需在根域中执行此步骤，但必须是根域中 Schema Admins 组的成员，并且是架构主机上 Enterprise Admins 组的成员。在资源林拓扑中，仅在资源林中执行此步骤，而不必在任何用户林中执行。在中央林拓扑中，仅在中央林中执行此步骤，而不必在任何用户林中执行。</span><span class="sxs-lookup"><span data-stu-id="f4abd-p101">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master. In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="f4abd-118"><a href="lync-server-2013-preparing-the-forest.md">准备 Lync Server 2013 的林</a></span><span class="sxs-lookup"><span data-stu-id="f4abd-118"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4abd-119">创建由 Lync Server 使用的全局设置和通用组。</span><span class="sxs-lookup"><span data-stu-id="f4abd-119">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="f4abd-120">对将在其中部署 Lync Server 的部署中的每个林运行一次。</span><span class="sxs-lookup"><span data-stu-id="f4abd-120">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="f4abd-121">在将在其中部署 Lync Server 的每个林的根域中。</span><span class="sxs-lookup"><span data-stu-id="f4abd-121">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="f4abd-122">您必须是 Enterprise Admins 组的成员才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="f4abd-122">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4abd-p103">在资源林拓扑中，仅在资源林中执行此步骤，而不必在任何用户林中执行。在中央林拓扑中，仅在中央林中执行此步骤，而不必在任何用户林中执行。</span><span class="sxs-lookup"><span data-stu-id="f4abd-p103">In a resource forest topology, run this step only in the resource forest, not in any user forests. In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="f4abd-125"><a href="lync-server-2013-preparing-domains.md">准备 Lync Server 2013 的域</a></span><span class="sxs-lookup"><span data-stu-id="f4abd-125"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f4abd-126">添加对通用组成员所要使用的对象的权限。</span><span class="sxs-lookup"><span data-stu-id="f4abd-126">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="f4abd-127">为每个用户域或服务器域运行一次。</span><span class="sxs-lookup"><span data-stu-id="f4abd-127">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f4abd-128">如果要从 Lync Server 2010 迁移到 Lync Server 2013，部署向导可能会指示已完成域准备工作。</span><span class="sxs-lookup"><span data-stu-id="f4abd-128">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="f4abd-129">无需再次运行域准备。</span><span class="sxs-lookup"><span data-stu-id="f4abd-129">You do not need to run domain preparation again.</span></span> <span data-ttu-id="f4abd-130">权限未从 Lync Server 2010 更改为 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f4abd-130">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="f4abd-131">在将部署 Lync Server 的每个域中的成员服务器上。</span><span class="sxs-lookup"><span data-stu-id="f4abd-131">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="f4abd-132">您必须是 Domain Admins 组的成员才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="f4abd-132">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="f4abd-133">Lync Server 2013 （如 Lync Server 2010）将大部分配置信息存储在中央管理存储中，而不是在 Office 通信服务器 2007 R2 中，而不是在 AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="f4abd-133">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="f4abd-134">但是，以下信息存储在 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="f4abd-134">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="f4abd-135">**架构扩展**：</span><span class="sxs-lookup"><span data-stu-id="f4abd-135">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="f4abd-136">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="f4abd-136">User object extensions</span></span>
    
      - <span data-ttu-id="f4abd-137">Office 通信服务器 2007 R2 类的扩展，以保持向后兼容性</span><span class="sxs-lookup"><span data-stu-id="f4abd-137">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="f4abd-138">存储在 Lync Server 扩展架构和现有架构类中的**数据** () ：</span><span class="sxs-lookup"><span data-stu-id="f4abd-138">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="f4abd-139">用户 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="f4abd-139">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="f4abd-140">应用程序（如响应组和会议助理）的联系人对象</span><span class="sxs-lookup"><span data-stu-id="f4abd-140">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="f4abd-141">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="f4abd-141">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="f4abd-142">Kerberos 身份验证帐户（可选计算机对象）</span><span class="sxs-lookup"><span data-stu-id="f4abd-142">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="f4abd-143">在 Lync Server 2013 中，通过向 RTCUniversalServerAdmins 通用组授予安装程序权限来委派安装和管理，以便该组的成员可以在本地服务器 (上安装和激活 Lync Server 2013，在将服务器添加到拓扑中并已发布并启用) 之后。</span><span class="sxs-lookup"><span data-stu-id="f4abd-143">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="f4abd-144">委派用户必须是安装和激活 Lync Server 2013 的计算机上的本地管理员，但不需要是 Domain Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="f4abd-144">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="f4abd-145">您也可以授予对特定组织单位 (OU) 中的对象的权限，以便在林准备期间创建的通用组成员无需是 Domain Admins 组成员即可访问这些对象。</span><span class="sxs-lookup"><span data-stu-id="f4abd-145">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="f4abd-146">对于 Lync Server 2013 的新部署，全局设置必须存储在配置容器中。</span><span class="sxs-lookup"><span data-stu-id="f4abd-146">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="f4abd-147">如果您的组织从早期版本升级，但在系统容器中仍有全局设置，则系统容器仍受支持。</span><span class="sxs-lookup"><span data-stu-id="f4abd-147">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4abd-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4abd-148">See Also</span></span>


[<span data-ttu-id="f4abd-149">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="f4abd-149">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="f4abd-150">Lync Server 2013 使用的 Active Directory 架构扩展、类和属性</span><span class="sxs-lookup"><span data-stu-id="f4abd-150">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="f4abd-151">准备 Lync Server 2013 的林</span><span class="sxs-lookup"><span data-stu-id="f4abd-151">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="f4abd-152">准备 Lync Server 2013 的域</span><span class="sxs-lookup"><span data-stu-id="f4abd-152">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

