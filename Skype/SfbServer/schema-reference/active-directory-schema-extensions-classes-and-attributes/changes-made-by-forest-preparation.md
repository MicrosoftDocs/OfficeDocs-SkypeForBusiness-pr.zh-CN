---
title: Skype for Business Server 中的林准备所做的更改
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本节介绍林准备步骤所创建的全局设置和对象以及通用服务组和通用管理组。
ms.openlocfilehash: b304dbb12cb7e05e7bc82bdc56ffc330ce0221c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098648"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="83019-103">Skype for Business Server 中的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="83019-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="83019-104">本节介绍林准备步骤所创建的全局设置和对象以及通用服务组和通用管理组。</span><span class="sxs-lookup"><span data-stu-id="83019-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="83019-105">Active Directory 全局设置和对象</span><span class="sxs-lookup"><span data-stu-id="83019-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="83019-106">如果在配置容器中存储全局设置 (则对于所有新的 Skype for Business Server 部署) ，林准备将使用现有服务容器，并添加 Configuration\Services 对象下的 **RTC 服务** 对象。</span><span class="sxs-lookup"><span data-stu-id="83019-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="83019-107">在 RTC 服务对象下，林准备添加一个 msRTCSIP-GlobalContainer 类型的 **Global Settings** 对象。</span><span class="sxs-lookup"><span data-stu-id="83019-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="83019-108">全局设置对象保留适用于 Skype for Business Server 部署的所有设置。</span><span class="sxs-lookup"><span data-stu-id="83019-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="83019-109">如果在系统容器中存储全局设置，则林准备会使用根域系统容器下的一个 Microsoft 容器，以及系统\Microsoft 对象下的一个 RTC 服务对象。</span><span class="sxs-lookup"><span data-stu-id="83019-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="83019-110">林准备还为从中运行此过程的根域添加一个新的 **msRTCSIP-Domain** 对象。</span><span class="sxs-lookup"><span data-stu-id="83019-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="83019-111">Active Directory 通用服务组和通用管理组</span><span class="sxs-lookup"><span data-stu-id="83019-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="83019-p102">林准备根据所指定的域创建通用组，并为这些组添加访问控制项 (ACE)。此步骤将在指定域的用户容器中创建通用组。</span><span class="sxs-lookup"><span data-stu-id="83019-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="83019-p103">通用组允许管理员访问并管理全局设置和服务。林准备将添加以下类型的通用组：</span><span class="sxs-lookup"><span data-stu-id="83019-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="83019-116">**管理组** 这些组定义 Skype for Business Server 网络的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="83019-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="83019-117">**基础结构组** 这些组提供访问 Skype for Business Server 基础结构的特定区域的权限。</span><span class="sxs-lookup"><span data-stu-id="83019-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="83019-118">它们用作管理组的组件。</span><span class="sxs-lookup"><span data-stu-id="83019-118">They function as components of administrative groups.</span></span> <span data-ttu-id="83019-119">您不应修改这些组或直接向其中添加用户。</span><span class="sxs-lookup"><span data-stu-id="83019-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="83019-120">**服务组** 这些组是访问各种 Skype for Business Server 服务所需的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="83019-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="83019-121">下表介绍的是管理组。</span><span class="sxs-lookup"><span data-stu-id="83019-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="83019-122">**在林准备期间创建的管理组**</span><span class="sxs-lookup"><span data-stu-id="83019-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="83019-123">**管理组**</span><span class="sxs-lookup"><span data-stu-id="83019-123">**Administrative group**</span></span>|<span data-ttu-id="83019-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="83019-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83019-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83019-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="83019-126">允许成员管理服务器和池设置，包括所有服务器角色、全局设置和用户。</span><span class="sxs-lookup"><span data-stu-id="83019-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="83019-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="83019-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="83019-128">允许成员管理用户设置，以及在不同的服务器或池之间移动用户。</span><span class="sxs-lookup"><span data-stu-id="83019-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="83019-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="83019-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="83019-130">允许成员读取服务器、池和用户设置。</span><span class="sxs-lookup"><span data-stu-id="83019-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="83019-131">下表介绍的是基础结构组。</span><span class="sxs-lookup"><span data-stu-id="83019-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="83019-132">**在林准备期间创建的基础结构组**</span><span class="sxs-lookup"><span data-stu-id="83019-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="83019-133">**基础结构组**</span><span class="sxs-lookup"><span data-stu-id="83019-133">**Infrastructure group**</span></span>|<span data-ttu-id="83019-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="83019-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83019-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="83019-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="83019-136">授予对 Skype for Business Server 的全局设置对象的写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="83019-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="83019-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83019-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="83019-138">授予对 Skype for Business Server 的全局设置对象的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="83019-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="83019-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83019-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="83019-140">授予对 Skype for Business Server 用户设置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="83019-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="83019-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="83019-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="83019-142">授予对 Skype for Business Server 设置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="83019-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="83019-143">此组没有对池级别设置的访问权限，只有对单个服务器专用设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="83019-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="83019-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="83019-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="83019-145">授予对 Skype for Business Server 配置的只读访问权限，在安装期间管理员组位于 survivable Branch 设备的本地服务器中。</span><span class="sxs-lookup"><span data-stu-id="83019-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="83019-146">下表介绍的是服务组。</span><span class="sxs-lookup"><span data-stu-id="83019-146">The following table describes the service groups.</span></span>

<span data-ttu-id="83019-147">**林准备期间创建的服务组**</span><span class="sxs-lookup"><span data-stu-id="83019-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="83019-148">**服务组**</span><span class="sxs-lookup"><span data-stu-id="83019-148">**Service group**</span></span>|<span data-ttu-id="83019-149">**说明**</span><span class="sxs-lookup"><span data-stu-id="83019-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83019-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83019-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="83019-151">包括用于运行前端服务器和 Standard Edition Server 的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="83019-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="83019-152">此组允许服务器对 Skype for Business Server 全局设置和 Active Directory 用户对象进行读/写访问。</span><span class="sxs-lookup"><span data-stu-id="83019-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="83019-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83019-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="83019-154">包括用于运行 A/V 会议服务器、Web 服务、中介服务器、存档服务器和监控服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="83019-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="83019-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83019-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="83019-156">包括用于运行 Skype for Business Server 边缘服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="83019-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="83019-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="83019-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="83019-158">包括可以参与 Skype for Business Server 中央管理存储复制的服务器。</span><span class="sxs-lookup"><span data-stu-id="83019-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="83019-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="83019-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="83019-160">授予对 Skype for Business Server 设置的只读访问权限，但允许配置 Survivable Branch Server 和 Survivable Branch Appliance 部署。</span><span class="sxs-lookup"><span data-stu-id="83019-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="83019-161">然后，林准备将服务组和管理组添加到适当的基础结构组，具体如下：</span><span class="sxs-lookup"><span data-stu-id="83019-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="83019-162">将 RTCUniversalServerAdmins 添加到 RTCUniversalGlobalReadOnlyGroup、RTCUniversalGlobalWriteGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 中。</span><span class="sxs-lookup"><span data-stu-id="83019-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="83019-163">RTCUniversalUserAdmins 被添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="83019-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="83019-164">RTCHSUniversalServices、RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 添加为 RTCUniversalGlobalReadOnlyGroup、RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="83019-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="83019-165">林准备还创建了以下基于角色的访问控制 (RBAC) 组：</span><span class="sxs-lookup"><span data-stu-id="83019-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="83019-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-166">CSAdministrator</span></span>

- <span data-ttu-id="83019-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="83019-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="83019-168">CSHelpDesk</span></span>

- <span data-ttu-id="83019-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="83019-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="83019-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-171">CSServerAdministrator</span></span>

- <span data-ttu-id="83019-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-172">CSUserAdministrator</span></span>

- <span data-ttu-id="83019-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="83019-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="83019-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="83019-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="83019-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="83019-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="83019-176">CsResponseGroupManager</span></span>

<span data-ttu-id="83019-177">有关 RBAC 角色以及允许每个角色执行的任务的详细信息，请参阅规划文档中的[Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control)。</span><span class="sxs-lookup"><span data-stu-id="83019-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) in the Planning documentation.</span></span>

<span data-ttu-id="83019-178">林准备同时创建专用和公共 ACE。</span><span class="sxs-lookup"><span data-stu-id="83019-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="83019-179">它在 Skype for Business Server 使用的全局设置容器上创建专用 AES。</span><span class="sxs-lookup"><span data-stu-id="83019-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="83019-180">此容器仅由 Skype for Business Server 使用，位于根域的"配置"容器或"系统"容器中，具体取决于存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="83019-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="83019-181">下表中列出了林准备所创建的公共 ACE。</span><span class="sxs-lookup"><span data-stu-id="83019-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="83019-182">**林准备所创建的公共 ACE**</span><span class="sxs-lookup"><span data-stu-id="83019-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="83019-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="83019-183">**ACE**</span></span>                                                                 | <span data-ttu-id="83019-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="83019-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="83019-185">读取根域系统容器 (继承) **\\**\*</span><span class="sxs-lookup"><span data-stu-id="83019-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="83019-186">X</span><span class="sxs-lookup"><span data-stu-id="83019-186">X</span></span>  <br/>                            |
| <span data-ttu-id="83019-187">读取 Configuration 的 DisplaySpecifiers 容器 (继承) </span><span class="sxs-lookup"><span data-stu-id="83019-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="83019-188">X</span><span class="sxs-lookup"><span data-stu-id="83019-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="83019-189"><strong>\\</strong>\*未继承的 AES 不会授予访问这些容器下的子对象的权限。</span><span class="sxs-lookup"><span data-stu-id="83019-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="83019-190">继承的 AES 授予访问这些容器下的子对象的权限。</span><span class="sxs-lookup"><span data-stu-id="83019-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="83019-191">在配置容器上的配置命名上下文中，林准备将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="83019-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="83019-192">在用户、联系人和 InetOrgPerson 的语言显示说明符（例如 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 adminContextMenu 和 adminPropertyPages 属性下，为“**RTC property**”页添加一个 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** 条目。</span><span class="sxs-lookup"><span data-stu-id="83019-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="83019-193">在 **Extended-Rights** 下添加一个适用于 User 和 Contact 类的 **controlAccessRight** 类型的 **RTCPropertySet** 对象。</span><span class="sxs-lookup"><span data-stu-id="83019-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="83019-194">在 **Extended-Rights** 下添加一个适用于 User、Contact、OU 和 DomainDNS 类的 **controlAccessRight** 类型的 **RTCUserSearchPropertySet** 对象。</span><span class="sxs-lookup"><span data-stu-id="83019-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="83019-195">在每个语言组织单位 (OU) 显示说明符（例如，CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性下添加 **msRTCSIP-PrimaryUserAddress**，并复制默认显示（例如，CN=default-Display, CN=409,CN=DisplaySpecifiers）的 **extraColumns** 属性值。</span><span class="sxs-lookup"><span data-stu-id="83019-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="83019-196">在 User、Contact 和 InetOrgPerson 对象的每个语言显示说明符（例如，英文为 CN=user-Display,CN=409,CN=DisplaySpecifiers）的 **attributeDisplayNames** 属性下，添加 **msRTCSIP-PrimaryUserAddress**、**msRTCSIP-PrimaryHomeServer** 和 **msRTCSIP-UserEnabled** 筛选属性。</span><span class="sxs-lookup"><span data-stu-id="83019-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>