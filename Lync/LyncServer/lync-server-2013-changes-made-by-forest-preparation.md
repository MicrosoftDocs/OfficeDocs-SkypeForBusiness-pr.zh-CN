---
title: Lync Server 2013：林准备所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6954e8a4cd76e103516fd1f2323ef04d820dc056
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="32c22-102">Lync Server 2013 中的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="32c22-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c22-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="32c22-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="32c22-104">本节介绍林准备步骤所创建的全局设置和对象以及通用服务组和通用管理组。</span><span class="sxs-lookup"><span data-stu-id="32c22-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="32c22-105">Active Directory 全局设置和对象</span><span class="sxs-lookup"><span data-stu-id="32c22-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="32c22-106">如果将全局设置存储在配置容器中（所有新的 Lync Server 2013 部署的情况），林准备将使用现有服务容器，并在配置\\服务对象下添加**RTC 服务**对象。</span><span class="sxs-lookup"><span data-stu-id="32c22-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="32c22-107">在 RTC 服务对象下，林准备添加一个 msRTCSIP-GlobalContainer 类型的**Global Settings**对象。</span><span class="sxs-lookup"><span data-stu-id="32c22-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="32c22-108">全局设置对象包含适用于 Lync Server 部署的所有设置。</span><span class="sxs-lookup"><span data-stu-id="32c22-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="32c22-109">如果将全局设置存储在系统容器中，林准备将使用根域系统容器下的 Microsoft 容器和系统\\Microsoft 对象下的 RTC 服务对象。</span><span class="sxs-lookup"><span data-stu-id="32c22-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="32c22-110">林准备还为从中运行此过程的根域添加一个新的 **msRTCSIP-Domain** 对象。</span><span class="sxs-lookup"><span data-stu-id="32c22-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="32c22-111">Active Directory 通用服务组和通用管理组</span><span class="sxs-lookup"><span data-stu-id="32c22-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="32c22-p102">林准备根据所指定的域创建通用组，并为这些组添加访问控制项 (ACE)。此步骤将在指定域的用户容器中创建通用组。</span><span class="sxs-lookup"><span data-stu-id="32c22-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="32c22-p103">通用组允许管理员访问并管理全局设置和服务。林准备将添加以下类型的通用组：</span><span class="sxs-lookup"><span data-stu-id="32c22-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="32c22-116">**管理组**   ：这些组定义 Lync Server 网络的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="32c22-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="32c22-117">**基础结构组**   ：这些组提供访问 Lync Server 基础结构的特定区域的权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="32c22-118">它们用作管理组的组件。</span><span class="sxs-lookup"><span data-stu-id="32c22-118">They function as components of administrative groups.</span></span> <span data-ttu-id="32c22-119">您不应修改这些组或直接向其中添加用户。</span><span class="sxs-lookup"><span data-stu-id="32c22-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="32c22-120">**服务组**   这些组是访问各种 Lync Server 服务所需的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="32c22-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="32c22-121">下表介绍的是管理组。</span><span class="sxs-lookup"><span data-stu-id="32c22-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="32c22-122">在林准备期间创建的管理组</span><span class="sxs-lookup"><span data-stu-id="32c22-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32c22-123">管理组</span><span class="sxs-lookup"><span data-stu-id="32c22-123">Administrative group</span></span></th>
<th><span data-ttu-id="32c22-124">Description</span><span class="sxs-lookup"><span data-stu-id="32c22-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32c22-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="32c22-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="32c22-126">允许成员管理服务器和池设置，包括所有服务器角色、全局设置和用户。</span><span class="sxs-lookup"><span data-stu-id="32c22-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c22-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="32c22-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="32c22-128">允许成员管理用户设置，以及在不同的服务器或池之间移动用户。</span><span class="sxs-lookup"><span data-stu-id="32c22-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32c22-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="32c22-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="32c22-130">允许成员读取服务器、池和用户设置。</span><span class="sxs-lookup"><span data-stu-id="32c22-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32c22-131">下表介绍的是基础结构组。</span><span class="sxs-lookup"><span data-stu-id="32c22-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="32c22-132">在林准备期间创建的基础结构组</span><span class="sxs-lookup"><span data-stu-id="32c22-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32c22-133">基础结构组</span><span class="sxs-lookup"><span data-stu-id="32c22-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="32c22-134">Description</span><span class="sxs-lookup"><span data-stu-id="32c22-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32c22-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="32c22-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="32c22-136">为 Lync Server 授予对全局设置对象的写入权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c22-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="32c22-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="32c22-138">为 Lync Server 授予对全局设置对象的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32c22-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="32c22-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="32c22-140">授予对 Lync Server 用户设置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c22-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="32c22-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="32c22-142">授予对 Lync Server 设置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="32c22-143">此组没有对池级别设置的访问权限，只有对单个服务器专用设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32c22-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="32c22-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="32c22-145">授予对 Lync Server 配置的只读访问权限，并将其放在安装过程中 survivable 分支设备的本地 Administrators 组中。</span><span class="sxs-lookup"><span data-stu-id="32c22-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32c22-146">下表介绍的是服务组。</span><span class="sxs-lookup"><span data-stu-id="32c22-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="32c22-147">林准备期间创建的服务组</span><span class="sxs-lookup"><span data-stu-id="32c22-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32c22-148">服务组</span><span class="sxs-lookup"><span data-stu-id="32c22-148">Service group</span></span></th>
<th><span data-ttu-id="32c22-149">Description</span><span class="sxs-lookup"><span data-stu-id="32c22-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32c22-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="32c22-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="32c22-151">包括用于运行前端服务器和 Standard Edition 服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="32c22-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="32c22-152">此组允许服务器对 Lync Server 全局设置和 Active Directory 用户对象的读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c22-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="32c22-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="32c22-154">包括用于运行 A/V 会议服务器、Web 服务、中介服务器、存档服务器和监视服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="32c22-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32c22-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="32c22-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="32c22-156">包括用于运行 Lync Server 边缘服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="32c22-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c22-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="32c22-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="32c22-158">包括可以参与 Lync Server 中央管理存储复制的服务器。</span><span class="sxs-lookup"><span data-stu-id="32c22-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32c22-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="32c22-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="32c22-160">授予对 Lync Server 设置的只读访问权限，但允许安装 survivable 分支服务器和 survivable 分支设备部署的配置。</span><span class="sxs-lookup"><span data-stu-id="32c22-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32c22-161">然后，林准备将服务组和管理组添加到适当的基础结构组，具体如下：</span><span class="sxs-lookup"><span data-stu-id="32c22-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="32c22-162">将 RTCUniversalServerAdmins 添加到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 中。</span><span class="sxs-lookup"><span data-stu-id="32c22-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="32c22-163">RTCUniversalUserAdmins 被添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="32c22-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="32c22-164">RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="32c22-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="32c22-165">林准备还创建了以下基于角色的访问控制 (RBAC) 组：</span><span class="sxs-lookup"><span data-stu-id="32c22-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="32c22-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-166">CSAdministrator</span></span>

  - <span data-ttu-id="32c22-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="32c22-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="32c22-168">CSHelpDesk</span></span>

  - <span data-ttu-id="32c22-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="32c22-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="32c22-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="32c22-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="32c22-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="32c22-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="32c22-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="32c22-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="32c22-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="32c22-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="32c22-176">CsResponseGroupManager</span></span>

<span data-ttu-id="32c22-177">有关 RBAC 角色和每个角色允许执行的任务的详细信息，请参阅规划文档中的在[Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="32c22-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="32c22-178">林准备同时创建专用和公共 ACE。</span><span class="sxs-lookup"><span data-stu-id="32c22-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="32c22-179">它在 Lync Server 使用的全局设置容器上创建专用 Ace。</span><span class="sxs-lookup"><span data-stu-id="32c22-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="32c22-180">此容器仅由 Lync Server 使用，并位于配置容器或根域中的系统容器中，具体取决于存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="32c22-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="32c22-181">下表中列出了林准备所创建的公共 ACE。</span><span class="sxs-lookup"><span data-stu-id="32c22-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="32c22-182">林准备所创建的公共 ACE</span><span class="sxs-lookup"><span data-stu-id="32c22-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32c22-183">ACE</span><span class="sxs-lookup"><span data-stu-id="32c22-183">ACE</span></span></th>
<th><span data-ttu-id="32c22-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="32c22-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32c22-185">读取根域系统容器（非继承）<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="32c22-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="32c22-186">X</span><span class="sxs-lookup"><span data-stu-id="32c22-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32c22-187">读取配置的 DisplaySpecifiers 容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="32c22-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="32c22-188">X</span><span class="sxs-lookup"><span data-stu-id="32c22-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="32c22-189"><STRONG>\*</STRONG>未继承的 Ace 不会向这些容器下的子对象授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="32c22-190">继承的 Ace 授予对这些容器下的子对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="32c22-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="32c22-191">在配置容器上的配置命名上下文中，林准备将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="32c22-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="32c22-192">在用户、联系人和 InetOrgPerson 的语言显示说明符（例如 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 adminContextMenu 和 adminPropertyPages 属性下，为“**RTC property**”页添加一个 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 条目。</span><span class="sxs-lookup"><span data-stu-id="32c22-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="32c22-193">在 **Extended-Rights** 下添加一个适用于 User 和 Contact 类的 **controlAccessRight** 类型的 **RTCPropertySet** 对象。</span><span class="sxs-lookup"><span data-stu-id="32c22-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="32c22-194">在 **Extended-Rights** 下添加一个适用于 User、Contact、OU 和 DomainDNS 类的 **controlAccessRight** 类型的 **RTCUserSearchPropertySet** 对象。</span><span class="sxs-lookup"><span data-stu-id="32c22-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="32c22-195">在每个语言组织单位 (OU) 显示说明符（例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性下添加 **msRTCSIP-PrimaryUserAddress**，并复制默认显示（例如，CN=default-Display, CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性值。</span><span class="sxs-lookup"><span data-stu-id="32c22-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="32c22-196">在 User、Contact 和 InetOrgPerson 对象的每个语言显示说明符（例如，英文为 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 **attributeDisplayNames** 属性下，添加 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 和 **msRTCSIP-UserEnabled** 筛选属性。</span><span class="sxs-lookup"><span data-stu-id="32c22-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

