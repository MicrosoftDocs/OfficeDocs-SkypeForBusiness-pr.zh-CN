---
title: Lync Server 2013： Lync Server 的 Active Directory 域服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a4e548f68f68a65ac4ecfb2e4ddc532b5f337c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529709"
---
# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="5463b-102">Lync Server 2013 的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="5463b-102">Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5463b-103">_**上次修改的主题：** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="5463b-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="5463b-104">Active Directory 域服务充当 Windows Server 2003、Windows Server 2008、Windows Server 2012 和 Windows Server 2012 R2 网络的目录服务。</span><span class="sxs-lookup"><span data-stu-id="5463b-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="5463b-105">Active Directory 域服务还充当 Microsoft Lync Server 2013 安全基础结构的构建基础。</span><span class="sxs-lookup"><span data-stu-id="5463b-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="5463b-106">本节的目的是说明 Lync Server 2013 如何使用 Active Directory 域服务为 IM、Web 会议、媒体和语音创建可信环境。</span><span class="sxs-lookup"><span data-stu-id="5463b-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="5463b-107">若要详细了解 Active Directory 域服务的 Lync Server 扩展和为 Active Directory 域服务准备环境的详细信息，请参阅部署文档中的 [为 Lync server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="5463b-108">有关 Active Directory 域服务在 Windows Server 网络中的角色的详细信息，请参阅正在使用的操作系统版本相应的文档。</span><span class="sxs-lookup"><span data-stu-id="5463b-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="5463b-109">Lync Server 2013 使用 Active Directory 域服务来存储：</span><span class="sxs-lookup"><span data-stu-id="5463b-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="5463b-110">在林中运行 Lync Server 2013 的所有服务器都需要的全局设置。</span><span class="sxs-lookup"><span data-stu-id="5463b-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="5463b-111">标识林中所有运行 Lync Server 2013 的服务器的角色的服务信息。</span><span class="sxs-lookup"><span data-stu-id="5463b-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="5463b-112">一些用户设置。</span><span class="sxs-lookup"><span data-stu-id="5463b-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="5463b-113">Active Directory 基础结构</span><span class="sxs-lookup"><span data-stu-id="5463b-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="5463b-114">Active Directory 的基础结构要求包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="5463b-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="5463b-115">域控制器的操作系统要求</span><span class="sxs-lookup"><span data-stu-id="5463b-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="5463b-116">域和林的功能级别要求</span><span class="sxs-lookup"><span data-stu-id="5463b-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="5463b-117">全局编录域要求</span><span class="sxs-lookup"><span data-stu-id="5463b-117">Global catalog domain requirements</span></span>

<span data-ttu-id="5463b-118">有关详细信息，请参阅部署文档中的 [Lync Server 2013 的 Active Directory 基础结构要求](lync-server-2013-active-directory-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="5463b-119">Active Directory 域服务准备</span><span class="sxs-lookup"><span data-stu-id="5463b-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5463b-120">建议您对“配置”容器而非“系统”容器部署全局设置。</span><span class="sxs-lookup"><span data-stu-id="5463b-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="5463b-121">这不会增强安全性，但是可提高一些 Active Directory 域服务拓扑的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="5463b-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="5463b-122">如果从 Microsoft Office 通信服务器2007迁移，并且已使用系统容器，但计划使用配置容器，则必须先移动系统容器中的设置，然后再执行任何升级准备。</span><span class="sxs-lookup"><span data-stu-id="5463b-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="5463b-123">若要将系统容器设置迁移到配置容器，请参阅在上的 Office 通信服务器2007全局设置迁移工具 <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> 。</span><span class="sxs-lookup"><span data-stu-id="5463b-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="5463b-124">部署 Lync Server 2013 时，第一步是准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="5463b-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="5463b-125">为 Lync Server 2013 准备 Active Directory 域服务包括以下三个步骤：</span><span class="sxs-lookup"><span data-stu-id="5463b-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="5463b-126">**准备架构**。</span><span class="sxs-lookup"><span data-stu-id="5463b-126">**Prepare Schema**.</span></span> <span data-ttu-id="5463b-127">此任务将 Active Directory 域服务中的架构扩展为包含特定于 Lync Server 2013 的类和属性。</span><span class="sxs-lookup"><span data-stu-id="5463b-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="5463b-128">有关准备架构的详细信息，请参阅部署文档中的在 [Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="5463b-129">有关详细信息，请参阅 [从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5463b-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="5463b-130">**准备林**。</span><span class="sxs-lookup"><span data-stu-id="5463b-130">**Prepare Forest**.</span></span> <span data-ttu-id="5463b-131">此任务将在目录林根级域中创建全局设置和对象，并创建用于管理针对这些设置和对象的访问的通用服务和管理组。</span><span class="sxs-lookup"><span data-stu-id="5463b-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="5463b-132">有关准备林的详细信息，请参阅部署文档中的 [为 Lync Server 2013 运行林准备](lync-server-2013-running-forest-preparation.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="5463b-133">**准备域**。</span><span class="sxs-lookup"><span data-stu-id="5463b-133">**Prepare Domain**.</span></span> <span data-ttu-id="5463b-134">此任务会向通用组添加必要的访问控制项 (ACE)，这些访问控制项可授予承载和管理域中用户的权限。</span><span class="sxs-lookup"><span data-stu-id="5463b-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="5463b-135">必须在要部署运行 Lync Server 2013 的服务器以及 Lync Server 用户所驻留的任何域的所有域中完成此任务。</span><span class="sxs-lookup"><span data-stu-id="5463b-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="5463b-136">有关准备域的详细信息，请参阅部署文档中的 [运行 Lync Server 2013 的域准备工作](lync-server-2013-running-domain-preparation.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="5463b-137">有关准备 Active Directory 的完整过程以及执行每个步骤所需的权限和权限的概述，请参阅部署文档中 [的 Lync Server 2013 的 Active Directory 基础结构要求](lync-server-2013-active-directory-infrastructure-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="5463b-138">通用组</span><span class="sxs-lookup"><span data-stu-id="5463b-138">Universal Groups</span></span>

<span data-ttu-id="5463b-139">在准备林的过程中，Lync Server 2013 在 Active Directory 域服务中创建了具有访问和管理全局设置和服务的权限的各种通用组。</span><span class="sxs-lookup"><span data-stu-id="5463b-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="5463b-140">这些通用组包括：</span><span class="sxs-lookup"><span data-stu-id="5463b-140">These universal groups include:</span></span>

  - <span data-ttu-id="5463b-141">**管理组**。</span><span class="sxs-lookup"><span data-stu-id="5463b-141">**Administrative groups**.</span></span> <span data-ttu-id="5463b-142">这些组定义 Lync Server 网络的基本管理员角色。</span><span class="sxs-lookup"><span data-stu-id="5463b-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="5463b-143">在林准备过程中，这些管理员组将添加到 Lync Server 基础结构组中。</span><span class="sxs-lookup"><span data-stu-id="5463b-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="5463b-144">**服务组**。</span><span class="sxs-lookup"><span data-stu-id="5463b-144">**Service groups**.</span></span> <span data-ttu-id="5463b-145">这些组是访问 Lync Server 提供的各种服务所需的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="5463b-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="5463b-146">**基础结构组**。</span><span class="sxs-lookup"><span data-stu-id="5463b-146">**Infrastructure groups**.</span></span> <span data-ttu-id="5463b-147">这些组提供访问 Lync Server 基础结构的特定区域的权限。</span><span class="sxs-lookup"><span data-stu-id="5463b-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="5463b-148">这些基础结构组将用作管理组的组件，不应修改这些基础结构组或直接向其中添加用户。</span><span class="sxs-lookup"><span data-stu-id="5463b-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="5463b-149">在林准备过程中，会将特定的服务和管理组添加到适当的基础结构组中。</span><span class="sxs-lookup"><span data-stu-id="5463b-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="5463b-150">有关在为 Lync Server 准备 AD 时创建的特定通用组的详细信息，以及添加到基础结构组的服务和管理组的详细信息，请参阅部署文档中的 [Lync Server 2013 中的林准备](lync-server-2013-changes-made-by-forest-preparation.md) 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5463b-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5463b-151">Lync Server 2013 支持 Windows Server 2012 中的通用组，用于运行 Lync Server 2013 的服务器，以及适用于域控制器的 Windows Server 2003 操作系统。</span><span class="sxs-lookup"><span data-stu-id="5463b-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="5463b-152">通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。</span><span class="sxs-lookup"><span data-stu-id="5463b-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="5463b-153">通用组支持（与管理员委派结合使用）简化了 Lync Server 部署的管理。</span><span class="sxs-lookup"><span data-stu-id="5463b-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="5463b-154">例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。</span><span class="sxs-lookup"><span data-stu-id="5463b-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="5463b-155">基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="5463b-155">Role-Based Access Control</span></span>

<span data-ttu-id="5463b-156">除了创建通用服务和管理组以及将服务和管理组添加到适当的通用组之外，林准备还会创建 Role-Based 访问控制 (RBAC) 组。</span><span class="sxs-lookup"><span data-stu-id="5463b-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="5463b-157">有关林准备创建的特定 RBAC 组的详细信息，请参阅部署文档中的 [Lync Server 2013 中的林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="5463b-158">有关 RBAC 组的详细信息，请参阅 [Lync Server 2013 的基于角色的访问控制 (RBAC) ](lync-server-2013-role-based-access-control-rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="5463b-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="5463b-159">访问控制项 (ACE) 与继承</span><span class="sxs-lookup"><span data-stu-id="5463b-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="5463b-160">林准备同时创建专用和公共 ACE，并为其创建的通用组添加 ACE。</span><span class="sxs-lookup"><span data-stu-id="5463b-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="5463b-161">它在由 Lync Server 使用的全局设置容器上创建特定的专用 Ace。</span><span class="sxs-lookup"><span data-stu-id="5463b-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="5463b-162">此容器仅由 Lync Server 使用，并位于配置容器或根域中的系统容器中，具体取决于存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="5463b-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="5463b-p114">域准备步骤将向通用组添加必要的访问控制项 (ACE)，这些访问控制项将授予承载和管理域中用户的权限。域准备过程将在域根和以下三个内置容器中创建 ACE：“用户”、“计算机”和“域控制器”。</span><span class="sxs-lookup"><span data-stu-id="5463b-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="5463b-165">有关由林准备和域准备创建和添加的公共 Ace 的详细信息，请参阅2013在部署文档中的 Lync Server 2013 中的 [林准备所做的更改](lync-server-2013-changes-made-by-forest-preparation.md) 和部署文档中的 [lync server 中的域准备](lync-server-2013-changes-made-by-domain-preparation.md) 所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5463b-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="5463b-166">组织经常会锁定 Active Directory 域服务 (AD DS) 以帮助缓解安全风险。</span><span class="sxs-lookup"><span data-stu-id="5463b-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="5463b-167">但是，锁定的 Active Directory 环境可以限制 Lync Server 2013 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="5463b-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="5463b-168">这可以包括从容器和 OU 中删除 ACE 以及在“用户”、“联系人”、“InetOrgPerson”或“计算机”对象上禁用权限继承。</span><span class="sxs-lookup"><span data-stu-id="5463b-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="5463b-169">在锁定的 Active Directory 环境中，必须在需要权限的容器和 OU 上手动设置权限。</span><span class="sxs-lookup"><span data-stu-id="5463b-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="5463b-170">有关详细信息，请参阅部署文档中的在 [Lync Server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="5463b-171">服务器信息</span><span class="sxs-lookup"><span data-stu-id="5463b-171">Server Information</span></span>

<span data-ttu-id="5463b-172">在激活过程中，Lync Server 2013 将服务器信息发布到 Active Directory 域服务中的以下三个位置：</span><span class="sxs-lookup"><span data-stu-id="5463b-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="5463b-173">与安装了 Lync Server 2013 的物理计算机对应的每个 Active Directory 计算机对象上的服务连接点 (SCP) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="5463b-174">在 **msRTCSIP-Pools** 类的容器中创建的服务器对象。</span><span class="sxs-lookup"><span data-stu-id="5463b-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="5463b-175">拓扑生成器中指定的受信任服务器。</span><span class="sxs-lookup"><span data-stu-id="5463b-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="5463b-176">服务连接点</span><span class="sxs-lookup"><span data-stu-id="5463b-176">Service Connection Points</span></span>

<span data-ttu-id="5463b-177">Active Directory 域服务中的每个 Lync Server 2013 对象都具有一个名为 RTC 服务的 SCP，后者又包含多个属性来标识每台计算机并指定它所提供的服务。</span><span class="sxs-lookup"><span data-stu-id="5463b-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="5463b-178">在这些 SCP 属性中，比较重要的 SCP 属性为 *serviceDNSName*、*serviceDNSNameType*、*serviceClassname* 和 *serviceBindingInformation*。</span><span class="sxs-lookup"><span data-stu-id="5463b-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="5463b-179">第三方资产管理应用程序可以通过针对上述 SCP 属性和其他 SCP 属性进行查询来检索部署中的服务器信息。</span><span class="sxs-lookup"><span data-stu-id="5463b-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="5463b-180">Active Directory 服务器对象</span><span class="sxs-lookup"><span data-stu-id="5463b-180">Active Directory Server Objects</span></span>

<span data-ttu-id="5463b-181">每个 Lync Server 2013 服务器角色都具有相应的 Active Directory 对象，其属性定义该角色提供的服务。</span><span class="sxs-lookup"><span data-stu-id="5463b-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="5463b-182">此外，当激活 Standard Edition 服务器或创建企业版池时，Lync Server 2013 将在**msRTCSIP**容器中创建一个新的**msRTCSIP**对象。</span><span class="sxs-lookup"><span data-stu-id="5463b-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="5463b-183">**MsRTCSIP**类指定池的完全限定的域名 (FQDN) ，以及池的前端和后端组件之间的关联。</span><span class="sxs-lookup"><span data-stu-id="5463b-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="5463b-184"> (Standard Edition server 被视为一个逻辑池，其前端和后端并置在一台计算机上。 ) </span><span class="sxs-lookup"><span data-stu-id="5463b-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="5463b-185">受信任的服务器</span><span class="sxs-lookup"><span data-stu-id="5463b-185">Trusted Servers</span></span>

<span data-ttu-id="5463b-186">在 Lync Server 2013 中，受信任的服务器是运行拓扑生成器并发布拓扑时指定的服务器。</span><span class="sxs-lookup"><span data-stu-id="5463b-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="5463b-187">发布的拓扑（包括所有服务器信息）存储在中央管理存储中。</span><span class="sxs-lookup"><span data-stu-id="5463b-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="5463b-188">只有中央管理存储中定义的服务器是受信任的。</span><span class="sxs-lookup"><span data-stu-id="5463b-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="5463b-189">在 Lync Server 2013 中，受信任的服务器是满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="5463b-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="5463b-190">服务器的 FQDN 出现在存储在中央管理存储中的拓扑中。</span><span class="sxs-lookup"><span data-stu-id="5463b-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="5463b-191">服务器提供了来自受信任的 CA 的有效证书。</span><span class="sxs-lookup"><span data-stu-id="5463b-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="5463b-192">有关详细信息，请参阅 [Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5463b-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="5463b-p120">如果未满足上述任一条件，则该服务器将不会受到信任，并且与该服务器的连接将被拒绝。此双重要求可防止未授权服务器可能通过尝试接管有效服务器的 FQDN 来发起攻击（虽然出现此情况的可能性不大）。</span><span class="sxs-lookup"><span data-stu-id="5463b-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="5463b-195">此外，若要启用 Microsoft Office 通信服务器 2007 R2 和 Microsoft Office 通信服务器2007部署以与 Lync Server 2013 服务器通信，Lync Server 2013 将在林准备期间创建容器，以容纳早期版本的受信任的服务器列表。</span><span class="sxs-lookup"><span data-stu-id="5463b-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="5463b-196">下表介绍为了与早期部署兼容而创建的容器。</span><span class="sxs-lookup"><span data-stu-id="5463b-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="5463b-197">与早期版本兼容的受信任的服务器列表及其 Active Directory 容器</span><span class="sxs-lookup"><span data-stu-id="5463b-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5463b-198">受信任的服务器列表</span><span class="sxs-lookup"><span data-stu-id="5463b-198">Trusted server list</span></span></th>
<th><span data-ttu-id="5463b-199">Active Directory 容器</span><span class="sxs-lookup"><span data-stu-id="5463b-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5463b-200">Standard Edition Server 和企业版池前端服务器</span><span class="sxs-lookup"><span data-stu-id="5463b-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="5463b-201">RTC 服务/全局设置</span><span class="sxs-lookup"><span data-stu-id="5463b-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5463b-202">会议服务器</span><span class="sxs-lookup"><span data-stu-id="5463b-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="5463b-203">RTC 服务/受信任的 MCU</span><span class="sxs-lookup"><span data-stu-id="5463b-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5463b-204">Web 组件服务器</span><span class="sxs-lookup"><span data-stu-id="5463b-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="5463b-205">RTC 服务/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="5463b-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5463b-206">中介服务器和 Communicator Web Access 服务器、应用程序服务器、QoE 注册器、A/V 会议服务（也称作第三方 SIP 服务器）</span><span class="sxs-lookup"><span data-stu-id="5463b-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="5463b-207">RTC 服务/受信任的服务</span><span class="sxs-lookup"><span data-stu-id="5463b-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5463b-208">代理服务器</span><span class="sxs-lookup"><span data-stu-id="5463b-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="5463b-209">Lync Server 2013 不支持代理服务器的向后兼容性</span><span class="sxs-lookup"><span data-stu-id="5463b-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5463b-210">若要支持早期版本的受信任服务器，必须运行最佳实践分析工具。</span><span class="sxs-lookup"><span data-stu-id="5463b-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="5463b-211">有关运行最佳实践分析工具的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) 。</span><span class="sxs-lookup"><span data-stu-id="5463b-211">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

