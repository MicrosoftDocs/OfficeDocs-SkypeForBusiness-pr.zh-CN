---
title: Skype 中为 Business Server 的林准备所做的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: 本节介绍的全局设置和对象以及通用服务组和管理组林准备步骤创建的。
ms.openlocfilehash: de5171887d84e3d3d5d835d6bb59af24fcb5820d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907125"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a><span data-ttu-id="0fe86-103">Skype 中为 Business Server 的林准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="0fe86-103">Changes made by forest preparation in Skype for Business Server</span></span>

<span data-ttu-id="0fe86-104">本节介绍的全局设置和对象以及通用服务组和管理组林准备步骤创建的。</span><span class="sxs-lookup"><span data-stu-id="0fe86-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="0fe86-105">Active Directory 全局设置和对象</span><span class="sxs-lookup"><span data-stu-id="0fe86-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="0fe86-106">如果 （如 Business Server 部署的所有新 Skype 的是这种情况） 在配置容器中存储全局设置，林准备使用现有的服务容器，并将添加下配置 \ **RTC 服务**对象对象。</span><span class="sxs-lookup"><span data-stu-id="0fe86-106">If you store global settings in the Configuration container (as is the case for all new Skype for Business Server deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\Services object.</span></span> <span data-ttu-id="0fe86-107">在 RTC 服务对象下，林准备添加一个 Msrtcsip-globalcontainer 类型的**全局设置**对象。</span><span class="sxs-lookup"><span data-stu-id="0fe86-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="0fe86-108">全局设置对象容纳适用于业务服务器部署 Skype 的所有设置。</span><span class="sxs-lookup"><span data-stu-id="0fe86-108">The global settings object holds all the settings that apply to the Skype for Business Server deployment.</span></span> <span data-ttu-id="0fe86-109">如果在系统容器中存储全局设置，林准备使用根域系统容器下的 Microsoft 容器和 System\Microsoft 对象下的 RTC 服务对象。</span><span class="sxs-lookup"><span data-stu-id="0fe86-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\Microsoft object.</span></span>

<span data-ttu-id="0fe86-110">林准备还添加新的**Msrtcsip-domain**对象在其中运行此过程的根域。</span><span class="sxs-lookup"><span data-stu-id="0fe86-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="0fe86-111">Active Directory 通用服务和通用管理组</span><span class="sxs-lookup"><span data-stu-id="0fe86-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="0fe86-112">林准备创建基于指定的域的通用组，并将这些组的访问控制项 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="0fe86-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="0fe86-113">此步骤所指定的域的用户容器中创建通用组。</span><span class="sxs-lookup"><span data-stu-id="0fe86-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="0fe86-114">通用组允许管理员访问和管理全局设置和服务。</span><span class="sxs-lookup"><span data-stu-id="0fe86-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="0fe86-115">林准备添加以下类型的通用组：</span><span class="sxs-lookup"><span data-stu-id="0fe86-115">Forest preparation adds the following types of universal groups:</span></span>

- <span data-ttu-id="0fe86-116">**管理组**这些组为 Business Server 网络 Skype 定义管理员角色。</span><span class="sxs-lookup"><span data-stu-id="0fe86-116">**Administrative groups** These groups define administrator roles for a Skype for Business Server network.</span></span>

- <span data-ttu-id="0fe86-117">**基础结构组**这些组将提供的特定区域的企业服务器基础结构 Skype 的访问权。</span><span class="sxs-lookup"><span data-stu-id="0fe86-117">**Infrastructure groups** These groups provide permission to access specific areas of the Skype for Business Server infrastructure.</span></span> <span data-ttu-id="0fe86-118">他们将作为管理组的组件。</span><span class="sxs-lookup"><span data-stu-id="0fe86-118">They function as components of administrative groups.</span></span> <span data-ttu-id="0fe86-119">不应修改这些组，或直接向其中添加用户。</span><span class="sxs-lookup"><span data-stu-id="0fe86-119">You should not modify these groups or add users directly to them.</span></span>

- <span data-ttu-id="0fe86-120">**服务组**这些组是访问业务 Server 服务的各种 Skype 所需的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="0fe86-120">**Service groups** These groups are service accounts that are required to access various Skype for Business Server services.</span></span>

<span data-ttu-id="0fe86-121">下表介绍的是管理组。</span><span class="sxs-lookup"><span data-stu-id="0fe86-121">The following table describes the administrative groups.</span></span>

<span data-ttu-id="0fe86-122">**林准备期间创建的管理组**</span><span class="sxs-lookup"><span data-stu-id="0fe86-122">**Administrative Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0fe86-123">**管理组**</span><span class="sxs-lookup"><span data-stu-id="0fe86-123">**Administrative group**</span></span>|<span data-ttu-id="0fe86-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="0fe86-124">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0fe86-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0fe86-125">RTCUniversalServerAdmins</span></span>  <br/> |<span data-ttu-id="0fe86-126">允许成员管理服务器和池设置，包括所有服务器角色、 全局设置和用户。</span><span class="sxs-lookup"><span data-stu-id="0fe86-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span>  <br/> |
|<span data-ttu-id="0fe86-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0fe86-127">RTCUniversalUserAdmins</span></span>  <br/> |<span data-ttu-id="0fe86-128">允许成员管理用户设置并将用户从一个服务器或池移到另一个。</span><span class="sxs-lookup"><span data-stu-id="0fe86-128">Allows members to manage user settings and move users from one server or pool to another.</span></span>  <br/> |
|<span data-ttu-id="0fe86-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="0fe86-129">RTCUniversalReadOnlyAdmins</span></span>  <br/> |<span data-ttu-id="0fe86-130">允许成员读取服务器、 池和用户设置。</span><span class="sxs-lookup"><span data-stu-id="0fe86-130">Allows members to read server, pool, and user settings.</span></span>  <br/> |

<span data-ttu-id="0fe86-131">下表介绍的是基础结构组。</span><span class="sxs-lookup"><span data-stu-id="0fe86-131">The following table describes the infrastructure groups.</span></span>

<span data-ttu-id="0fe86-132">**林准备期间创建的基础结构组**</span><span class="sxs-lookup"><span data-stu-id="0fe86-132">**Infrastructure Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0fe86-133">**基础结构组**</span><span class="sxs-lookup"><span data-stu-id="0fe86-133">**Infrastructure group**</span></span>|<span data-ttu-id="0fe86-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="0fe86-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0fe86-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="0fe86-135">RTCUniversalGlobalWriteGroup</span></span>  <br/> |<span data-ttu-id="0fe86-136">授予对业务服务器 Skype 的全局设置对象的写访问权限。</span><span class="sxs-lookup"><span data-stu-id="0fe86-136">Grants write access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="0fe86-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="0fe86-137">RTCUniversalGlobalReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0fe86-138">授予对 Skype 的全局设置对象的只读访问权限的业务服务器。</span><span class="sxs-lookup"><span data-stu-id="0fe86-138">Grants read-only access to global setting objects for Skype for Business Server.</span></span>  <br/> |
|<span data-ttu-id="0fe86-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="0fe86-139">RTCUniversalUserReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0fe86-140">授予对 Skype 的只读访问权限的企业服务器用户设置。</span><span class="sxs-lookup"><span data-stu-id="0fe86-140">Grants read-only access to Skype for Business Server user settings.</span></span>  <br/> |
|<span data-ttu-id="0fe86-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="0fe86-141">RTCUniversalServerReadOnlyGroup</span></span>  <br/> |<span data-ttu-id="0fe86-142">授予对 Skype 的只读访问权限的业务服务器设置。</span><span class="sxs-lookup"><span data-stu-id="0fe86-142">Grants read-only access to Skype for Business Server settings.</span></span> <span data-ttu-id="0fe86-143">此组没有对池级别设置，仅对特定于单个服务器设置的访问。</span><span class="sxs-lookup"><span data-stu-id="0fe86-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span>  <br/> |
|<span data-ttu-id="0fe86-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="0fe86-144">RTCUniversalSBATechnicians</span></span>  <br/> |<span data-ttu-id="0fe86-145">授予对 Skype 的只读访问权限的业务服务器配置和安装过程中被放在 survivable branch appliance 的 Local Administrators 组中。</span><span class="sxs-lookup"><span data-stu-id="0fe86-145">Grants read-only access to Skype for Business Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span>  <br/> |

<span data-ttu-id="0fe86-146">下表介绍的是服务组。</span><span class="sxs-lookup"><span data-stu-id="0fe86-146">The following table describes the service groups.</span></span>

<span data-ttu-id="0fe86-147">**林准备期间创建的服务组**</span><span class="sxs-lookup"><span data-stu-id="0fe86-147">**Service Groups Created During Forest Preparation**</span></span>

|<span data-ttu-id="0fe86-148">**服务组**</span><span class="sxs-lookup"><span data-stu-id="0fe86-148">**Service group**</span></span>|<span data-ttu-id="0fe86-149">**说明**</span><span class="sxs-lookup"><span data-stu-id="0fe86-149">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0fe86-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0fe86-150">RTCHSUniversalServices</span></span>  <br/> |<span data-ttu-id="0fe86-151">包括用于运行前端服务器和 Standard Edition server 的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="0fe86-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="0fe86-152">此组允许 Skype 服务器读/写访问业务 Server 全局设置和 Active Directory 用户对象。</span><span class="sxs-lookup"><span data-stu-id="0fe86-152">This group allows servers read/write access to Skype for Business Server global settings and Active Directory user objects.</span></span>  <br/> |
|<span data-ttu-id="0fe86-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0fe86-153">RTCComponentUniversalServices</span></span>  <br/> |<span data-ttu-id="0fe86-154">包括服务帐户用于运行 A / V 会议服务器、 Web 服务、 中介服务器、 存档服务器和监控服务器。</span><span class="sxs-lookup"><span data-stu-id="0fe86-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span>  <br/> |
|<span data-ttu-id="0fe86-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0fe86-155">RTCProxyUniversalServices</span></span>  <br/> |<span data-ttu-id="0fe86-156">包括用于运行 Skype 业务 Server 边缘服务器的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="0fe86-156">Includes service accounts used to run Skype for Business Server Edge Servers.</span></span>  <br/> |
|<span data-ttu-id="0fe86-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="0fe86-157">RTCUniversalConfigReplicator</span></span>  <br/> |<span data-ttu-id="0fe86-158">业务 Server 中央管理存储复制 Skype 包括可参与的服务器。</span><span class="sxs-lookup"><span data-stu-id="0fe86-158">Includes servers that can participate in Skype for Business Server Central Management store replication.</span></span>  <br/> |
|<span data-ttu-id="0fe86-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="0fe86-159">RTCSBAUniversalServices</span></span>  <br/> |<span data-ttu-id="0fe86-160">授予对 Skype 的只读访问权限的业务服务器设置，但允许配置 survivable branch server 和 survivable branch appliance 部署的安装。</span><span class="sxs-lookup"><span data-stu-id="0fe86-160">Grants read-only access to Skype for Business Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span>  <br/> |

<span data-ttu-id="0fe86-161">然后，林准备，如下所示将服务和管理组添加到适当的基础结构组：</span><span class="sxs-lookup"><span data-stu-id="0fe86-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

- <span data-ttu-id="0fe86-162">RTCUniversalServerAdmins 添加到 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalGlobalWriteGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 中。</span><span class="sxs-lookup"><span data-stu-id="0fe86-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="0fe86-163">RTCUniversalUserAdmins 被添加为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="0fe86-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

- <span data-ttu-id="0fe86-164">RTCHSUniversalServices、 RTCComponentUniversalServices 和 RTCUniversalReadOnlyAdmins 添加为 RTCUniversalGlobalReadOnlyGroup、 RTCUniversalServerReadOnlyGroup 和 RTCUniversalUserReadOnlyGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="0fe86-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="0fe86-165">林准备还创建以下基于角色的访问控制 (RBAC) 组：</span><span class="sxs-lookup"><span data-stu-id="0fe86-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

- <span data-ttu-id="0fe86-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-166">CSAdministrator</span></span>

- <span data-ttu-id="0fe86-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-167">CSArchivingAdministrator</span></span>

- <span data-ttu-id="0fe86-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="0fe86-168">CSHelpDesk</span></span>

- <span data-ttu-id="0fe86-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-169">CSLocationAdministrator</span></span>

- <span data-ttu-id="0fe86-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-170">CSResponseGroupAdministrator</span></span>

- <span data-ttu-id="0fe86-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-171">CSServerAdministrator</span></span>

- <span data-ttu-id="0fe86-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-172">CSUserAdministrator</span></span>

- <span data-ttu-id="0fe86-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-173">CSViewOnlyAdministrator</span></span>

- <span data-ttu-id="0fe86-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0fe86-174">CSVoiceAdministrator</span></span>

- <span data-ttu-id="0fe86-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="0fe86-175">CsPersistentChatAdministator</span></span>

- <span data-ttu-id="0fe86-176">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="0fe86-176">CsResponseGroupManager</span></span>

<span data-ttu-id="0fe86-177">有关 RBAC 角色以及允许每个任务的详细信息，请参阅规划文档中的[基于角色的访问控制](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0fe86-177">For details about RBAC roles and the tasks allowed for each, see [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="0fe86-178">林准备创建专用和公共 Ace。</span><span class="sxs-lookup"><span data-stu-id="0fe86-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="0fe86-179">它在 for Business Server 使用的 Skype 的全局设置容器创建专用 Ace。</span><span class="sxs-lookup"><span data-stu-id="0fe86-179">It creates private ACEs on the global settings container used by Skype for Business Server.</span></span> <span data-ttu-id="0fe86-180">此容器只能由 Skype 用于业务服务器，并位于在配置容器或根域，具体取决于您在其中存储全局设置中的系统容器中。</span><span class="sxs-lookup"><span data-stu-id="0fe86-180">This container is used only by Skype for Business Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="0fe86-181">下表列出了林准备所创建的公共 Ace。</span><span class="sxs-lookup"><span data-stu-id="0fe86-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

<span data-ttu-id="0fe86-182">**林准备创建的公共 Ace**</span><span class="sxs-lookup"><span data-stu-id="0fe86-182">**Public ACEs created by Forest Preparation**</span></span>


| <span data-ttu-id="0fe86-183">**ACE**</span><span class="sxs-lookup"><span data-stu-id="0fe86-183">**ACE**</span></span>                                                                 | <span data-ttu-id="0fe86-184">**RTCUniversalGlobalReadOnlyGroup**</span><span class="sxs-lookup"><span data-stu-id="0fe86-184">**RTCUniversalGlobalReadOnlyGroup**</span></span> |
|:------------------------------------------------------------------------|:------------------------------------|
| <span data-ttu-id="0fe86-185">读取根域系统容器 （非继承）**\\**\*</span><span class="sxs-lookup"><span data-stu-id="0fe86-185">Read root domain System Container (not inherited) **\\**\*</span></span> <br/>        | <span data-ttu-id="0fe86-186">X</span><span class="sxs-lookup"><span data-stu-id="0fe86-186">X</span></span>  <br/>                            |
| <span data-ttu-id="0fe86-187">读取配置的 DisplaySpecifiers 容器 （非继承）</span><span class="sxs-lookup"><span data-stu-id="0fe86-187">Read Configuration's DisplaySpecifiers container (not inherited)</span></span>  <br/> | <span data-ttu-id="0fe86-188">X</span><span class="sxs-lookup"><span data-stu-id="0fe86-188">X</span></span>  <br/>                            |

> [!NOTE]
> <span data-ttu-id="0fe86-189"><strong>\\</strong>\* 不继承的 Ace 不会授予对这些容器下的子对象的访问。</span><span class="sxs-lookup"><span data-stu-id="0fe86-189"><strong>\\</strong>\*ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="0fe86-190">继承的 Ace 将授予对这些容器下的子对象的访问。</span><span class="sxs-lookup"><span data-stu-id="0fe86-190">ACEs that are inherited grant access to child objects under these containers.</span></span>

<span data-ttu-id="0fe86-191">在配置容器下配置命名上下文中，林准备将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0fe86-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

- <span data-ttu-id="0fe86-192">添加条目 **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** **RTC 属性**页下 adminContextMenu 和 adminPropertyPages 属性的语言显示说明符用户、 联系人和 Inetorgperson (例如，CN =User-display，CN = 409，CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="0fe86-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="0fe86-193">添加在适用于 User 和 Contact 类的**扩展权限**下，键入**controlAccessRight**的**RTCPropertySet**对象。</span><span class="sxs-lookup"><span data-stu-id="0fe86-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

- <span data-ttu-id="0fe86-194">添加在适用于用户、 联系人、 OU 和 DomainDNS 类的**扩展权限**下，键入**controlAccessRight**的**RTCUserSearchPropertySet**对象。</span><span class="sxs-lookup"><span data-stu-id="0fe86-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

- <span data-ttu-id="0fe86-195">添加的每个语言组织单位 (OU) 显示说明符的**extraColumns**属性下**Msrtcsip-primaryuseraddress** (例如，CN = Organizationalunit-display，CN = 409，CN = DisplaySpecifiers)，并将复制的值默认显示的**extraColumns**属性 (例如，CN = Default-display，CN = 409，CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="0fe86-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

- <span data-ttu-id="0fe86-196">添加**Msrtcsip-primaryuseraddress**、 **Msrtcsip-primaryhomeserver**和**Msrtcsip-userenabled**筛选属性的每种语言的**attributeDisplayNames**属性下显示用户、 联系人、 说明符和 InetOrgPerson 对象 (例如，英文： CN = User-display，CN = 409，CN = DisplaySpecifiers)。</span><span class="sxs-lookup"><span data-stu-id="0fe86-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>


