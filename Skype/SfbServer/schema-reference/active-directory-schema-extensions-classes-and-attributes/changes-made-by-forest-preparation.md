---
title: 由林准备在 Skype 业务服务器所做的更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本部分介绍的全局设置和对象，以及通用的服务和管理组创建的目录林的准备步骤。
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="a8206-103">由林准备在 Skype 业务服务器所做的更改</span><span class="sxs-lookup"><span data-stu-id="a8206-103">Changes made by forest preparation in Skype for Business Server</span></span>
 
<span data-ttu-id="a8206-104">本部分介绍的全局设置和对象，以及通用的服务和管理组创建的目录林的准备步骤。</span><span class="sxs-lookup"><span data-stu-id="a8206-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>
  
## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="a8206-105">Active Directory 全局设置和对象</span><span class="sxs-lookup"><span data-stu-id="a8206-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="a8206-106">如果存储的全局设置配置容器中 （如所有新业务服务器部署 Skype 的是这种情况）、 林准备使用现有的服务容器，添加配置下的**RTC 服务**对象对象。</span><span class="sxs-lookup"><span data-stu-id="a8206-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="a8206-107">在 RTC 服务对象中，林准备过程添加类型 msRTCSIP GlobalContainer**全局设置**对象。</span><span class="sxs-lookup"><span data-stu-id="a8206-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="a8206-108">全局设置对象包含应用于业务服务器部署 Skype 的所有设置。</span><span class="sxs-lookup"><span data-stu-id="a8206-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="a8206-109">如果系统容器中存储的全局设置，林准备过程将使用根域系统容器下的 Microsoft 容器和 RTC 服务对象的 System\Microsoft 对象下。</span><span class="sxs-lookup"><span data-stu-id="a8206-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>
  
<span data-ttu-id="a8206-110">林准备过程还将添加新的**msRTCSIP 域**对象运行该过程时的根域。</span><span class="sxs-lookup"><span data-stu-id="a8206-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>
  
## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="a8206-111">活动目录的通用服务和管理组</span><span class="sxs-lookup"><span data-stu-id="a8206-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="a8206-112">林准备过程创建基于您指定的域的通用组，并将这些组的访问控制项 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="a8206-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="a8206-113">此步骤在您指定的域的用户容器中创建通用组。</span><span class="sxs-lookup"><span data-stu-id="a8206-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span> 
  
<span data-ttu-id="a8206-114">通用组，管理员可以访问和管理全局设置和服务。</span><span class="sxs-lookup"><span data-stu-id="a8206-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="a8206-115">林准备过程将添加下列类型的通用组中：</span><span class="sxs-lookup"><span data-stu-id="a8206-115">Forest preparation adds the following types of universal groups:</span></span>
  
- <span data-ttu-id="a8206-116">**管理组**这些组定义为 Skype 业务服务器网络管理员角色。</span><span class="sxs-lookup"><span data-stu-id="a8206-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>
    
- <span data-ttu-id="a8206-117">**基础结构部门**这些组提供了特定区域的 Skype 业务服务器基础结构的访问权。</span><span class="sxs-lookup"><span data-stu-id="a8206-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="a8206-118">它们的功能组件的管理组。</span><span class="sxs-lookup"><span data-stu-id="a8206-118">They function as components of administrative groups.</span></span> <span data-ttu-id="a8206-119">您不应修改这些组或直接向其添加用户。</span><span class="sxs-lookup"><span data-stu-id="a8206-119">You should not modify these groups or add users directly to them.</span></span>
    
- <span data-ttu-id="a8206-120">**服务组**这些组是访问各种 Skype 业务服务器服务所需的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="a8206-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>
    
<span data-ttu-id="a8206-121">下表描述了管理组。</span><span class="sxs-lookup"><span data-stu-id="a8206-121">The following table describes the administrative groups.</span></span>
  
<span data-ttu-id="a8206-122">**林准备过程中创建的管理组**</span><span class="sxs-lookup"><span data-stu-id="a8206-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="a8206-123">**管理组**</span><span class="sxs-lookup"><span data-stu-id="a8206-123">**Administrative group**</span></span>|<span data-ttu-id="a8206-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="a8206-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8206-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a8206-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="a8206-126">允许管理服务器和池设置，包括所有的服务器角色、 全局设置，以及用户成员。</span><span class="sxs-lookup"><span data-stu-id="a8206-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="a8206-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a8206-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="a8206-128">允许管理用户设置并将用户从一个服务器或池移到另一个成员。</span><span class="sxs-lookup"><span data-stu-id="a8206-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="a8206-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="a8206-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="a8206-130">允许读取服务器、 池和用户设置的成员。</span><span class="sxs-lookup"><span data-stu-id="a8206-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |
   
<span data-ttu-id="a8206-131">下表描述基础结构部门。</span><span class="sxs-lookup"><span data-stu-id="a8206-131">The following table describes the infrastructure groups.</span></span>
  
<span data-ttu-id="a8206-132">**林准备过程中创建的基础结构部门**</span><span class="sxs-lookup"><span data-stu-id="a8206-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="a8206-133">**基础结构小组**</span><span class="sxs-lookup"><span data-stu-id="a8206-133">**Infrastructure group**</span></span>|<span data-ttu-id="a8206-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="a8206-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8206-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="a8206-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="a8206-136">授予对 Skype 业务服务器的全局设置对象的写访问权限。</span><span class="sxs-lookup"><span data-stu-id="a8206-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="a8206-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a8206-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="a8206-138">为业务服务器的 Skype 授予全局设置对象的只读访问。</span><span class="sxs-lookup"><span data-stu-id="a8206-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="a8206-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a8206-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="a8206-140">企业服务器用户设置的只读访问权限授予 Skype。</span><span class="sxs-lookup"><span data-stu-id="a8206-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="a8206-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a8206-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="a8206-142">业务服务器设置为 Skype 授予只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="a8206-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="a8206-143">此组没有访问池级设置，仅对特定于单个服务器的设置。</span><span class="sxs-lookup"><span data-stu-id="a8206-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="a8206-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="a8206-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="a8206-145">只读访问权限授予 Skype 业务服务器配置和安装过程都放在本地管理员组的高存活力的分支装置。</span><span class="sxs-lookup"><span data-stu-id="a8206-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |
   
<span data-ttu-id="a8206-146">下表描述了服务组。</span><span class="sxs-lookup"><span data-stu-id="a8206-146">The following table describes the service groups.</span></span>
  
<span data-ttu-id="a8206-147">**林准备过程中创建的服务组**</span><span class="sxs-lookup"><span data-stu-id="a8206-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="a8206-148">**服务组**</span><span class="sxs-lookup"><span data-stu-id="a8206-148">**Service group**</span></span>|<span data-ttu-id="a8206-149">**说明**</span><span class="sxs-lookup"><span data-stu-id="a8206-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8206-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a8206-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="a8206-151">包括用于运行前端服务器，标准版服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="a8206-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="a8206-152">此组允许业务服务器全局设置以及 Active Directory 用户对象对 Skype 的服务器读/写访问。</span><span class="sxs-lookup"><span data-stu-id="a8206-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="a8206-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a8206-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="a8206-154">包含服务帐户来运行 A / V 会议服务器、 Web 服务、 中介服务器、 存档的服务器和监视服务器。</span><span class="sxs-lookup"><span data-stu-id="a8206-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="a8206-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a8206-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="a8206-156">包含用于为业务服务器边缘服务器运行 Skype 的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="a8206-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="a8206-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="a8206-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="a8206-158">包括 Skype 业务服务器集中管理存储复制的服务器可以参与。</span><span class="sxs-lookup"><span data-stu-id="a8206-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="a8206-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a8206-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="a8206-160">只读访问权限授予 Skype 业务服务器设置，但允许高存活力的分支服务器和高存活力的分支装置部署的安装配置。</span><span class="sxs-lookup"><span data-stu-id="a8206-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |
   
<span data-ttu-id="a8206-161">然后林准备过程，如下所示添加到适当的基础结构组的服务和管理组：</span><span class="sxs-lookup"><span data-stu-id="a8206-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>
  
- <span data-ttu-id="a8206-162">RTCUniversalServerAdmins 被添加到 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalGlobalWriteGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup。</span><span class="sxs-lookup"><span data-stu-id="a8206-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>
    
- <span data-ttu-id="a8206-163">RTCUniversalUserAdmins 将添加为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="a8206-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>
    
- <span data-ttu-id="a8206-164">RTCHSUniversalServices、 RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 作为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="a8206-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>
    
<span data-ttu-id="a8206-165">林准备过程还将创建以下基于角色的访问控制 (RBAC) 组：</span><span class="sxs-lookup"><span data-stu-id="a8206-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>
  
- <span data-ttu-id="a8206-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-166">CSAdministrator</span></span>
    
- <span data-ttu-id="a8206-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-167">CSArchivingAdministrator</span></span>
    
- <span data-ttu-id="a8206-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="a8206-168">CSHelpDesk</span></span>
    
- <span data-ttu-id="a8206-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-169">CSLocationAdministrator</span></span>
    
- <span data-ttu-id="a8206-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-170">CSResponseGroupAdministrator</span></span>
    
- <span data-ttu-id="a8206-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-171">CSServerAdministrator</span></span>
    
- <span data-ttu-id="a8206-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-172">CSUserAdministrator</span></span>
    
- <span data-ttu-id="a8206-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-173">CSViewOnlyAdministrator</span></span>
    
- <span data-ttu-id="a8206-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a8206-174">CSVoiceAdministrator</span></span>
    
- <span data-ttu-id="a8206-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="a8206-175">CsPersistentChatAdministator</span></span>
    
- <span data-ttu-id="a8206-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="a8206-176">CsResponseGroupManager</span></span>
    
<span data-ttu-id="a8206-177">RBAC 角色和允许为每个任务的详细信息，请参阅规划文档中[基于角色的访问控制](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a8206-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>
  
<span data-ttu-id="a8206-178">林准备过程创建私钥和公钥的 Ace。</span><span class="sxs-lookup"><span data-stu-id="a8206-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="a8206-179">它在全局设置容器用于通过 Skype 业务服务器上创建专用的 Ace。</span><span class="sxs-lookup"><span data-stu-id="a8206-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="a8206-180">该容器用于业务服务器只能通过 Skype 和位于配置容器或根域，这取决于您在那里存储全局设置中的系统容器中。</span><span class="sxs-lookup"><span data-stu-id="a8206-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="a8206-181">下表中列出了公共 Ace 由林准备过程。</span><span class="sxs-lookup"><span data-stu-id="a8206-181">The public ACEs created by forest preparation are listed in the following table.</span></span>
  
<span data-ttu-id="a8206-182">**林准备过程所创建的公用 Ace**</span><span class="sxs-lookup"><span data-stu-id="a8206-182">**Public ACEs created by Forest Preparation**</span></span>

|<span data-ttu-id="a8206-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="a8206-183">**ACE**</span></span>|<span data-ttu-id="a8206-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="a8206-184">**RTCUniversalGlobalReadOnlyGroup**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8206-185">根域系统容器 （不继承所得） 中读取**\***</span><span class="sxs-lookup"><span data-stu-id="a8206-185">Read root domain System Container (not inherited) **\***</span></span> <br/> |<span data-ttu-id="a8206-186">X</span><span class="sxs-lookup"><span data-stu-id="a8206-186">X</span></span>  <br/> |
|<span data-ttu-id="a8206-187">读取配置 DisplaySpecifiers 容器 （不继承）</span><span class="sxs-lookup"><span data-stu-id="a8206-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> |<span data-ttu-id="a8206-188">X</span><span class="sxs-lookup"><span data-stu-id="a8206-188">X</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="a8206-189">**\***不能继承的 Ace 不授予在这些容器的子对象的访问。</span><span class="sxs-lookup"><span data-stu-id="a8206-189">**\***ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="a8206-190">继承的 Ace 授予在这些容器的子对象的访问。</span><span class="sxs-lookup"><span data-stu-id="a8206-190">ACEs that are inherited grant access to child objects under these containers.</span></span> 
  
<span data-ttu-id="a8206-191">在配置容器中配置命名上下文，林准备过程执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="a8206-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>
  
- <span data-ttu-id="a8206-192">添加在 adminContextMenu 下的**RTC 属性**页面项**{AB255F23-2DBD-4bb6-891D-38754AC280EF}**和语言的 adminPropertyPages 属性显示为用户、 联系人和 InetOrgPersons 说明符 (例如，CN =用户显示，CN = 409，CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="a8206-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>
    
- <span data-ttu-id="a8206-193">添加下**扩展权限**应用于用户和联系人类类型**controlAccessRight**的一个**RTCPropertySet**对象。</span><span class="sxs-lookup"><span data-stu-id="a8206-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>
    
- <span data-ttu-id="a8206-194">添加下**扩展权限**应用于用户、 联系人、 OU 和 DomainDNS 类的类型**controlAccessRight**的一个**RTCUserSearchPropertySet**对象。</span><span class="sxs-lookup"><span data-stu-id="a8206-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>
    
- <span data-ttu-id="a8206-195">添加在每个语言的组织单位 (OU) 显示说明符的**extraColumns**属性下的**msRTCSIP PrimaryUserAddress** (例如，CN = organizationalUnit 显示，CN = 409，CN = DisplaySpecifiers)，并将复制的值默认显示的**extraColumns**属性 (例如，CN = 默认显示，CN = 409，CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="a8206-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>
    
- <span data-ttu-id="a8206-196">添加**msRTCSIP PrimaryUserAddress**， **msRTCSIP PrimaryHomeServer**， **msRTCSIP UserEnabled**筛选在每种语言的**attributeDisplayNames**属性下的属性显示为用户、 联系人、 说明符和 InetOrgPerson 对象 (例如，在英语： CN = 用户显示，CN = 409，CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="a8206-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>
    

