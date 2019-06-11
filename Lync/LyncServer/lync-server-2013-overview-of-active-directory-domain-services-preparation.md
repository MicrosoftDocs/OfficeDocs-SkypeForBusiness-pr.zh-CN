---
title: Lync Server 2013：Active Directory 域服务准备概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a><span data-ttu-id="f0f93-102">Lync Server 2013 中的 Active Directory 域服务准备概述</span><span class="sxs-lookup"><span data-stu-id="f0f93-102">Overview of Active Directory Domain Services preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0f93-103">_**主题上次修改时间:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="f0f93-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="f0f93-104">若要为 Lync Server 2013 部署准备 Active Directory 域服务, 必须按特定顺序执行三个步骤。</span><span class="sxs-lookup"><span data-stu-id="f0f93-104">To prepare Active Directory Domain Services for your Lync Server 2013 deployment, you must perform three steps in a specific sequence.</span></span>

<span data-ttu-id="f0f93-105">下表介绍了为 Lync Server 准备 AD DS 所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="f0f93-105">The following table describes the steps required to prepare AD DS for Lync Server.</span></span>

### <a name="active-directory-preparation-steps"></a><span data-ttu-id="f0f93-106">Active Directory 准备步骤</span><span class="sxs-lookup"><span data-stu-id="f0f93-106">Active Directory Preparation Steps</span></span>

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
<th><span data-ttu-id="f0f93-107">步骤</span><span class="sxs-lookup"><span data-stu-id="f0f93-107">Step</span></span></th>
<th><span data-ttu-id="f0f93-108">说明</span><span class="sxs-lookup"><span data-stu-id="f0f93-108">Description</span></span></th>
<th><span data-ttu-id="f0f93-109">运行位置</span><span class="sxs-lookup"><span data-stu-id="f0f93-109">Where run</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><span data-ttu-id="f0f93-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">在 Lync Server 2013 中准备 Active Directory 架构</a></span><span class="sxs-lookup"><span data-stu-id="f0f93-110"><a href="lync-server-2013-preparing-the-active-directory-schema.md">Preparing the Active Directory schema in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0f93-111">通过添加 Lync Server 使用的新类和属性, 扩展 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="f0f93-111">Extends the Active Directory schema by adding new classes and attributes that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="f0f93-112">对将在其中部署 Lync Server 的部署中的每个林运行一次。</span><span class="sxs-lookup"><span data-stu-id="f0f93-112">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="f0f93-113">对于将在其中部署 Lync Server 的每个林的根域中的架构主机。</span><span class="sxs-lookup"><span data-stu-id="f0f93-113">Against the schema master in the root domain of each forest where Lync Server will be deployed.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f0f93-114">如果你拥有架构主机的权限, 则无需在根域中运行此步骤, 但你必须是根域中的架构管理员组的成员, 以及架构主机上企业管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="f0f93-114">You do not need to run this step in the root domain if you have permissions on the schema master, but you must be a member of the Schema Admins group in the root domain and a member of the Enterprise Admins group on the schema master.</span></span> <span data-ttu-id="f0f93-115">在资源林拓扑中, 仅在资源目录林中运行此步骤, 而不是在任何用户林中运行。</span><span class="sxs-lookup"><span data-stu-id="f0f93-115">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="f0f93-116">在中央林拓扑中, 仅在中央林中 (而不是在任何用户林中) 运行此步骤。</span><span class="sxs-lookup"><span data-stu-id="f0f93-116">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><span data-ttu-id="f0f93-117"><a href="lync-server-2013-preparing-the-forest.md">为 Lync Server 2013 准备林</a></span><span class="sxs-lookup"><span data-stu-id="f0f93-117"><a href="lync-server-2013-preparing-the-forest.md">Preparing the forest for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0f93-118">创建由 Lync Server 使用的全局设置和通用组。</span><span class="sxs-lookup"><span data-stu-id="f0f93-118">Creates global settings and universal groups that are used by Lync Server.</span></span></p>
<p><span data-ttu-id="f0f93-119">对将在其中部署 Lync Server 的部署中的每个林运行一次。</span><span class="sxs-lookup"><span data-stu-id="f0f93-119">Run once for each forest in your deployment where Lync Server will be deployed.</span></span></p></td>
<td><p><span data-ttu-id="f0f93-120">在将在其中部署 Lync Server 的每个林的根域中。</span><span class="sxs-lookup"><span data-stu-id="f0f93-120">In the root domain of each forest where Lync Server will be deployed.</span></span> <span data-ttu-id="f0f93-121">若要运行此步骤, 您必须是企业管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="f0f93-121">To run this step, you must be a member of the Enterprise Admins group.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f0f93-122">在资源林拓扑中, 仅在资源目录林中运行此步骤, 而不是在任何用户林中运行。</span><span class="sxs-lookup"><span data-stu-id="f0f93-122">In a resource forest topology, run this step only in the resource forest, not in any user forests.</span></span> <span data-ttu-id="f0f93-123">在中央林拓扑中, 仅在中央林中 (而不是在任何用户林中) 运行此步骤。</span><span class="sxs-lookup"><span data-stu-id="f0f93-123">In a central forest topology, run this step only in the central forest, not in any user forests.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><span data-ttu-id="f0f93-124"><a href="lync-server-2013-preparing-domains.md">为 Lync Server 2013 准备域</a></span><span class="sxs-lookup"><span data-stu-id="f0f93-124"><a href="lync-server-2013-preparing-domains.md">Preparing domains for Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="f0f93-125">在要由通用组成员使用的对象上添加权限。</span><span class="sxs-lookup"><span data-stu-id="f0f93-125">Adds permissions on objects to be used by members of universal groups.</span></span></p>
<p><span data-ttu-id="f0f93-126">每个用户域或服务器域运行一次。</span><span class="sxs-lookup"><span data-stu-id="f0f93-126">Run once per user domain or server domain.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="f0f93-127">如果要从 Lync Server 2010 迁移到 Lync Server 2013, 则部署向导可能会指示域准备已完成。</span><span class="sxs-lookup"><span data-stu-id="f0f93-127">If you are migrating from Lync Server 2010 to Lync Server 2013, the Deployment Wizard may indicate that domain preparation is already complete.</span></span> <span data-ttu-id="f0f93-128">无需再次运行域准备。</span><span class="sxs-lookup"><span data-stu-id="f0f93-128">You do not need to run domain preparation again.</span></span> <span data-ttu-id="f0f93-129">权限未从 Lync Server 2010 更改为 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f0f93-129">Permissions were not changed from Lync Server 2010 to Lync Server 2013.</span></span>


</div></td>
<td><p><span data-ttu-id="f0f93-130">在将部署 Lync Server 的每个域中的成员服务器上。</span><span class="sxs-lookup"><span data-stu-id="f0f93-130">On a member server in each domain where Lync Server will be deployed.</span></span> <span data-ttu-id="f0f93-131">若要运行此步骤, 您必须是域管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="f0f93-131">To run this step, you must be a member of the Domain Admins group.</span></span></p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

<span data-ttu-id="f0f93-132">Lync Server 2013 (如 Lync Server 2010) 将大部分配置信息存储在中央管理存储中, 而不是在 Office 通信服务器 2007 R2 中的情况下, 而不是在 AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="f0f93-132">Lync Server 2013, like Lync Server 2010, stores much of the configuration information in the Central Management store instead of in AD DS as was the case in Office Communications Server 2007 R2.</span></span> <span data-ttu-id="f0f93-133">但是, 以下信息存储在 AD DS 中:</span><span class="sxs-lookup"><span data-stu-id="f0f93-133">However, the following information is stored in AD DS:</span></span>

  - <span data-ttu-id="f0f93-134">**架构扩展**:</span><span class="sxs-lookup"><span data-stu-id="f0f93-134">**Schema extensions**:</span></span>
    
      - <span data-ttu-id="f0f93-135">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="f0f93-135">User object extensions</span></span>
    
      - <span data-ttu-id="f0f93-136">用于维护向后兼容性的 Office 通信服务器 2007 R2 类的扩展</span><span class="sxs-lookup"><span data-stu-id="f0f93-136">Extensions for Office Communications Server 2007 R2 classes to maintain backward compatibility</span></span>

<!-- end list -->

  - <span data-ttu-id="f0f93-137">**数据**(存储在 Lync Server 扩展架构和现有架构类中):</span><span class="sxs-lookup"><span data-stu-id="f0f93-137">**Data** (stored in Lync Server extended schema and in existing schema classes):</span></span>
    
      - <span data-ttu-id="f0f93-138">用户 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="f0f93-138">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
      - <span data-ttu-id="f0f93-139">响应组和会议助理等应用程序的联系人对象</span><span class="sxs-lookup"><span data-stu-id="f0f93-139">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
      - <span data-ttu-id="f0f93-140">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="f0f93-140">A pointer to the Central Management store</span></span>
    
      - <span data-ttu-id="f0f93-141">Kerberos 身份验证帐户 (可选的计算机对象)</span><span class="sxs-lookup"><span data-stu-id="f0f93-141">Kerberos Authentication Account (an optional computer object)</span></span>

<span data-ttu-id="f0f93-142">在 Lync Server 2013 中, 你可以通过向 RTCUniversalServerAdmins 通用组授予设置权限来委派设置和管理, 以便该组的成员可以在本地服务器上安装和激活 Lync Server 2013 (在将服务器添加到拓扑、已发布和已启用)。</span><span class="sxs-lookup"><span data-stu-id="f0f93-142">In Lync Server 2013, you delegate setup and administration by granting setup permissions to the RTCUniversalServerAdmins universal group so that members of that group can install and activate Lync Server 2013 on a local server (after the server has been added to the topology, published, and enabled).</span></span> <span data-ttu-id="f0f93-143">委派用户必须是安装和激活 Lync Server 2013 的计算机上的本地管理员, 但不需要是域管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="f0f93-143">The delegated users must be local administrators on the computer where they are installing and activating Lync Server 2013, but they do not need to be members of the Domain Admins group.</span></span> <span data-ttu-id="f0f93-144">你还可以为指定组织单位 (Ou) 中的对象授予权限, 以便在林准备期间创建的通用组的成员可以访问这些对象, 而不是域管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="f0f93-144">You can also grant permissions for objects in specified organizational units (OUs) so that members of the universal groups created during forest preparation can access those objects without being members of the Domain Admins group.</span></span>

<span data-ttu-id="f0f93-145">对于 Lync Server 2013 的新部署, 全局设置必须存储在配置容器中。</span><span class="sxs-lookup"><span data-stu-id="f0f93-145">For new deployments of Lync Server 2013, global settings must be stored in the Configuration container.</span></span> <span data-ttu-id="f0f93-146">如果你的组织从早期版本升级, 并且在系统容器中仍具有全局设置, 则系统容器仍受支持。</span><span class="sxs-lookup"><span data-stu-id="f0f93-146">If your organization is upgrading from an earlier version and you still have global settings in the System container, the System container is still supported.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0f93-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f93-147">See Also</span></span>


[<span data-ttu-id="f0f93-148">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="f0f93-148">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
[<span data-ttu-id="f0f93-149">Lync Server 2013 使用的 Active Directory 架构扩展、类和属性</span><span class="sxs-lookup"><span data-stu-id="f0f93-149">Active Directory schema extensions, classes, and attributes used by Lync Server 2013</span></span>](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[<span data-ttu-id="f0f93-150">为 Lync Server 2013 准备林</span><span class="sxs-lookup"><span data-stu-id="f0f93-150">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="f0f93-151">为 Lync Server 2013 准备域</span><span class="sxs-lookup"><span data-stu-id="f0f93-151">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

